# vncservice
Service file to start TightVNC or TigerVNC as a service

Raspberry Pi service to turn on avahi-daemon if /boot/avahi is present.  



#### To install the service:  

*sudo cp vncserver@.service /lib/systemd/system/*  
*systemctl enable vncserver@1.service && systemctl start vncserver@1.service*

#### Important Notice:

The VNC server restricts connections from the localhost only for security reasons. To connect to the vnc server over the network use an ssh tunnel:
Assuming your vnc server runs on 192.168.137.137, type this on your remote client:

ssh -L 5902:localhost:5901 root@192.168.137.137
vncviewer 127.0.0.1::5902

Since you are ssh'ing into your remote machine, you might as well just type "vncserver" and be done instead of unning it as a service.
