# Validation Checklist

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
