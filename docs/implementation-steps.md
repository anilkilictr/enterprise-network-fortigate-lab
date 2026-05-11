# Implementation Steps

## 1. Build the EVE-NG Topology

- Add routers R1 and R2.
- Add FortiGate between R1, R2 and the external lab network.
- Add distribution and access switches.
- Place endpoints according to VLAN membership.

## 2. Create VLANs

Create the following VLANs on access/distribution switches:

| VLAN | Name | Subnet |
|---:|---|---|
| 10 | IT | `10.1.1.0/24` |
| 20 | HR | `20.1.1.0/24` |
| 30 | SALES | `30.1.1.0/24` |
| 40 | ENGINEERING | `40.1.1.0/24` |
| 100 | SERVERS | `192.168.100.0/24` |

## 3. Configure Routed Links

Use the IP plan in `docs/addressing-plan.md` for all L3 transit interfaces.

## 4. Configure Inter-VLAN Routing

Configure SVI or router-on-a-stick depending on the lab device roles.

## 5. Configure DHCP Relay

If Windows Server in VLAN 100 provides DHCP service for user VLANs, configure helper addresses on each user VLAN gateway.

Example:

```cisco
interface Vlan10
 ip helper-address 192.168.100.10
```

## 6. Configure FortiGate Policies

Create policy rules for:

- Ankara user VLANs to server VLAN
- Server VLAN to required services only
- Internal networks to Internet/NAT
- Deny unnecessary east-west or inter-department traffic
