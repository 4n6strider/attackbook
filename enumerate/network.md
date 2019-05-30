---
description: Network flyover and host discovery
---

# Network

## Netdiscover

Good for local subnets, uses ARP

```bash
netdiscover -r 10.10.10.0/24
```

## Masscan

Good for large subnets or the whole internet, but be careful - very powerful

```bash
#similar syntax as nmap
masscan -p80,8000-8100 10.0.0.0/8

#banner grabbing

```

## Nmap

Versatile scanner with many options: 

{% embed url="https://explainshell.com/explain?cmd=nmap" %}

```bash
#ping scan - fast
nmap -v -sP --open -oA flyover_ping $range

#syn scan - fast
nmap -v -sS -T4 -Pn -n --top-ports 100 --open -oA flyover_syn $range

#udp scan - slow
nmap -v -sU -T4 -Pn -n --top-ports 100 --open -oA flyover_udp $range

#tcp syn scan, more ports, os and service detection - slow
nmap -v -sS -sV --version-all -O -Pn -n -oA flyover_detect --top-ports 1000 -T4 --open $range

#--version-intensity 8

# resume a scan
nmap -v -sS -T4 -Pn -n --top-ports 100 --open -oA flyover_syn $range
--resume $nmap_file

#grep
grep Up flyover_ping.gnmap | cut -d" " -f2 > hosts.txt

#make a directory for each host
for host in $(cat hosts.txt); do mkdir $host; done

#determine if host is behind a firewall
nmap -sA $ip
nmap -PN $ip

#Decoys
nmap -n -D$d1,$d2,$d3 $ip

#Set source port
nmap -g $source_port ...

```



