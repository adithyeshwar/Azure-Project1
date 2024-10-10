
# Azure ARM Template Guide 🚀

## 1. Getting Started with ARM Templates 💻
Let’s dive into ARM! When working with ARM templates, the key sections you'll come across include:

- **Parameters**
- **Functions**
- **Resources**
- **Variables**

## 2. Dependencies to Check 🔄
Before you start building resources, it’s important to make sure you have the necessary dependencies in place:

- **Resource Group**  
- **Virtual Network (VNet)**  
- **Subnet**  
- **Network Security Group (NSG)**

## 3. Creating a Network Security Group (NSG) 🛡️
To create an NSG, run the following command:

```bash
Arm-nsg
```

This will generate an NSG configuration like the one below:

```json
{
    "name": "networkSecurityGroup1",
    "type": "Microsoft.Network/networkSecurityGroups",
    "apiVersion": "2023-11-01",
    "location": "[resourceGroup().location]",
    "properties": {
        "securityRules": [
            {
                "name": "nsgRule1",
                "properties": {
                    "description": "description",
                    "protocol": "Tcp",
                    "sourcePortRange": "*",
                    "destinationPortRange": "*",
                    "sourceAddressPrefix": "*",
                    "destinationAddressPrefix": "*",
                    "access": "Allow",
                    "priority": 100,
                    "direction": "Inbound"
                }
            }
        ]
    }
}
```

## 4. Creating a Virtual Network (VNet) 🌐
Next, let’s create a VNet by using the following command:

```bash
arm-vnet
```

You’ll get the following output:

```json
{
    "name": "virtualNetwork1",
    "type": "Microsoft.Network/virtualNetworks",
    "apiVersion": "2023-11-01",
    "location": "[resourceGroup().location]",
    "tags": {
        "displayName": "virtualNetwork1"
    },
    "dependsOn": [
        "[resourceId('Microsoft.Network/networkSecurityGroups', variables('networkSecurityGroupName'))]"
    ],
    "properties": {
        "addressSpace": {
            "addressPrefixes": [
                "10.0.0.0/16"
            ]
        },
        "subnets": [
            {
                "name": "Subnet-1",
                "properties": {
                    "addressPrefix": "10.0.0.0/24",
                    "networkSecurityGroup": {
                        "id": "[resourceId('Microsoft.Network/networkSecurityGroups', variables('networkSecurityGroupName'))]"
                    }
                }
            },
            {
                "name": "Subnet-2",
                "properties": {
                    "addressPrefix": "10.0.1.0/24",
                    "networkSecurityGroup": {
                        "id": "[resourceId('Microsoft.Network/networkSecurityGroups', variables('networkSecurityGroupName'))]"
                    }
                }
            }
        ]
    }
}
```

## 5. Defining Undefined Variables 🔧
In the output above, we noticed an **undefined variable**: `networkSecurityGroupName`. We need to define it in the variables section. Add the following line:

```json
"variables": {
    "networkSecurityGroupName": "mynsg"
}
```

## 6. Update NSG Name in the Template ✏️
Next, update the NSG name in the previous configuration (Step 3) to use the variable we just defined:

```json
{
    "name": "[variables('networkSecurityGroupName')]",
    "type": "Microsoft.Network/networkSecurityGroups",
    "apiVersion": "2023-11-01",
    "location": "[resourceGroup().location]",
    "properties": {
        "securityRules": [
            {
                "name": "nsgRule1",
                "properties": {
                    "description": "description",
                    "protocol": "Tcp",
                    "sourcePortRange": "*",
                    "destinationPortRange": "*",
                    "sourceAddressPrefix": "*",
                    "destinationAddressPrefix": "*",
                    "access": "Allow",
                    "priority": 100,
                    "direction": "Inbound"
                }
            }
        ]
    }
}
```

## 7. Deploying the ARM Template 🚀
Let’s log in to Azure and deploy the template:

### Step 1: Log in to Azure
```bash
az login
```

### Step 2: Create a Resource Group
```bash
az group create --resource-group heaven --location centralindia
```

### Step 3: Deploy the Template
```bash
az deployment group create --resource-group heaven --template-file prac2.json
```

And that’s it! 🎉 Your resources will now be deployed using the ARM template.

---

![Deployment Success](https://github.com/user-attachments/assets/85b16da2-1315-47ef-85c2-116de6b27ad9)

