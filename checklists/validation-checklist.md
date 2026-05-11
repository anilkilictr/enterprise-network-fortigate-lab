# Validation Checklist

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
