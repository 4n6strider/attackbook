# Windows List

### History

```text
wevtutil el  (list logs)
wevtutil cl <LogName> (Clear specific lowbadming)
del %WINDIR%\*.log /a /s /q /f
```

### Files

```text
%SYSTEMDRIVE%\boot.ini
%WINDIR%\win.ini
%SYSTEMROOT%\repair\SAM
%SYSTEMROOT%\System32\config\RegBack\SAM
%SYSTEMROOT%\repair\system
%SYSTEMROOT%\System32\config\RegBack\system
%SYSTEMDRIVE%\autoexec.bat
%SYSTEMDRIVE%\pagefile.sys
%WINDIR%\debug\NetSetup.log
%WINDIR%\repair\sam
%WINDIR%\repair\system
%WINDIR%\repair\software
%WINDIR%\repair\security
%WINDIR%\iis6.log (5, 6 or 7)
%WINDIR%\system32\logfiles\httperr\httperr1.log
%SystemDrive%\inetpub\logs\LogFiles 
%WINDIR%\system32\logfiles\w3svc1\exYYMMDD.log (year month day)
%WINDIR%\system32\config\AppEvent.Evt
%WINDIR%\system32\config\SecEvent.Evt
%WINDIR%\system32\config\default.sav
%WINDIR%\system32\config\security.sav
%WINDIR%\system32\config\software.sav
%WINDIR%\system32\config\system.sav
%WINDIR%\system32\CCM\logs\*.log
%USERPROFILE%\ntuser.dat
%USERPROFILE%\LocalS~1\Tempor~1\Content.IE5\index.dat
%WINDIR%\System32\drivers\etc\hosts
unattend.txt, unattend.xml, sysprep.inf
```

### Commands - System Info

```text
whoami
whoami /all
set
fsutil fsinfo drives
```

### Commands - Networking

```text
ipconfig /all
ipconfig /displaydns
netstat -nabo
netstat -r
netstat -na | findstr :445
netstat -nao | findstr LISTENING
netstat -anob | findstr “services, process or port”
netsh diag show all
net view
net view /domain
net view /domain:otherdomain
net user %USERNAME% /domain
net user /domain
net accounts
net accounts /domain
net localgroup administrators
net localgroup administrators /domain
net group “Domain Admins” /domain
net group “Enterprise Admins” /domain
net group “Domain Controllers” /domain
net share
net session | find / “\\”
arp -a
route print
browstat (Not working on XP)
netsh wlan show profiles
netsh wlan export profile folder=. key=clear
netsh wlan [start|stop] hostednetwork
netsh wlan set hostednetwork ssid=<ssid> key=<passphrase> keyUsage=persistent|temporary
netsh wlan set hostednetwork mode=[allow|disallow]
wmic ntdomain list
```

### Commands - Configs

```text
gpresult /z
sc qc <servicename>
sc query
sc queryex
type %WINDIR%\System32\drivers\etc\hosts
echo %COMSPEC%
c:\windows\system32\gathernetworkinfo.vbs
```

### Commands - Finding Files

```text
tree C:\ /f /a > C:\output_of_tree.txt
dir /a
dir /b /s [Directory or Filename]
dir \ /s /b | find /I “searchstring”
```

### Commands - Remote Access

```text
net share \\computername
tasklist /V /S computername
qwinsta /SERVER:computername
qprocess /SERVER:computername *
net use \\computername
net use \\computername /user:DOMAIN\username password
reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Terminal Server" /v fDenyTSConnections /t REG_DWORD /d 0 /f
reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Terminal Server" /v fAllowToGetHelp /t REG_DWORD /d 1 /f
```

### Commands - Autostart

```text
#Windows NT 6.1, 6.0
%SystemDrive%\ProgramData\Microsoft\Windows\Start Menu\Programs\Startup\

#Windows NT 5.2, 5.1, 5,0
%SystemDrive%\Documents And Settings\All Users\Start Menu\Programs\StartUp\

#Windows 9x
%SystemDrive%\wmiOWS\Start Menu\Programs\StartUp\

#Windows NT 4.0, 3.51, 3.50
%SystemDrive%\WINNT\Profiles\All Users\Start Menu\Programs\StartUp\
```

### Commands - wmic

```text
wmic bios
wmic qfe qfe get hotfixid
  (This gets patches IDs)
wmic startupwmic service
wmic process get caption,executablepath,commandline
wmic process call create “process_name” (executes a program)
wmic process where name=”process_name” call terminate (terminates program)
wmic logicaldisk where drivetype=3 get name, freespace, systemname, filesystem, size, volumeserialnumber (hard drive information)
wmic useraccount (usernames, sid, and various security related goodies)
wmic useraccount get /ALL
wmic share get /ALL (you can use ? for gets help ! )
wmic startup list full (this can be a huge list!!!)
wmic /node:"hostname" bios get serialnumber (this can be great for finding warranty info about target)

wmic product get name /value (this gets software names)
wmic product where name="XXX" call uninstall /nointeractive (this uninstalls software)
```

### Commands - reg

```text
reg save HKLM\Security security.hive  (Save security hive to a file)
reg save HKLM\System system.hive (Save system hive to a file)
reg save HKLM\SAM sam.hive (Save sam to a file)=
reg add [\\TargetIPaddr\] [RegDomain][ \Key ] 
reg export [RegDomain]\[Key] [FileName] 
reg import [FileName ]
reg query [\\TargetIPaddr\] [RegDomain]\[ Key ] /v [Valuename!] (you can to add /s for recurse all values )
```

