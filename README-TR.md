# Active Directory Rehberi

[ENG] [Click here for English README](README.md)

> *Windows Server 2022 Active Directory kurulumumdan notlar, rehberler, TikTok videoları ve scriptler.*

---

## 📌 Bu Repo Ne Hakkında?
Bu repo benim öğrenme sürecimi paylaştığım açık not defterimdir:
- ✍️ **Lab Notları:** Süreç boyunca kullandığım adım adım rehberler ve komutlar.
- 🎬 **Video Linkleri:** Notlarla doğrudan bağlantılı TikTok videoları.
- ⚡ **PowerShell Scriptleri:** İleride yapmayı planladığım otomasyon araçları (toplu kullanıcı oluşturma, temizlik scriptleri vb.).

---

## 🧪 Mevcut Lab Kurulumu
- **Sanallaştırma (Hypervisor):** VirtualBox
- **Domain Controller:** Windows Server 2022 (`DC01`)
- **Domain (Alan Adı):** `medipolis.local`
- **İstemciler (Clients):** Windows 10/11 (`CLIENT01`)

---

## 📚 Lab Notları ve İlerleme

| Adım | Konu / Modül | İçerik & Açıklama | Notlar (ENG / TR) | TikTok Videosu |
| :---: | :--- | :--- | :---: | :---: |
| **00** | **Server IP Ayarları** | Statik IP, Subnet, Gateway ve DNS Loopback (`127.0.0.1`) kurulumu. | [English](./00-server-ip-setup/server-ip-setup-eng.md) / [Türkçe](./00-server-ip-setup/server-ip-setup-tr.md) | [İzle 🎬](https://www.tiktok.com/@cozyxss/video/7688731015560334613?is_from_webapp=1&sender_device=pc) |
| **01** | **Hostname & Prep** | Sunucu adını `DC01` yapma, güncellemeler ve ilk hazırlıklar. |[English](./01-hostname-update/01-hostname-update-eng.md) / [Türkçe](./01-hostname-update/01-hostname-update-tr.md) | [İzle 🎬](https://www.tiktok.com/@cozyxss/video/7690963596574018822) |
| **02** | **AD DS Kurulumu** | Active Directory Domain Services rolünün Server Manager ile yüklenmesi. | *Hazırlanıyor... 🔄* | Yakında |
| **03** | **DC Promotion** | Yeni Forest (`medipolis.local`) oluşturma, DSRM şifresi ve SYSVOL kontrolleri. | *Hazırlanıyor... 🔄* | Yakında |
| **04** | **DNS & DHCP Setup** | Forward/Reverse Lookup Zone, DHCP Scope (`192.168.10.X`) ve Option ayarları. | *Planlanıyor ⏳* | Yakında |
| **05** | **İstemci Hazırlığı** | Windows 10/11 IP/DNS yönlendirmesi ve `nslookup` / `ping` testleri. | *Planlanıyor ⏳* | Yakında |
| **06** | **Domain Join** | `CLIENT01` istemcisini domaine ekleme ve doğrulama adımları. | *Planlanıyor ⏳* | Yakında |
| **07** | **OU Hiyerarşisi** | ADUC üzerinde katmanlı OU mimarisi (`IT`, `HR`, `Finance`, `Computers`). | *Planlanıyor ⏳* | Yakında |
| **08** | **Kullanıcı & Gruplar** | RBAC yapısı, Güvenlik Grupları (`SG_IT_Admins`) ve yetki atamaları. | *Planlanıyor ⏳* | Yakında |
| **09** | **Domain Oturumu** | İstemcide domain hesabı ile oturum açma ve kullanıcı profili kontrolleri. | *Planlanıyor ⏳* | Yakında |
| **10** | **Group Policy (GPO)** | GPMC ile duvar kâğıdı sabitleme, parola ve ekran kilit politikaları. | *Planlanıyor ⏳* | Yakında |
| **11** | **Mapped Drives** | Paylaşımlı klasör yetkileri (NTFS/Share) ve GPO ile `Z:\` sürücüsü bağlama. | *Planlanıyor ⏳* | Yakında |
| **12** | **LAPS Entegrasyonu** | İstemci yerel admin şifrelerini AD üzerinde dinamik olarak yönetme. | *Planlanıyor ⏳* | Yakında |
| **13** | **AD Recycle Bin** | Silinen kullanıcı/OU nesnelerini Active Directory Recycle Bin ile kurtarma. | *Planlanıyor ⏳* | Yakında |
| **14** | **Secondary DC & FSMO** | İkinci DC (`DC02`) kurulumu, replikasyon kontrolü ve FSMO rol mantığı. | *Planlanıyor ⏳* | Yakında |

---

## ⚡ PowerShell ve Otomasyon *(Planlanan)*

Temel lab tamamlandıktan sonra günlük AD işlerini otomatikleştirmek için geliştireceğim PowerShell scriptlerini buraya ekleyeceğim.

---

## 🌐 Bana Buradan Ulaşabilirsiniz

- 🎵 **TikTok:** [tiktok.com/@cozyxss](https://www.tiktok.com/@cozyxss) (Kısa ders notları ve videolar)
- ✍️ **Medium:** [medium.com/@cozyxss](https://medium.com/@cozyxss) (Detaylı proje rehberleri)
- 💼 **LinkedIn:** [linkedin.com/in/bbetulkaya](https://linkedin.com/in/bbetulkaya) (Kariyer ve biten projeler)
