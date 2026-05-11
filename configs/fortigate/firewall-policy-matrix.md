# Firewall Policy Matrix

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
