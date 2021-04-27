# Operating systems
# Gentoo Linux 
* Full customization and can be built up from no binary components. 

* Allows you to review precisely what your computer has been instructed to do in source code form.

* It is complicated for a new user; Alot of time to learn source code 

# Arch Linux
* A hybrid of Gentoo like power and Debian like stability

* Still has some capability of source code components 

* Highy customizable but all done though the linux command line

# Debian 
* Easy config

* Stable; fast security updates

* Kali Linux uses this 

# Ubuntu
* Easy for beginners; similar to macOS

* Everything seems to work on Ubuntu such as drivers.

# Kali Linux 
* Install on a VM; not a host os 

* Use for the labs in this book 

# Verify Downloads
Use the command below to allow ```sha256sum``` on mac os. 
```
function sha256sum() { shasum -a 256 "$@" ; } && export -f sha256sum
```
To verify files to compare hashes use 
```
sha256sum <PathToFile>
```
Files sent with **HTTP** are sent in plain text while files with **HTTPS** are encrypted.

# Disk Encryption 
* It is important to have your files encrypted

* On macOS, filevault is used and it is important that it is turned 

* It is impossilbe to have your whole SSD encrypted unless it is established at start up

* You can decrypt folder but it only shows the hacker that there is sensitive data there

# Password managers 
* [1password](https://1password.com/)

*[keepassx](https://www.keepassx.org/)

# Email 
* It is important to send encrypted emails espically if it is a lab report to one of your clients. 

* Advanced Encryption standard (AES) 











