# Windows Server, Active Directory and DHCP Relay Notes

## Windows Server Roles

- Active Directory Domain Services
- DNS Server
- DHCP Server

## Example Domain

- Domain: `lab.local`
- Domain Controller: `SRV-IST-AD-01`
- Server VLAN: `192.168.100.0/24`
- Server IP: `192.168.100.10`

## DHCP Scopes

| Scope | Subnet | Gateway | DNS |
|---|---|---|---|
| IT Scope | `10.1.1.0/24` | `10.1.1.1` | `192.168.100.10` |
| HR Scope | `20.1.1.0/24` | `20.1.1.1` | `192.168.100.10` |
| Sales Scope | `30.1.1.0/24` | `30.1.1.1` | `192.168.100.10` |
| Engineering Scope | `40.1.1.0/24` | `40.1.1.1` | `192.168.100.10` |
| Server Scope | `192.168.100.0/24` | `192.168.100.1` | `192.168.100.10` |

## DHCP Relay Logic

Clients in different VLANs do not directly reach the DHCP broadcast domain. Therefore, the gateway interface uses DHCP Relay / IP Helper to forward DHCP requests to the central DHCP server.

Cisco example:

```cisco
ip helper-address 192.168.100.10
```

## Validation

- Client receives IP from correct scope
- Client receives correct gateway and DNS
- Client resolves domain name
- Client can join domain if AD DS is enabled
- GPOs apply successfully after domain join if AD DS is enabled
