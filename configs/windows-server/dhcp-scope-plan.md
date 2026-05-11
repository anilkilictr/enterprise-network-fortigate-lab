# Windows Server DHCP Scope Plan

Assumed DHCP server IP: `192.168.100.10`

## DHCP Scopes

| Scope | Range Example | Gateway | DNS |
|---|---|---|---|
| VLAN 10 IT - `10.1.1.0/24` | `10.1.1.50 - 10.1.1.200` | `10.1.1.1` | `192.168.100.10` |
| VLAN 20 HR - `20.1.1.0/24` | `20.1.1.50 - 20.1.1.200` | `20.1.1.1` | `192.168.100.10` |
| VLAN 30 Sales - `30.1.1.0/24` | `30.1.1.50 - 30.1.1.200` | `30.1.1.1` | `192.168.100.10` |
| VLAN 40 Engineering - `40.1.1.0/24` | `40.1.1.50 - 40.1.1.200` | `40.1.1.1` | `192.168.100.10` |
| VLAN 100 Servers - `192.168.100.0/24` | Static preferred | `192.168.100.1` | `192.168.100.10` |

## Cisco DHCP Relay Example

```cisco
interface Vlan10
 ip helper-address 192.168.100.10
```
