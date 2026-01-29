# 📚 Kütüphane Yönetim Sistemi

Bu proje, **C programlama dili** kullanılarak geliştirilmiş, **dosya tabanlı bir Kütüphane Yönetim Sistemi**dir.  
Sistem; kitapların takibini, ödünç alma ve iade süreçlerini, kullanıcı yönetimini ve gecikme kontrollerini **kalıcı veri depolama (persistent storage)** yöntemiyle gerçekleştirir.

Veriler RAM üzerinde geçici olarak tutulmak yerine `.txt` dosyalarında saklanır ve program kapatılsa dahi korunur.

---

## 🚀 Proje Hakkında

Bu uygulama, gerçek hayattaki bir kütüphane sisteminin temel işleyişini simüle etmek amacıyla geliştirilmiştir.  
Sistem içerisinde **Admin** ve **Kullanıcı (Öğrenci/Personel)** olmak üzere iki farklı yetki seviyesi bulunmaktadır.

### Öne Çıkan Teknik Özellikler

- **Struct Yapıları:** Kitap ve kullanıcı verileri için özel veri yapıları
- **Dosya İşlemleri (File I/O):** `fopen`, `fscanf`, `fprintf` kullanılarak dosya tabanlı veri yönetimi
- **Zaman Yönetimi:** `time.h` kütüphanesi ile otomatik teslim tarihi hesaplama
- **Gecikme Kontrolü:** Süresi geçen kitapların tespit edilmesi
- **Dinamik Arama:** Kitap adı, yazar veya kategoriye göre (büyük/küçük harf duyarsız) arama
- **Yetkilendirme:** Rol tabanlı sistem (Admin / Kullanıcı)

---

## ⚙️ Özellikler

Sistem iki ana modülden oluşmaktadır:

### 1️⃣ Admin Modülü

- Sisteme yeni kullanıcı ekleme (öğrenci veya personel)
- Kütüphaneye kitap ekleme ve silme
- Teslim tarihi geçen kitapları ve sorumlu kullanıcıları görüntüleme
- Tüm kitapları ve kullanıcıları detaylı şekilde listeleme

---

### 2️⃣ Kullanıcı Modülü

- Kitap arama (isim, yazar veya kategoriye göre)
- Kitap ödünç alma  
  - En fazla **3 kitap**
  - Ödünç süresi **15 gün**
- Kitap iade etme ve stok durumunu güncelleme
- Profil görüntüleme:
  - Üzerindeki kitaplar
  - Teslim tarihleri

---

## 💻 Kurulum ve Çalıştırma

Projeyi çalıştırabilmek için sisteminizde bir **C derleyicisi (GCC)** bulunmalıdır.

### 1️⃣ Projeyi İndirin veya Klonlayın
	```bash
	git clone https://github.com/kullaniciadi/kutuphane-yonetim-sistemi.git
	cd kutuphane-yonetim-sistemi

### 2️⃣ Derleme (Compile)
	```bash
	gcc main.c -o kutuphane_sistemi
	
### 3️⃣ Çalıştırma (Run)
	```bash
	./kutuphane_sistemi      # macOS / Linux
	kutuphane_sistemi.exe   # Windows

## 📂 Dosya Yapısı ve Veri Formatı

Sistem, veri saklamak için metin dosyalarını kullanır.
Dosya okuma sırasında hata oluşmaması için metin alanlarındaki boşluklar "_" (alt çizgi) karakteri ile değiştirilmiştir.

### users.txt (Kullanıcı Veritabanı)

Format:
ID | KullanıcıAdı | Şifre | Rol | Kitap1_ID | Kitap2_ID | Kitap3_ID

Örnek:
1 admin admin123 admin -1 -1 -1
2 beyza 12345 ogrenci 3 3 -1

### books.txt (Kitap Veritabanı)

Format:
ID | KitapAdı | Yazar | Kategori | Durum(0/1) | AlanKullanıcıID | TeslimTarihi

Örnek:
3 suc_ve_ceza dostoyevski roman 1 5 08/06/2025

---

## 🔐 Test Giriş Bilgileri

Rol: Admin
Kullanıcı Adı: admin
Şifre: admin123

Rol: Öğrenci
Kullanıcı Adı: beyza
Şifre: 12345

---

## 🛠 Geliştirme Planları (To-Do)

- Veritabanı entegrasyonu (SQLite veya MySQL)
- Grafiksel Kullanıcı Arayüzü (GUI)
- Şifrelerin hashlenerek saklanması (MD5 / SHA-256)
- Dosya işlemleri için gelişmiş hata yakalama (error handling)

---

## 📝 Lisans

Bu proje MIT Lisansı altında sunulmuştur.
Eğitim amaçlı geliştirilmiştir.

---

## 👩‍💻 Geliştirici

Beyza  Nur Ulukuş
Kocaeli Üniversitesi – Yazılım Mühendisliği








