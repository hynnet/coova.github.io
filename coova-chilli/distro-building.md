---
layout: page
title: CoovaChilli distrobution building
permalink: /CoovaChilli/DistroBuilding/
---

Building [CoovaChilli](/CoovaChilli) Binaries
=============================================

RPM (Redhat/Fedora)
-------------------

    wget https://coova.github.io/coova-chilli/coova-chilli-1.1.X.tar.gz
    cp coova-chilli-1.1.X.tar.gz /usr/src/redhat/SOURCES/
    tar xzf coova-chilli-1.1.X.tar.gz
    cd coova-chilli-1.1.X/
    rpmbuild -ba coova-chilli.spec

DEB (Debian/Ubuntu)
-------------------

    wget https://coova.github.io/coova-chilli/coova-chilli-1.1.X.tar.gz
    tar xzf coova-chilli-1.1.X.tar.gz
    cd coova-chilli-1.1.X/
    debuild -b
    
Gentoo Linux
------------

The ebuild is available on Sunrise overlay so install this overlay first (if you don't have it yet):
(This needs updating for Git).

    # Install layman to manage gentoo overlays
    sudo USE="subversion" emerge -a layman
    # Install sunrise overlay
    sudo layman -f -a sunrise
    sudo echo "source /var/lib/layman/make.conf" >> /etc/make.conf
    # To keep the overlay up to date run
    sudo layman -s overlay

Now you can install the CoovaChilli package by running emerge:

    sudo emerge -a coova-chilli
    
To start chilli:

    sudo /etc/init.d/chilli
    
PKG (FreeBSD)
-------------

Make sure your ports tree is up to date, quickest way is to use the portsnap utility, see:
http://www.freebsd.org/doc/en_US.ISO8859-1/books/handbook/updating-upgrading-portsnap.html

Once you're up to date

    cd /usr/ports/net-mgmt/coovachilli
    make package

