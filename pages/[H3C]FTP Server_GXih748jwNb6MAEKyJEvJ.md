# \[H3C]FTP Server

```纯文本
#
local-user ftpuser class manage
 service-type ftp
 authorization-attribute work-directory flash:/
 authorization-attribute user-role network-admin
 authorization-attribute user-role network-operator
#
```

