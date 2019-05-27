# Network



```bash
#show active connections
netstat -lntp

#find a listening service
netstat -antp|grep [service]

#download a file
wget [url]

#show interfaces
ifconfig -a
ifconfig et0 up

#config
/etc/network/interfaces
/etc/resolve.config

# Manage up/down
ifup eth0
ifdown eth0

#routes
route
ip route
netstat -r
```

Network Manager

```bash
# Stop NetworkManager
sudo systemctl stop NetworkManager.service

# Start NetworkManager
sudo systemctl start NetworkManager.service

# Disable it so it won't start at boot
sudo systemctl disable NetworkManager

#Enable it so it will start at boot
sudo systemctl disable NetworkManager
```

