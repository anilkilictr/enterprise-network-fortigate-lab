# Troubleshooting Guide

## 1. VLAN Client Cannot Reach Gateway

Check:

- Access port VLAN assignment
- Trunk allowed VLAN list
- SVI/interface status
- Default gateway configured on endpoint

Commands:

```cisco
show vlan brief
show interfaces trunk
show ip interface brief
```

## 2. DHCP Is Not Working

Check:

- DHCP scope exists on Windows Server
- DHCP server IP is reachable from gateway
- `ip helper-address` is configured on user VLAN gateways
- Firewall policy allows DHCP relay traffic where required

## 3. Inter-Site Connectivity Fails

Check:

- R1 ↔ FortiGate `1.1.1.0/30`
- FortiGate ↔ R2 `2.1.1.0/30`
- Routing table on R1, R2 and FortiGate
- Firewall policies between sites

## 4. Server VLAN Is Not Reachable

Check:

- VLAN 100 access/trunk configuration
- Server default gateway
- Routing toward `192.168.100.0/24`
- FortiGate security policy
