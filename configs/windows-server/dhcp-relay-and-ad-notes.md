# Windows Server, Active Directory and DHCP Relay Notes

## Windows Server Roles

- Active Directory Domain Services
- DNS Server
- DHCP Server

## Example Domain

- Domain: lab.local
- Domain Controller: SRV-HQ-AD-01
- Server VLAN: 10.10.40.0/24
- Server IP: 10.10.40.10

## DHCP Scopes

| Scope | Subnet | Gateway | DNS |
|---|---|---|---|
| IT Scope | 10.10.10.0/24 | 10.10.10.1 | 10.10.40.10 |
| HR Scope | 10.10.20.0/24 | 10.10.20.1 | 10.10.40.10 |
| Sales Scope | 10.10.30.0/24 | 10.10.30.1 | 10.10.40.10 |
| Branch Scope | 10.20.10.0/24 | 10.20.10.1 | 10.10.40.10 |

## DHCP Relay Logic

Clients in different VLANs do not directly reach the DHCP broadcast domain.  
Therefore, the gateway interface uses DHCP Relay / IP Helper to forward DHCP requests to the central DHCP server.

Cisco example:

`ip helper-address 10.10.40.10`

## Validation

- Client receives IP from correct scope
- Client receives correct gateway and DNS
- Client resolves domain name
- Client can join domain
- GPOs apply successfully after domain join
