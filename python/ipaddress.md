## Usage
### Get network address, CIDR notation
```
>>> net = ipaddress.ip_network('192.178.2.55/255.255.255.0', strict=False)
>>> net
IPv4Network('192.178.2.0/24')
>>> net.network_address
IPv4Address('192.178.2.0')
>>> net.netmask
IPv4Address('255.255.255.0')
```

or 

```
>>> iface = ipaddress.ip_interface('192.178.2.55/255.255.255.0')
>>> iface
IPv4Interface('192.178.2.55/24')
>>> iface.network
IPv4Network('192.178.2.0/24')
>>> iface.netmask
IPv4Address('255.255.255.0')
>>> iface.ip
IPv4Address('192.178.2.55')
>>> iface.network.network_address
IPv4Address('192.178.2.0')
```
