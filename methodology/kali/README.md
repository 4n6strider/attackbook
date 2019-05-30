# Kali Linux

* [ ] Change the root password
* [ ] Set unique background color
* [ ] Update packages and distribution if needed

### Update 

```bash
apt-get update && apt-get dist-upgrade -y
```

### Install Additional Packages

```bash
#seclists
apt-get install seclists -y

#gufw firewall manager gui
apt-get install gufw -y

#python-smb - needed for some exploits
apt-get install python-smb -y

#mingw-w64 - needed for cross-compiling
apt-get install mingw-w64 -y

# wine
dpkg --add-architecture i386 && apt-get update && apt-get install wine32 -y

```

## Setup Aliases

### ls

```text
echo "alias ll='ls -lvhAF --file-type --group-directories-first'" >> ~/.bash_aliases
echo "alias lr='ll -R'" >> ~/.bash_aliases
echo "alias ld='ll -tr'" >> ~/.bash_aliases
echo "alias lc='ll -tcr'" >> ~/.bash_aliases

source ~/.bash_aliases
```

## Scripts Directory

Create a user scripts directory in the PATH

```text
mkdir -p ~/bin
export PATH=$PATH:~/bin     #put this in .bashrc
```

## Tools

### Nikto

```bash
#change the user agent to be more stealthy
gedit /etc/nikto.conf

#comment out the current USERAGENT and add
USERAGENT=Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/74.0.3729.131 Safari/537.36
```

### Metasploit

```bash
#start and enable persistent postgresql service
systemctl start postgresql && systemctl enable postgresql

#setup the db
msfdb init 

#update 
msfupdate

#start the console and check db
msfconsole
> db_status
> db_rebuild_cache

```

### Searchsploit

```bash
searchsploit -u
```





