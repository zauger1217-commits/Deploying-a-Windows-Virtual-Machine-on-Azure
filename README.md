# SOP: Deploying a Windows Virtual Machine on Azure

## Objective
Successfully provision, configure, and connect to a Windows Server Virtual Machine (VM) using the Azure Portal.

## Prerequisites
- An active Microsoft Azure account
- Access to the Azure Portal: https://portal.azure.com

---

## Phase 1: Project Setup

### 1. Navigate to the Virtual Machine Service
1. Log in to the Azure Portal.
2. In the top search bar, type **Virtual machines** and select the service.
3. Click **+ Create** → **Azure virtual machine**.

### 2. Configure Basic Settings (Basics Tab)
- **Subscription:** Select your active subscription
- **Resource Group:** Create new  
  - Naming convention: `RG-[ProjectName]-[Date]`  
  - Example: `RG-WinServer-Lab-10-25`
- **Virtual Machine Name:** Example: `VM-WinServer-01`
- **Region:** (US) East US (or nearest region)
- **Availability Options:** No infrastructure redundancy required
- **Security Type:** Standard
- **Image:** Windows Server 2019 Datacenter (x64 Gen2) or 2022
- **VM Architecture:** x64
- **Size:**  
  - Recommended for labs: `Standard_B1s` or `Standard_B2s`

### 3. Administrator Account
- **Username:** Example: `azureuser`
- **Password:**  
  - Minimum 12 characters  
  - Uppercase, lowercase, number, and special character required  
- **Action:** Save credentials securely

### 4. Inbound Port Rules
- **Public inbound ports:** Allow selected ports
- **Allowed ports:** RDP (3389)

---

## Phase 2: Disks & Networking

### 5. Disks
- OS Disk Type: Standard SSD (recommended for labs)
- Leave remaining options as default

### 6. Networking
- Virtual Network, Subnet, and Public IP: Auto-created
- NIC Network Security Group: Basic
- Public inbound ports: Allow selected ports (RDP 3389)

---

## Phase 3: Validation & Creation

### 7. Review
- Click **Review + create**
- Wait for **Validation passed**
- Fix any errors if validation fails

### 8. Deploy
- Review pricing estimate
- Click **Create**
- Deployment typically completes in 2–5 minutes

---

## Phase 4: Connecting to the VM

### 9. Access the Resource
- Click **Go to resource** after deployment

### 10. Connect via RDP
1. Click **Connect**
2. Select **Native RDP**
3. Click **Download RDP File**

### 11. Login
1. Open the downloaded `.rdp` file
2. Click **Connect**
3. Choose **More choices** → **Use a different account** if needed
4. Enter admin credentials
5. Accept the certificate warning

You are now logged into your Windows Virtual Machine.

---

## Phase 5: Lab Clean-Up (Important)

### 12. Destroy Resources
1. Go to Azure Portal **Home**
2. Search for **Resource groups**
3. Select your resource group
4. Click **Delete resource group**
5. Type the resource group name to confirm

**Why:** Ensures all resources are deleted to prevent unexpected charges.
