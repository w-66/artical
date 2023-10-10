# \[En]Elastic



-   `elasticsearch.yml`

    ElasticSearch配置文件
    -   设置跨域

        ![](../image/image_UjORgnAiWY.png)

        http.cors.enabled:true
        http.cors.allow-origin:"\*"
    **ElasticSearch Configuration**

    NOTE：ElasticSearch comes with [reasonable](reasonable_ihzYZa6DWunayNSRhkKiwW.md "reasonable") default [for](for_qPw3yCN9JeMJ1dPrcfv66w.md "for") [most](most_ga744r4xkbBnUwkKp4AYpv.md "most") settings. Before you set set [out](out_84c8V1sDWVAh6DmzpQ5W1m.md "out") [tweak](tweak_b7GcB2w1w1zkzV99fJpqpV.md "tweak") and [tune](tune_aLh8pugoeALZV23d6ZoVsJ.md "tune") the configuration， [make](make_wfWqS66sZiR6ao5Bi9JPw8.md "make") [sure](sure_vPpLsr5eZZLdRTdYiHe6Xa.md "sure") you [understand](understand_jEUu5PoDDLGDaEGWNTJDjb.md "understand") what you trying to [accomplish](accomplish_trbfZrDQ9YNS5ModBM8LC5.md "accomplish") and the consequences.
    注意: ElasticSearch带有大多数设置的合理默认值。在开始调整和调整配置之前，请确保您了解要完成的工作以及后果。

    The [primary](primary_dek2RKPWMf7jYaJtY3FEjV.md "primary") way of configuring a node is [via](via_pfxSsm1HiJ6FFqhYBCBcMp.md "via") this file. this [template](template_gmCk6L5a7v9jRVGH6y9xHj.md "template") lists the [most](most_ga744r4xkbBnUwkKp4AYpv.md "most") [important](important_uoewADvM5cJ851J3LfHbjm.md "important") settings you want to configure for a [production](production_rWfMMaCKVBUoWLkc2sbkP5.md "production") [cluster](cluster_8YDutxXWDQtNt59ztGrWwH.md "cluster").
    配置节点的主要方法是通过此文件。此模板列出了要为生产集群配置的最重要的设置/*此模板列出了最重要的设置，为了你生产集群想要的配置*。

    please [consult](consult_f6S1pHCjritXDFPT9AEpj1.md "consult") the [documentation](documentation_hRZSJdxZJbDp2iVQuHQtYF.md "documentation") for [further](further_iN88ZjMUmcx4L3Np1QSi6W.md "further") information on configuration option:https\://www\.elastic.co/guide/en/elasticsearch/reference/index.html
    有关配置选项的更多信息，请查阅文档: https\://www\.elastic.co/guide/en/elasticsearch/reference/index.html

    **Cluster**

    Use a [descriptive](descriptive_pQaRuBrr71dRq1iAPecZWY.md "descriptive") name for your cluster:
    为您的集群使用描述性名称:

    `cluster.name: my-application`

    **Node**

    Use a [descriptive](descriptive_pQaRuBrr71dRq1iAPecZWY.md "descriptive") name for the node:


    `node.name: node-1`

    Add custom attributes to the node:
    向节点添加自定义属性:

    `node.attr.rack: r1`

    **Paths**

    Path to [directory](directory_tmxpUPUPr1YCsCG4mYQPPi.md "directory") where to store the data (separate multiple locations [by](by_t4A4ncLjGUjTXrDMUFWo8d.md "by") [comma](comma_fmLrEUBx5YqADDBqGLTwnU.md "comma")):
    存储数据的目录路径 (用逗号分隔多个位置):

    Path to log files
    日志文件的路径

    **Memory**

    Lock the [memory](memory_bbhJrQreyFtpMzArwUdnP3.md "memory") on startup:
    启动时锁定内存:

    `bootstrap.memory_lock: true`

    Make sure that the [heap](heap_chtnwAMqnfqRFdkPmyytzq.md "heap") size is set to about half the memory available on the system and that the [owner](owner_nex99K8ury62tDLEv5zJUh.md "owner") of the [process](process_w7PaCoRSzRZ1N3YLdvejFM.md "process") is allowed to use this limit.
    确保将堆大小设置为系统上可用内存的一半左右，并且允许进程所有者使用此限制。

    Elasticsearch performs [poorly](poorly_cQ59VZPRAdpbQ2eonNSuaj.md "poorly") [when](when_rYmuCVx7ymoqRUQtu8gGob.md "when") the system is swapping the memory.
    当系统交换内存时，Elasticsearch的性能很差。

    **Network**

    By default Elasticsearch is only [accessible](accessible_bG8veVF3SCfH85VjraV3Qn.md "accessible") on localhost. Set a different address here to [expose](expose_tvd6K9JKrFbjF1oE5nRUeh.md "expose")(公开) this node on the network:
    默认情况下，Elasticsearch只能在本地主机上访问。在这里设置一个不同的地址在网络中公开此节点:

    `network.host: 192.168.0.1`

    For more information, [consult](consult_f6S1pHCjritXDFPT9AEpj1.md "consult") the network [module](module_bDVPYc4B9pMo3KkboHpgqL.md "module") [documentation](documentation_hRZSJdxZJbDp2iVQuHQtYF.md "documentation").
    有关更多信息，请参阅网络模块文档。

    **Discovery**

    Pass an [initial](initial_xo87wDi1MLZ1vhvwhsuYRk.md "initial") list of hosts to [perform](perform_cEJXzW7E7gWp2XMN6CGGjQ.md "perform") discovery when this node is started:
    在启动此节点时传递初始主机列表以执行发现:

    The default list of hosts is \["127.0.0.1", "\[::1]"]
    主机的默认列表是 \["127.0.0.1"，"\[::1]"]

    `discovery.seed_hosts: ["host1", "host2"]`

    [Bootstrap](Bootstrap_rJsHpej7ho83tfeQQSPxYE.md "Bootstrap") the [cluster](cluster_8YDutxXWDQtNt59ztGrWwH.md "cluster") using an [initial](initial_xo87wDi1MLZ1vhvwhsuYRk.md "initial") set of[master](master_YeWDWetiruimRC5D26gLY.md "master")-[eligible](eligible_2gtYBfMqD64zhyktAKRycy.md "eligible") nodes:
    使用初始的一组主合格节点引导群集:

    `cluster.initial_master_nodes: ["node-1", "node-2"]`

    For more information, consult the discovery and cluster [formation](formation_cAiQFiK7VECo3EgCV5Uf2E.md "formation") module documentation.
    有关更多信息，请参阅发现和集群形成模块文档。

    Various

    Require [explicit](explicit_ny8afircZQ8VHEW5BCfRvA.md "explicit") names when deleting indices:
    删除索引时需要 显式/明确 名称:

    `action.destructive_requires_name: true`

    **Security**

    \*\*\* WARNING \*\*\*

    Elasticsearch security features are not enabled by default.


    These features are [free](free_nTEXuvz5ueunBX2pbt1e42.md "free"), but [require](require_79JFrpeLbA121Nq1aEohEC.md "require") configuration changes to enable [them](them_uV6bk45gMFZdu15JQydK52.md "them").
    这些功能是免费的，但需要更改配置才能启用它们。

    This means that users don't have to [provide](provide_4FErUyaUkqbBTxVrLgUB7T.md "provide") credentials and can get full access to the cluster. Network connections are also not encrypted.
    这意味着用户不必提供凭据，并且可以获得对群集的完全访问权限。网络连接也没有加密。

    To [protect](protect_s6ucMWR3rjeKjTby8XVYrJ.md "protect") your data, we [strongly](strongly_jvyz6sxNm4WT2216kGSCem.md "strongly") [encourage](encourage_c2nUXWHoRmBKhB4rVe81xG.md "encourage") you to enable the Elasticsearch security features.&#x20;
    为了保护您的数据，我们强烈建议您启用Elasticsearch安全功能。

    [refer](refer_wktUkapcjyuCYxbaWzea15.md "refer") to the following documentation for for instructions.
    有关说明，请参阅以下文档。

    https\://www\.elastic.co/guide/en/elasticsearch/reference/7.16/configuring-stack-security.html
    ```yaml
    # ======================== Elasticsearch Configuration =========================
    #
    # NOTE: Elasticsearch comes with reasonable defaults for most settings.
    #       Before you set out to tweak and tune the configuration, make sure you
    #       understand what are you trying to accomplish and the consequences.
    #
    # The primary way of configuring a node is via this file. This template lists
    # the most important settings you may want to configure for a production cluster.
    #
    # Please consult the documentation for further information on configuration options:
    # https://www.elastic.co/guide/en/elasticsearch/reference/index.html
    #
    # ---------------------------------- Cluster -----------------------------------
    #
    # Use a descriptive name for your cluster:
    #
    #cluster.name: my-application
    #
    # ------------------------------------ Node ------------------------------------
    #
    # Use a descriptive name for the node:
    #
    #node.name: node-1
    #
    # Add custom attributes to the node:
    #
    #node.attr.rack: r1
    #
    # ----------------------------------- Paths ------------------------------------
    #
    # Path to directory where to store the data (separate multiple locations by comma):
    #
    #path.data: /path/to/data
    #
    # Path to log files:
    #
    #path.logs: /path/to/logs
    #
    # ----------------------------------- Memory -----------------------------------
    #
    # Lock the memory on startup:
    #
    #bootstrap.memory_lock: true
    #
    # Make sure that the heap size is set to about half the memory available
    # on the system and that the owner of the process is allowed to use this
    # limit.
    #
    # Elasticsearch performs poorly when the system is swapping the memory.
    #
    # ---------------------------------- Network -----------------------------------
    #
    # By default Elasticsearch is only accessible on localhost. Set a different
    # address here to expose this node on the network:
    #
    #network.host: 192.168.0.1
    #
    # By default Elasticsearch listens for HTTP traffic on the first free port it
    # finds starting at 9200. Set a specific HTTP port here:
    #
    #http.port: 9200
    #
    # For more information, consult the network module documentation.
    #
    # --------------------------------- Discovery ----------------------------------
    #
    # Pass an initial list of hosts to perform discovery when this node is started:
    # The default list of hosts is ["127.0.0.1", "[::1]"]
    #
    #discovery.seed_hosts: ["host1", "host2"]
    #
    # Bootstrap the cluster using an initial set of master-eligible nodes:
    #
    #cluster.initial_master_nodes: ["node-1", "node-2"]
    #
    # For more information, consult the discovery and cluster formation module documentation.
    #
    # ---------------------------------- Various -----------------------------------
    #
    # Require explicit names when deleting indices:
    #
    #action.destructive_requires_name: true
    #
    # ---------------------------------- Security ----------------------------------
    #
    #                                 *** WARNING ***
    #
    # Elasticsearch security features are not enabled by default.
    # These features are free, but require configuration changes to enable them.
    # This means that users don’t have to provide credentials and can get full access
    # to the cluster. Network connections are also not encrypted.
    #
    # To protect your data, we strongly encourage you to enable the Elasticsearch security features. 
    # Refer to the following documentation for instructions.
    #
    # https://www.elastic.co/guide/en/elasticsearch/reference/7.16/configuring-stack-security.html
    ```


[kibana.yml](kibana.yml_bEoRwiLaM8NDPthpZ26AR8.md "kibana.yml")



-   \#! Elasticsearch built-in security features are not enabled. Without authentication, your cluster could be accessible to anyone. See [https://www.elastic.co/guide/en/elasticsearch/reference/7.16/security-minimal-setup.html](https://www.elastic.co/guide/en/elasticsearch/reference/7.16/security-minimal-setup.html "https://www.elastic.co/guide/en/elasticsearch/reference/7.16/security-minimal-setup.html") to enable security.

    [🖼️ 图片](../image/image_aat0AAWnei.png "🖼️ 图片")
