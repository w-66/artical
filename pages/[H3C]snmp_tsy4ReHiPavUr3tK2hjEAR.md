# \[H3C]snmp

### display snmp-agent community

### snmp-agent target-host

```javascript
【举例】
# 允许向10.1.1.1发送SNMPv1 Trap报文，使用团体名public。
<Sysname> system-view
[Sysname] snmp-agent trap enable standard
[Sysname] snmp-agent target-host trap address udp-domain 10.1.1.1 params securityname public
# 允许向vpn1中，地址为10.1.1.1的设备发送SNMPv3 Trap报文，使用用户名v3test。
<Sysname> system-view
[Sysname] snmp-agent trap enable standard
[Sysname] snmp-agent target-host trap address udp-domain 10.1.1.1 vpn-instance vpn1 params securityname v3test v3
1.1.21  snmp-agent trap enable
```

***

```javascript
 snmp-agent
 snmp-agent local-engineid 800063A2803CD2E5668EC800000001
 snmp-agent sys-info version v2c v3 
 snmp-agent target-host trap address udp-domain 10.43.1.116 params securityname hnslt2014 v2c
 snmp-agent target-host trap address udp-domain 10.43.1.253 params securityname hnslt2014 v2c
```

