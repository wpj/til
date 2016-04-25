loopback / localhost
====================

[Reference](http://askubuntu.com/questions/247625/what-is-the-loopback-device-and-how-do-i-use-it)

The loopback interface is a virtual network interface that a computer can use to communicate with itself.

### Addresses on loopback

For IPv4, the loopback interface is assigned all the IPs in the 127.0.0.0/8 address block (127.0.0.1 - 127.255.255.254). In other words, your computer can be accessed via any IP in that range. For most purposes, you only ever need to refer to 127.0.0.1. Usually, this IP is mapped to the `localhost` hostname (in /etc/hosts)

As with other network adapters, the loopback interface shows up in the output of `ifconfig` under the name `lo`.
