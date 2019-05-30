---
description: Preparing virtual machines
---

# Machines

* [ ] Download virtual machine images / appliances
* [ ] Setup and configure virtual machines
* [ ] Fix resolution \(HiDPI\)
* [ ] Install Guest Extensions
* [ ] Snapshot virtual machines
* [ ] \[optional\] Backup test machine to OVA

{% tabs %}
{% tab title="Test Machine" %}
Kali is a Linux distribution tailored for penetration testing and comes with loads of curated tools already installed.

{% embed url="https://www.offensive-security.com/kali-linux-vm-vmware-virtualbox-image-download/" %}

{% embed url="https://www.kali.org/downloads/" %}
{% endtab %}

{% tab title="Secondary Machines" %}
If you expect to be analyzing exploits and customizing buffer overflows then setup Windows and Linux virtual machines for this.

{% embed url="https://developer.microsoft.com/en-us/microsoft-edge/tools/vms/" %}

{% embed url="https://www.osboxes.org/virtualbox-images/" %}

{% embed url="http://www.oldapps.com/" %}
{% endtab %}

{% tab title="Backup" %}
You may also want to have your primary test machine \(once fully configured and prepped\) exported as an OVA and stored on backup media, just in case.
{% endtab %}
{% endtabs %}



