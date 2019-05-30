---
description: 'TCP/53, UDP/53'
---

# DNS

Discovery with netcat

```bash
for i in {1..254}; do nc -v -n -z -w 1 10.10.10.$i 53; done   
```

Discovery with nmap

```bash
#find name servers with nmap and store results in a file
nmap -p 53 $range -oA dns_sweep && grep open dns-sweep.gnmap |cut -d" " -f2 > nameservers.txt

```

Name server scan with nmap

```bash
nmap -v -sT -sV -O -Pn --top-ports 1000  -iL nameservers.txt
```

Enumerate DNS

```bash
dnsenum $domain --dnsserver $ip
host -t ns $domain $ip
host -t mx $domain $ip
host -l $domain $ip   #zone transfer
dnsrecon -d $domain -n $server -a -c [path].csv
dnsrecon -r $range -n $server -t rvl -c [path].csv
```

Windows

```text
nslookup 
> set type=any 
> ls -d $domain
```





