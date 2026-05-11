# Security Hardening Checklist

## Repository Safety

- [ ] Do not publish real device backups
- [ ] Remove passwords, keys, SNMP communities, and tokens
- [ ] Use sample hostnames and lab IP addresses only
- [ ] Review screenshots before publishing
- [ ] Keep public examples sanitized

## Network Devices

- [ ] Disable unused switch ports
- [ ] Use SSH instead of Telnet
- [ ] Use strong local credentials or centralized authentication
- [ ] Restrict management access to trusted subnets
- [ ] Configure NTP
- [ ] Configure syslog
- [ ] Document allowed services between VLANs

## FortiGate

- [ ] Remove unused policies
- [ ] Avoid broad `any-any` allow rules
- [ ] Enable logging on critical policies
- [ ] Restrict admin access
- [ ] Keep firmware updated
- [ ] Use named address and service objects
- [ ] Apply least privilege firewall policies

## Windows Server

- [ ] Use least privilege
- [ ] Apply updates
- [ ] Configure DNS properly
- [ ] Review GPOs if AD is enabled
- [ ] Back up AD if AD is enabled
- [ ] Monitor event logs
