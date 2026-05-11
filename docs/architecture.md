# Architecture

## Design Goal

The goal of this lab is to build a multi-site enterprise network architecture where routing, switching, security and identity services operate together.

## Main Design Decisions

### 1. Core & Distribution Layer

The HQ location uses redundant Cisco core/distribution switches. HSRP provides default gateway redundancy for user VLANs, while EtherChannel improves uplink availability and bandwidth usage.

### 2. Routing

OSPF is used as the internal routing protocol because it is widely used in enterprise environments and suitable for multi-area or scalable internal designs.

### 3. FortiGate Edge Security

FortiGate is placed at the edge to centralize NAT, firewall inspection and WAN traffic control. This makes the security layer more visible and easier to manage compared to router-only edge routing.

### 4. Hub-and-Spoke WAN

Branch locations route traffic through the HQ FortiGate. This allows centralized control, logging and policy management.

### 5. Centralized Services

Windows Server is placed in the server VLAN and provides Active Directory, DNS and DHCP services. DHCP Relay is used so clients in different VLANs can receive IP addresses from centralized DHCP pools.

## Traffic Flow Examples

| Source | Destination | Expected Path |
|---|---|---|
| IT User | Internet | VLAN 10 → Core → FortiGate HQ → Internet |
| Branch User | AD Server | Branch FortiGate → HQ FortiGate → Core → Server VLAN |
| HR User | Sales User | Blocked or restricted by firewall / ACL policy |
| Client VLAN | DHCP Server | DHCP Relay → Server VLAN DHCP service |

