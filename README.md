Cisco VPN Client Patches
========================

Linux Patches for Unsuported Cisco VPN Client (32bit)

Kernel 3.2.x is not supported! Kernel 3.1.x is last supported kernel.

Usage
-----

Download and unpack vpnclient-linux-x86_64-4.8.02.0030-k9.tar.gz (Linux 32-bit and x86_64 (biarch))

    wget http://projects.tuxx-home.at/ciscovpn/clients/linux/4.8.02/vpnclient-linux-x86_64-4.8.02.0030-k9.tar.gz
    tar xzvf vpnclient-linux-x86_64-4.8.02.0030-k9.tar.gz 

Apply patch vpnclient-linux-2.6.31-final.diff

    wget https://github.com/ruphert/CiscoVpnClient-Patches/raw/master/vpnclient-linux-2.6.31-final.diff
    patch -d vpnclient/ < vpnclient-linux-2.6.31-final.diff

Apply patch kernel-3.x-support.diff

    wget https://github.com/ruphert/CiscoVpnClient-Patches/raw/master/kernel-3.x-support.diff
    patch -d vpnclient/ < kernel-3.x-support.diff 

Kernel source fix

    sudo sed -i 's/const\ struct\ net_device_ops\ \*netdev_ops;/struct\ net_device_ops\ \*netdev_ops;/' `find /usr/src -name netdevice.h`

Usability
---------

This patch was tested on Fedora 16 (Verne) with PAE kernel (3.1.8-2.fc16.i686.PAE).

Credits
-------

* http://forum.tuxx-home.at/viewforum.php?f=15&sid=379c517ec0a051e76623cc901f3c4db4
* http://www.lamnk.com/blog/vpn/how-to-install-cisco-vpn-client-on-ubuntu-jaunty-jackalope-and-karmic-koala-64-bit/

Release Notes
------
http://www.cisco.com/en/US/docs/security/vpn_client/cisco_vpn_client/vpn_client48/release/notes/48client.html
http://www.fi.upm.es/ccfi/vpn/cliente/vpnclient-linux-4.8.02.0030-readme.txt
