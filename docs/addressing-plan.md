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
| R1 Ankara to FortiGate port2 | `1.1.1.0/30` | Ankara edge transit |
| FortiGate port3 to R2 Istanbul | `2.1.1.0/30` | Istanbul edge transit |
| FortiGate port1 to Internet / NAT network | `192.168.174.0/24` | Lab Internet-side network |
| R1 to SW-3 | `12.1.1.0/24` | Ankara distribution uplink |
| R1 to SW-4 | `13.1.1.0/24` | Ankara distribution uplink |
| SW-3 to SW-4 | `10.0.0.0/30` | Distribution routed interconnect |
| R2 to SW-5 | `14.1.1.0/24` | Istanbul distribution uplink |
| R2 to SW-6 | `15.1.1.0/24` | Istanbul distribution uplink |
| R2 to SW-7 | `16.1.1.0/24` | Istanbul distribution uplink |
| R2 to SW-8 | `17.1.1.0/24` | Istanbul distribution uplink |
| SW-5 to SW-6 | `11.0.0.0/30` | Distribution routed interconnect |

## Endpoint Placement

| Endpoint Group | Switch Area | VLAN | Subnet |
|---|---|---:|---|
| VPC15, VPC16 | Ankara IT | 10 | `10.1.1.0/24` |
| VPC17, VPC18 | Ankara HR | 20 | `20.1.1.0/24` |
| VPC19, VPC20 | Ankara Sales | 30 | `30.1.1.0/24` |
| VPC21, VPC22 | Ankara Engineering | 40 | `40.1.1.0/24` |
| Windows Server, Server VPC | Istanbul Servers | 100 | `192.168.100.0/24` |

## Naming Convention

| Device | Example Name |
|---|---|
| FortiGate Edge | FG-EDGE-01 |
| Ankara Router | R1-ANKARA |
| Istanbul Router | R2-ISTANBUL |
| Ankara Distribution Switches | SW3-ANK-DIST, SW4-ANK-DIST |
| Istanbul Distribution Switches | SW5-IST-DIST, SW6-IST-DIST |
| Windows Server | SRV-IST-AD-01 |
