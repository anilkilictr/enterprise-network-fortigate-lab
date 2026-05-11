# GitHub Upload Commands

Use these commands after creating a new GitHub repository named:

`enterprise-network-fortigate-lab`

## Windows PowerShell

```powershell
cd enterprise-network-fortigate-lab
git init
git add .
git commit -m "Initial corrected enterprise network and FortiGate lab"
git branch -M main
git remote add origin https://github.com/anilkilictr/enterprise-network-fortigate-lab.git
git push -u origin main
```

If the remote already exists:

```powershell
git remote set-url origin https://github.com/anilkilictr/enterprise-network-fortigate-lab.git
git push -u origin main
```

## Suggested Repository Description

`Multi-site enterprise network lab with Cisco routing and switching, FortiGate NGFW, VLAN segmentation, DHCP Relay, and Windows Server services.`

## Suggested Topics

```text
eveng
cisco
fortigate
network-security
enterprise-network
vlan
ospf
dhcp-relay
windows-server
firewall
network-engineering
```
