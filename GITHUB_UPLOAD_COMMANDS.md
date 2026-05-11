# GitHub Upload Commands

Run these commands from inside the extracted repository folder:

```powershell
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
