# Addressing Plan

This document reflects the corrected IP plan based on the uploaded topology image.

## Ankara VLANs

| VLAN | Name | Subnet | Example Gateway |
|---:|---|---|---|
| 10 | IT | `10.1.1.0/24` | `10.1.1.1` |
| 20 | HR | `20.1.1.0/24` | `20.1.1.1` |
| 30 | Sales | `30.1.1.0/24` | `30.1.1.1` |
| 40 | Engineering | `40.1.1.0/24` | `40.1.1.1` |

## Istanbul VLANs

| VLAN | Name | Subnet | Example Gateway |
|---:|---|---|---|
| 100 | Servers | `192.168.100.0/24` | `192.168.100.1` |

## WAN / Transit Networks

| Connection | Subnet | Notes |
|---|---|---|
| R1 Ankara ↔ FortiGate port2 | `1.1.1.0/30` | Ankara edge transit |
| FortiGate port3 ↔ R2 Istanbul | `2.1.1.0/30` | Istanbul edge transit |
| FortiGate port1 ↔ Internet / NAT network | `192.168.174.0/24` | Lab Internet-side network |
| R1 ↔ SW-3 | `12.1.1.0/24` | Ankara distribution uplink |
| R1 ↔ SW-4 | `13.1.1.0/24` | Ankara distribution uplink |
| SW-3 ↔ SW-4 | `10.0.0.0/30` | Distribution routed interconnect |
| R2 ↔ SW-5 | `14.1.1.0/24` | Istanbul distribution uplink |
| R2 ↔ SW-6 | `15.1.1.0/24` | Istanbul distribution uplink |
| R2 ↔ SW-7 | `16.1.1.0/24` | Istanbul distribution uplink |
| R2 ↔ SW-8 | `17.1.1.0/24` | Istanbul distribution uplink |
| SW-5 ↔ SW-6 | `11.0.0.0/30` | Distribution routed interconnect |

## Endpoint Placement

| Endpoint Group | Switch Area | VLAN | Subnet |
|---|---|---:|---|
| VPC15, VPC16 | Ankara IT | 10 | `10.1.1.0/24` |
| VPC17, VPC18 | Ankara HR | 20 | `20.1.1.0/24` |
| VPC19, VPC20 | Ankara Sales | 30 | `30.1.1.0/24` |
| VPC21, VPC22 | Ankara Engineering | 40 | `40.1.1.0/24` |
| Windows Server, Server VPC | Istanbul Servers | 100 | `192.168.100.0/24` |
