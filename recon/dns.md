---
description: Public DNS Recon
---

# DNS

### dnsrecon

```bash
#gather info
dnsrecon.py -d [domain]

#zone transfer
dnsrecon.py -d [domain] -t axfr

#zone walk
dnsrecon.py -d [host] -t zonewalk

#reverse lookup
dnsrecon.py -r 10.0.0.1-10.0.0.254

#brute
dnsrecon.py -d [domain] -D [list] -t brt
```

### recon-ng

```bash
recon-ng> help
recon-ng> modules
> load contacts_linkedin
> options
> set [option]
> run

> set SOURCE [domain]
> show modules
> use recon/domains-hosts/bing_domain_web 
> use recon/domains-hosts/brute_hosts 
> use recon/domains-hosts/google_site_web 
> use recon/domains-hosts/netcraft 
> run
```

### Brute with nmap

```bash
nmap -p 80 --script dns-brute [website]
```

### Reverse with nmap

```bash
nmap -p 80 --script http-reverse-ip [website]
```

