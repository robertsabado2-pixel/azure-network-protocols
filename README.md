<p align="center">
<img width="1360" height="700" alt="image" src="https://github.com/user-attachments/assets/0ccfa4b5-c11f-483c-b323-2d52e75e34fb" />
  

</p>

# Preparing Active Directory Infrastructure in Azure

This project demonstrates setting up the foundational infrastructure for an **Active Directory (AD) lab** in Microsoft Azure.  
The lab includes creating resource groups, virtual networks, domain controller and client VMs, configuring networking and DNS, and verifying connectivity.

---

## 🖥️ Environment & Technologies Used

- Microsoft Azure (Cloud Infrastructure)  
- Windows Server 2022 (Domain Controller)  
- Windows 10 Pro (Client VM)  
- Active Directory Domain Services  
- DNS Configuration  
- Resource Groups and Virtual Networks in Azure  

---

## 📌 Project Overview

In this lab, I:

- Created a Resource Group and Virtual Network in Azure  
- Deployed two VMs:  
  - **DC-1** (Domain Controller, Windows Server 2022)  
  - **Client-1** (Client Machine, Windows 10 Pro)  
- Configured static private IP for the Domain Controller  
- Disabled Windows Firewall on the Domain Controller  
- Updated client DNS to point to the Domain Controller  
- Verified connectivity with `ping` and `ipconfig /all`  

This setup prepares the lab environment for domain joining and further Active Directory exercises.

---

## ⚙️ Step-by-Step Setup

### Step 1: Create Resource Group & Virtual Network

- Create a **Resource Group** named e.g., `Active Directory Lab` in your region (East US 2 recommended).  
- Create a **Virtual Network** named e.g., `active-directory-vnet` and attach it to your Resource Group.

<p align="center">
<img width="673" height="574" alt="Screenshot 2026-03-03 163002" src="https://github.com/user-attachments/assets/914881f5-12c2-44fd-bf85-93158d343d5d" />

</p>

---

### Step 2: Deploy Virtual Machines

**Domain Controller (DC1)**  
- OS: Windows Server 2022  
- Name: DC-1  
- Set username/password  

**Client Machine (Client1)**  
- OS: Windows 10 Pro  
- Name: client-1  
- Use same credentials as DC1  

Both VMs are in the same Resource Group and Virtual Network.

<p align="center">
<img width="1759" height="1019" alt="Screenshot 2026-03-03 163444" src="https://github.com/user-attachments/assets/8f34b181-287c-47f1-afba-56c6d4d36349" />

</p>

---

### Step 3: Configure Networking

- Set **DC1’s private IP** to static (ensures DNS reliability)  
- Disable Windows Firewall on DC1 (lab/testing purposes)  

<p align="center">
⬇️⬇️⬇️ REPLACE THIS WITH YOUR SCREENSHOT ⬇️⬇️⬇️  
`screenshots/ad-dc-network.png`
</p>

---

### Step 4: Configure DNS on Client VM

- On Client-1, set the **DNS server** to DC1’s private IP (not Azure’s default DNS)  
- Restart the client VM to apply changes  

<p align="center">
⬇️⬇️⬇️ REPLACE THIS WITH YOUR SCREENSHOT ⬇️⬇️⬇️  
`screenshots/ad-client-dns.png`
</p>

---

### Step 5: Verify Connectivity

- Log into Client-1 and ping DC1’s private IP  
- Run `ipconfig /all` on the client to confirm DNS is pointing to DC1  

<p align="center">
⬇️⬇️⬇️ REPLACE THIS WITH YOUR SCREENSHOT ⬇️⬇️⬇️  
`screenshots/ad-verification.png`
</p>

---

## ✅ Key Points Learned

- The Domain Controller acts as both AD and DNS server  
- Correct DNS configuration on the client is critical for domain joining  
- Static IP for the DC ensures clients retain connectivity even after restarts  
- Disabling Windows Firewall on DC is for ease of testing in a lab environment  

---

## 🔐 Skills Demonstrated

- Azure Resource Group and Virtual Network configuration  
- VM deployment and management in Azure  
- Windows Server 2022 Domain Controller setup  
- DNS configuration for AD environment  
- Client machine network setup for domain joining  
- Verification of network and DNS connectivity
