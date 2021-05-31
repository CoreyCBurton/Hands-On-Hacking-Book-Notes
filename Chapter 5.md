# Implications of Hacking DNS
- Companies rely on name servers to provide answers to queries such as the ip address of www.yourcompany.com
  - Distributed denial-of-service (DDOS) attacks are commmon against a DNS

 - You can send customers false details aboute sites and lead them to a false one with poisioning techniques

# A Brief History of DNS
- Standford Research Institute became the offical source file that contained the names of IP addreses conned to the ARPANET.
  - Now it is on the Domain Name System, a global decentralized database 

# The DNS Hierarchy
- It stores information to serve information when requested

- root name server stores .com,.net,and .org.
  - It does not give you IP but it does point you in the right direction

- The domain system is similar to a directory like ``/home/donnyg/Downloads``. 
  - A dot represents the roots level and further along the directories while moving foward.

# A Basic DNS Query
- When you type in a domain name like ``duckduckgo.com``, the OS will try to resolve the domain name which is the IP address. 
  - If there is no cached answer, it will be sent to the local network
  - It will then be sent to the DNS server which will then be sent to your ISP.

- The ISP has the cached answer; most likely someone has visted it before
  - If the ISP does not have it cached in a .com server, then it will ask one of the **Root Name Servers**

- check out on virtual box ftp://rs.internic.net/domain/named.root

- Your isp will quiery duckduckgo and get ``ns-175-awsdns-21.com``. The ip address is then sent to a final query and receives the IP address. 

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

# BIND9 
* To install **BIND9**, use the command ``sudo apt install bind9``. I have installed this onto my Ubuntu LTS server.

* the commands below are listed to show where the config file is 

```
cd /etc/bind # This is the directory path 
cat named.conf # to show what is in named.conf
```
* In ``named.conf`` it leads to another file which is ``named.conf.local`` 

# DNS Hacking Toolkit 
* The three main tools used in the book is NMAP, Metasploit, and Wireshark 

* Dig - A DNS querying tool

* [NSlookup](https://www.nslookup.io/) - An alternative DNS querying tool 

* [DNSrecon](https://tools.kali.org/information-gathering/dnsrecon) - A script for carrying out reconnaissance on a name server 

* [DNSenum](https://tools.kali.org/information-gathering/dnsenum) - A tool for enumerating infromation from a name server 

* [Fierce](https://tools.kali.org/information-gathering/fierce) - A name server server scanning tool, similar to Dnsrecon and DNSenum 

* Host - Another DNS querying tool

* [WHOIS](https://www.whois.net/) - The name of a protocol and tool for querying information

* DNSspoof - A tool for spoofing DNS packets

* Dsniff - A tool for sniffing DNS caches and packets 

* Hping3 - A tool for creatinng and injecting custom packets useful in many scenarios 

* [Scapy](https://scapy.readthedocs.io/en/latest/installation.html) - A packet injection tool 

* [Nmap](https://nmap.org/) - a port scanner for scanning any host and returning useful information

* [Searchsploit](https://www.exploit-db.com/searchsploit) - A tool for searching for known exploit scripts and information 

* [MSFconsole](https://www.offensive-security.com/metasploit-unleashed/msfconsole/) - Command line tool that is part of the populat metasploit penetration testing framework

* [Wireshark](https://www.wireshark.org/) - A tool for inspecting packets on your network 

# WHOIS 
* A protocol used for quering domain name and IP address information. This is apart of OSINT work 

* using command `` whois hacker.house `` information can be pulled up about the domain. 

* Guessing domains can be easy, engineers create common domain names to make life easier. 
















