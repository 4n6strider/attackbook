# Permissions

* 4: read permission 
* 2: write permission 
* 1: execute permission

```bash
#change owner, group and user permissions
chmod 755 myfile
chmod u+x myfile

#change user and group ownership 
chown user:group myfile

# suid / sgid
chmod u+s myfile
chmod g+s myfile

#sticky bit
chmod +t mydir
```

