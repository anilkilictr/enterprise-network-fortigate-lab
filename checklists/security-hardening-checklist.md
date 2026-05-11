# Security Hardening Checklist

<<<<<<< HEAD
- [ ] Do not publish real device backups
- [ ] Remove passwords, keys, SNMP communities and tokens
- [ ] Use sample hostnames and lab IP addresses only
- [ ] Restrict management access to trusted subnets
- [ ] Apply least privilege firewall policies
- [ ] Disable unused switch ports
- [ ] Use SSH instead of Telnet
- [ ] Document allowed services between VLANs
=======
## Network Devices

- [ ] Disable unused ports
- [ ] Use SSH instead of Telnet
- [ ] Use strong local credentials or centralized authentication
- [ ] Restrict management access to management VLAN
- [ ] Configure NTP
- [ ] Configure syslog

## FortiGate

- [ ] Remove unused policies
- [ ] Avoid broad any-any rules
- [ ] Enable logging on critical policies
- [ ] Restrict admin access
- [ ] Keep firmware updated
- [ ] Use named address and service objects

## Windows Server

- [ ] Use least privilege
- [ ] Apply updates
- [ ] Configure DNS properly
- [ ] Review GPOs
- [ ] Backup AD
- [ ] Monitor event logs
>>>>>>> 3e93d57fe7003addf57d61508e7861286b2cbf96
