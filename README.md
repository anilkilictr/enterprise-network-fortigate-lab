# Enterprise Network & FortiGate Security Lab

![Project Status](https://img.shields.io/badge/status-active_lab-blue)
![Platform](https://img.shields.io/badge/platform-EVE--NG-orange)
![Network](https://img.shields.io/badge/network-Cisco%20%7C%20Fortinet%20%7C%20Windows%20Server-00B4D8)
![License](https://img.shields.io/badge/license-MIT-green)

A multi-site enterprise network lab built in **EVE-NG**. The topology demonstrates Cisco routing and switching, VLAN segmentation, routed Layer 3 links, FortiGate NGFW edge security, DHCP Relay, and Windows Server services.

> This repository uses sanitized lab documentation. No real production IPs, passwords, VPN keys, firewall exports, or organization-specific data are included.

## Architecture Summary

| Layer | Technologies | Purpose |
|---|---|---|
| Access and Distribution | Cisco Switching, VLANs, trunks | Department segmentation and endpoint access |
| Routing | Routed links, inter-VLAN routing, OSPF-ready design | Site and VLAN reachability |
| Security and WAN | FortiGate NGFW, NAT, firewall policies | Edge security, traffic inspection, and controlled inter-site access |
| Identity and Services | Windows Server, DHCP Relay, DNS/AD-ready services | Centralized server-side lab services |

## Topology
<img width="800" height="550" alt="image" src="https://github.com/user-attachments/assets/ad0967c4-b152-4d0d-87e9-233ffdb067c1" />

## Key Features

### Cisco Routing and Switching

- VLAN-based segmentation for IT, HR, Sales, Engineering, and Servers
- Routed uplinks between routers and distribution switches
- Inter-VLAN routing design
- OSPF-ready routed topology
- Access and trunk port validation workflow

### FortiGate Security

- FortiGate positioned as the central NGFW between Ankara, Istanbul, and the lab Internet/NAT network
- Service-based firewall policy matrix
- Least privilege traffic control between user and server networks
- Optional NAT for lab Internet access

### Microsoft Services

- Windows Server placed in the Istanbul server VLAN
- DHCP scope planning for centralized address assignment
- DHCP Relay / IP Helper design for multi-VLAN clients
- DNS and AD-ready server segment documentation

## Correct VLAN and IP Plan

### Ankara Site

| Segment | VLAN | Subnet | Purpose |
|---|---:|---|---|
| IT | 10 | `10.1.1.0/24` | IT users |
| HR | 20 | `20.1.1.0/24` | Human Resources users |
| Sales | 30 | `30.1.1.0/24` | Sales users |
| Engineering | 40 | `40.1.1.0/24` | Engineering users |

### Istanbul Site

| Segment | VLAN | Subnet | Purpose |
|---|---:|---|---|
| Servers | 100 | `192.168.100.0/24` | Windows Server and server-side test clients |

### Routed / Transit Networks

| Link | Subnet |
|---|---|
| Ankara R1 to FortiGate | `1.1.1.0/30` |
| FortiGate to Istanbul R2 | `2.1.1.0/30` |
| FortiGate WAN / Internet-side lab network | `192.168.174.0/24` |
| Ankara R1 to SW-3 | `12.1.1.0/24` |
| Ankara R1 to SW-4 | `13.1.1.0/24` |
| SW-3 to SW-4 routed link | `10.0.0.0/30` |
| Istanbul R2 to SW-5 | `14.1.1.0/24` |
| Istanbul R2 to SW-6 | `15.1.1.0/24` |
| Istanbul R2 to SW-7 | `16.1.1.0/24` |
| Istanbul R2 to SW-8 | `17.1.1.0/24` |
| SW-5 to SW-6 routed link | `11.0.0.0/30` |

## Repository Structure

```text
.
├── README.md
├── LICENSE
├── SECURITY.md
├── CONTRIBUTING.md
├── GITHUB_UPLOAD_COMMANDS.md
├── docs/
│   ├── addressing-plan.md
│   ├── architecture.md
│   ├── implementation-steps.md
│   ├── troubleshooting.md
│   └── lessons-learned.md
├── diagrams/
│   ├── topology.png
│   ├── topology.mmd
│   └── topology-notes.md
├── configs/
│   ├── cisco/
│   │   ├── branch-switch-sample.cfg
│   │   ├── core-sw1-sample.cfg
│   │   ├── core-sw2-sample.cfg
│   │   ├── r1-ankara-sample.cfg
│   │   ├── r2-istanbul-sample.cfg
│   │   ├── sw3-ankara-distribution-sample.cfg
│   │   ├── sw4-ankara-distribution-sample.cfg
│   │   └── sw14-server-access-sample.cfg
│   ├── fortigate/
│   │   ├── fortigate-edge-sample.conf
│   │   ├── fortigate-hq-sample.conf
│   │   └── firewall-policy-matrix.md
│   └── windows-server/
│       ├── dhcp-relay-and-ad-notes.md
│       └── dhcp-scope-plan.md
└── checklists/
    ├── pre-deployment-checklist.md
    ├── validation-checklist.md
    └── security-hardening-checklist.md
```

## Configuration Samples

Configuration examples are intentionally simplified and sanitized. They are designed to show the design logic, not to expose production-ready secrets or real infrastructure data.

See:

- [`configs/cisco/r1-ankara-sample.cfg`](configs/cisco/r1-ankara-sample.cfg)
- [`configs/cisco/r2-istanbul-sample.cfg`](configs/cisco/r2-istanbul-sample.cfg)
- [`configs/cisco/sw3-ankara-distribution-sample.cfg`](configs/cisco/sw3-ankara-distribution-sample.cfg)
- [`configs/cisco/sw4-ankara-distribution-sample.cfg`](configs/cisco/sw4-ankara-distribution-sample.cfg)
- [`configs/fortigate/fortigate-edge-sample.conf`](configs/fortigate/fortigate-edge-sample.conf)
- [`configs/fortigate/firewall-policy-matrix.md`](configs/fortigate/firewall-policy-matrix.md)
- [`configs/windows-server/dhcp-scope-plan.md`](configs/windows-server/dhcp-scope-plan.md)

## Validation Checklist

- [ ] VLANs created and assigned correctly
- [ ] Trunk links carry required VLANs
- [ ] Routed links are up
- [ ] Inter-VLAN routing works
- [ ] R1 reaches FortiGate over `1.1.1.0/30`
- [ ] R2 reaches FortiGate over `2.1.1.0/30`
- [ ] FortiGate NAT policies are verified
- [ ] Firewall policies allow only required traffic
- [ ] DHCP Relay assigns IP addresses to user VLANs if centralized DHCP is used
- [ ] Server VLAN services are reachable only from approved sources
- [ ] Unauthorized inter-VLAN traffic is blocked

## Suggested GitHub Topics

`eveng` `cisco` `fortigate` `network-security` `enterprise-network` `vlan` `ospf` `dhcp-relay` `windows-server` `firewall` `network-engineering`

## Lab Notes

This lab is suitable for:

- CCNA / CCNP Enterprise practice
- FortiGate security policy design practice
- Windows Server and DHCP Relay integration practice
- Enterprise network documentation portfolio work
- GitHub technical portfolio improvement

## Disclaimer

This project is for educational and portfolio purposes only. All IP ranges, hostnames, policies, and configurations are fictional or sanitized lab examples.
