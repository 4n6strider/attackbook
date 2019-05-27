# Networking

### Subnetting

Classful

```text
Class A IP Address Range    0.0.0.0 – 127.255.255.255
Class B IP Address Range    128.0.0.0 – 191.255.255.255
Class C IP Address Range    192.0.0.0 – 223.255.255.255
Class D IP Address Range    224.0.0.0 – 239.255.255.255
Class E IP Address Range    240.0.0.0 – 255.255.255.255
```

Private

```text
Class A Private Address Range    10.0.0.0 – 10.255.255.255
Class B Private Address Range    172.16.0.0 – 172.31.255.255
Class C Private Address Range    192.168.0.0 – 192.168.255.255
127.0.0.0 – 127.255.255.255
```

CIDR

```text
CIDR    Decimal Mask    Number of Hosts
/31    255.255.255.254    1 Host
/30    255.255.255.252    2 Hosts
/29    255.255.255.249    6 Hosts
/28    255.255.255.240    14 Hosts
/27    255.255.255.224    30 Hosts
/26    255.255.255.192    62 Hosts
/25    255.255.255.128    126 Hosts
/24    255.255.255.0    254 Hosts
/23    255.255.254.0    512 Host
/22    255.255.252.0    1022 Hosts
/21    255.255.248.0    2046 Hosts
/20    255.255.240.0    4094 Hosts
/19    255.255.224.0    8190 Hosts
/18    255.255.192.0    16382 Hosts
/17    255.255.128.0    32766 Hosts
/16    255.255.0.0    65534 Hosts
/15    255.254.0.0    131070 Hosts
/14    255.252.0.0    262142 Hosts
/13    255.248.0.0    524286 Hosts
/12    255.240.0.0    1048674 Hosts
/11    255.224.0.0    2097150 Hosts
/10    255.192.0.0    4194302 Hosts
/9    255.128.0.0    8388606 Hosts
/8    255.0.0.0    16777214 Hosts
```

### Cisco Commands

```text
enable    Enters enable mode
conf t    Short for, configure terminal
(config)# interface fa0/0    Configure FastEthernet 0/0
(config-if)# ip addr 0.0.0.0 255.255.255.255    Add ip to fa0/0
(config-if)# ip addr 0.0.0.0 255.255.255.255    Add ip to fa0/0
(config-if)# line vty 0 4    Configure vty line
(config-line)# login    Cisco set telnet password
(config-line)# password YOUR-PASSWORD    Set telnet password
# show running-config    Show running config loaded in memory
# show startup-config    Show sartup config
# show version    show cisco IOS version
# show session    display open sessions
# show ip interface    Show network interfaces
# show interface e0    Show detailed interface info
# show ip route    Show routes
# show access-lists    Show access lists
# dir file systems    Show available files
# dir all-filesystems    File information
# dir /all    SHow deleted files
# terminal length 0    No limit on terminal output
# copy running-config tftp    Copys running config to tftp server
# copy running-config startup-config    Copy startup-config to running-config
```

