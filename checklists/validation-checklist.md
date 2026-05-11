# Validation Checklist

<<<<<<< HEAD
- [ ] VLAN 10 clients receive/reach `10.1.1.1`
- [ ] VLAN 20 clients receive/reach `20.1.1.1`
- [ ] VLAN 30 clients receive/reach `30.1.1.1`
- [ ] VLAN 40 clients receive/reach `40.1.1.1`
- [ ] Server VLAN clients reach `192.168.100.1`
- [ ] R1 reaches FortiGate over `1.1.1.0/30`
- [ ] R2 reaches FortiGate over `2.1.1.0/30`
- [ ] Ankara VLANs can reach required server services
- [ ] Unnecessary inter-VLAN traffic is denied by policy
- [ ] DHCP Relay works for all user VLANs if centralized DHCP is used
=======
## Switching

- [ ] VLANs exist on switches
- [ ] Access ports are in correct VLANs
- [ ] Trunks carry required VLANs
- [ ] EtherChannel is up

## Routing

- [ ] HSRP state is correct
- [ ] OSPF neighbors are established
- [ ] All required routes exist
- [ ] Inter-VLAN routing works

## Security

- [ ] FortiGate policies match design
- [ ] NAT is enabled only where required
- [ ] Deny rules are tested
- [ ] Policy logs are visible

## Services

- [ ] DHCP works across VLANs
- [ ] DNS resolution works
- [ ] Domain join works
- [ ] Branch users reach allowed HQ services
>>>>>>> 3e93d57fe7003addf57d61508e7861286b2cbf96
