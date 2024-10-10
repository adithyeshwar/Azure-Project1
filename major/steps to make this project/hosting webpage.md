
# 🚀 Deploying a Static Webpage on Azure VM

This script automates the process of setting up a static website using **Nginx** and **Git** on an **Azure Virtual Machine**.

```bash
#!/bin/bash
# Update system packages
sudo apt update

# Install Nginx and Git
sudo apt install nginx git -y

# Clone your website from GitHub
cd /tmp && git clone https://github.com/adithyeshwar/Azurep1.git mysite

# Replace the default Nginx index page
sudo rm -rf /var/www/html/index.nginx-debian.html
sudo cp -r /tmp/mysite/* /var/www/html

# Set the correct permissions
cd /var/www/html/
sudo chown -R www-data:www-data /var/www/html
sudo chmod -R 755 /var/www/html
```

---

## 📜 **Steps to Deploy the Webpage**

Here’s a quick guide to follow:

1. **Create the Azure VM:**
   - Use the Azure Portal to create a new **Resource Group** (e.g., `MySite-RG`).
   - Choose an **Ubuntu Linux VM** (1 CPU, 1 GB RAM - B1s, Standard SSD).

2. **Access the VM:**
   - Use **Putty**, **PowerShell**, or the **Command Prompt** to log in to the VM.
   - Run the following command to update system packages:
     ```bash
     sudo apt update
     ```

3. **Install Nginx:**
   - Install the Nginx web server:
     ```bash
     sudo apt install nginx -y
     ```

4. **Verify Nginx Installation:**
   - Check the status:
     ```bash
     systemctl status nginx
     ```

5. **Access the Nginx Page:**
   - Copy the public IP of the VM from the Azure portal and paste it into your browser. The default Nginx page should appear.

6. **Download Website Files:**
   - Create a directory and download the template:
     ```bash
     mkdir MySite
     cd MySite
     wget <your-website-template-link>
     ```

7. **Unzip the Files:**
   - Install the `unzip` tool and extract the template:
     ```bash
     sudo apt install unzip -y
     unzip <filename.zip>
     ```

8. **Move Files to Nginx Directory:**
   - Replace the default Nginx files with your website files:
     ```bash
     sudo rm -rf /var/www/html/*
     sudo cp -r /path/to/unzipped/files/* /var/www/html/
     ```

9. **Set Permissions:**
   - Ensure the correct permissions are set for Nginx:
     ```bash
     sudo chown -R www-data:www-data /var/www/html
     sudo chmod -R 755 /var/www/html
     ```

10. **Reload Nginx:**
    - If the webpage doesn’t load, try reloading Nginx:
      ```bash
      sudo systemctl reload nginx
      ```

---

## 🛠️ **Command History Example**

Here’s an example history of the commands used to deploy the page:

```bash
azureuser@Assent1:/var/www/html$ history
1. sudo apt update
2. sudo apt install nginx -y
3. mkdir mysite
4. cd mysite
5. git clone https://github.com/adithyeshwar/Azurep1
6. sudo cp -r /home/azureuser/mysite/Azurep1/* /var/www/html/
7. sudo chown -R www-data:www-data /var/www/html
8. sudo chmod -R 755 /var/www/html
```

---

## 💡 **How to Clone from GitHub**

Whenever you want to get a folder from GitHub, follow these steps:

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd <repository-folder>
   ```

2. **Copy files to Nginx:**
   ```bash
   sudo cp -r /path/to/repository/* /var/www/html/
   sudo chown -R www-data:www-data /var/www/html
   sudo chmod -R 755 /var/www/html
   ```

---

## 📷 **Example Output**
![Webpage Example](https://github.com/user-attachments/assets/392119fb-e4f8-46e9-9db6-27831acc08c5)
