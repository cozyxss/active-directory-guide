# 🌐 Windows Server 2022 - Statik IP ve Ağ Ayarları

Windows Server 2022 kurulumunu tamamladıktan sonra yapmamız gereken ilk ve en kritik adım **Statik IP (Sabit IP)** ayarını yapmaktır.

---

## ❓ Neden Statik IP Kullanıyoruz?
Bir sunucunun IP adresi dinamik (DHCP ile otomatik değişen) olamaz. Çünkü bu makine ağdaki diğer cihazlara hizmet verecek. Eğer IP adresi sürekli değişirse, diğer istemciler (bilgisayarlar) sunucuya ulaşamaz ve iletişim kopar.

---

## ⚙️ Yapılandırılan IPv4 Ayarları ve Anlamları

Windows'ta `ncpa.cpl` (Ağ Bağlantıları) üzerinden **IPv4 Properties** ekranına girerek aşağıdaki sabit değerleri atadık:

<img width="397" height="453" alt="image" src="https://github.com/user-attachments/assets/bd4f3642-62fa-4e77-bc55-f9b5ad9bf26a" />


---

## 💡 Kavramlar ve Kısa Açıklamaları

### 1. IP Adresi & IP Aralıkları (`192.168.X.X`)
IP adresleri kullanım alanlarına göre belirli sınıflara (A, B, C) ve aralıklara ayrılır:
* **`10.X.X.X`:** Çok büyük ağlar ve devasa kurumlar içindir.
* **`172.16.X.X` - `172.31.X.X`:** Orta ve büyük ölçekli şirketler/ağlar içindir.
* **`192.168.X.X`:** Küçük ölçekli ağlar, evler ve küçük lab ortamları içindir.

> Biz lab ortamımız için **`192.168.10.10`** IP adresini seçtik.

---

### 2. Alt Ağ Maskesi (Subnet Mask)
Subnet Mask, bulunduğumuz ağda kaç tane cihazın (makinenin) birbiriyle konuşabileceğini belirler:
* **`255.255.255.0` (`/24`):** Bu ağda kullanılabilecek toplam **254** adet kullanılabilir IP adresi vardır. Küçük ağlar için idealdir.
* **`255.255.0.0` (`/16`):** Ağ büyür ve bağlanabilecek cihaz sayısı **65.000'in üzerine** çıkar.

---

### 3. Varsayılan Ağ Geçidi (Default Gateway) — *Ev Adresi Örneği* 🏠
Ağımızdaki cihazların dış dünyaya (İnternete) çıkış kapısıdır.

**💡 Örnek:** Şirket veya ev içinde herkesin kendi odası/ismi vardır (Yerel IP adresi). Ancak kargocu geldiğinde veya dışarıdan bakıldığında hepimizin adresi **binaların dış kapı numarasıdır** (Default Gateway / Dış IP). 
Yerel ağdaki cihazlar kendi aralarında yerel IP'leri ile konuşur, fakat internete çıkmak istediklerinde hepsi Gateway'e (`192.168.10.1`) giderek dış dünyaya adım atarlar.

---

### 4. Tercih Edilen DNS (Preferred DNS)
DNS, IP adresleri ile alan adlarını (domain) birbirine bağlayan bir telefon rehberidir. 

Ayar ekranında DNS kısmına **`127.0.0.1`** (Loopback - Kendisi) yazdık. Çünkü ileride bu Windows Server üzerine **Active Directory** ve **DNS Server** rollerini kuracağız. Sunucunun DNS sorguları için doğrudan kendisine başvurmasını istediğimiz için bu şekilde yapılandırdık.
