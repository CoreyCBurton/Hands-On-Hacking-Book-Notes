# Open Source Intelligence Gathering
* Hackers look for domain names, hostnames, IP addresses, URLs, email addresses, and potential passwords

* Public information makes it easy for hackers to find certain knowledge 

* It is open source, it is free to obtain 

* **OSINT** assessment is important 

# Does Your Client Needs an OSINT Review?
* Only if the client asks for it 

* Some clients asks for an indepth to make sure their social media is clear among the board. 

* Using DuckDuckGO, Bing, or Google, you are not actually sending any data to the target company. It is querying a database 

* You cannot blindly trust information you find. 

# What are you looking for?
* To obtain information that will assist you in carrying out an attack in order to gain access to a computer system 

* Find hosts with a public facing IP 

* Lookout for a VPN portal, Mail servers, web servers, database servers, Linux machines, UNIX machines, Windows boxes, IoT devices. 

* Bulid up target IP addresses, hostnames. and domain names. 

* Never limit yourself to a single database

# Summary of things to look for
> Usernames, profile names and/or email addresses
 
> Passwords (private keys, PINs, and so forth 

> Domain names

> Hostnames

> IP addresses

> Software and operating system types, names, and versions

> Technial documentation

# Where do you find info?
> Personal websites; blogs

> Alot of search engines

> Social media; Linkedin, Facebook, Twitter, and Instagram

> Github, Forums, newsgroups, and mailing lists

> Public data basses such as ICANN and domain name registrars

# OSINT tools
* [Search engines](google.com)

* [Goog-mail.py](https://github.com/leebaird/discover/blob/master/mods/goog-mail.py)

* Application programming interfaces for public databases
 
* [Recon-ng](https://github.com/lanmaster53/recon-ng)
 
* [TheHarvester](https://github.com/laramies/theHarvester/stargazers)

* [FOCA](https://github.com/ElevenPaths/FOCA)

* [Metagoofil](https://tools.kali.org/information-gathering/metagoofil)

* [Exiftool](https://exiftool.org/)

* [Maltego CE](https://www.maltego.com/products/)

* Linkedint

* [Shodan](https://www.shodan.io/)

* Various Domain Name System (DNS) utilites such as Dig, Host, Nslookup, and WHOIS

# Grabbing Email Addresses from Google 
* Download [goog-mail.py](www.hackerhousebook.com/files/goog-mail.py) or using the script ``wget --user=student --password=student www.hackerhousebook.com/files/goog-mail.py``

* using command ``python2 goog-mail.py uk.ibm.com`` we can pull some email addresses. There is nothing I am going to do with these email addresses, It is just querying public data.

>![Capture](https://user-images.githubusercontent.com/81980702/116955410-11c2a300-ac58-11eb-8505-fd3d74948250.JPG)

* This method can be used for bots to send spam, it can gather easy targets.

# Google Dorking 
* Google can be useful tool in the OSINT kit because of google dorking

* you can find some good data using ``inurl:/etc/passwd`` or even ``root:x:0:0:root:/root:/bin/bash``

# Introduction to Passwd and Shadow Files 
* Linux and Unix passwd file is readable by anyone on the system; they do not include password hashes 

* Holds additional information in the GECOS field. Contains the user's full name and other personallu identifiable informtion

* Back then. a Linux password and Unix distributions used to store username and passwords in a file. Now it is in a shadow file.

* using ``cat /etc/shadow`` you can see a list of users and their hashes.

* Contact the user that has been infected with [OpenPGP](https://www.openpgp.org/) which encryptes the data

# The Google Hacking Databse
* THere is an entire data base found at www.exploit-db.com/google-hacking-database 

* If a passwd file is exposed, most likely there are plenty of other sensitive data that can be exposed

* Another dork used is ``inurl:"q=user/password`` which locates **Drupal**; Find vulnerable web frameworks

* Important to check other public records such as Ofcom (UK) or the Federal Communications Commission (USA).

# Have You Been "Pwned" Yet?
* Pwned comes from the hacker/gamer culture. 

* haveibeenpwned.com

* HIBP collects leaked data and shows if you are on the list 

* [HIBP API](haveibeenpwned.com/API/Key) can automate this process. The command below can add the key
`` curl -H "hibp-api-key <APIKEY>" https://haveibeenpwned.com/api/v3/breachedaccount/<email_address>``

* Using HIBP, you can see if an account has had a leak before and obtain the hash will allow some knowledge into the account

* You can automate the process with a script and add a pause. Then using ``grep``, we can then access what we gathered. 

# OSINT Framework Recon-ng
* [Recon-ng](https://github.com/lanmaster53/recon-ng) developed by LaNMaSteR53 is a module-based framework that is user-friendly

* for Recon-ng to communicate effectively, importing API keys is crucial 

# Create a workspace in recon-ng
* a work space called hackerhouse can be created using ``workspaces create hackerhouse``

* Any intel will be gathered in that workspace, using command ``workspace list``, you can see what is added 

* ``marketplace install all`` will download different modules 

* Loading in, there are intimidating red messages as shown below
```
[!] Module 'recon/companies-hosts/censys_org' disabled. Dependency required: ''censys''.
[!] Module 'recon/companies-hosts/censys_tls_subjects' disabled. Dependency required: ''censys''.
[!] Module 'recon/hosts-hosts/censys_hostname' disabled. Dependency required: ''censys''.
[!] Module 'recon/hosts-hosts/censys_query' disabled. Dependency required: ''censys''.
[!] 'virustotal_api' key not set. virustotal module will likely fail at runtime. See 'keys add'.
[!] 'bing_api' key not set. bing_ip module will likely fail at runtime. See 'keys add'.
[!] 'ipinfodb_api' key not set. ipinfodb module will likely fail at runtime. See 'keys add'.
[!] 'ipstack_api' key not set. ipstack module will likely fail at runtime. See 'keys add'.
```
* For those you have to add the api

* ``Modules search`` brings up a list with discovery, Exploitation, Import, and Recon

# Profiler module 
* using the command ``modules load recon/profiles-profiles/profiler``

* after loading in the module and typing in ``info``, this is what is brought up
```
Name: OSINT HUMINT Profile Collector
    Author: Micah Hoffman (@WebBreacher)
   Version: 1.0

Description:
  Takes each username from the profiles table and searches a variety of web sites for those users. The
  list of valid sites comes from the parent project at https://github.com/WebBreacher/WhatsMyName

Options:
  Name    Current Value  Required  Description
  ------  -------------  --------  -----------
  SOURCE  default        yes       source of input (see 'info' for details)

Source Options:
  default        SELECT DISTINCT username FROM profiles WHERE username IS NOT NULL
  <string>       string representing a single input
  <path>         path to a file containing a list of inputs
  query <sql>    database query returning one column of inputs

Comments:
  * Note: The global timeout option may need to be increased to support slower sites.
  * Warning: Using this module behind a filtering proxy may cause false negatives as some of these
  sites may be blocked.
```
* This is a profile collector 

* you can call the profiles using the command ``show profiles`` but it will be blank. Use the command below to add 
```
db insert profiles <UserName>~~~~
```
* after that using command ``show profiles`` it returns 
```
+---------------------------------------------------------------------+
  | rowid | username | resource | url | category | notes |    module    |
  +---------------------------------------------------------------------+
  | 1     | CoreyCburton |          |     |        |  | user_defined |
+---------------------------------------------------------------------+
```
* Once that is selected, type ``run`` and it will began the search

* The username database can bring alot of information om certain websites. Below shows what the profiler returned with my username
```
coreycburton | GitHub          | https://github.com/coreycburton                 | coding       |       | profiler     |
```
# Harvesting the Web


































