# Firewall Policy Matrix

| Policy Name | Source | Destination | Services | Action | NAT | Notes |
|---|---|---|---|---|---|---|
| IT_to_Servers | Ankara VLAN 10 IT | Server VLAN 100 | DNS, DHCP relay, ICMP, HTTPS, RDP/SSH if required | Allow | Disabled | IT administration and testing |
| HR_to_Servers | Ankara VLAN 20 HR | Server VLAN 100 | DNS, DHCP relay, HTTPS | Allow | Disabled | Business-required services only |
| Sales_to_Servers | Ankara VLAN 30 Sales | Server VLAN 100 | DNS, DHCP relay, HTTPS | Allow | Disabled | Business-required services only |
| Engineering_to_Servers | Ankara VLAN 40 Engineering | Server VLAN 100 | DNS, DHCP relay, HTTPS, SSH/RDP if required | Allow | Disabled | Engineering/admin testing |
| Servers_to_Users | Server VLAN 100 | Ankara VLANs | Established / required services | Allow limited | Disabled | Avoid broad server-to-client access |
| Internal_to_Internet | Ankara VLANs, Server VLAN 100 | Internet / Lab NAT | HTTP, HTTPS, DNS | Allow | Enabled | Optional lab Internet access |
| Block_InterDepartment | User VLANs | Other user VLANs | Any | Deny | Disabled | Enforce segmentation |
| Default_Deny | Any | Any | Any | Deny | Disabled | Least privilege baseline |

## Policy Design Notes

- Use direction-based and service-based rules.
- Place deny or restrictive rules before broad allow rules.
- Avoid `any-any` allow rules in production designs.
- Log important allow and deny policies for visibility.
- Separate NAT behavior from security policy logic where possible.
- Confirm routes before troubleshooting firewall policy hits.
