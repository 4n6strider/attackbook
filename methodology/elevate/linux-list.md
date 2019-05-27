# Linux List

### History

Disable history to hide tracks

```bash
export HISTFILE=
unset HISTFILE
```

### Files

```bash
/etc/resolv.conf
/etc/motd
/etc/issue
/etc/passwd
/etc/shadow
/etc/group
/etc/gshadow
/home/xxx/.bash_history
/home/*/.ssh/id*
/home/*/.gnupg/secring.gpgs
/tmp/krb5cc_*, /tmp/krb5.keytab #kerberos tickets
```

### Commands - System Info

```bash
uname -a
ps aux
top -n 1 -d
id
arch, uname -m
w
who -a
gcc -v
mysql --version
perl -v
ruby -v
python --version
df -k
mount
last -a
lastcomm
lastlog
lastlogin (BSD)
getenforce
dmesg
lspci
lsusb
lscpu
lshw
ex
cat /proc/cpuinfo
cat /proc/meminfo
du -h --max-depth=1 /
which nmap
locate bin/nmap
locate bin/nc
jps -l
java -version
```

### Commands - Networking

```bash
hostname -f
ip addr show
ip ro show
ifconfig -a
route -n
cat /etc/network/interfaces
iptables -L -n -v
iptables -t nat -L -n -v
ip6tables -L -n -v
iptables-save
netstat -anop
netstat -r
netstat -nltupw (root with raw sockets)
arp -a
lsof -nPi
```

### Commands - Configs

```bash
ls -aRl /etc/ | awk '$1 ~ /w.$/' | grep -v lrwx 2>/dev/nullte    
cat /etc/issue{,.net}
cat /etc/master.passwd
cat /etc/group
cat /etc/hosts
cat /etc/crontab
cat /etc/sysctl.conf
for user in $(cut -f1 -d: /etc/passwd); do echo $user; crontab -u $user -l; done # (Lists all crons)
cat /etc/resolv.conf
cat /etc/syslog.conf
cat /etc/chttp.conf
cat /etc/lighttpd.conf
cat /etc/cups/cupsd.confcda
cat /etc/inetd.conf    
cat /opt/lampp/etc/httpd.conf
cat /etc/samba/smb.conf
cat /etc/openldap/ldap.conf
cat /etc/ldap/ldap.conf
cat /etc/exports
cat /etc/auto.master
cat /etc/auto_master
cat /etc/fstab
find /etc/sysconfig/ -type f -exec cat {} \;
```

### Commands - Packages

```bash
rpm -qa --last | head
yum list | grep installed

#sources
cat /etc/apt/sources.list
ls -l /etc/yum.repos.d/
cat /etc/yum.conf

#Debian
dpkg -l
dpkg -l | grep -i “linux-image”
dpkg --get-selections

#BSD
pkg_info

#Solaris
pkginfo

#Gentoo
cd /var/db/pkg/ && ls -d */*

#Arch Linux
pacman -Q
```

### Commands - Files

```bash
ls -dlR */ 
ls -alR | grep ^d
find /var -type d
ls -dl `find /var -type d`
ls -dl `find /var -type d` | grep -v root
find /var ! -user root -type d -ls
find /var/log -type f -exec ls -la {} \;
find / -perm -4000 (find all suid files)
ls -alhtr /mnt
ls -alhtr /media
ls -alhtr /tmp
ls -alhtr /home
cd /home/; treels /home/*/.ssh/*
find /home -type f -iname '.*history'
ls -lart /etc/rc.d/
locate tar | grep [.]tar$  # Remember to updatedb before running locate
locate tgz | grep [.]tgz$
locate sql | grep [.]sql$
locate settings | grep [.]php$  
locate config.inc | grep [.]php$
ls /home/*/id*
 .properties | grep [.]properties # java config files
locate .xml | grep [.]xml # java/.net config files
find /sbin /usr/sbin /opt /lib `echo $PATH | ‘sed s/:/ /g’` -perm /6000  -ls # find suids
locate rhosts
```

### Commands - User Info

```bash
ls -alh /home/*/    
ls -alh /home/*/.ssh/
cat /home/*/.ssh/authorized_keys
cat /home/*/.ssh/known_hosts
cat /home/*/.*hist* # you can learn a lot from this
find /home/*/.vnc /home/*/.subversion -type f 
grep ^ssh /home/*/.*hist*
grep ^telnet `/home/*/.*hist*
grep ^mysql /home/*/.*hist*
cat /home/*/.viminfo
sudo -l # if sudoers is not. readable, this sometimes works per user
crontab -l
cat /home/*/.mysql_history
```

### Commands - Escalation

```bash
ls -alh /root/
sudo -l
cat /etc/sudoers
cat /etc/shadow
cat /etc/master.passwd # OpenBSD
cat /var/spool/cron/crontabs/* | cat /var/spool/cron/*
lsof -nPi
ls /home/*/.ssh/*
```

