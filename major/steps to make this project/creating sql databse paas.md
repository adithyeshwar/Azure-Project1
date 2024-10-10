
# **Creating and Managing an Azure SQL Database**

Follow these steps to create and manage your Azure SQL database:

### 1. **Open the Azure Portal**
   - In the search bar, type **SQL Database**.

### 2. **Create a New SQL Database**
   - Click on the **Create** button.

### 3. **Fill in the Required Details**
   - Provide the necessary information for your database.
   - **Note**: If a server does not exist, create a new one.
   - **Authentication Method**: Choose **SQL Authentication**.
   - **Compute + Storage**: Select the **Basic** or any cost-effective option that suits your needs.

### 4. **Review and Create**
   - Once the details are filled, click **Review + Create** to deploy your SQL database.

### 5. **Navigate to SQL Server**
   - After deployment, go to your newly created **SQL Server**.

### 6. **Set Networking and Firewall Rules**
   - Under the **Networking** section, adjust the firewall rules:
     - **Add your IP address** (IPv4) if your network is IPv6-based.
     - **Tip**: You can find your IPv4 address by searching "What is my IP address" on Google.

### 7. **Access SQL Database via Query Editor**
   - Go back to the **SQL Database** and open **Query Editor**.
   - Enter your **username** and **password** to log in.

### 8. **Ensure SSMS is Installed**
   - **Note**: Make sure you have installed **Microsoft SQL Server Management Studio (SSMS)** to execute SQL commands.

### 9. **Execute SQL Code**
   - In SSMS, you can execute the following command to create a table:
     ```sql
     CREATE TABLE class (
         name VARCHAR(10),
         phone INT
     );
     ```
     
### 10. **Verify Table Creation**
   - Once the command runs successfully, you will see a new table named **class** in your database.







1. Open the Azure portal searh for SQl database .
	2. Click create option 
	3. Fill the details as required:
note:  create a new server if not exists.
            Select -Use SQL authentication in Authentication method.
           In Compute + storage select basic or frindly option
	4. Go to review & create
	5. After creating go to sql server .
	6. Go to networking : change the firewall rules : add your ipaddress in ipv4 format if your network is of ipv6.
note: go to google and search what is my ipaddress you can find your ipv4 ip even if you have ipv6.
	7. Now again go to sql data base and go to Query editer and enter your uusername and password to login.
	8. Note: make sure you have installed microsoft Sql server management studio (SSmS).
	9. In that you will get a cli in which we enter sql code:

	create table class(name varchar(10),phone int)
	10. You can see new table has created.



![image](https://github.com/user-attachments/assets/0f5201c9-7cf3-46a4-9feb-16a67fcd4cf7)
