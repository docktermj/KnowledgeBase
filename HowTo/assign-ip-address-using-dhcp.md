# Assign IP address using DHCP

Sometimes when doing `ip addr show`, there is no IP address from DHCP.
To fix:


## CentOS

```console
sudo dhclient -v
```
