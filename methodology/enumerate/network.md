---
description: Network flyover and host discovery
---

# Network

### Netdiscover

```text
netdiscover -r 10.10.10.0/24
```







Discovery with nmap

\#find name servers with nmap and store results in a file

nmap -v -sT -sV -O -Pn --top-ports 100  -oG report.txt \[range\]



nmap -vv -Pn -A -sC -sS -T 4 -p- -oN \[ip\]

nmap -vv -Pn -A -sC -sU -T 4 --top-ports 200 -oN \[ip\]



grep file and make directory for each

grep Up report.txt \| cut -d" " -f2 &gt; hosts.txt



for host in $\(cat report.txt\); do mkdir $host; done



\#grep files for services



 



TCP/UDP nmap scans to identify open ports/services for additional enumeration \(see below\)

HTTP/S enumeration \(via additional nmap scans and web file/directory brute forcing\)

MS-SQL enumeration \(via nmap\)

SSH enumeration \(account guessing via Hydra\)

SNMP enumeration \(via nmap and onesixtyone\)

SMTP enumeration \(via nmap and custom account guessing scripts\)

SMB enumeration \(via samrdump\)

FTP enumeration \(via nmap and hydra\)



