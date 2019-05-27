# IP Tables



```bash
#list rules
iptables -L
iptables -L INPUT or OUTPUT or TCP

#Deny traffic to ports except for Local Loopback 
iptables -A INPUT -p tcp --destination-port [port] ! -d $ip -j DROP 

#Flush, delete, accept all
iptables -P INPUT ACCEPT
iptables -P FORWARD ACCEPT
iptables -P OUTPUT ACCEPT
iptables -t nat -F
iptables -t mangle -F
iptables -F
iptables -X
 
#monitor bandwidth
iptables -I INPUT 1 -s [destination-ip] -j ACCEPT 
iptables -I OUTPUT 1 -d [destination-ip] -j ACCEPT 
iptables -Z (zero the packet and byte counters) 
iptables -vn -L (view counters) 

#save and restore
iptables-save -c > iptables-backup.txt
iptables-restore -c < iptables-backup.txt
```

