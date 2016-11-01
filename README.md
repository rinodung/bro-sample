#Overview
BBro is a powerful system that on top of the functionality it provides out of the box, also offers the flexibility to customize analysis pretty much arbitrarily. 
We provide a range of documentation material ranging from introductory material to get you started, to full references of Bro’s various frameworks.
#Installation
1. Install the required dependencies
`sudo apt-get install cmake make gcc g++ flex bison libpcap-dev libssl-dev python-dev swig zlib1g-dev`
2. Install Bro From Git
`git clone --recursive git://git.bro.org/bro`
```
sudo ./configure
sudo make
sudo make install
```


OR From Package
```
sudo sh -c "echo 'deb http://download.opensuse.org/repositories/network:/bro/xUbuntu_14.04/ /' >> /etc/apt/sources.list.d/bro.list"
sudo apt-get update
sudo apt-get install bro
```
https://www.bro.org/sphinx/install/install.html

# Configure the Run-Time Environment
export PATH=/usr/local/bro/bin:$PATH

# Managing Bro with BroControl
Default: $PREFIX /usr/local/bro

1. $PREFIX/etc/node.cfg, set the right interface to monitor.
2. $PREFIX/etc/networks.cfg, comment out the default settings and add the networks that Bro will consider local to the monitored environment.
3. $PREFIX/etc/broctl.cfg, change the MailTo email address to a desired recipient and the LogRotationInterval to a desired log archival frequency.

Now start the BroControl shell like: 
`sudo broctl`

Since this is the first-time use of the shell, perform an initial installation of the BroControl configuration:
`[BroControl] > install`

Then start up a Bro instance:
`[BroControl] > start`
Stop Bro
`[BroControl] > stop`