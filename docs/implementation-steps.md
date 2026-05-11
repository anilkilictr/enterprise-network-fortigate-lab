# Implementation Steps

## 1. Build the EVE-NG Topology

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

