# Azure Virtual Machines: Deployment and Access Guide ☁️

## Table of Contents 🔗
1. [Create an Azure Account](#create-an-azure-account)
2. [Create a Resource Group](#create-a-resource-group)
3. [Create a Virtual Network](#create-a-virtual-network)
4. [Deploy a Linux Virtual Machine](#deploy-a-linux-virtual-machine)
5. [Access the Linux VM using SSH](#access-the-linux-vm-using-ssh)
6. [Deploy a Windows Virtual Machine](#deploy-a-windows-virtual-machine)
7. [Access the Windows VM using RDP](#access-the-windows-vm-using-rdp)
8. [Additional Resources](#additional-resources)

## Create a Resource Group 🗃️

1. **Navigate to the Azure Portal**:
   - Go to [portal.azure.com](https://portal.azure.com/) and sign in with your Azure account.
   
2. **Create Resource Group**:
   - In the Azure portal, click on "Resource groups" on the left-hand menu.
   - Click "Create" to start creating a new resource group.
   - Provide a name for your resource group and select a region (e.g., East US).
   - Click "Review + create" and then "Create".

## Create a Virtual Network 🌐

1. **Navigate to Virtual Networks**:
   - Click on "Virtual networks" in the left-hand menu.
   - Click "Create" to start the process.

2. **Configure the Virtual Network**:
   - Basics: Select your subscription, resource group, and give your VNet a name (e.g., MyVNet). Choose a region.
   - IP Addresses: Define the address space (e.g., 10.0.0.0/16) and add subnets (e.g., 10.0.1.0/24).
   - Security: Default settings are fine for now.
   - Review + create: Click "Review + create" and then "Create".

## Deploy a Linux Virtual Machine 🖥️

1. **Navigate to Virtual Machines**:
   - Click on "Virtual machines" in the left-hand menu.
   - Click "Create" and then "Azure virtual machine".

2. **Configure the Linux VM**:
   - Basics: Select your subscription, resource group, and give your VM a name (e.g., MyLinuxVM). Choose the region where your VNet is located.
   - Image: Choose "Ubuntu Server 20.04 LTS".
   - Size: Select a VM size (e.g., Standard_B1s).
   - Administrator account: Choose SSH public key, enter your username (e.g., azureuser), and paste your SSH public key.
   - Disks: Use the default settings.
   - Networking: Select your VNet and subnet created earlier. Make sure to allow SSH (port 22).
   - Management, Advanced, and Tags: Default settings are fine.
   - Review + create: Click "Review + create" and then "Create".

## Access the Linux VM using SSH 📡

1. **Find the Public IP Address**:
   - Go to your VM’s overview page in the Azure portal.
   - Note the public IP address.

2. **Connect via SSH**:
   - Open a terminal on your local machine.
   - Connect using SSH: `ssh azureuser@192.168.1.1`.

## Deploy a Windows Virtual Machine 💻

1. **Navigate to Virtual Machines**:
   - Click on "Virtual machines" in the left-hand menu.
   - Click "Create" and then "Azure virtual machine".

2. **Configure the Windows VM**:
   - Basics: Select your subscription, resource group, and give your VM a name (e.g., MyWindowsVM). Choose the region where your VNet is located.
   - Image: Choose "Windows Server 2019 Datacenter".
   - Size: Select a VM size (e.g., Standard_B2s).
   - Administrator account: Enter a username and password.
   - Disks: Use the default settings.
   - Networking: Select your VNet and subnet created earlier. Make sure to allow RDP (port 3389).
   - Management, Advanced, and Tags: Default settings are fine.
   - Review + create: Click "Review + create" and then "Create".

## Access the Windows VM using RDP 📶

1. **Find the Public IP Address**:
   - Go to your VM’s overview page in the Azure portal.
   - Note the public IP address.

2. **Connect via RDP**:
   - On your local Windows machine, open Remote Desktop Connection (RDP).
   - Enter the public IP address of your Windows VM.
   - Enter the username and password you specified during VM creation.
