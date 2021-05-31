# Gentoo Linux 
- Full customization and can be built up from no binary components. 
  - Allows you to review precisely what your computer has been instructed to do in source code form.

-it is complicated for a new user
  - Alot of time to learn source code 

# Arch Linux
- A hybrid of Gentoo like power and Debian like stability
  - Still has some capability of source code components 

- Highy customizable, but all done though the linux command line

# Debian 
- Easy config

- Stable; fast security updates

- Kali Linux uses this 

# Ubuntu
- Easy for beginners; similar to macOS
  - Everything seems to work on Ubuntu such as drivers.

# Kali Linux 
- Install on a VM; not a host os 
  -  Use for the labs in this book 

# Verify Downloads
- Use the command below to allow ```sha256sum``` on mac os. 
```
function sha256sum() { shasum -a 256 "$@" ; } && export -f sha256sum
```
- To verify files to compare hashes use 
```
sha256sum <PathToFile>
```
- Files sent with **HTTP** are sent in plain text 
  - Files sent with **HTTPS** are encrypted.

# Disk Encryption 
- It is important to have your files encrypted

- On macOS, filevault is used and it is important that it is turned 
  - It is impossilbe to have your whole SSD encrypted unless it is established at start up

- You can have a encrypted folder but it shows the hacker that there is sensitive data there. 
  - They will target folder

# Password managers 
- [1password](https://1password.com/)

- [keepassx](https://www.keepassx.org/)

# Email 
- It is important to send encrypted emails espically if it is a lab report to one of your clients. 
  - Advanced Encryption standard (AES) should be used

# Setting up Mail server and Booklab

- Download the [iso file](www.hackerhousebook.com/hh-mailserver-v1-i386.hybrid.iso) provided in the book which is the mail server. 
  - After it is downloaded, the picture below is what you should see
![Capture](https://user-images.githubusercontent.com/81980702/116940216-3f492580-ac33-11eb-941c-b9af647f4cbc.JPG)

- Download the [iso file](www.hackerhousebook.com/hh-booklab-v1-i386.hybrid.iso) provided in the book which is the book lab. 
  - After it is downloaded, the picture below is what you should see
![Capture1](https://user-images.githubusercontent.com/81980702/116941409-3c4f3480-ac35-11eb-9b41-8a00dbecea35.JPG)

# Installing guest additions
- On VirtualBox, go to devices > Insert Guest Additions CD image 
  - This allows the VM to be seen in FUll Screen and add other features

- In some VMs the virtual CD is mounted to ``/media/cdrom0``

# Testing Virtual Environment 
- The mail server ip is ``192.168.1.108`` 

- Using Kali Linux, the user can ping the mail server using ``ping <TargetIP>`` and receive some feedback. 
  - The image below shows that Kali can connect to the mail server
![Capture](https://user-images.githubusercontent.com/81980702/116943227-c351dc00-ac38-11eb-8cd2-bc6d78a9725f.JPG)

  - ``Ctrl + C`` stops the device from continuously pinging 

# Creating Vulnerable Servers
- [vulnhub](www.vulnhub.com) has great "boot2root" challenges 
  - VMs are great for testing exploits or tools
  - **Hypervisor** and **cloudbursts** can run malware on your computer through a virtual machine 


















