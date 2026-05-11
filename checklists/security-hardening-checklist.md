# Security Hardening Checklist

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
