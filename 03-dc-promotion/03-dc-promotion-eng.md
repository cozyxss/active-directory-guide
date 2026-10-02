# 03. Domain Controller Promotion & Forest Configuration

## 📌 Overview
In this step, the Windows Server (DC01) with the installed AD DS role was formally promoted to a **Domain Controller**, establishing a brand-new Active Directory Forest named `dundermifflin.local`.

---

## ❓ Technical Concepts & Notes

### 1. Forest Deployment Options
Explanation and use cases for the 3 core options in the Domain Controller Promotion Wizard:

* **Add a new forest:**
  * **Meaning:** Creates the first Active Directory infrastructure from scratch when no AD exists.
  * **Example:** Used when setting up the initial DC for a new company or isolated lab environment (`dundermifflin.local`). *(Option selected for this lab)*

* **Add a domain controller to an existing domain:**
  * **Meaning:** Adds a secondary/backup Domain Controller to an established domain.
  * **Example:** Used when adding `DC02` alongside `DC01` for high availability and redundancy.

* **Add a new domain to an existing forest:**
  * **Meaning:** Creates a new child domain/branch under an existing parent organization structure.
  * **Example:** Adding `europe.dundermifflin.local` under the parent `dundermifflin.local` domain.

---

### 2. DSRM (Directory Services Restore Mode) Password
* **What is it?** A safe mode boot environment used for Active Directory database maintenance and disaster recovery.
* **Why is it important?** If the AD database corrupts or fails, the server is booted into DSRM. The standard Domain Administrator password will not work here; access requires this specific DSRM password defined during setup.

---

### 3. Automatically Created Files & Folders
During promotion, 3 critical system structures are generated:

* **`NTDS` Folder (`NTDS.dit`):** The primary database file for Active Directory containing all users, computers, and hashed credentials.
* **`NTDS Logs`:** Transaction logs that temporarily store database modifications before committing.
* **`SYSVOL` Folder:** A shared network directory accessible by all domain clients and servers. It stores Group Policy Objects (GPOs) and login scripts, replicating across all DCs.

---

## 🛠 Installation Methods

### Method 1: Promotion via Server Manager (GUI)
1. Click the notification flag in Server Manager and select **Promote this server to a domain controller**.
2. Under Deployment Configuration, select **Add a new forest** and enter `dundermifflin.local` as the Root domain name.
3. In Domain Controller Options, set the DSRM password (ensuring DNS Server and Global Catalog remain checked).
4. Confirm NetBIOS domain name (`DUNDERMIFFLIN`) and default file paths (`NTDS`, `SYSVOL`).
5. Complete the Prerequisites Check and click **Install**. The server will reboot automatically upon completion.

---

### Method 2: Promotion via PowerShell (Fast Method)
Execute the following command in an elevated PowerShell terminal:

```powershell
Import-Module ADDSDeployment
Install-ADDSForest `
    -CreateDnsDelegation:$false `
    -DatabasePath "C:\Windows\NTDS" `
    -DomainMode "WinThreshold" `
    -DomainName "dundermifflin.local" `
    -DomainNetbiosName "DUNDERMIFFLIN" `
    -ForestMode "WinThreshold" `
    -InstallDns:$true `
    -LogPath "C:\Windows\NTDS" `
    -SysvolPath "C:\Windows\SYSVOL" `
    -Force:$true
```
---

## 🔍 Verification
Once restarted, verify logon screen displays DUNDERMIFFLIN\Administrator. Open PowerShell and run:

 ```powershell
Get-ADDomain
```
