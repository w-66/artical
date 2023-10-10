# \[H3C]DHCP

```html
# H3C Comware Software, Version 7.1.070, Release 7557P03
# H3C S7003E
#
 dhcp enable
 dhcp server forbidden-ip 10.43.236.100 10.43.236.128
#
dhcp server ip-pool 1
 gateway-list 10.43.236.126
 network 10.43.236.0 mask 255.255.255.128
 dns-list 114.114.114.114 59.51.78.210
 forbidden-ip 10.43.236.100
 forbidden-ip 10.43.236.128
```
