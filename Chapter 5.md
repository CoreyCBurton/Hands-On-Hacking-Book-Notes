# The Domain Name System 
# Implications of Hacking DNS
* Companies rely on name servers to provide answers to queries such as the ip address of www.yourcompany.com

* Distributed denial-of-service (DDOS) attacks 

* You can send customers false details aboute sites and lead them to a false one

# A Brief History of DNS
* Standford Research Institute became the offical source file that contained the names of IP addreses conned to the ARPANET. Now it is on the Domain Name System, a global decentralized database 

# The DNS Hierarchy
* It stores information to serve information when requested

* root name server store .com,.net,and .org. It does not give you IP but it does point you in the right direction

* The domain system is similar to a directory like ``/home/donnyg/Downloads``. A dot represents the roots level and further along the directories while moving foward.

# A BAsic DNS Query
* When you type in a domain name like ``duckduckgo.com``, the OS will try to resolve the domain name which is the IP address. If there is no cached answer, it will be sent to the local network

* It will then be sent to the DNS server which will then be sent to your ISP.

* ISP has the cached answer; most likely someone has visted it before

* If the ISP does not have it cached in a .com server, then it will ask one of the **Root Name Servers**

* check out ftp://rs.internic.net/domain/named.root

* Your isp will quiery duckduckgo and get ``ns-175-awsdns-21.com``. The ip address is then sent to a final query and receives the IP address. 

# Authority and Zones
* the Start of Authority (SOA) for ``duckduckgo.com`` is responsible for domains only within ``duckduckgo.com``

* IF one server goes offline, the next one handles the request.

# DNS Resource Records
* DNS is a decentrailzed database which is one of its strengths.

- **Address of Host (A)** - THe IP address of the host for instance 123.45.67.89. This is the information taht you/re requesting when you send a query containing the hostname

- **Address of Host (AAAA)** - This is an IPv6 address rather than an IPv4

- **Canonical Name (CNAME)** - A company might have two domains that point to the same place.

- **Mail Exchanger (MX)** - This refers to a mail server, and it could be either a hostname or an IP address.

- **Name Server (NS)** - contains name server information for a zone

- **Start of Authority(SOA)** - The record is bigger thanothers, it can be found at the beginning of every zone file. 

- **Pointer (PTR)** Pointer records are used to reverse lookups in DNS. You can find the hostname by supplying the an IP address

- **Text(TXT)** - A simple text record, adds extra functions to DNS and stores information. Human readable notes  

















