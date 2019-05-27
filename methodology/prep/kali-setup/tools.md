# Tools

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





