# Firewall Policy Matrix

<<<<<<< HEAD
| Source | Destination | Service | Action | Notes |
|---|---|---|---|---|
| Ankara VLAN 10 IT | Server VLAN 100 | DNS, DHCP, ICMP, HTTPS | Allow | IT administration and testing |
| Ankara VLAN 20 HR | Server VLAN 100 | DNS, DHCP, HTTPS | Allow | Business-required services only |
| Ankara VLAN 30 Sales | Server VLAN 100 | DNS, DHCP, HTTPS | Allow | Business-required services only |
| Ankara VLAN 40 Engineering | Server VLAN 100 | DNS, DHCP, HTTPS, SSH/RDP if required | Allow | Engineering/admin testing |
| Server VLAN 100 | Ankara VLANs | Established / required services | Allow limited | Avoid broad server-to-client access |
| Any Internal | Internet/Lab NAT | HTTP/HTTPS/DNS | Allow with NAT | Optional lab Internet access |
| Any | Any | Unnecessary traffic | Deny | Least privilege baseline |
=======
| Policy Name | Source | Destination | Services | Action | NAT | Notes |
|---|---|---|---|---|---|---|
| LAN_to_Internet | IT, HR, Sales | Internet | HTTP, HTTPS, DNS | Allow | Enabled | Standard user internet access |
| Branch_to_AD_DNS | Branch Users | Server VLAN | DNS, LDAP, Kerberos, SMB | Allow | Disabled | Domain authentication and DNS |
| IT_to_Management | IT VLAN | Management VLAN | SSH, HTTPS, RDP | Allow | Disabled | Restricted admin access |
| HR_to_Sales | HR VLAN | Sales VLAN | Any | Deny | Disabled | Segmentation policy |
| Guest_to_Internal | Guest VLAN | RFC1918 Networks | Any | Deny | Disabled | Internal isolation |

## Policy Design Notes

- Use direction-based and service-based rules.
- Place deny or restrictive rules before broad allow rules.
- Avoid `any-any` rules in production designs.
- Log important allow and deny policies for visibility.
- Separate NAT rules from security logic where possible.
>>>>>>> 3e93d57fe7003addf57d61508e7861286b2cbf96
