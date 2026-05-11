# Addressing Plan

| Site | Segment | VLAN | Subnet | Gateway | Notes |
|---|---|---:|---|---|---|
| HQ | IT | 10 | 10.10.10.0/24 | 10.10.10.1 | IT users |
| HQ | HR | 20 | 10.10.20.0/24 | 10.10.20.1 | HR users |
| HQ | Sales | 30 | 10.10.30.0/24 | 10.10.30.1 | Sales users |
| HQ | Servers | 40 | 10.10.40.0/24 | 10.10.40.1 | AD, DNS, DHCP |
| HQ | Management | 99 | 10.10.99.0/24 | 10.10.99.1 | Device management |
| Branch Ankara | Users | 110 | 10.20.10.0/24 | 10.20.10.1 | Ankara branch users |
| Branch Istanbul | Users | 120 | 10.30.10.0/24 | 10.30.10.1 | Istanbul branch users |

## Naming Convention

| Device | Example Name |
|---|---|
| FortiGate HQ | FG-HQ-01 |
| FortiGate Branch | FG-BR-ANK-01 |
| Core Switch 1 | SW-HQ-CORE-01 |
| Core Switch 2 | SW-HQ-CORE-02 |
| Windows Server | SRV-HQ-AD-01 |

