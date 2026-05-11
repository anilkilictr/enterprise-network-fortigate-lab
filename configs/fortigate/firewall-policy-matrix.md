# Firewall Policy Matrix

| Source | Destination | Service | Action | Notes |
|---|---|---|---|---|
| Ankara VLAN 10 IT | Server VLAN 100 | DNS, DHCP, ICMP, HTTPS | Allow | IT administration and testing |
| Ankara VLAN 20 HR | Server VLAN 100 | DNS, DHCP, HTTPS | Allow | Business-required services only |
| Ankara VLAN 30 Sales | Server VLAN 100 | DNS, DHCP, HTTPS | Allow | Business-required services only |
| Ankara VLAN 40 Engineering | Server VLAN 100 | DNS, DHCP, HTTPS, SSH/RDP if required | Allow | Engineering/admin testing |
| Server VLAN 100 | Ankara VLANs | Established / required services | Allow limited | Avoid broad server-to-client access |
| Any Internal | Internet/Lab NAT | HTTP/HTTPS/DNS | Allow with NAT | Optional lab Internet access |
| Any | Any | Unnecessary traffic | Deny | Least privilege baseline |
