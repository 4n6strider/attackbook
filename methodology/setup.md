# Setup

## Install Vagrant

{% embed url="https://www.vagrantup.com/" %}

## Kali Box

```text
#Add the Kali vagrant box
vagrant box add "offensive-security/kali-linux"
```

## Kali Vagrant File

Create a vagrant file in a directory and customize it

```text
# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  #box
  config.vm.box = "offensive-security/kali-linux"
  config.vm.box_check_update = false

  #custom name
  config.vm.hostname = "kaliva"

  #networking
  #config.vm.network "private_network", ip: "172.16.16.16"
  #config.vm.network "public_network", type: "dhcp", bridge: "Intel(R) Dual Band Wireless-AC 7265"
  #config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"

  #shared folder
  config.vm.synced_folder "/shared", "/root/shared", create: true, owner: "root", group: "root", automount: true
 
  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.name = "kaliva"
    vb.memory = "8192"
    vb.cpus = "4"
    #v.customize ["modifyvm", :id, "--cpuexecutioncap", "50"]
  end

  config.vm.provision "shell", inline: $script_packages
  config.vm.provision "shell", inline: $script_aliases
  config.vm.provision "shell", inline: $script_tools
  config.vm.provision "shell", inline: $script_swap
  config.vm.provision "shell", inline: $script_network

end

$script_packages = <<-SCRIPT
  apt-get update 
  DEBIAN_FRONTEND=noninteractive apt-get -y -o Dpkg::Options::="--force-confdef" -o Dpkg::Options::="--force-confold" dist-upgrade
  apt-get install seclists -y
  apt-get install ftp -y
  apt-get install python-smb -y
  apt-get install mingw-w64 -y
  dpkg --add-architecture i386 && apt-get update && apt-get install wine32 -y
SCRIPT

$script_aliases = <<-SCRIPT
  echo "alias ll='ls -lvhAF --file-type --group-directories-first'" >> ~/.bash_aliases
  echo "alias lr='ll -R'" >> ~/.bash_aliases
  echo "alias ld='ll -tr'" >> ~/.bash_aliases
  echo "alias lc='ll -tcr'" >> ~/.bash_aliases
  source ~/.bash_aliases
SCRIPT

$script_tools = <<-SCRIPT
  systemctl start postgresql
  systemctl enable postgresql
  msfdb init 
  searchsploit -u
  gunzip /usr/share/wordlists/rockyou.txt.gz
SCRIPT

$script_swap = <<-SCRIPT
  echo "Creating 6GB swap space in /swapfile..."
  fallocate -l 6G /swapfile
  chown root:root /swapfile
  chmod 0600 /swapfile
  mkswap /swapfile
  swapon /swapfile
  cp /etc/fstab /etc/fstab.bak
  echo '/swapfile none swap sw 0 0' | tee -a /etc/fstab
SCRIPT

$script_network = <<-SCRIPT
  echo "supersede domain-name-servers 1.1.1.1, 1.0.0.1;" >> /etc/dhcp/dhclient.conf
SCRIPT
```

## Vagrant Commands

```text
vagrant up      #start vm
vagrant ssh     #connect
vagrant status
vagrant halt     #graceful stop
vagrant suspend
vagrant resume
vagrant restart #same as halt + resume
vagrant destroy
```

Linux Config

```bash
#change root password
su  -
passwd

#tmux

#ufw
ufw disable

#set variables
lhost=
rhost=
rhosts=
lport=

#change the user agent to be more stealthy
gedit /etc/nikto.conf

#comment out the current USERAGENT and add
USERAGENT=Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/74.0.3729.131 Safari/537.36
```

