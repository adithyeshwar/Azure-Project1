	Create a vm in which we give custem data:


	#!/bin/bash
	sudo apt update
	sudo apt install nginx git -y
	cd /tmp && git clone https://github.com/adithyeshwar/Azurep1.git mysite
	sudo rm -rf /var/www/html/index.nginx-debian.html
	sudo cp -r /tmp/mysite/* /var/www/html
	cd /var/www/html/
	sudo chown -R www-data:www-data /var/www/html
	sudo chmod -R 755 /var/www/html


	Make sure all the resources are created in 1 resource group
	Create 2 vm's and a load balancer
	Add 2 machines to load balancer and copy the load balancers ip and check wether the web page is working or not.
![image](https://github.com/user-attachments/assets/101f4bb2-baf4-4945-ab35-79233efefaaf)
