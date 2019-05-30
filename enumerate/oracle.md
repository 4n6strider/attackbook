---
description: TCP/1521
---

# Oracle

## Enumerating with nmap

```bash
nmap -v -n -Pn -sT -p 1521 --open --oA report_oracle $range
grep open report_oracle.gnmap | cut -d" " -f2 > hosts_oracle.txt
```

## Enumeration with NSE

```bash
nmap -p 1521 --script oracle-sid-brute $ip
nmap -p 1521 --script oracle-brute --script-args oracle-brute.sid=$sid $ip
```

