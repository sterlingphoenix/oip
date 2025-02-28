OIP - NOW WITH UBUNTU 24.04 SUPPORT!
---

OrganicIP (OIP) visualizer uses libpcap and Simple DirectMedia Layer (SDL) to visualize IP traffic between endpoints.

Supported Distributions
-----------------------

Any linux distribution with the necessary [dependencies](#dependencies) is supported with [installation instructions](#installation-from-source). Pre-built packages are available for the following operating systems are _theoretically_ supported. The pre-fork version supported debian sid and bullseye, and Ubuntu 18.04, 20.04, and 21.10. 

This version has been tested on Ubuntu 24.04. 

Colors
------

On packet-balls:
 - Red for UDP
 - Green for TCP
 - White/blue for any other IP protocol

On hosts:
 - defined by oip.conf (ABGR, with A ignored)

Running
-------

Steps to run the server/client for a live capture

 - create /etc/oip.conf and, at a minimum, set a secret
 - start the server: `oipd <interface>`
 - start the client: `oip [-f <pcap_filter>] -s <server>`

The client also supports reading from a pcap file

 - `oip -c <pcap_file>`, can use `-e <number>` to change speed (1000 is default, number of ms per 1 second in the pcap)

Controls
--------

On the gui, you can use the mouse and the keyboard.

Mouse controls:

 - left click on host to reposition
 - right click on host to bring up context menu
 - add actions to context menu in oip.conf on client

Keyboard keys:

 - ! to open the menu
 - , to start displaying the capture (Load button)
 - p to pause and play the capture
 - <ESC> to disconnect

Dependencies
------------

The following are the dependent packages needed for OIP to compile: 

 ```
 apt-get install build-essential git libcrypto++-dev libsdl-image1.2-dev libpcap-dev libsdl1.2-dev libfreetype6-dev g++ make libfontconfig1-dev autoconf
 ```

Installation from Source
------------------------

To compile OIP from source execute the following commands:
```
git clone https://github.com/sterlingphoenix/oip.git
cd oip
./autogen.sh
./configure
make
make install
```

If you have any dependency missing that is not mentioned above, you'll have to track it down and install it.

Authors
-------

- Rian Shelley (Utah State University)
- Maintained by Eldon Koyle (Utah State University)
- Additional features added by Sebastian Garcia (eldraco@gmail.com) and Vojtech Uhlir (wojtyla@agents.felk.cvut.cz) (Czech Technical University)
- This fork by sterlingphoenix was made to add Ubuntu 24.04 support. 
