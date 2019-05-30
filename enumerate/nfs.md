---
description: 'TCP/111, UDP/111, TCP/2049, UDP/2049'
---

# NFS

### nmap scans

```bash
nmap -sV --script=nfs-showmount $ip
```

### NFS commands

```bash
showmount -e $ip

mkdir /temp/
mount -t nfs [ip]:/ /temp -o nolock
df -h
cd /temp
```

