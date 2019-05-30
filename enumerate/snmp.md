---
description: 'TCP/161, UDP/161'
---

# SNMP

## Enumerating with nmap

```bash
nmap -v -n -Pn -sT -sU -p U:161,T:161 --open --oA report_snmp $range
grep open report_snmp.gnmap | cut -d" " -f2 > hosts_snmp.txt
```

## Enumerating with NSE

```bash
nmap -v -n -Pn -p 161 --script=snmp-info $ip
```



apt-get install snmp-mibs-downloader download-mibs 

echo "" &gt; /etc/snmp/snmp.conf



/usr/share/metasploit-framework/data/wordlists/snmp\_default\_pass.txt

