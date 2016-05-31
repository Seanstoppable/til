Change Default NAT
======

On OSX, VirtualBox uses 10.0.1.0/24 as the default NAT.

In some cases, this might overlap withan existing internal network, preventing images from routing traffic appropriately.

In order to change, use the following:

```bash
/Applications/VirtualBox.app/Contents/MacOS/VBoxManage modifyvm default --natnet1 "172.23.24/24"
```
