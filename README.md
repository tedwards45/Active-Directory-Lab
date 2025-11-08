# Lab 1: Active Directory Setup in Azure  
**Created by:** Terrence Edwards  

---

## 🧠 Overview
As part of my ongoing education in **Digital Forensics and Cybersecurity**, this lab demonstrates how to create and manage a **Windows Server environment** within **Microsoft Azure**.  
You will learn how to:
- Set up a Windows Server Virtual Machine (VM)
- Configure Active Directory and key server roles
- Create users and groups
- Securely connect using Azure Bastion
- Deallocate resources to minimize costs

---

## ⚙️ Phase 1: Setting Up the Windows Server VM in Azure  

### Step 1: Create an Azure Account
If you don’t already have one, go to [portal.azure.com](https://portal.azure.com) and sign in or create a free account.  
Then, click **Create a Resource**, choose **Virtual Machine**, and proceed to set up your environment.

---

### Step 2: Create a New Resource Group
![Create a Resource Group](https://github.com/user-attachments/assets/0e03a3a1-a3a7-494e-a779-6b314938df73)
![Creating New Resource Group](https://github.com/user-attachments/assets/c41df9b4-bdd6-4f51-80de-4ba35e233c42)

Click **Create a Resource** to make a **Resource Group** that will contain your Windows Server VM and related resources.

- Example names:
  - **VM Name:** `labIT`
  - **Resource Group Name:** `lab-test`

> **Note:** Names can vary — just ensure they meet Azure’s naming criteria.

Choose the image **Windows Server 2022 Datacenter: Azure Edition Hotpatch - x64 Gen2**.

> **Tip:** The price shown is an estimate — you won’t be charged if you delete your resource group after each use.

---

### Step 3: Image in Use
![Image in Use](https://github.com/user-attachments/assets/f5e0147e-b8a8-4874-a960-f4eb0ec4962c)

Confirm that the correct Windows Server image is selected before continuing.

---

### Step 4: Select None for Public Ports
![Select None for Public inbound ports](https://github.com/user-attachments/assets/d6edbadf-fb2d-4373-90bb-f6f176eab568)

When configuring network settings, set **Public inbound ports** to **None**.  
This helps secure your VM by preventing direct access from the internet.  
Click **Review + Create** when done.

---

### Step 5: Deploying Bastion 
![Deploying Bastion](https://github.com/user-attachments/assets/db609bfc-906d-41e5-8435-62113a333b97)

Deploying **Azure Bastion** provides secure access to your VM without exposing it to the public internet.

- **RDP (Remote Desktop Protocol):** Allows remote access to Windows servers through a graphical interface.  
- **SSH (Secure Shell):** Enables secure command-line connections to Linux systems.  

> **Bastion** acts as a managed host within your subnet, ensuring protected, browser-based connectivity.

---

### Step 6: Setting a Static IP 
![Setting a Static IP](https://github.com/user-attachments/assets/3b0ed3bd-f1d3-4973-8f9f-f4db2c799d82)

1. Go to **Network Settings** → **Network interface/IP configuration**.  
2. Select **ipconfig** under **Private IP addresses**.  
3. Change **IP assignment** to **Static**, then click **Save**.

---

### Step 7: Connecting via Bastion 
![Connecting via Bastion](https://github.com/user-attachments/assets/5e896525-4145-4b16-bb34-a505b7f21c24)
![Connecting via Bastion-Credentials](https://github.com/user-attachments/assets/fac75309-a4ff-442a-a0dd-a48146d6c021)

To connect to your VM:
1. Select **Bastion** on your VM’s overview page.  
2. Enter the **username** and **password** you set when creating your VM.  
3. Click **Connect**.

---

### Step 8: Disable Server Manager Auto-Start
![Turning Off Server Manager (Auto)](https://github.com/user-attachments/assets/ec0baea2-c6f2-4a11-bfb5-b6f88a70d417)

To stop Server Manager from opening every time you log in:
1. Click **Manage** → **Server Manager Properties**.  
2. Check **Do not start Server Manager automatically at login**.  

![Turning Off Server Manager (Auto) Cont.](https://github.com/user-attachments/assets/82e89679-b947-43f5-a7ec-a2e1b034082f)

---

### Step 9: Installing Roles and Features
![Installing Roles and Features](https://github.com/user-attachments/assets/19e3d33e-3501-4ea3-98b1-2b98c203ee37)

Click **Manage** → **Add Roles and Features** to open the setup wizard.

![Installing Roles and Features Cont.](https://github.com/user-attachments/assets/ab105365-7d81-4e82-86f0-bd668478ac2d)
Click **Next** to continue.

![Installing Roles and Features Cont.](https://github.com/user-attachments/assets/9a405360-1c16-43fc-b0f5-d465bd01ba17)
Keep **Role-based or feature-based installation** selected, then click **Next** on this window and the next one.

Add the following roles:
- **Active Directory Domain Services**
- **DHCP Server**
- **DNS Server**
- **Print and Document Services**
- **Web Server (IIS)**

Click **Add Features** → **Continue** → **Next**.  
Under **Features**, ensure **Group Policy Management** is selected.  
Click **Next** until you see the **Install** button, then select **Install**.

After installation completes, your Server Manager should resemble the example below:

![Server Manager](https://github.com/user-attachments/assets/32c20517-b8ca-428d-9076-022325460f23)

Finally, **restart your virtual machine**:
- Click the **Power** button (bottom left) → **Restart** → **Continue**.  

> **Note:** Rebooting ensures that all installed roles and configurations apply successfully.

---

### Step 10: Deleting / Deallocating Resources
![Deleting/Deallocating Resources](https://github.com/user-attachments/assets/b5926df9-1012-4e89-89c0-aaea0b3c6aa5)

To prevent unnecessary charges:
1. Go to your **Home** dashboard in Azure.  
2. Select your **Resource Group**.  
3. Click **Delete Resource Group**.  
4. Type the name of your resource group to confirm, then click **Delete**.

![Deleting/Deallocating Resources Cont.](https://github.com/user-attachments/assets/fdfb8b3f-252a-43cb-9912-3f9e8993b89a)

---

## 🧩 Resources
- [Azure Portal](https://portal.azure.com)  
- [Jake’s Tech Journey - Build IT Lab Series](https://www.youtube.com/@Jakestechjourney)

---

## 🎯 Summary: What You Learned
By completing this lab, you’ve successfully:
- Created and configured a Windows Server VM in Azure  
- Used **Azure Bastion** for secure, browser-based RDP/SSH access  
- Installed and configured essential roles: **AD DS**, **DNS**, **DHCP**, **IIS**, and **GPMC**  
- Managed static IP settings and server startup configurations  
- Learned cost management best practices through resource deallocation  

> ✅ This lab builds the foundation for setting up and managing **Active Directory environments** within the Azure cloud.











