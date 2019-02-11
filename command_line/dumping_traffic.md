# Dumping Traffic

If trying to figure out what network communication is going on a few things:

Completely raw capture:

`tcpdump -i eth0 -w traffic.eth0`

Which can be read with:

`tcpdump -r traffic.eth0`

Listing active connections:

`netstat -tulpn`


