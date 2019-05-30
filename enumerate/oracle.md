---
description: TCP/1521
---

# Oracle

### nmap scripts

```bash
nmap -p 1521 --script oracle-sid-brute $ip

nmap -p 1521 --script oracle-brute --script-args oracle-brute.sid=$sid $ip
```

