# 01. Renaming Hostname and Initial Preparations

## 📌 Overview
In this step, we updated the default randomized and complex server name (`WIN-V3IN303QSAS`) assigned after the Windows Server installation to **DC01** in accordance with enterprise Naming Conventions.

---

## ❓ How Do We Decide on Server Names? (Naming Convention)
In enterprise IT infrastructures, server names are never left to chance. The following standards are followed when determining server names:

* **Role-Based Naming:** Refers to the primary function performed by the server.
  * `DC` = Domain Controller (Identity Management Server)
  * `FS` = File Server (Data Sharing Server)
  * `EXCH` = Exchange Server (Email Server)
* **Sequence Number:** Since multiple servers can exist under the same role, a sequence number is appended (`DC01`, `DC02`).
* **Location / Region Code (Optional):** In larger infrastructures, city or data center codes are added (e.g., `IST-DC01`).

### 🎯 Why Did We Choose `DC01`?
Since this server will act as the primary **Domain Controller** for the **Dunder Mifflin** environment, we chose **DC01** to reflect its role and primary server status.

---

## 🛠️ Methods to Rename Hostname

### Method 1: Via Server Manager (GUI / Interface)
1. Navigate to the **Local Server** tab on the left menu of the **Server Manager** dashboard.
2. Click on the default name (`WIN-XXXXX`) in the **Computer name** field.
3. In the opened **System Properties** window, click the **Change...** button.
4. Type **DC01** in the **Computer name** field and click **OK**.
5. Restart the server for the changes to take effect.

![System Properties Change](../images/01-hostname-update-2.png)
---

### Method 2: Via PowerShell (Fast Method)
Execute a single command in an elevated PowerShell terminal to rename the server and restart the system automatically:

```powershell
Rename-Computer -NewName "DC01" -Restart
```
---
## 🔍 Verification of Changes
After the server restarts, run the following command in PowerShell or CMD terminal to verify that the new name is active:
```powershell
hostname
```
![System Properties Change](../images/01-hostname-update-3.png)
