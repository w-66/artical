# \[E\&Q]Docker

-   \[Q]容器怎么开机自启脚本 \[[\~/.bashrc](~-.bashrc_a1Wf19BvMgFks77EV26ZuB.md "~/.bashrc")]
    -   示例1：Linux 系统开机执行自动某个脚本文件等，这在自动化运维方面有一定的用处。(但是，不完美，每次ssh登录都会执行一次)
        1.  修改 `/home/hj/.bashrc` 文件：
            ```纯文本
            sudo vim /home/hj/.bashrc
            echo '这句话开机就会启动'            
            python3 /home/hj/test.py            

            ```
        2.  当 Linux 开机后：

            ![](https://raw.githubusercontent.com/hj1933/img/master/iimg/20190611151954.png)

            可以看到 Linux 开机后加载了 `.bashrc` 文件。
-   \[Q]怎么删除同哈希不通tag的; 怎么删除其中一个 \[`docker rmi`]
    ```python
    [@NAS543Bmini dockerfile]$ docker images | grep django
    ubuntudjango                           3.2             5743555176a2   About a minute ago   1.77GB
    qusay/ubuntu_django3.2                 v11             5743555176a2   About a minute ago   1.77GB

    ```

    ```python
    docker rmi qusay/ubuntu_django3.2:v11
    ```
-   \[Q]docker部署的mysql修改配置后导致无法启动|怎么直接修改容器中的数据不通过 \[`docker inspect`]

    docker inspect 容器id 查看容器所在的物理路径

    `docker inspect ab7ebf4b0af9 | grep -C8 MergedDir`
    -   详细
        ```纯文本
        ]$ docker inspect ab7ebf4b0af9 | grep -C8 MergedDir
                        "/proc/irq",
                        "/proc/sys",
                        "/proc/sysrq-trigger"
                    ]
                },
                "GraphDriver": {
                    "Data": {
                        "LowerDir": "/share/CACHEDEV3_DATA/resources/Container/container-station-data/lib/docker/overlay2/00674551efc3c38c50ce0d2037a2bd7f53521c226d922289db94e0394aa51543-init/diff:/share/CACHEDEV3_DATA/resources/Container/container-station-data/lib/docker/overlay2/7a2fb1cea6220181336d1ecda86d75c257b80db975af938917ef52b89b303600/diff:/share/CACHEDEV3_DATA/resources/Container/container-station-data/lib/docker/overlay2/bbdda490809055bab3f25259c3195ca2a5b977123166cd3b64d5d846d150b4ce/diff:/share/CACHEDEV3_DATA/resources/Container/container-station-data/lib/docker/overlay2/0666adacef95d9a47dd4e7f658399be65f18ce48709cf5ccd6cca1648785fc64/diff:/share/CACHEDEV3_DATA/resources/Container/container-station-data/lib/docker/overlay2/eadc64287f57832d8b5a3e75604659126c2ccd910a5556461b7854f7823736a5/diff:/share/CACHEDEV3_DATA/resources/Container/container-station-data/lib/docker/overlay2/e28710b08d05f30776a7a3ea2d2823d5066b52a9ddacffd90f96fbe9eb357cc9/diff:/share/CACHEDEV3_DATA/resources/Container/container-station-data/lib/docker/overlay2/66b9d8054ce5a327a9bf03a895af8ed59571c78481f3821d78b7a581fc598183/diff:/share/CACHEDEV3_DATA/resources/Container/container-station-data/lib/docker/overlay2/b62bbe46d5aa71137ff5eb20c20c58b0ded7dfd17fe59f39e9517888d5f90ebc/diff:/share/CACHEDEV3_DATA/resources/Container/container-station-data/lib/docker/overlay2/e82d7cb64c814c3d543580c42817dc1ac726bd8375b55a15c53ad4d704f24507/diff:/share/CACHEDEV3_DATA/resources/Container/container-station-data/lib/docker/overlay2/3f32121aa2ce7f5884fcaecfbcc85a7eb39c9309036fc2ab7a3fb19ec0788700/diff:/share/CACHEDEV3_DATA/resources/Container/container-station-data/lib/docker/overlay2/7f5e73b7f98ef1965fd4470a3137da6e881a67bb63a799c4cca530f70cc0ba3e/diff:/share/CACHEDEV3_DATA/resources/Container/container-station-data/lib/docker/overlay2/5233a0f92d4d298624a0ee8ff0c51c3879cf70b428cb3ad9d1747c2c935aec10/diff",
                        "MergedDir": " /share/CACHEDEV3_DATA/resources/Container/container-station-data/lib/docker/overlay2/00674551efc3c38c50ce0d2037a2bd7f53521c226d922289db94e0394aa51543 /merged",
                        "UpperDir": "/share/CACHEDEV3_DATA/resources/Container/container-station-data/lib/docker/overlay2/00674551efc3c38c50ce0d2037a2bd7f53521c226d922289db94e0394aa51543/diff",
                        "WorkDir": "/share/CACHEDEV3_DATA/resources/Container/container-station-data/lib/docker/overlay2/00674551efc3c38c50ce0d2037a2bd7f53521c226d922289db94e0394aa51543/work"
                    },
                    "Name": "overlay2"
                },
                "Mounts": [
                    {
                        "Type": "volume",
        ```
    ```纯文本
    ] cd diff
    ] ll
    total 48K
    drwxr-xr-x 8 admin administrators 4.0K 2022-09-15 00:02 ./
    drwx--x--- 4 admin administrators 4.0K 2022-09-15 00:21 ../
    drwxr-xr-x 6 admin administrators 4.0K 2022-09-15 00:15 etc/
    dr-xr-x--- 2 admin administrators 4.0K 2022-09-15 00:15 root/
    drwxr-xr-x 3 admin administrators 4.0K 2022-09-15 00:07 run/
    drwxrwxrwt 2 admin administrators 4.0K 2022-09-15 00:09 tmp/
    drwxr-xr-x 5 admin administrators 4.0K 2022-08-24 07:20 usr/
    drwxr-xr-x 6 admin administrators 4.0K 2022-08-24 07:20 var/
    ```
    -   简言：停止后修改文件，启动生效

        修改文件之后需要stop然后start，直接restart无效
-   \[E]`Error response from daemon: conflict: unable to delete d74aa8c9fdc3 (cannot be forced) - image has dependent child images`

    参考：[https://stackoverflow.com/questions/38118791/can-t-delete-docker-image-with-dependent-child-images](https://stackoverflow.com/questions/38118791/can-t-delete-docker-image-with-dependent-child-images "https://stackoverflow.com/questions/38118791/can-t-delete-docker-image-with-dependent-child-images")

    删除的名称有多个tag，所以会有报错，加上tag既可


    ```html
    ] docker rmi d74aa8c9f:latest-data-1 
    Untagged: d74aa8c9f:latest-data-1
    ```
-   \[E]Error response from daemon: Get "https\://registry-1.docker.io/v2/": net/http: TLS handshake timeout

    错误响应来自守护进程...TLS握手超时

    docker默认的源为国外官方源
-   \[E]（docker: command not found）

    [https://blog.csdn.net/bpqdwo/article/details/93714482](https://blog.csdn.net/bpqdwo/article/details/93714482 "https://blog.csdn.net/bpqdwo/article/details/93714482")

    **docker容器内执行docker命令报以下错误**
    ```.properties
    docker: command not found
    ```
    这是没有docker命令

    需要挂载

    privileged: true

    volumes:
    -   /var/run/docker.sock:/var/run/docker.sock
    -   /bin/docker:/bin/docker
    **这是没有权限执行**
    ```.properties
    Got permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Get http://%2Fvar%2Frun%2Fdocker.sock/v1.39/containers/json: dial unix /var/run/docker.sock: connect: permission denied
    ```
    \#则需要把将当前用户加入docker组
    ```.properties
    sudo gpasswd -a ${USER} docker
    ```
    \#或者将当前用户直接加到文件中
    ```.properties
    sudo echo "docker:x:994:${USER}" >> /etc/group
    ```
    \#查看docker用户组成员
    ```.properties
    cat /etc/group |grep docker
    ```
    \#重新启动docker服务
    ```.properties
    sudo systemctl restart docker
    ```
    # 赋予权限
    ```.properties
    sudo chmod a+rw /var/run/docker.sock
    ```

20220106

-   \[E]在下载docker镜像的时候：failed to register layer: Error processing tar file(exit status 1): archive/tar: invalid tar header

    ![](../image/image_D4ah41HXwQ.png)

    Pulling fs laye什么意思r


-   \[E]unable to prepare context: unable to evaluate symlinks in Dockerfile path: lstat /var/lib/snapd/void/Dockerfile: no such file or directory
    ```纯文本
    root@VM-0-2-ubuntu:/usr/frp/frp_image# docker build -t="thyiad/my-frp" .
    unable to prepare context: unable to evaluate symlinks in Dockerfile path: lstat /var/lib/snapd/void/Dockerfile: no such file or directory
    ```
-   \[E]ERROR: for wordpress  Cannot create container for service wordpress: Conflict. The container name "/wordpress" is already in use by container dbaf59bed0d7f4766b782ec14e9c176c5502107bbb180e136fab98ce8bfcdf31. You have to remove (or rename) that container to be [able](able_8RPNfkf5yPkz6JBbKF334X.md "able") to reuse that name.
    ERROR: Encountered errors while bringing up the project.

