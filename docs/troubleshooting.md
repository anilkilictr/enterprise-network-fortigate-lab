# Troubleshooting Guide

## VLAN Issues

### Symptoms

- Client cannot reach gateway
- Client is in the wrong subnet
- Trunk does not carry required VLAN

### Checks

- Verify access port VLAN assignment.
- Verify trunk allowed VLAN list.
- Verify SVI or routed interface status.
- Verify endpoint default gateway.

Commands:

```cisco
show vlan brief
show interfaces trunk
show ip interface brief
```

## Routing Issues

### Symptoms

- Inter-site traffic fails
- VLAN routes are missing
- Server VLAN is unreachable

### Checks

- Verify R1 to FortiGate connectivity over `1.1.1.0/30`.
- Verify FortiGate to R2 connectivity over `2.1.1.0/30`.
- Check routing tables on R1, R2, distribution switches, and FortiGate.
- Confirm that VLAN and transit networks are advertised or statically routed.

Commands:

```cisco
show ip route
show ip protocols
show ip ospf neighbor
```

## DHCP Relay Issues

### Symptoms

- Client receives APIPA address
- Client cannot get IP from centralized DHCP
- Only server-local VLAN clients receive addresses

### Checks

- Verify DHCP scopes exist on Windows Server.
- Verify the DHCP server IP is reachable from VLAN gateways.
- Verify `ip helper-address` is configured on user VLAN gateways.
- Verify firewall policy allows DHCP relay traffic where required.

## FortiGate Policy Issues

### Symptoms

- Ping works but application access fails
- Ankara users cannot access server services
- Internet access fails
- Expected deny rule is not taking effect

### Checks

- Validate route lookup.
- Validate NAT policy.
- Check source and destination interfaces.
- Check service objects.
- Check firewall policy order.
- Use FortiGate logs and policy hit counters.

## Server VLAN Issues

### Symptoms

- Windows Server is not reachable
- DNS or DHCP does not respond
- Server VPC cannot reach remote VLANs

### Checks

- Verify VLAN 100 access and trunk configuration.
- Verify server default gateway.
- Verify routing toward `192.168.100.0/24`.
- Verify FortiGate policy between Ankara VLANs and server VLAN.
