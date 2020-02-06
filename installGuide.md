
#install gcc53-c++-5.3.0-1.el6.x86_64

Download https://drive.google.com/file/d/0B7S255p3kFXNbTBneHgwSzBodFE/view

dnf install ./gcc53-c++-5.3.0-1.el6.x86_64.rpm

# Then to install ns-allinone-2.35_gcc5

$ yum update

Download https://drive.google.com/file/d/0B7S255p3kFXNVVlxR0ZNRGVORjQ/view

$ tar xvf ns-allinone-2.35_gcc5.tar.gz

$ cd ns-allinone-2.35/

$ sudo export CC=gcc53 CXX=g++53 && ./install

$ cd ns-2.35/

$ sudo make install

$ cd ../nam-1.15/

$ sudo make install

$ reboot



# if using debian os's then

$ sudo apt-get update

$ sudo apt-get install ns2

$ sudo apt-get install nam

$ sudo apt-get install xgraph



# if xgraph dident install then

Package : xgraph-12.1-1.pclos2013.x86_64.rpm

$ sudo dnf install ./xgraph-12.1-1.pclos2013.x86_64.rpm

EDIT : Even the old "2013 build" is not completely stable. Animation.xg fails.
( A build with Fedora 27 will fail all xgraph plot files.)

We have another option :
An older 32bits build, xgraph-12.1-7pclos2011.i586.rpm

$ sudo dnf remove xgraph-12.1-1.pclos2013.x86_64

$ sudo dnf install ./xgraph-12.1-7pclos2011.i586.rpm

Test : $ cd xgraph-12.2/examples

$ xgraph Animation.xg



# if cannot install rpm file 

RPM packages are precompiled and built for Red Hat Based Linux Distribution and can be installed only using yum, 
Zypper and RPM based package managers.Since Kali Linux is based on Debian you can not install RPM packages directly 
using apt or dpkg package managers.

However, you can try a utility called Alien which can convert one package format into other but this doesn't mean 
every RPM will work since packages link to another packages for dependencies and this can cause troubles.

To install Alien and necessary package, run this command

$ sudo apt-get install alien dpkg-dev debhelper build-essential

To convert a package from RPM to debian format, use this command:

$ sudo alien packagename.rpm

To install the package:

$ sudo dpkg -i packagename.deb


