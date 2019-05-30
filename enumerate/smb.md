# SMB

## Enumerating with nmap

* TCP and UDP scan that saves to report files 

```bash
nmap -v -n -Pn -sT -sU -p U:137-139,T:137-139,T:445 --oA report_smb $range
grep open report_smb.gnmap | cut -d" " -f2 > hosts_smb.txt
```

## Enumerating with NSE

* Enumerate shares

```bash
nmap -p 139,445 -v --script smb-enum-shares.nse --script-args=unsafe=1 -oA report_smb_shares -iL hosts_smb.txt
```

* Identify OS

```bash
nmap -sU -sT --script smb-os-discovery.nse --script-args=unsafe=1 -p U:137-139,T:137-139,T:445 -oA report_smb_os -iL hosts_smb.txt
```

* SAMBA CVE-2012-1182 Scan

```bash
nmap --script=samba-vuln-cve-2012-1182 --script-args=unsafe=1 -p 139 -oA report_samba_vuln -iL hosts_smb.txt
```

* SMB Brute Force

```bash
nmap -sU -sS --script smb-brute.nse --script-args=unsafe=1 -p U:137-139,T:137-139,T:445 -oA report_smb_brute -iL hosts_smb.txt

--script-args userdb=users.txt,passdb=passwords.txt $ip
```

* SMB Vuln Scripts

```bash
nmap -sU -sT --script smb-vuln-* -p U:137-139,T:137-139,T:445 --script-args=unsafe=1 -oA report_smb_vuln -iL hosts_smb.txt
```

## Enumerate names with nbtscan

```bash
nbtscan -v -s " " -h -f hosts_smb.txt
```

## Enumerate everything with enum4linux

```bash
enum4linux -a $ip

for ip in $(cat hosts_smb.txt);do enum4linux -a $ip >> report_smb_enum4l.txt;done

for ip in $(cat hosts_smb.txt);do enum4linux -a $ip > report_$ip_smb.txt & ;done
```

## Connect to Shares with smbclient

```bash
smbclient -L $ip
smbclient \\\\$ip\\$share
smb: \> h

smbclient -L $ip
smbclient //$ip/tmp
smbclient \\\\$ip\\ipc$ -U $user
smbclient //$ip/ipc$ -U $user
```

## SMB Ports

```text
137/tcp netbios-ns
138/tcp netbios-dgm
139/tcp netbios-ssn
445/tcp microsoft-ds
137/udp netbios-ns
138/udp netbios-dgm
139/udp netbios-ssn
```

## SMB Versions

```text
SMB 1.0 (DOS)
CIFS (Windows 95)
SMB 2.0 (Windows Vista, Windows Server 2008)
SMB 2.1 (Windows Server 2008 R2, Windows 7)
SMB 3.0 (Windows 8, Windows Server 2012)
SMB 3.02 (Windows 8.1, Windows Server 2012 R2)
SMB 3.1.1 (Windows 10, Windows Server 2016)
```

