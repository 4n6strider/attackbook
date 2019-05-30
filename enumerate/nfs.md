---
description: 'TCP/111, UDP/111, TCP/2049, UDP/2049'
---

# NFS

## Enumerating with nmap

```bash
nmap -v -n -Pn -sT -sU -p U:111,T:111,U:2049,T:2049 --oA report_nfs $range
grep open report_nfs.gnmap | cut -d" " -f2 > hosts_nfs.txt
```

## Enumerating with NSE

```bash
nmap -sV --script=nfs-showmount $ip
```

## NFS commands

```bash
showmount -e $ip

mkdir /temp/
mount -t nfs $ip:/ /temp -o nolock
df -h
cd /temp
```

