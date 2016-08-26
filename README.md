# btpdsnap: snapcraft for btpd


I wanted to take snapd and snapcraft for a spin, so chose btpd, a text based BitTorrent client. 

Three apps are installed as part of this snap.

* btpdsnap.btpd
* btpdsnap.cli
* btpdsnap.info

To start the btpd daemon just issue `btdpsnap.btpd` and the daemon will be started in the background as your user.  Note: I was unable to use the 'daemon' capabilities of snappy because the daemon and CLI need to communicate over a local socket.  If started as a snappy daemon the socket will be created by `root`.   So, for now the btpd daemon will run as user.   

**NOTE:** Since snapd doesn't know that btpdsnap.btpd is a daemon, it doesn't know how to stop it, so you'll need to manage that manually.  Especially important when you need to update or remove the snap!  You can stop the daemon via `btdpsnap.cli kill`. 

