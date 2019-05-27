---
description: Public Email Recon
---

# Email

### Email with nmap

```bash
nmap -p 80 --script http-google-email,http-email-harvest [website]
```

### theharvester

```bash
# basics
theharvester -d [domain] -b [source]
theharvester –d [domain] –l 300 –b all –f log.txt

# Perform a DNS reverse query on all ranges discovered
theharvester -d [domain] -n

# Perform a DNS brute force for the domain name
theharvester -d [domain] -c

# use SHODAN database to query discovered hosts
theharvester -d [domain] -h
```

