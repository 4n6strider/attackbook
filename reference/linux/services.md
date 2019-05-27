# Services

Common commands for controlling services

```bash
systemctl start [service]
systemctl stop [service]  
systemctl enable [service] 

netstat -antp | grep [service] 

/etc/init.d/[service] start
/etc/init.d/[service] stop

nano /usr/sbin/update-rc.d (whitelist / blacklist) 
```

