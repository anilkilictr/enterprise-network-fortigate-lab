# Enterprise Network & FortiGate Lab

A multi-site enterprise network lab built in **EVE-NG**. The topology demonstrates Cisco routing/switching, VLAN segmentation, OSPF-ready routed links, FortiGate NGFW edge security, and Windows Server services.

> This repository uses sanitized lab documentation. No real production IPs, passwords, VPN keys, or organization-specific data are included.

## Lab Topology

![Enterprise Network FortiGate Lab Topology](diagrams/topology.png)

## Main Technologies

- Cisco routing and switching
- FortiGate NGFW edge firewall
- VLAN segmentation
- Inter-VLAN routing
- Routed L3 links
- DHCP Relay / IP Helper concept
- Windows Server services
- Enterprise network documentation

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
| Ankara R1 ↔ FortiGate | `1.1.1.0/30` |
| FortiGate ↔ Istanbul R2 | `2.1.1.0/30` |
| FortiGate WAN / Internet-side lab network | `192.168.174.0/24` |
| Ankara R1 ↔ SW-3 | `12.1.1.0/24` |
| Ankara R1 ↔ SW-4 | `13.1.1.0/24` |
| SW-3 ↔ SW-4 routed link | `10.0.0.0/30` |
| Istanbul R2 ↔ SW-5 | `14.1.1.0/24` |
| Istanbul R2 ↔ SW-6 | `15.1.1.0/24` |
| Istanbul R2 ↔ SW-7 | `16.1.1.0/24` |
| Istanbul R2 ↔ SW-8 | `17.1.1.0/24` |
| SW-5 ↔ SW-6 routed link | `11.0.0.0/30` |

## Repository Structure

```text
.
├── README.md
├── docs/
│   ├── addressing-plan.md
│   ├── architecture.md
│   ├── implementation-steps.md
│   ├── troubleshooting.md
│   └── lessons-learned.md
├── diagrams/
│   ├── topology.png
│   └── topology.mmd
├── configs/
│   ├── cisco/
│   │   ├── r1-ankara-sample.cfg
│   │   ├── r2-istanbul-sample.cfg
│   │   ├── sw3-ankara-distribution-sample.cfg
│   │   ├── sw4-ankara-distribution-sample.cfg
│   │   └── sw14-server-access-sample.cfg
│   ├── fortigate/
│   │   ├── fortigate-edge-sample.conf
│   │   └── firewall-policy-matrix.md
│   └── windows-server/
│       └── dhcp-scope-plan.md
└── checklists/
    ├── validation-checklist.md
    └── security-hardening-checklist.md
```

## Suggested GitHub Topics

`eveng` `cisco` `fortigate` `network-security` `enterprise-network` `vlan` `ospf` `dhcp-relay` `windows-server` `firewall` `network-engineering`

## Notes

This lab is designed as a technical portfolio project. It focuses on network design, documentation quality, and troubleshooting methodology rather than exposing any production configuration.
