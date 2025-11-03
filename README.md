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

-> Then you want to give your VM & Resource Group a Name: For example, my lab name is **labIT** 


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

