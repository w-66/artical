参考：

[https://www.elastic.co/guide/en/elasticsearch/reference/current/docker.html#docker-compose-file](https://www.elastic.co/guide/en/elasticsearch/reference/current/docker.html#docker-compose-file "https://www.elastic.co/guide/en/elasticsearch/reference/current/docker.html#docker-compose-file")

[https://www.elastic.co/blog/getting-started-with-the-elastic-stack-and-docker-compose](https://www.elastic.co/blog/getting-started-with-the-elastic-stack-and-docker-compose "https://www.elastic.co/blog/getting-started-with-the-elastic-stack-and-docker-compose")

[https://docs.docker.com/compose/compose-file/05-services/](https://docs.docker.com/compose/compose-file/05-services/ "https://docs.docker.com/compose/compose-file/05-services/")

[https://docs.docker.com/compose/compose-file/07-volumes/](https://docs.docker.com/compose/compose-file/07-volumes/ "https://docs.docker.com/compose/compose-file/07-volumes/")

***

-   1、创建文件
    ```javascript
    touch .env
    touch docker-compose.yml
    ```
-   1.1、编辑 .env
    ```javascript
    # Password for the 'elastic' user (at least 6 characters)
    ELASTIC_PASSWORD=admin123.

    # Password for the 'kibana_system' user (at least 6 characters)
    KIBANA_PASSWORD=admin123.

    # Version of Elastic products
    STACK_VERSION=8.10.4

    # Set the cluster name
    CLUSTER_NAME=docker-cluster

    # Set to 'basic' or 'trial' to automatically start the 30-day trial
    LICENSE=basic
    #LICENSE=trial

    # Port to expose Elasticsearch HTTP API to the host
    ES_PORT=9200
    #ES_PORT=127.0.0.1:9200

    # Port to expose Kibana to the host
    KIBANA_PORT=5601
    #KIBANA_PORT=80

    # Increase or decrease based on the available host memory (in bytes)
    MEM_LIMIT=1073741824

    # Project namespace (defaults to the current folder name if not set)
    #COMPOSE_PROJECT_NAME=myproject

    ```
-   1.2、编辑docker-compose.yml
    -   设置容器 \[`-c`,[\[Shell\]exit](https://www.wolai.com/7AztQVDQAVY7JQtmiUUx8x "\[Shell]exit"),`[-f]`,`-en`]ₛₗ
        ```javascript
        version: "3.8"  # Docker compose 文件的版本

        volumes:  # 定义用于存储数据的卷
         certs:  # 存储证书的卷
           driver: local
         esdata01:  # 存储 Elasticsearch 数据的卷
           driver: local
         kibanadata:  # 存储 Kibana 数据的卷
           driver: local
         metricbeatdata01:  # 存储 Metricbeat 数据的卷
           driver: local
         filebeatdata01:  # 存储 Filebeat 数据的卷
           driver: local
         logstashdata01:  # 存储 Logstash 数据的卷
           driver: local

        networks:  # 定义网络
         default:  # 默认网络
           name: elastic
           external: false

        services:  # 定义服务
         setup:  # 设置服务
           image: docker.elastic.co/elasticsearch/elasticsearch:${STACK_VERSION}  # 使用的镜像
           volumes:  # 使用的卷
             - certs:/usr/share/elasticsearch/config/certs
           user: "0"  # 使用 root 用户运行
           command: >
             bash -c '  # 执行shell
               if [ x${ELASTIC_PASSWORD} == x ]; then   # 判断变量ELASTIC_PASSWORD是否为空
                 echo "Set the ELASTIC_PASSWORD environment variable in the .env file"; # 如果为空，提示用户未在.env中设置ELASTIC_PASSWORD变量
                 exit 1;  # 并返回一个状态为1，表示执行失败
               elif [ x${KIBANA_PASSWORD} == x ]; then
                 echo "Set the KIBANA_PASSWORD environment variable in the .env file";
                 exit 1;  # 退出状态设置为1，表示执行失败
               fi;
               if [ ! -f config/certs/ca.zip ]; then  # 判断是否为普通文件
                 echo "Creating CA";
                 bin/elasticsearch-certutil ca --silent --pem -out config/certs/ca.zip;
                 unzip config/certs/ca.zip -d config/certs;
               fi;
               if [ ! -f config/certs/certs.zip ]; then
                 echo "Creating certs";
                 echo -ne \
                 "instances:\n"\
                 "  - name: es01\n"\
                 "    dns:\n"\
                 "      - es01\n"\
                 "      - localhost\n"\
                 "    ip:\n"\
                 "      - 127.0.0.1\n"\
                 "  - name: kibana\n"\
                 "    dns:\n"\
                 "      - kibana\n"\
                 "      - localhost\n"\
                 "    ip:\n"\
                 "      - 127.0.0.1\n"\
                 > config/certs/instances.yml;
                 bin/elasticsearch-certutil cert --silent --pem -out config/certs/certs.zip --in config/certs/instances.yml --ca-cert config/certs/ca/ca.crt --ca-key config/certs/ca/ca.key;
                 unzip config/certs/certs.zip -d config/certs;
               fi;
               echo "Setting file permissions"
               chown -R root:root config/certs;
               find . -type d -exec chmod 750 \{\} \;;
               find . -type f -exec chmod 640 \{\} \;;
               echo "Waiting for Elasticsearch availability";
               until curl -s --cacert config/certs/ca/ca.crt https://es01:9200 | grep -q "missing authentication credentials"; do sleep 30; done;
               echo "Setting kibana_system password";
               until curl -s -X POST --cacert config/certs/ca/ca.crt -u "elastic:${ELASTIC_PASSWORD}" -H "Content-Type: application/json" https://es01:9200/_security/user/kibana_system/_password -d "{\"password\":\"${KIBANA_PASSWORD}\"}" | grep -q "^{}"; do sleep 10; done;
               echo "All done!";
             '
           healthcheck:  # 健康检查，检查证书是否存在
             test: ["CMD-SHELL", "[ -f config/certs/es01/es01.crt ]"]
             interval: 1s
             timeout: 5s
             retries: 120
        ```
        -   无注释
            ```javascript
            version: "3.8"


            volumes:
             certs:
               driver: local
             esdata01:
               driver: local
             kibanadata:
               driver: local
             metricbeatdata01:
               driver: local
             filebeatdata01:
               driver: local
             logstashdata01:
               driver: local


            networks:
             default:
               name: elastic
               external: false


            services:
             setup:
               image: docker.elastic.co/elasticsearch/elasticsearch:${STACK_VERSION}
               volumes:
                 - certs:/usr/share/elasticsearch/config/certs
               user: "0"
               command: >
                 bash -c '
                   if [ x${ELASTIC_PASSWORD} == x ]; then
                     echo "Set the ELASTIC_PASSWORD environment variable in the .env file";
                     exit 1;
                   elif [ x${KIBANA_PASSWORD} == x ]; then
                     echo "Set the KIBANA_PASSWORD environment variable in the .env file";
                     exit 1;
                   fi;
                   if [ ! -f config/certs/ca.zip ]; then
                     echo "Creating CA";
                     bin/elasticsearch-certutil ca --silent --pem -out config/certs/ca.zip;
                     unzip config/certs/ca.zip -d config/certs;
                   fi;
                   if [ ! -f config/certs/certs.zip ]; then
                     echo "Creating certs";
                     echo -ne \
                     "instances:\n"\
                     "  - name: es01\n"\
                     "    dns:\n"\
                     "      - es01\n"\
                     "      - localhost\n"\
                     "    ip:\n"\
                     "      - 127.0.0.1\n"\
                     "  - name: kibana\n"\
                     "    dns:\n"\
                     "      - kibana\n"\
                     "      - localhost\n"\
                     "    ip:\n"\
                     "      - 127.0.0.1\n"\
                     > config/certs/instances.yml;
                     bin/elasticsearch-certutil cert --silent --pem -out config/certs/certs.zip --in config/certs/instances.yml --ca-cert config/certs/ca/ca.crt --ca-key config/certs/ca/ca.key;
                     unzip config/certs/certs.zip -d config/certs;
                   fi;
                   echo "Setting file permissions"
                   chown -R root:root config/certs;
                   find . -type d -exec chmod 750 \{\} \;;
                   find . -type f -exec chmod 640 \{\} \;;
                   echo "Waiting for Elasticsearch availability";
                   until curl -s --cacert config/certs/ca/ca.crt https://es01:9200 | grep -q "missing authentication credentials"; do sleep 30; done;
                   echo "Setting kibana_system password";
                   until curl -s -X POST --cacert config/certs/ca/ca.crt -u "elastic:${ELASTIC_PASSWORD}" -H "Content-Type: application/json" https://es01:9200/_security/user/kibana_system/_password -d "{\"password\":\"${KIBANA_PASSWORD}\"}" | grep -q "^{}"; do sleep 10; done;
                   echo "All done!";
                 '
               healthcheck:
                 test: ["CMD-SHELL", "[ -f config/certs/es01/es01.crt ]"]
                 interval: 1s
                 timeout: 5s
                 retries: 120
            ```
    -   设置服务 es01
        ```javascript
         es01:
           depends_on:
             setup:
               condition: service_healthy
           image: docker.elastic.co/elasticsearch/elasticsearch:${STACK_VERSION}
           labels:
             co.elastic.logs/module: elasticsearch
           volumes:
             - certs:/usr/share/elasticsearch/config/certs
             - esdata01:/usr/share/elasticsearch/data
           ports:
             - ${ES_PORT}:9200
           environment:
             - node.name=es01
             - cluster.name=${CLUSTER_NAME}
             - discovery.type=single-node
             - ELASTIC_PASSWORD=${ELASTIC_PASSWORD}
             - bootstrap.memory_lock=true
             - xpack.security.enabled=true
             - xpack.security.http.ssl.enabled=true
             - xpack.security.http.ssl.key=certs/es01/es01.key
             - xpack.security.http.ssl.certificate=certs/es01/es01.crt
             - xpack.security.http.ssl.certificate_authorities=certs/ca/ca.crt
             - xpack.security.transport.ssl.enabled=true
             - xpack.security.transport.ssl.key=certs/es01/es01.key
             - xpack.security.transport.ssl.certificate=certs/es01/es01.crt
             - xpack.security.transport.ssl.certificate_authorities=certs/ca/ca.crt
             - xpack.security.transport.ssl.verification_mode=certificate
             - xpack.license.self_generated.type=${LICENSE}
           mem_limit: ${ES_MEM_LIMIT}
           ulimits:
             memlock:
               soft: -1
               hard: -1
           healthcheck:
             test:
               [
                 "CMD-SHELL",
                 "curl -s --cacert config/certs/ca/ca.crt https://localhost:9200 | grep -q 'missing authentication credentials'",
               ]
             interval: 10s
             timeout: 10s
             retries: 120
        ```
    -   最后使用的compose文件
        ```javascript
        version: "2.2"

        services:
          setup:
            image: docker.elastic.co/elasticsearch/elasticsearch:${STACK_VERSION}
            volumes:
              - certs:/usr/share/elasticsearch/config/certs
            user: "0"
            command: >
              bash -c '
                if [ x${ELASTIC_PASSWORD} == x ]; then
                  echo "Set the ELASTIC_PASSWORD environment variable in the .env file";
                  exit 1;
                elif [ x${KIBANA_PASSWORD} == x ]; then
                  echo "Set the KIBANA_PASSWORD environment variable in the .env file";
                  exit 1;
                fi;
                if [ ! -f config/certs/ca.zip ]; then
                  echo "Creating CA";
                  bin/elasticsearch-certutil ca --silent --pem -out config/certs/ca.zip;
                  unzip config/certs/ca.zip -d config/certs;
                fi;
                if [ ! -f config/certs/certs.zip ]; then
                  echo "Creating certs";
                  echo -ne \
                  "instances:\n"\
                  "  - name: es01\n"\
                  "    dns:\n"\
                  "      - es01\n"\
                  "      - localhost\n"\
                  "    ip:\n"\
                  "      - 127.0.0.1\n"\
                  "  - name: es02\n"\
                  "    dns:\n"\
                  "      - es02\n"\
                  "      - localhost\n"\
                  "    ip:\n"\
                  "      - 127.0.0.1\n"\
                  "  - name: es03\n"\
                  "    dns:\n"\
                  "      - es03\n"\
                  "      - localhost\n"\
                  "    ip:\n"\
                  "      - 127.0.0.1\n"\
                  > config/certs/instances.yml;
                  bin/elasticsearch-certutil cert --silent --pem -out config/certs/certs.zip --in config/certs/instances.yml --ca-cert config/certs/ca/ca.crt --ca-key config/certs/ca/ca.key;
                  unzip config/certs/certs.zip -d config/certs;
                fi;
                echo "Setting file permissions"
                chown -R root:root config/certs;
                find . -type d -exec chmod 750 \{\} \;;
                find . -type f -exec chmod 640 \{\} \;;
                echo "Waiting for Elasticsearch availability";
                until curl -s --cacert config/certs/ca/ca.crt https://es01:9200 | grep -q "missing authentication credentials"; do sleep 30; done;
                echo "Setting kibana_system password";
                until curl -s -X POST --cacert config/certs/ca/ca.crt -u "elastic:${ELASTIC_PASSWORD}" -H "Content-Type: application/json" https://es01:9200/_security/user/kibana_system/_password -d "{\"password\":\"${KIBANA_PASSWORD}\"}" | grep -q "^{}"; do sleep 10; done;
                echo "All done!";
              '
            healthcheck:
              test: ["CMD-SHELL", "[ -f config/certs/es01/es01.crt ]"]
              interval: 1s
              timeout: 5s
              retries: 120

          es01:
            container_name: es01
            depends_on:
              setup:
                condition: service_healthy
            image: docker.elastic.co/elasticsearch/elasticsearch:${STACK_VERSION}
            volumes:
              - certs:/usr/share/elasticsearch/config/certs
              - esdata01:/usr/share/elasticsearch/data
            ports:
              - ${ES_PORT}:9200
            environment:
              - node.name=es01
              - cluster.name=${CLUSTER_NAME}
              - cluster.initial_master_nodes=es01,es02,es03
              - discovery.seed_hosts=es02,es03
              - ELASTIC_PASSWORD=${ELASTIC_PASSWORD}
              - bootstrap.memory_lock=true
              - xpack.security.enabled=true
              - xpack.security.http.ssl.enabled=true
              - xpack.security.http.ssl.key=certs/es01/es01.key
              - xpack.security.http.ssl.certificate=certs/es01/es01.crt
              - xpack.security.http.ssl.certificate_authorities=certs/ca/ca.crt
              - xpack.security.transport.ssl.enabled=true
              - xpack.security.transport.ssl.key=certs/es01/es01.key
              - xpack.security.transport.ssl.certificate=certs/es01/es01.crt
              - xpack.security.transport.ssl.certificate_authorities=certs/ca/ca.crt
              - xpack.security.transport.ssl.verification_mode=certificate
              - xpack.license.self_generated.type=${LICENSE}
            mem_limit: ${MEM_LIMIT}
            ulimits:
              memlock:
                soft: -1
                hard: -1
            healthcheck:
              test:
                [
                  "CMD-SHELL",
                  "curl -s --cacert config/certs/ca/ca.crt https://localhost:9200 | grep -q 'missing authentication credentials'",
                ]
              interval: 10s
              timeout: 10s
              retries: 120

          es02:
            container_name: es02
            depends_on:
              - es01
            image: docker.elastic.co/elasticsearch/elasticsearch:${STACK_VERSION}
            volumes:
              - certs:/usr/share/elasticsearch/config/certs
              - esdata02:/usr/share/elasticsearch/data
            environment:
              - node.name=es02
              - cluster.name=${CLUSTER_NAME}
              - cluster.initial_master_nodes=es01,es02,es03
              - discovery.seed_hosts=es01,es03
              - bootstrap.memory_lock=true
              - xpack.security.enabled=true
              - xpack.security.http.ssl.enabled=true
              - xpack.security.http.ssl.key=certs/es02/es02.key
              - xpack.security.http.ssl.certificate=certs/es02/es02.crt
              - xpack.security.http.ssl.certificate_authorities=certs/ca/ca.crt
              - xpack.security.transport.ssl.enabled=true
              - xpack.security.transport.ssl.key=certs/es02/es02.key
              - xpack.security.transport.ssl.certificate=certs/es02/es02.crt
              - xpack.security.transport.ssl.certificate_authorities=certs/ca/ca.crt
              - xpack.security.transport.ssl.verification_mode=certificate
              - xpack.license.self_generated.type=${LICENSE}
            mem_limit: ${MEM_LIMIT}
            ulimits:
              memlock:
                soft: -1
                hard: -1
            healthcheck:
              test:
                [
                  "CMD-SHELL",
                  "curl -s --cacert config/certs/ca/ca.crt https://localhost:9200 | grep -q 'missing authentication credentials'",
                ]
              interval: 10s
              timeout: 10s
              retries: 120

          es03:
            container_name: es03
            depends_on:
              - es02
            image: docker.elastic.co/elasticsearch/elasticsearch:${STACK_VERSION}
            volumes:
              - certs:/usr/share/elasticsearch/config/certs
              - esdata03:/usr/share/elasticsearch/data
            environment:
              - node.name=es03
              - cluster.name=${CLUSTER_NAME}
              - cluster.initial_master_nodes=es01,es02,es03
              - discovery.seed_hosts=es01,es02
              - bootstrap.memory_lock=true
              - xpack.security.enabled=true
              - xpack.security.http.ssl.enabled=true
              - xpack.security.http.ssl.key=certs/es03/es03.key
              - xpack.security.http.ssl.certificate=certs/es03/es03.crt
              - xpack.security.http.ssl.certificate_authorities=certs/ca/ca.crt
              - xpack.security.transport.ssl.enabled=true
              - xpack.security.transport.ssl.key=certs/es03/es03.key
              - xpack.security.transport.ssl.certificate=certs/es03/es03.crt
              - xpack.security.transport.ssl.certificate_authorities=certs/ca/ca.crt
              - xpack.security.transport.ssl.verification_mode=certificate
              - xpack.license.self_generated.type=${LICENSE}
            mem_limit: ${MEM_LIMIT}
            ulimits:
              memlock:
                soft: -1
                hard: -1
            healthcheck:
              test:
                [
                  "CMD-SHELL",
                  "curl -s --cacert config/certs/ca/ca.crt https://localhost:9200 | grep -q 'missing authentication credentials'",
                ]
              interval: 10s
              timeout: 10s
              retries: 120

          kibana:
            container_name: kibana
            depends_on:
              es01:
                condition: service_healthy
              es02:
                condition: service_healthy
              es03:
                condition: service_healthy
            image: docker.elastic.co/kibana/kibana:${STACK_VERSION}
            volumes:
              - certs:/usr/share/kibana/config/certs
              - kibanadata:/usr/share/kibana/data
            ports:
              - ${KIBANA_PORT}:5601
            environment:
              - SERVERNAME=kibana
              - ELASTICSEARCH_HOSTS=https://es01:9200
              - ELASTICSEARCH_USERNAME=kibana_system
              - ELASTICSEARCH_PASSWORD=${KIBANA_PASSWORD}
              - ELASTICSEARCH_SSL_CERTIFICATEAUTHORITIES=config/certs/ca/ca.crt
            mem_limit: ${MEM_LIMIT}
            healthcheck:
              test:
                [
                  "CMD-SHELL",
                  "curl -s -I http://localhost:5601 | grep -q 'HTTP/1.1 302 Found'",
                ]
              interval: 10s
              timeout: 10s
              retries: 120
        volumes:
          certs:
            name: "certs"
            driver: local
            driver_opts:
              type: "none"
              o: bind
              device: "/ES/certs"
          esdata01:
            name: "esdata01"
            driver: local
            driver_opts:
              type: "none"
              o: bind
              device: "/ES/esdata01"
          esdata02:
            name: "esdata02"
            driver: local
            driver_opts:
              type: "none"
              o: bind
              device: "/ES/esdata02"
          esdata03:
            name: "esdata03"
            driver: local
            driver_opts:
              type: "none"
              o: bind
              device: "/ES/esdata03"
          kibanadata:
            name: "kibabadata"
            driver: local
            driver_opts:
              type: "none"
              o: bind
              device: "/ES/kibanadata"

        ```
        -   \[E]Volume certs specifies nonexistent driver /ES/certs
            ```javascript
            volumes:
              certs:
                name: "certs"
                driver: "/ES/certs"  # driver 是驱动程序，应该是local。device才是挂载路径
                driver_opts:
                  type: "none"
                  o: "certs"
                  device: "/ES/certs"
            ```
            ```javascript
            root@Qusay-PC1:/ES/docker-compose# docker-compose up -d
            Creating volume "certs" with /ES/certs driver
            ERROR: Volume certs specifies nonexistent driver /ES/certs
            ```
        -   \[E]Cannot start service setup: error while mounting volume failed to mount local volume; no such device; Encountered errors while bringing up the project
            ```javascript
            volumes:
              certs:
                name: "certs"
                driver: "/ES/certs"
                driver_opts:
                  type: "none"
                  o: "certs"  # 这里应该是bind，垃圾阿里......
                  device: "/ES/certs"
            ```
            ```javascript
            root@Qusay-PC1:/ES/docker-compose# dock-compose up -d
            Creating volume "certs" with local driver
            Creating volume "esdata01" with local driver
            Creating volume "esdata02" with local driver
            Creating volume "esdata03" with local driver
            Creating volume "kibabadata" with local driver
            Creating docker-compose_setup_1 ... error

            ERROR: for docker-compose_setup_1  Cannot start service setup: error while mounting volume '/var/lib/docker/volumes/certs/_data': failed to mount local volume: mount /ES/certs:/var/lib/docker/volumes/certs/_data, data: certs: no such device

            ERROR: for setup  Cannot start service setup: error while mounting volume '/var/lib/docker/volumes/certs/_data': failed to mount local volume: mount /ES/certs:/var/lib/docker/volumes/certs/_data, data: certs: no such device
            ERROR: Encountered errors while bringing up the project
            ```
-   2、运行compose \[`docker-compose up -d`]
    ```javascript
    docker-compose up -d

    ```
    ```javascript
    root@Qusay-PC1:/ES/docker-compose# docker-compose up -d
    Creating docker-compose_setup_1 ... done
    Creating es01                   ... done
    Creating es02                   ... done
    Creating es03                   ... done
    Creating kibana                 ... done
    ```
-   3、检查：容器运行情况 \[`docker stats`]
    ```javascript
    CONTAINER ID   NAME                     CPU %     MEM USAGE / LIMIT     MEM %     NET I/O           BLOCK I/O         PIDS
    f33fc6e661f2   docker-compose_setup_1   3.34%     137.3MiB / 15.51GiB   0.86%     3.68kB / 232B     438MB / 1.15GB    3
    44bc886d3769   es01                     7.84%     1017MiB / 1GiB        99.36%    3.8MB / 417kB     19.2MB / 5.64MB   92
    85999014a92b   es02                     3.35%     1021MiB / 1GiB        99.66%    1.16MB / 4.37MB   8.9MB / 4.65MB    144
    0415c8739463   es03                     5.27%     1018MiB / 1GiB        99.42%    939kB / 1.09MB    6.3MB / 4.05MB    147
    159c1cf17d7c   kibana                   116.72%   242.5MiB / 1GiB       23.68%    2.47kB / 0B       971kB / 0B        12
    ```

***
