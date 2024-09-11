	1. Arm!
	2. We will get the below options:

parametes,funtions ,resouces,variabes

	3. While we are creting some thing we need to check the dependences as well:

	    -> Resource Group
	    -> VNet
	    -> Subnet
	    -> NSG
	
	4. Command:
Arm-nsg
	5. We will get :

	
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

	6. We need to create a vnet:
command: arm-vnet
	7. We will get:

	
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
	    ],
	    "outputs": {}
	}
	
	8. In this we can see there is a undefined varable that is "networkSecurityGroupName" that we nned to define in varables.
	
	9. In variables type command: new 
	"variables": {
	        "networkSecurityGroupName": "mynsg"
	    }
	10. We need to change the name in the set 5. nsg as follows:


	
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
	11. Az login
	12. az group create --resource-group heaven --location centralindia
	13. az deployment group create --resource-group heaven --template-file prac2.json
	14. 
	
![image](https://github.com/user-attachments/assets/85b16da2-1315-47ef-85c2-116de6b27ad9)
