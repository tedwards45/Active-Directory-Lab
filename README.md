 # Lab 1: Active Directory Setup in Azure  
**Created by:** Terrence Edwards  

## Overview
As part of my ongoing education in Digital Forensics and Cybersecurity, this lab demonstrates how to create and manage a Windows Server environment within Microsoft Azure. The lab will cover setting up a Windows Server virtual machine, configuring Active Directory, and creating users and groups.

---

## Phase 1: Setting Up the Windows Server VM in Azure  

### Step 1: Create an Azure Account (if you don’t already have one)
-> Click on **Create** under **Virtual Machine**



### Step 2: Create New Resource Group
![Create a Resource Group](https://github.com/user-attachments/assets/0e03a3a1-a3a7-494e-a779-6b314938df73)
![Creating New Resource Group](https://github.com/user-attachments/assets/c41df9b4-bdd6-4f51-80de-4ba35e233c42)


**Reference Screenshot Above:**  
In this step, click **“Create a Resource”**. This will allow you to create the **Resource Group** that will contain your Windows Server virtual machine and related resources. 

-> Then you want to give your VM & Resource Group a Name: For example, my lab name is **labIT** & my resource group name is **lab-test** 


    -Note: Name can be whatever you like to name your VM within the criteria 

-> Image should be **Windows Server 2022 datacenter: Azure Edition Hotpatch - x64 Gen2** 

**Reference Screenshot below:**

    -Note: The price on the side is not the actual price that you will be charged. We will delete our resource group at the end of each use to minimize costs.  

  ### Step 3: Image in Use
![Image in Use](https://github.com/user-attachments/assets/f5e0147e-b8a8-4874-a960-f4eb0ec4962c)

### Step 4: Select None for Public Ports
![Select None for Public inbound ports](https://github.com/user-attachments/assets/d6edbadf-fb2d-4373-90bb-f6f176eab568)
In this step, make sure to click **None** for **Public Inbound Ports** 
Finally, now click **Review+Create**


### Step 5: Deploying Bastion 
![Deploying Bastion](https://github.com/user-attachments/assets/db609bfc-906d-41e5-8435-62113a333b97)
In this step, the point behind the deployment of Bastion:

  -Deploying Azure Bastion provides secure **RDP(Remote Desktop Protocol)** and **SSH(Secure Shell)** access to your virtual machines without exposing them to the internet. RDP allows remote access to Windows      servers through a graphical interface, while SSH securely connects to Linux systems through the command line. **Bastion acts as a managed host within your subnet, ensuring protected, browser-based connectivity.**



### Step 6: Setting a Static IP 
![Setting a Static IP](https://github.com/user-attachments/assets/3b0ed3bd-f1d3-4973-8f9f-f4db2c799d82)
In this step, first click **Network Settings**, then click **Network interface/IP configuration** (as shown in the first picture). Note: Yours will have different names unless you choose to use the ones I use. Click on **ipconfig**: Under Private IP addresses 

 -Select **Static**
 - Click **Save**


### Step 7: Connecting via Bastion 
![Connecting via Bastion](https://github.com/user-attachments/assets/5e896525-4145-4b16-bb34-a505b7f21c24)
![Connecting via Bastion-Credentials](https://github.com/user-attachments/assets/fac75309-a4ff-442a-a0dd-a48146d6c021)

In the window that pops up, please enter your username and password from when we created our VM. **Refer to the second picture**, then click **Connect**


### Step 8: Turning Off Server Manager (Auto)
![Turning Off Server Manager (Auto)](https://github.com/user-attachments/assets/ec0baea2-c6f2-4a11-bfb5-b6f88a70d417)
In this step, click on **Manage** in the upper right-hand corner, then click **Server Manage Properties**

Refer to the picture below to turn off the server manager from auto-starting every log on by selecting **Do not start Server Manager automatically at login**
![Turning Off Server Manager (Auto) Cont.](https://github.com/user-attachments/assets/82e89679-b947-43f5-a7ec-a2e1b034082f)

### Step 9: Installing Roles and Features
![Installing Roles and Features](https://github.com/user-attachments/assets/19e3d33e-3501-4ea3-98b1-2b98c203ee37)
In this step, click **Manage**  in the upper right-hand corner, then click **Add Roles and Features**

![Installing Roles and Features Cont.](https://github.com/user-attachments/assets/ab105365-7d81-4e82-86f0-bd668478ac2d)
In this step, click **Next**

![Installing Roles and Features Cont.](https://github.com/user-attachments/assets/9a405360-1c16-43fc-b0f5-d465bd01ba17)
In this step, keep **Role-based or feature hand-installation** selected, then click **Next** on this window as well as the next window
We will be adding the following **Active Directory Domain Services**, **DHCP Server**, **DNS Server**,**Print and Document Services**, and **Web Server (IIS)** then click **Add Features** then click **Continue**
Finally click **Next**
In the next window, ensure **Group Policy Management** is selected, then continue to click **Next** until the **Install** button shows up; click **Install** 

Refer to the picture below. This is how your server manager should look:
If your server manager looks like the picture below, then we are going to reboot our virtual machine by clicking the **Power** button in the bottom left-hand corner then click **Restart** then click **Continue** 
![Server Manager](https://github.com/user-attachments/assets/32c20517-b8ca-428d-9076-022325460f23)


### Step 10: Deleting/ Deallocating Resources
In this step, we will click **Home**, then click on your Resources Group. Refer to the picture below:
![Deleting/Deallocating Resources](https://github.com/user-attachments/assets/b5926df9-1012-4e89-89c0-aaea0b3c6aa5)
The picture below click **Delete Resource Group** then type what your resource group is to be deleted in the bottom where it says **Enter resource group name to confirm deletion**, then finally click **Delete**
![Deleting/Deallocating Resources Cont.](https://github.com/user-attachments/assets/fdfb8b3f-252a-43cb-9912-3f9e8993b89a)





Resources:

portal.azure.com

https://www.youtube.com/@Jakestechjourney (Build IT Lab Series)









