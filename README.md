Cisco VPN Client Patches
========================

Linux Patches for Unsuported Cisco VPN Client (32bit)

Usage
-----

Download and unpack vpnclient-linux-x86_64-4.8.02.0030-k9.tar.gz

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

Credits
-------

* http://forum.tuxx-home.at/viewforum.php?f=15&sid=379c517ec0a051e76623cc901f3c4db4
* http://www.lamnk.com/blog/vpn/how-to-install-cisco-vpn-client-on-ubuntu-jaunty-jackalope-and-karmic-koala-64-bit/
