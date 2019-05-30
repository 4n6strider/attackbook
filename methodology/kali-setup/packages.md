# Packages

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

