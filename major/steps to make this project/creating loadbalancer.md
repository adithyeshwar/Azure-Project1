
![image](https://github.com/user-attachments/assets/101f4bb2-baf4-4945-ab35-79233efefaaf)



# Azure Virtual Machine Setup with Custom Data

In this guide, you'll learn how to create two virtual machines (VMs) and a load balancer using a custom script that deploys a website. Follow the steps below to configure everything within a single resource group.

---

### **1. Custom Data Script for VM Setup**

We'll start by running a custom bash script that updates the system, installs Nginx and Git, and clones your project repository to serve it as a website.

```bash
#!/bin/bash
# Update the system and install necessary packages
sudo apt update
sudo apt install nginx git -y

# Clone your GitHub repository into the /tmp directory
cd /tmp && git clone https://github.com/adithyeshwar/Azurep1.git mysite

# Remove the default Nginx welcome page and replace it with your website
sudo rm -rf /var/www/html/index.nginx-debian.html
sudo cp -r /tmp/mysite/* /var/www/html

# Set the appropriate file permissions for Nginx to serve your content
cd /var/www/html/
sudo chown -R www-data:www-data /var/www/html
sudo chmod -R 755 /var/www/html
```

---

### **2. Ensure Resources Are in a Single Resource Group**

To keep everything organized and manageable, ensure that all your resources (VMs, Load Balancer, etc.) are created within **one resource group**.

---

### **3. Steps to Create VMs and Load Balancer**

1. **Create two virtual machines** with the custom data script mentioned above.
   
2. **Set up a load balancer** to distribute traffic between the two VMs.
   
3. **Add both VMs to the load balancer's backend pool** to ensure traffic is shared between them.

4. **Get the public IP of the load balancer** and open it in a browser to verify that the webpage is served correctly.

---

### **4. Verifying the Setup**

After setting up the VMs and the load balancer, copy the **load balancer's IP address** and open it in your web browser. If everything was configured correctly, you should see your deployed web page live!

---

Now you're ready to create scalable web deployments on Azure! Feel free to reach out for any questions or issues.

-
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
