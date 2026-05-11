# Troubleshooting Guide

<<<<<<< HEAD
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
=======
## VLAN Issues

### Symptoms
- Client cannot reach gateway
- Client is in wrong subnet
- Trunk does not carry required VLAN

### Checks
- `show vlan brief`
- `show interfaces trunk`
- `show etherchannel summary`
- Verify access port VLAN assignment

## HSRP Issues

### Symptoms
- Gateway IP unreachable
- Both switches appear active
- Failover does not work

### Checks
- `show standby brief`
- Verify HSRP group number
- Verify virtual IP address
- Verify interface VLAN status

## OSPF Issues

### Symptoms
- Branch or VLAN routes missing
- OSPF neighbor not forming
- Inter-site traffic fails

### Checks
- `show ip ospf neighbor`
- `show ip route ospf`
- Verify network statements
- Verify interface MTU and passive-interface settings

## DHCP Relay Issues

### Symptoms
- Client receives APIPA address
- Client cannot get IP from central DHCP server
- Only local VLAN works

### Checks
- Verify DHCP scope
- Verify relay/helper address
- Verify firewall policy allows DHCP relay traffic
- Verify route between client VLAN and DHCP server

## FortiGate Policy Issues

### Symptoms
- Ping works but application fails
- Branch users cannot access HQ server
- Internet access fails

### Checks
- Validate route lookup
- Validate NAT policy
- Validate firewall policy order
- Check source/destination interfaces
- Check service objects
- Use FortiGate log viewer and policy hit counters

>>>>>>> 3e93d57fe7003addf57d61508e7861286b2cbf96
