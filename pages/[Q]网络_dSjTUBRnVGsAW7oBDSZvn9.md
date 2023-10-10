# \[Q]网络

-   怎么找出交换机与交换机连接的相连的接口？
    -   情况一：在使用聚合端口将交换机串联在一起的拓扑中：方式一：查看接口MAC，然后在网关上查看对应IP、方式二：使用[LLDP](LLDP_bpQe1cVpnm4DeLF8M7USpN.md "LLDP")查看
    方式一：查看接口MAC，然后在网关上查看对应IP
    1.  使用`display eth-trunk`查看对端(`Partner`的`SystemID`也是MAC
    2.  在核心使用ARP查看MAC对应的管理IP既可知道对端连接的是什么设备
    方式二：使用[LLDP](LLDP_bpQe1cVpnm4DeLF8M7USpN.md "LLDP")查看
    1.  `display lldp neighbor brief`

        既可看到相连的设备接口，以及设备名称
        ```bash
        27L_S5720LI_227> dis lldp neighbor bri
        Local Intf    Neighbor Dev             Neighbor Intf             Exptime(s)
        GE0/0/49      27L_S5720LI_230     GE0/0/51                  110    
        GE0/0/50      27L_S5720LI_230     GE0/0/52                  110    
        GE0/0/51      27L_S5720LI_224     GE0/0/49                  105    
        GE0/0/52      27L_S5720LI_224     GE0/0/50                  105 
        ```

