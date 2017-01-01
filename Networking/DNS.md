# Hostname
A label assigned to a device connected to a computer network, nicknames for IP addresses.
- on the internet, hostnames have a DNS domain appended to them

# Domain Name System
decentralized naming system for computers and services connected to the internet
- translates domain names to the numerical IP addresses need for the purpose of locating and identifying services and devices
### DNS Zone
Any distinct contiguous portion of the domain name space in the Domain Name System. 

The domain name space of the Internet is a hierarchy of subdomains below the DNS root domain. Individual domains serve as delagation points. It is desirable to implement fine grained boundaries of delegation, so sub-levels of a domain can be managed independently.

### Dyn
An Internet performance management company, offering products to monitor, control, and optimize online infrastructure. 

[source](https://en.wikipedia.org/wiki/Domain_Name_System)

### `resolv.conf`
File used in various operating systems to configure the system's DNS resolver
- resolving is the process of determining the IP address from a domain name
- a DNS resolver is responsible for initiating and sequencing queries that lead to the right resource (translation of domain name into IP address)
- an individual DNS query may be non-recursive, recursive, iterative, combinations of these
- when DHCP is used, it is usually updated with `resolvconf` utility
