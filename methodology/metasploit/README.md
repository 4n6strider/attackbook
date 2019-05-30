# Metasploit

Workspaces

```text
> workspaces
> workspaces -a newspace

```

Port Scanning

```text
#scan with nmap or import results from -oA
>db_nmap
>db_import

#msf scans
> use auxiliary/scanner/
> use auxiliary/scanner/portscan/syn
> use auxiliary/scanner/portscan/tcp

>show options
>set RHOSTS, THREADS, PORTS
```

Hosts

```text
> hosts
> hosts -R # set RHOSTS


```

Services

```text
> services
```

Search

```text
> search name:something type:exploit platform:windows
-app
-author
-bid 
-cve
-edb
-name
-platform
-ref
-type

```

Sessions

```text
#list
> sessions -l

> sessions -i 1

```



