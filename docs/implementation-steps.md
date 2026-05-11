# Implementation Steps

## 1. Build the EVE-NG Topology

<<<<<<< HEAD
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
=======
- Add Cisco core/distribution switches
- Add FortiGate HQ and branch firewall nodes
- Add Windows Server VM
- Add client VMs for IT, HR, Sales and branch users
- Connect uplinks and access ports according to the topology

## 2. Configure VLANs

- Create VLAN 10, 20, 30, 40 and 99 on core switches
- Assign access ports
- Configure trunk links
- Validate VLAN propagation

## 3. Configure EtherChannel

- Bundle redundant uplinks
- Validate port-channel status
- Confirm trunk operation over port-channel

## 4. Configure HSRP

- Create redundant default gateway for user VLANs
- Validate active/standby state
- Test gateway failover

## 5. Configure OSPF

- Enable OSPF on routed links
- Advertise internal VLAN networks
- Validate neighbor relationships
- Check routing table

## 6. Configure FortiGate

- Configure internal, WAN and branch-facing interfaces
- Configure static or dynamic routing
- Configure NAT
- Create firewall policies based on traffic direction and service
- Validate allowed and denied flows

## 7. Configure Windows Server Services

- Install AD DS role
- Promote server to Domain Controller
- Configure DNS
- Configure DHCP scopes
- Configure DHCP Relay on gateway interfaces

## 8. Validate End-to-End Connectivity

- Client IP assignment
- DNS resolution
- Domain join
- Internet access
- Branch-to-HQ access
- Inter-VLAN policy restrictions

>>>>>>> 3e93d57fe7003addf57d61508e7861286b2cbf96
