	#!/bin/bash
	sudo apt update
	sudo apt install nginx git -y
	cd /tmp && git clone https://github.com/adithyeshwar/Azurep1.git mysite
	sudo rm -rf /var/www/html/index.nginx-debian.html
	sudo cp -r /tmp/mysite/* /var/www/html
	cd /var/www/html/
	sudo chown -R www-data:www-data /var/www/html
	sudo chmod -R 755 /var/www/html

below code is the history of me tring to deploy a static web page:

1)Create the Azure VM in the Portal with the Following Configurations
-> Create Resource Group with Any Name (Eg: MySite-RG)
-> Mention any Name under VM Name
2)Select the Operating System with Linux Based VM (Ubuntu).
3)Select the Size of the VM as 1CPU and 1GB RAM (B1s)
4)Select the Disk as Standard SDD.
5)Click on Review and Create
6)Login to VM by using Putty/Powershell/Cmd Promt.
7)Update the System Packages
by using commands like 
	- sudo apt update
8)Then Install the Nginx Package in the VM
a)sudo apt install nginx -y
9)Check the Installation is working fine or not.
a)systemctl status nginx
10)Copy the VM public Ip address from the portal and Paste it on your browser.
11)Check the Nginx Page is reflecting or not.
12)In the VM create the directory for website files by done by you or from CSS Templates
a)mkdir MySite
b)wget (copy the websites link from CSS Templates) copied link address.
c)It will download the file and look like in Zip Format.
13)To unzip the file we need to install respective package
a)sudo apt install unzip -y
14)To unzip the file try this command
a)unzip (filename.zip)
15)It will be in the new directory file, go inside of the directory and check the files.
16)Go to Nginx installer location where default webpage is available, we need to remove the default file and then place your CSS Template file from Unzipped Location.
17)Just follow the mentioned steps
a)cd /var/www/html
b)sudo rm -rf *
c)sudo cp -r /path/to/mywebsite/* /var/www/html/
d)sudo chown -R www-data:www-data /var/www/html
e)sudo chmod -R 755 /var/www/html
18)After performing all the steps if the webpage is not displayed, just follow this command to display the webpage
a)sudo systemctl reload nginx
19)After completing all the steps the desired webpage will be displayed under the VM.







1  clear
    2  sudo apt update
    3  sudo apt install nginx -y
    4  mkdir mysite
    5  cd mysite/
    6  wget https://www.free-css.com/assets/files/free-css-templates/download/page296/finexo.zip
    7  ls
    8  sudo apt install unzip -y
    9  ls
   10  unzip finexo.zip
   11  ls
   12  cd finexo-html/
   13  ls
   14  ls -l
   15  pwd
   16  cd
   17  sudo cp -r /home/madhan/mysite/finexo-html/* /var/www/html/
   18  cd /var/www/html/
   19  ls
   20  ls -l
   21  sudo chown -R www-data:www-data /var/www/html
   22  ls -l
   23  sudo chmod -R 755 /var/www/html
	•    24  ls -l


when erver u want to get the folder from git hub you have to follow steps:


	• drag and drop the folder from destop to github repositry.
	• Copy the repository url.
	• Type command in powershell:
git clone "URL"
	• Cd folder/
	• Ls
	• Ls -l
	•  sudo cp -r /home/pranathi03/mysite/Azurep1/* /var/www/html/
	sudo chown -R www-data:www-data /var/w
	ww/html
	• if u  have any space in the repositry name include "\" ;
sport webpage-sports\webpage



exmaple:


	azureuser@Assent1:/var/www/html$ history
	    1  sudo apt update
	1.     2  sudo apt install nginx -y
	2.       -sudo rm -rf /var/www/html/index.filename.html
	    3  mkdir mysite
	    4  ls
	    5  cd mysite
	    6  git clone https://github.com/adithyeshwar/Azurep1
	    7  ls
	    8  cd Azurep1
	    9  ls
	   10  pwd
	   11  cd
	   12  sudo cp -r /home/azureuser/mysite/Azurep1/* /var/www/html/
	   13  cd /var/www/html/
	   14  ls
	   15  sudo chown -R www-data:www-data /var/www/html
	   16  ls -l
	   17  sudo chmod -R 755 /var/www/html
	   18  ls
	   19  history
	• 

	Windows PowerShell
	Copyright (C) Microsoft Corporation. All rights reserved.
	
	Install the latest PowerShell for new features and improvements! https://aka.ms/PSWindows
	
	PS C:\Users\gouda> ssh azureuser@20.197.46.172
	The authenticity of host '20.197.46.172 (20.197.46.172)' can't be established.
	ED25519 key fingerprint is SHA256:3qubiFcmjUkpaR+5tHOOhIk8eeLyzZPuZNFZ7KWwMa8.
	This key is not known by any other names
	Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
	Warning: Permanently added '20.197.46.172' (ED25519) to the list of known hosts.
	azureuser@20.197.46.172's password:
	Welcome to Ubuntu 24.04 LTS (GNU/Linux 6.8.0-1013-azure x86_64)
	
	 * Documentation:  https://help.ubuntu.com
	 * Management:     https://landscape.canonical.com
	 * Support:        https://ubuntu.com/pro
	
	 System information as of Tue Sep  3 17:37:06 UTC 2024
	
	  System load:  0.13              Processes:             110
	  Usage of /:   5.0% of 28.02GB   Users logged in:       0
	  Memory usage: 30%               IPv4 address for eth0: 10.0.0.4
	  Swap usage:   0%
	
	Expanded Security Maintenance for Applications is not enabled.
	
	0 updates can be applied immediately.
	
	Enable ESM Apps to receive additional future security updates.
	See https://ubuntu.com/esm or run: sudo pro status
	
	
	The list of available updates is more than a week old.
	To check for new updates run: sudo apt update
	
	
	The programs included with the Ubuntu system are free software;
	the exact distribution terms for each program are described in the
	individual files in /usr/share/doc/*/copyright.
	
	Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
	applicable law.
	
	To run a command as administrator (user "root"), use "sudo <command>".
	See "man sudo_root" for details.
	
	azureuser@Assent1:~$ sudo apt update
	Hit:1 http://azure.archive.ubuntu.com/ubuntu noble InRelease
	Get:2 http://azure.archive.ubuntu.com/ubuntu noble-updates InRelease [126 kB]
	Get:3 http://azure.archive.ubuntu.com/ubuntu noble-backports InRelease [126 kB]
	Get:4 http://azure.archive.ubuntu.com/ubuntu noble-security InRelease [126 kB]
	Get:5 http://azure.archive.ubuntu.com/ubuntu noble/universe amd64 Packages [15.0 MB]
	Get:6 http://azure.archive.ubuntu.com/ubuntu noble/universe Translation-en [5982 kB]
	Get:7 http://azure.archive.ubuntu.com/ubuntu noble/universe amd64 Components [3871 kB]
	Get:8 http://azure.archive.ubuntu.com/ubuntu noble/universe amd64 c-n-f Metadata [301 kB]
	Get:9 http://azure.archive.ubuntu.com/ubuntu noble/multiverse amd64 Packages [269 kB]
	Get:10 http://azure.archive.ubuntu.com/ubuntu noble/multiverse Translation-en [118 kB]
	Get:11 http://azure.archive.ubuntu.com/ubuntu noble/multiverse amd64 Components [35.0 kB]
	Get:12 http://azure.archive.ubuntu.com/ubuntu noble/multiverse amd64 c-n-f Metadata [8328 B]
	Get:13 http://azure.archive.ubuntu.com/ubuntu noble-updates/main amd64 Packages [470 kB]
	Get:14 http://azure.archive.ubuntu.com/ubuntu noble-updates/main Translation-en [117 kB]
	Get:15 http://azure.archive.ubuntu.com/ubuntu noble-updates/main amd64 c-n-f Metadata [7808 B]
	Get:16 http://azure.archive.ubuntu.com/ubuntu noble-updates/universe amd64 Packages [348 kB]
	Get:17 http://azure.archive.ubuntu.com/ubuntu noble-updates/universe Translation-en [143 kB]
	Get:18 http://azure.archive.ubuntu.com/ubuntu noble-updates/universe amd64 Components [45.0 kB]
	Get:19 http://azure.archive.ubuntu.com/ubuntu noble-updates/universe amd64 c-n-f Metadata [13.8 kB]
	Get:20 http://azure.archive.ubuntu.com/ubuntu noble-updates/restricted amd64 Packages [281 kB]
	Get:21 http://azure.archive.ubuntu.com/ubuntu noble-updates/restricted Translation-en [54.8 kB]
	Get:22 http://azure.archive.ubuntu.com/ubuntu noble-updates/multiverse amd64 Packages [14.4 kB]
	Get:23 http://azure.archive.ubuntu.com/ubuntu noble-updates/multiverse Translation-en [3608 B]
	Get:24 http://azure.archive.ubuntu.com/ubuntu noble-updates/multiverse amd64 Components [212 B]
	Get:25 http://azure.archive.ubuntu.com/ubuntu noble-updates/multiverse amd64 c-n-f Metadata [532 B]
	Get:26 http://azure.archive.ubuntu.com/ubuntu noble-backports/main amd64 Components [208 B]
	Get:27 http://azure.archive.ubuntu.com/ubuntu noble-backports/main amd64 c-n-f Metadata [112 B]
	Get:28 http://azure.archive.ubuntu.com/ubuntu noble-backports/universe amd64 Packages [10.3 kB]
	Get:29 http://azure.archive.ubuntu.com/ubuntu noble-backports/universe Translation-en [10.5 kB]
	Get:30 http://azure.archive.ubuntu.com/ubuntu noble-backports/universe amd64 Components [17.6 kB]
	Get:31 http://azure.archive.ubuntu.com/ubuntu noble-backports/universe amd64 c-n-f Metadata [1016 B]
	Get:32 http://azure.archive.ubuntu.com/ubuntu noble-backports/restricted amd64 Components [216 B]
	Get:33 http://azure.archive.ubuntu.com/ubuntu noble-backports/restricted amd64 c-n-f Metadata [116 B]
	Get:34 http://azure.archive.ubuntu.com/ubuntu noble-backports/multiverse amd64 Components [212 B]
	Get:35 http://azure.archive.ubuntu.com/ubuntu noble-backports/multiverse amd64 c-n-f Metadata [116 B]
	Get:36 http://azure.archive.ubuntu.com/ubuntu noble-security/main amd64 Packages [324 kB]
	Get:37 http://azure.archive.ubuntu.com/ubuntu noble-security/main Translation-en [73.6 kB]
	Get:38 http://azure.archive.ubuntu.com/ubuntu noble-security/main amd64 c-n-f Metadata [4276 B]
	Get:39 http://azure.archive.ubuntu.com/ubuntu noble-security/universe amd64 Packages [263 kB]
	Get:40 http://azure.archive.ubuntu.com/ubuntu noble-security/universe Translation-en [110 kB]
	Get:41 http://azure.archive.ubuntu.com/ubuntu noble-security/universe amd64 Components [8632 B]
	Get:42 http://azure.archive.ubuntu.com/ubuntu noble-security/universe amd64 c-n-f Metadata [9936 B]
	Get:43 http://azure.archive.ubuntu.com/ubuntu noble-security/restricted amd64 Packages [280 kB]
	Get:44 http://azure.archive.ubuntu.com/ubuntu noble-security/restricted Translation-en [54.8 kB]
	Get:45 http://azure.archive.ubuntu.com/ubuntu noble-security/multiverse amd64 Packages [10.6 kB]
	Get:46 http://azure.archive.ubuntu.com/ubuntu noble-security/multiverse Translation-en [2808 B]
	Get:47 http://azure.archive.ubuntu.com/ubuntu noble-security/multiverse amd64 Components [208 B]
	Get:48 http://azure.archive.ubuntu.com/ubuntu noble-security/multiverse amd64 c-n-f Metadata [344 B]
	Fetched 28.7 MB in 5s (5536 kB/s)
	Reading package lists... Done
	Building dependency tree... Done
	Reading state information... Done
	83 packages can be upgraded. Run 'apt list --upgradable' to see them.
	azureuser@Assent1:~$ sudo apt install nginx -y
	Reading package lists... Done
	Building dependency tree... Done
	Reading state information... Done
	The following additional packages will be installed:
	  nginx-common
	Suggested packages:
	  fcgiwrap nginx-doc ssl-cert
	The following NEW packages will be installed:
	  nginx nginx-common
	0 upgraded, 2 newly installed, 0 to remove and 83 not upgraded.
	Need to get 552 kB of archives.
	After this operation, 1596 kB of additional disk space will be used.
	Get:1 http://azure.archive.ubuntu.com/ubuntu noble/main amd64 nginx-common all 1.24.0-2ubuntu7 [31.2 kB]
	Get:2 http://azure.archive.ubuntu.com/ubuntu noble/main amd64 nginx amd64 1.24.0-2ubuntu7 [521 kB]
	Fetched 552 kB in 0s (10.7 MB/s)
	Preconfiguring packages ...
	Selecting previously unselected package nginx-common.
	(Reading database ... 64525 files and directories currently installed.)
	Preparing to unpack .../nginx-common_1.24.0-2ubuntu7_all.deb ...
	Unpacking nginx-common (1.24.0-2ubuntu7) ...
	Selecting previously unselected package nginx.
	Preparing to unpack .../nginx_1.24.0-2ubuntu7_amd64.deb ...
	Unpacking nginx (1.24.0-2ubuntu7) ...
	Setting up nginx (1.24.0-2ubuntu7) ...
	Setting up nginx-common (1.24.0-2ubuntu7) ...
	Created symlink /etc/systemd/system/multi-user.target.wants/nginx.service → /usr/lib/systemd/system/nginx.service.
	Processing triggers for ufw (0.36.2-6) ...
	Processing triggers for man-db (2.12.0-4build2) ...
	Scanning processes...
	Scanning linux images...
	
	Running kernel seems to be up-to-date.
	
	No services need to be restarted.
	
	No containers need to be restarted.
	
	No user sessions are running outdated binaries.
	
	No VM guests are running outdated hypervisor (qemu) binaries on this host.
	azureuser@Assent1:~$ mkdir mysite
	azureuser@Assent1:~$ ls
	mysite
	azureuser@Assent1:~$ cd mysite
	azureuser@Assent1:~/mysite$ git clone https://github.com/adithyeshwar/Azurep1
	Cloning into 'Azurep1'...
	remote: Enumerating objects: 24, done.
	remote: Counting objects: 100% (24/24), done.
	remote: Compressing objects: 100% (22/22), done.
	remote: Total 24 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
	Receiving objects: 100% (24/24), 2.73 MiB | 20.67 MiB/s, done.
	Resolving deltas: 100% (1/1), done.
	azureuser@Assent1:~/mysite$ ls
	Azurep1
	azureuser@Assent1:~/mysite$ cd Azurep1
	azureuser@Assent1:~/mysite/Azurep1$ ls
	README.md  app.js  image  index.html  style.css
	azureuser@Assent1:~/mysite/Azurep1$ pwd
	/home/azureuser/mysite/Azurep1
	azureuser@Assent1:~/mysite/Azurep1$ cd
	azureuser@Assent1:~$ sudo cp -r /home/azureuser/mysite/Azurep1/* /var/www/ht
	ml/
	azureuser@Assent1:~$ cd /var/www/html/
	azureuser@Assent1:/var/www/html$ ls
	README.md  app.js  image  index.html  index.nginx-debian.html  style.css
	azureuser@Assent1:/var/www/html$ sudo chown -R www-data:www-data /var/www/ht
	ml
	azureuser@Assent1:/var/www/html$ ls -l
	total 36
	-rw-r--r-- 1 www-data www-data    9 Sep  3 17:42 README.md
	-rw-r--r-- 1 www-data www-data 1675 Sep  3 17:42 app.js
	drwxr-xr-x 2 www-data www-data 4096 Sep  3 17:42 image
	-rw-r--r-- 1 www-data www-data 9453 Sep  3 17:42 index.html
	-rw-r--r-- 1 www-data www-data  615 Sep  3 17:38 index.nginx-debian.html
	-rw-r--r-- 1 www-data www-data 6671 Sep  3 17:42 style.css
	azureuser@Assent1:/var/www/html$ sudo chmod -R 755 /var/www/html
	azureuser@Assent1:/var/www/html$ ls
	README.md  app.js  image  index.html  index.nginx-debian.html  style.css
	
	
	#!/bin/bash
	sudo apt update
	sudo apt install nginx git -y
	cd /tmp && git clone https://github.com/adithyeshwar/Azurep1.git mysite
	sudo rm -rf /var/www/html/index.nginx-debian.html
	sudo cp -r /tmp/mysite/* /var/www/html
	cd /var/www/html/
	sudo chown -R www-data:www-data /var/www/html
	sudo chmod -R 755 /var/www/html
![image](https://github.com/user-attachments/assets/392119fb-e4f8-46e9-9db6-27831acc08c5)

