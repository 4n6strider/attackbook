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

## Mibs

```bash
apt-get install snmp-mibs-downloader download-mibs 
echo "" > /etc/snmp/snmp.conf
```

## Wordlists

```bash
/usr/share/metasploit-framework/data/wordlists/snmp_default_pass.txt
```

## Enumeration Tools

```bash
onesixtyone -c public -i $ip

snmpcheck -t $ip -c public

snmpwalk -c public -v1 $ip 1| grep hrSWRunName|cut -d* * -f 

snmpenum -t $ip
```







