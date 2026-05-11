# Architecture

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
