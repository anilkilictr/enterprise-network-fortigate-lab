# Troubleshooting Guide

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

