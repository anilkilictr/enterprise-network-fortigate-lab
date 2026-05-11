# Architecture

The lab represents a two-site enterprise topology:

- **Ankara Site:** user VLANs for IT, HR, Sales, and Engineering.
- **Istanbul Site:** routed campus/distribution area and server VLAN.
- **FortiGate Edge:** central NGFW between the Ankara router, Istanbul router, and the external lab network.

## Design Goals

1. Segment departments with separate VLANs and subnets.
2. Route traffic between VLANs and sites using Layer 3 links.
3. Use FortiGate as the security enforcement point for WAN and edge traffic.
4. Place Windows Server services in a dedicated server VLAN.
5. Keep documentation and configurations safe for public GitHub sharing.

## Main Design Decisions

### 1. VLAN Segmentation

Each department uses a dedicated VLAN and subnet. This keeps broadcast domains small and gives the firewall/routing layer clear policy boundaries.

### 2. Routed Distribution Links

Distribution switches and routers use routed links for predictable Layer 3 behavior and simpler route advertisement.

### 3. FortiGate Edge Security

FortiGate is placed between the Ankara and Istanbul routed domains and the lab Internet/NAT network. This centralizes NAT, firewall inspection, and inter-site policy enforcement.

### 4. Centralized Services

Windows Server is placed in VLAN 100. DHCP Relay can be configured on user VLAN gateways so clients in Ankara can receive addresses from centralized DHCP scopes.

## High-Level Traffic Flow

| Source | Destination | Expected Path |
|---|---|---|
| Ankara user VLAN | Istanbul server VLAN | VLAN gateway to R1 to FortiGate to R2 to server VLAN |
| Ankara user VLAN | Internet / lab NAT | VLAN gateway to R1 to FortiGate port1 |
| Server VLAN | Ankara VLANs | R2 to FortiGate to R1, limited by policy |
| Client VLAN | DHCP Server | DHCP Relay to Windows Server in VLAN 100 |

## Security Model

- Allow only required services between user VLANs and server VLAN.
- Restrict server-to-client access to established or explicitly required flows.
- Log important allow and deny rules.
- Avoid broad `any-any` policies.
- Keep sample configs sanitized before public sharing.
