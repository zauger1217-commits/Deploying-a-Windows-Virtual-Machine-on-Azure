# 🖥️ Azure Windows Virtual Machine Deployment SOP

This repository provides a **standard operating procedure (SOP)** for deploying, accessing, and cleaning up a **Windows Server Virtual Machine** using the **Azure Portal**.  
It is intended for **labs, learning environments, and basic testing scenarios**.

WATCH ME BUILD IT HERE:
https://www.loom.com/share/e8890da3f9414ac8bfaeff2a70f78535
---

## 📌 Objective

Provision, configure, connect to, and safely decommission a Windows Server Virtual Machine (VM) in Microsoft Azure.

---

## ✅ Prerequisites

- Active **Microsoft Azure account**
- Access to the **Azure Portal**: https://portal.azure.com
- Basic familiarity with Azure navigation

---

## 🚀 Phase 1: Project Setup

### 1️⃣ Navigate to the Virtual Machine Service

1. Log in to the Azure Portal.
2. Use the top search bar to search for **Virtual machines**.
3. Select **Virtual machines**.
4. Click **+ Create** → **Azure virtual machine**.

---

### 2️⃣ Configure Basic Settings (Basics Tab)

| Setting | Value |
|------|------|
| **Subscription** | Your active subscription |
| **Resource Group** | Create new |
| **Naming Convention** | `RG-[ProjectName]-[Date]` |
| **VM Name** | `VM-WinServer-01` |
| **Region** | (US) East US (or nearest region) |
| **Availability Options** | No infrastructure redundancy required |
| **Security Type** | Standard |
| **Image** | Windows Server 2019 or 2022 Datacenter |
| **Architecture** | x64 |
| **Size** | `Standard_B1s` or `Standard_B2s` (recommended for labs) |

> 💡 **Tip:** B‑series VMs are cost‑effective and ideal for lab environments.

---

### 3️⃣ Administrator Account

- **Username:** Example: `azureuser`
- **Password Requirements:**
  - Minimum 12 characters
  - Uppercase, lowercase, number, and special character
- **Best Practice:** Store credentials in a password manager

---

### 4️⃣ Inbound Port Rules

- **Public inbound ports:** Allow selected ports
- **Allowed port:** `RDP (3389)`

---

## 💾 Phase 2: Disks & Networking

### 5️⃣ Disks

- **OS Disk Type:** Standard SSD (recommended for labs)
- Leave remaining settings as default

---

### 6️⃣ Networking

- Virtual Network, Subnet, and Public IP: Auto-created
- **NIC Network Security Group:** Basic
- **Public inbound ports:** Allow selected ports (RDP 3389)

---

## ✔️ Phase 3: Validation & Creation

### 7️⃣ Review

1. Click **Review + create**
2. Wait for **Validation passed**
3. Fix any highlighted errors if validation fails

---

### 8️⃣ Deploy

- Review the estimated hourly cost
- Click **Create**
- Deployment usually completes in **2–5 minutes**

---

## 🔐 Phase 4: Connect to the VM

### 9️⃣ Access the Resource

- Click **Go to resource** after deployment completes

---

### 🔟 Connect via RDP

1. Click **Connect**
2. Select **Native RDP**
3. Click **Download RDP File**

---

### 1️⃣1️⃣ Login

1. Open the downloaded `.rdp` file
2. Click **Connect**
3. Select **More choices → Use a different account** (if prompted)
4. Enter the admin credentials
5. Accept the certificate warning

✅ You are now logged into your Windows Virtual Machine.

---

## 🧹 Phase 5: Lab Clean‑Up (CRITICAL)

### 1️⃣2️⃣ Destroy Resources

> ⚠️ **Never leave lab resources running when not in use**

1. Go to **Azure Portal → Home**
2. Search for **Resource groups**
3. Select your created resource group
4. Click **Delete resource group**
5. Type the resource group name to confirm
6. Click **Delete**

### 💡 Why This Matters

Deleting the resource group removes:
- Virtual Machine
- OS Disk
- Public IP
- Virtual Network

This ensures **no unexpected Azure charges**.

---

## 📘 Notes

- This SOP is designed for **learning and lab use**
- Not recommended for production deployments without additional security hardening
- Consider using **Azure Bastion** or **Just‑In‑Time access** for production

---

## 🧾 License

This documentation is provided for educational purposes.  
Use and modify freely.

