# Architecture

<<<<<<< HEAD
The lab represents a two-site enterprise topology:

- **Ankara Site:** user VLANs for IT, HR, Sales and Engineering.
- **Istanbul Site:** routed campus/distribution area and server VLAN.
- **FortiGate Edge:** central NGFW between the Ankara and Istanbul routers and the external lab network.

## Design Goals

1. Segment departments with separate VLANs and subnets.
2. Route traffic between VLANs and sites using Layer 3 links.
3. Use FortiGate as the security enforcement point for WAN/edge traffic.
4. Place Windows Server services in a dedicated server VLAN.
5. Keep documentation and configurations safe for public GitHub sharing.

## High-Level Traffic Flow

- Ankara user VLANs route toward R1 and FortiGate.
- Istanbul server VLAN routes toward R2 and FortiGate.
- Inter-site traffic is controlled by firewall policy.
- DHCP services can be centralized on Windows Server using DHCP Relay / IP Helper.
=======
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

>>>>>>> 3e93d57fe7003addf57d61508e7861286b2cbf96
