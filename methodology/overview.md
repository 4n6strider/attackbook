# Overview

This is my opinionated configuration for penetration testing using my Windows 10 laptop.

* Windows 10 Pro with virtualization enabled in the BIOS
* Oracle Virtual Box 
* Visual Studio Code
* Cmdr
* Vagrant

With these tools I can spawn headless Kali virtual machines that allow me to:

* Run multiple, parallel scans for recon and enumeration, compile and host exploits using Kali tools
* Store resulting logs and screenshots in shared folders so that I can view and edit them from Windows
* Throw everything away, trash the VM and be able to start clean with minimal effort and time

Why I like this approach:

* Kali tools work best when running as root, but this can expose your VM to threats.  Using this method you can easily throw away your VM and start clean with the latest Kali updates without losing any data or having to spend a lot of time customizing your Kali environment
* Data is centralized and stored so that you can resume quickly in case of unexpected failures
* Can use a consistent tool set, for example VS Code on Windows for editing scripts and log data
* Can port VM config to other platforms like cloud providers and run scans from different source networks









