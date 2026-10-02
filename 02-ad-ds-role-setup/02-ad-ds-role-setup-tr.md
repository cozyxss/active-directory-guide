# 02. Active Directory Domain Services (AD DS) Rolünün Kurulumu

## 📌 Genel Bakış
Bu adımda, Windows Server (DC01) üzerinde Active Directory altyapısının temelini oluşturan **Active Directory Domain Services (AD DS)** rolü ve gerekli yönetim araçları yüklenmiştir.

---

## ❓ Ne Nedir? (Teknik Notlar)

### 1. Rol (Role) Nedir?
* Sunucunun üstlendiği **ana iş alanıdır** veya şirketteki **unvanıdır**. 
* Sunucuya bir rol eklendiğinde ona büyük bir yetki ve sorumluluk verilir.
* **Örnekler:** Active Directory Domain Services (AD DS), DNS Server, DHCP Server, File Server.

### 2. Özellik (Feature) Nedir?
* Rollerin çalışmasını destekleyen, sunucuya ek işlevsellik katan **yardımcı araçlar, protokoller veya yazılımlardır**.
* Tek başlarına genelde bir servis sunmazlar, ana rolleri tamamlarlar.
* **Örnekler:** PowerShell modülleri, .NET Framework, Remote Server Administration Tools (RSAT).

### 3. Role-based vs Feature-based Installation Nedir?
* **Role-based (Rol Tabanlı):** Sunucuya doğrudan ana bir servis veya sorumluluk (örn: AD DS) yüklemek istediğimizde tercih edilir.
* **Feature-based (Özellik Tabanlı):** Sunucuya sadece yardımcı bir bileşen veya yönetim aracı ekleneceğinde tercih edilir.
> *Windows Server arayüzünde bu iki seçenek "Role-based or feature-based installation" adı altında birleştirilmiştir.*

---

## 🛠️️ Kurulum Yöntemleri

### Yöntem 1: Server Manager (GUI) ile Kurulum
1. Server Manager ekranından **Manage > Add Roles and Features** seçeneğine girilir.
2. Installation Type adımında **Role-based or feature-based installation** seçilir.
3. Server Selection adımında hedef sunucu olarak **DC01** doğrulanır.
4. Server Roles listesinden **Active Directory Domain Services** işaretlenir ve gerekli yönetim araçları (**Add Features**) eklenir.
5. Confirmation sekmesine kadar ilerlenip **Install** butonuna basılarak kurulum tamamlanır.

![Server Manager AD DS Kurulumu](images/02-ad-ds-setup-1.png)

---

### Yöntem 2: PowerShell ile Kurulum (Hızlı Yöntem)
Yönetici haklarıyla açılan PowerShell terminalinde aşağıdaki komut çalıştırılarak rol ve yönetim araçları yüklenir:

```powershell
Install-WindowsFeature -Name AD-Domain-Services -IncludeManagementTools
```

---

## 🔍 Değişikliğin Doğrulanması (Verification)
Kurulum tamamlandıktan sonra PowerShell üzerinden rolün durumunu kontrol etmek için aşağıdaki komut çalıştırılır:

```powershell
Get-WindowsFeature -Name AD-Domain-Services
```
![Server Manager AD DS Kurulumu](images/02-ad-ds-setup-2.png)
