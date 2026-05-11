# Validation Checklist

## Switching

- [ ] VLAN 10 clients receive/reach `10.1.1.1`
- [ ] VLAN 20 clients receive/reach `20.1.1.1`
- [ ] VLAN 30 clients receive/reach `30.1.1.1`
- [ ] VLAN 40 clients receive/reach `40.1.1.1`
- [ ] Server VLAN clients reach `192.168.100.1`
- [ ] Access ports are in correct VLANs
- [ ] Trunks carry required VLANs

## Routing

- [ ] R1 reaches FortiGate over `1.1.1.0/30`
- [ ] R2 reaches FortiGate over `2.1.1.0/30`
- [ ] R1 reaches SW-3 over `12.1.1.0/24`
- [ ] R1 reaches SW-4 over `13.1.1.0/24`
- [ ] R2 reaches Istanbul distribution links over `14.1.1.0/24` through `17.1.1.0/24`
- [ ] All required routes exist
- [ ] Inter-VLAN routing works

## Security

- [ ] FortiGate policies match design
- [ ] NAT is enabled only where required
- [ ] Deny rules are tested
- [ ] Policy logs are visible
- [ ] Unnecessary inter-VLAN traffic is denied by policy

## Services

- [ ] Ankara VLANs can reach required server services
- [ ] DHCP Relay works for all user VLANs if centralized DHCP is used
- [ ] DNS resolution works if DNS is enabled
- [ ] Domain join works if AD DS is enabled
