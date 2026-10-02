# 02. Active Directory Domain Services (AD DS) Role Installation

## 📌 Overview
In this step, the **Active Directory Domain Services (AD DS)** role and its required management tools were installed on Windows Server (DC01).

---

## ❓ Technical Concepts & Notes

### 1. What is a "Role"?
* Refers to the **primary function** or **title** assigned to a server within the network.
* Adding a role equips the server with specific capabilities and responsibilities.
* **Examples:** Active Directory Domain Services (AD DS), DNS Server, DHCP Server, File Server.

### 2. What is a "Feature"?
* Supporting **tools, protocols, or software** that enhance server functionality and assist active roles.
* Features generally do not provide primary services on their own; instead, they complement roles.
* **Examples:** PowerShell modules, .NET Framework, Remote Server Administration Tools (RSAT).

### 3. Role-based vs Feature-based Installation
* **Role-based:** Selected when deploying a primary service or responsibility (e.g., AD DS) directly onto the server.
* **Feature-based:** Selected when adding supporting components or administration utilities.
> *In the Windows Server Wizard, these options are combined under "Role-based or feature-based installation".*

---

## 🛠️ Installation Methods

### Method 1: Via Server Manager (GUI)
1. Navigate to **Manage > Add Roles and Features** in Server Manager.
2. Under Installation Type, select **Role-based or feature-based installation**.
3. Confirm **DC01** as the target server in Server Selection.
4. Check **Active Directory Domain Services** from the Server Roles list and accept the required management tools (**Add Features**).
5. Proceed to the Confirmation tab and click **Install** to complete the process.

![Server Manager AD DS Installation](images/02-ad-ds-setup-1.png)

---

### Method 2: Via PowerShell (Fast Method)
Execute the following command in an elevated PowerShell terminal to install the role along with management tools:

```powershell
Install-WindowsFeature -Name AD-Domain-Services -IncludeManagementTools
```

## 🔍 Verification
After the installation completes, run the following command in PowerShell to verify the status of the role:

```powershell
Get-WindowsFeature -Name AD-Domain-Services
```
![Server Manager AD DS Installation](images/02-ad-ds-setup-2.png)
