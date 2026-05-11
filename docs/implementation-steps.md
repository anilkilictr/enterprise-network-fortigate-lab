# Implementation Steps

## 1. Build the EVE-NG Topology

- Add routers R1 and R2.
- Add FortiGate between R1, R2, and the external lab network.
- Add distribution and access switches.
- Add Windows Server in the Istanbul server segment.
- Place endpoints according to VLAN membership.

## 2. Create VLANs

Create the following VLANs on access and distribution switches:

| VLAN | Name | Subnet |
|---:|---|---|
| 10 | IT | `10.1.1.0/24` |
| 20 | HR | `20.1.1.0/24` |
| 30 | SALES | `30.1.1.0/24` |
| 40 | ENGINEERING | `40.1.1.0/24` |
| 100 | SERVERS | `192.168.100.0/24` |

## 3. Configure Access and Trunk Ports

- Assign endpoint-facing ports to the correct access VLAN.
- Configure trunk links where multiple VLANs must cross a switch link.
- Validate VLAN membership with `show vlan brief`.
- Validate trunks with `show interfaces trunk`.

## 4. Configure Routed Links

Use the IP plan in `docs/addressing-plan.md` for all Layer 3 transit interfaces.

Key transit networks:

- R1 to FortiGate: `1.1.1.0/30`
- FortiGate to R2: `2.1.1.0/30`
- R1 to SW-3: `12.1.1.0/24`
- R1 to SW-4: `13.1.1.0/24`
- R2 to SW-5/SW-6/SW-7/SW-8: `14.1.1.0/24` through `17.1.1.0/24`

## 5. Configure Inter-VLAN Routing

Configure SVI-based routing or router-on-a-stick depending on the lab device roles.

Example:

```cisco
interface Vlan10
 description IT_USERS
 ip address 10.1.1.1 255.255.255.0
 no shutdown
```

## 6. Configure Dynamic or Static Routing

- Advertise internal VLAN and routed-link networks.
- Confirm that R1, R2, distribution switches, and FortiGate have routes for required networks.
- Validate routing tables before troubleshooting firewall policy.

## 7. Configure DHCP Relay

If Windows Server in VLAN 100 provides DHCP service for user VLANs, configure helper addresses on each user VLAN gateway.

Example:

```cisco
interface Vlan10
 ip helper-address 192.168.100.10
```

## 8. Configure FortiGate

- Configure WAN, Ankara-facing, and Istanbul-facing interfaces.
- Configure routes for Ankara VLANs and Istanbul server VLAN.
- Configure NAT for lab Internet access if required.
- Create firewall policies based on traffic direction and required services.
- Validate policy hit counters and logs.

## 9. Validate End-to-End Connectivity

- Client gateway reachability
- DHCP address assignment
- DNS resolution
- Server VLAN reachability
- Ankara-to-Istanbul allowed flows
- Internet/NAT access if enabled
- Denied inter-VLAN traffic
