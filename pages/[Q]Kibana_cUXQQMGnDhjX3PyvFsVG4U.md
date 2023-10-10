# \[Q]Kibana

-   提取数据时出错`Unable to create actions client because the Encrypted Saved Objects plugin is missing encryption key. Please set xpack.encryptedSavedObjects.encryptionKey in the kibana.yml or use the bin/kibana-encryption-keys command.`

    ![](../image/image_KeY4I9TzET.png)

    ![](../image/image_yhyYFOpHjO.png)
    ```纯文本
    65/c/u<@http://10.43.1.51:5601/46307/bundles/plugin/cases/8.0.0/cases.chunk.0.js:3:22565

    ```
    -   创建密钥
        ```纯文本
        elkb@ELKBServer:~/kibana-7.16.2-linux-x86_64/bin$ ./kibana-encryption-keys generate
        ## Kibana Encryption Key Generation Utility

        The 'generate' command guides you through the process of setting encryption keys for:

        xpack.encryptedSavedObjects.encryptionKey
            Used to encrypt stored objects such as dashboards and visualizations
            https://www.elastic.co/guide/en/kibana/current/xpack-security-secure-saved-objects.html#xpack-security-secure-saved-objects

        xpack.reporting.encryptionKey
            Used to encrypt saved reports
            https://www.elastic.co/guide/en/kibana/current/reporting-settings-kb.html#general-reporting-settings

        xpack.security.encryptionKey
            c
            https://www.elastic.co/guide/en/kibana/current/security-settings-kb.html#security-session-and-cookie-settings


        Already defined settings are ignored and can be regenerated using the --force flag.  Check the documentation links for instructions on how to rotate encryption keys.
        Definitions should be set in the kibana.yml used configure Kibana.

        Settings:
        xpack.encryptedSavedObjects.encryptionKey: 9a8b1ba556669bdb1635755dbf2dbbf2
        xpack.reporting.encryptionKey: 856a0f1f0a5ec6a78e8804e819093260
        xpack.security.encryptionKey: 8e49b7f7c8a014c8999930c92ff97427
        ```
    `vim `[kibana.yml](kibana.yml_bEoRwiLaM8NDPthpZ26AR8.md "kibana.yml")新增内容
    ```纯文本
    xpack.encryptedSavedObjects:
      encryptionKey: 9a8b1ba556669bdb1635755dbf2dbbf2
    ```
