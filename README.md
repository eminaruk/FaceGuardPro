# FaceGuardPro v3.0 Kurulum Rehberi

FaceGuardPro v3.0'a hoş geldiniz! Yapay zeka destekli akıllı güvenlik sistemi ile ev, ofis ve işyeri güvenliğinizi üst seviyeye taşıyın.

---

## Yeni Özellikler (v3.0)

| Özellik | Açıklama |
|---------|----------|
| **Hibrit Tanıma** | Yüz + Vücut + İskelet birleşik tanıma sistemi |
| **6 Dil Desteği** | Türkçe, İngilizce, Almanca, Fransızca, İspanyolca, Arapça |
| **Obje Tespiti** | 15 farklı obje kategorisi (araç, hayvan, eşya) |
| **Bebek Bakıcılığı** | Bölge tabanlı hareket algılama ve bildirim |
| **Gelişmiş Bildirimler** | Telegram ile anlık fotoğraflı uyarılar |
| **Çoklu Cihaz** | Tek hesapla 3 cihaza kadar kullanım |

---

## İçindekiler

1. [Windows Kurulumu](#windows-kurulumu)
2. [Linux Kurulumu](#linux-kurulumu)
3. [macOS Kurulumu](#macos-kurulumu)
4. [Özellikler](#özellikler)
5. [Sorun Giderme](#sorun-giderme)
6. [Sistem Gereksinimleri](#sistem-gereksinimleri)

---

## Windows Kurulumu

### Kurulum Adımları

1. **Setup Dosyasını İndirin**
   - [`FaceGuardPro_v3.0_setup.exe`](https://github.com/eminaruk/FaceGuardPro/releases/download/v3.0/FaceGuardPro_v3.0_setup.exe) dosyasını indirin

2. **Kurulumu Başlatın**
   - Setup dosyasına çift tıklayın
   - Windows SmartScreen uyarısı alırsanız:
     - "More info" (Daha fazla bilgi) seçeneğine tıklayın
     - "Run anyway" (Yine de çalıştır) butonuna basın

3. **Kurulum Sihirbazı**
   - Dil seçimini yapın (Türkçe önerilir)
   - Kurulum konumunu seçin (varsayılan bırakmanız önerilir)
   - "İleri" butonlarına tıklayarak kurulumu tamamlayın
   - Masaüstü kısayolu oluşturulmasını tercih edebilirsiniz

4. **İlk Çalıştırma**
   - Kurulum tamamlandığında "FaceGuardPro'yu Başlat" seçeneğini işaretleyip "Bitir" butonuna basın
   - VEYA Masaüstü kısayolundan veya Başlat Menüsünden çalıştırın

### Güncelleme (v2.0'dan v3.0'a)

Eğer FaceGuardPro v2.0 zaten yüklüyse:
- Setup dosyasını çalıştırın
- "Güncellemek istiyor musunuz?" sorusuna "Evet" deyin
- Mevcut ayarlarınız ve kayıtlı yüzleriniz korunacaktır

### Windows Defender SmartScreen Uyarısı Çözümü

**Seçenek 1: Geçici Olarak İzin Verme**
```
"More info" (Daha fazla bilgi) linkine tıklayın
"Run anyway" (Yine de çalıştır) butonuna basın
```

**Seçenek 2: Dosyayı Güvenli Listesine Ekleme**
```
Setup dosyasına sağ tıklayın
"Properties" (Özellikler) seçin
En altta "Unblock" (Engeli kaldır) kutucuğunu işaretleyin
"Apply" → "OK" butonlarına basın
```

### Kaldırma

**Kontrol Paneli Üzerinden**
```
Kontrol Paneli → Programs → Programs and Features
"FaceGuardPro" → Sağ tık → "Uninstall"
```

**Ayarlar Üzerinden (Windows 10/11)**
```
Settings → Apps → Apps & features
"FaceGuardPro" → "Uninstall"
```

---

## Linux Kurulumu

> **Not:** Linux v3.0 build'i yakında yayınlanacaktır.

### Kurulum Adımları

1. **ZIP Dosyasını İndirin**
   - [`linux_faceguard_setup.zip`](https://github.com/eminaruk/FaceGuardPro/releases) dosyasını indirin

2. **ZIP'i Açın ve Kurun**
   ```bash
   unzip FaceGuardPro_Linux.zip
   cd FaceGuardPro/
   chmod +x install.sh
   sudo ./install.sh
   ```

3. **Uygulamayı Başlatın**
   ```bash
   /opt/FaceGuardPro/FaceGuardPro
   ```
   Veya uygulama menüsünden: Applications → FaceGuardPro

### Kamera İzni
```bash
sudo usermod -a -G video $USER
# Oturumu kapatıp tekrar açın
```

### Kaldırma
```bash
sudo ./uninstall.sh
```

---

## macOS Kurulumu

> **Not:** macOS v3.0 build'i yakında yayınlanacaktır.

### Kurulum Adımları

1. **ZIP Dosyasını İndirin**
   - [`macos_faceguard_setup.zip`](https://github.com/eminaruk/FaceGuardPro/releases) dosyasını indirin

2. **ZIP'i Açın ve Quarantine Kaldırın**
   ```bash
   unzip FaceGuardPro_macOS.zip
   xattr -cr FaceGuardPro
   ```

3. **Uygulamayı Başlatın**
   - FaceGuardPro dosyasına SAĞ TIKLAYIN → "Open" seçin
   - Güvenlik uyarısında tekrar "Open" butonuna basın

### "Unidentified Developer" Uyarısı Çözümü

1. Uygulamaya SAĞ TIKLAYIN (çift tıklamayın)
2. "Open" seçeneğine tıklayın
3. Güvenlik uyarısında "Open" butonuna basın

### Kamera İzni
```
System Preferences → Security & Privacy → Privacy → Camera
✓ FaceGuardPro'yu işaretleyin
```

---

## Özellikler

### Tanıma Modları

| Mod | Açıklama |
|-----|----------|
| **Yüz Tanıma** | Gerçek zamanlı yüz tespiti ve tanıma |
| **Hibrit Tanıma** | Yüz + Vücut + İskelet birleşik tanıma |
| **Vücut Tanıma** | Kıyafet ve vücut özelliklerine göre tanıma |
| **İskelet Tanıma** | Vücut oranlarına göre tanıma |
| **Obje Tespiti** | 15 farklı obje kategorisi tespiti |

### Güvenlik Modları

- **Güvenlik Modu:** Giriş-çıkış takibi ve bildirim
- **Bebek Bakıcılığı Modu:** Bölge tabanlı hareket algılama
- **Obje Tespiti Modu:** Araç, hayvan, eşya tespiti

### Desteklenen Kameralar

| Tür | Format |
|-----|--------|
| USB Webcam | Otomatik tespit |
| IP Kamera | RTSP stream |
| HTTP Stream | MJPEG |

### Telegram Bildirimleri

1. [@BotFather](https://t.me/BotFather) ile bot oluşturun
2. [@userinfobot](https://t.me/userinfobot) ile Chat ID'nizi öğrenin
3. Ayarlar → Telegram bölümüne bilgileri girin

### Dil Desteği

Türkçe, English, Deutsch, Français, Español, العربية

---

## Sorun Giderme

### Uygulama açılmıyor

- Antivirüs yazılımını geçici olarak devre dışı bırakın
- Dosyaları tekrar indirin
- Sistemi yeniden başlatın

### Kamera bulunamıyor

- Kameranın başka uygulama tarafından kullanılmadığını kontrol edin
- Kamera iznini kontrol edin
- USB kamera için farklı port deneyin

### Firebase bağlantı hatası

- İnternet bağlantınızı kontrol edin
- Firewall ayarlarını kontrol edin
- VPN kullanıyorsanız devre dışı bırakın

### Windows: "VCRUNTIME140.dll not found"

Microsoft Visual C++ Redistributable indirin:
https://aka.ms/vs/17/release/vc_redist.x64.exe

### macOS: "Damaged and can't be opened"

```bash
xattr -cr FaceGuardPro.app
```

### macOS: Apple Silicon (M1/M2)

```bash
softwareupdate --install-rosetta
```

---

## Sistem Gereksinimleri

### Windows

| Gereksinim | Minimum | Önerilen |
|------------|---------|----------|
| İşletim Sistemi | Windows 10 (64-bit) | Windows 11 |
| İşlemci | Intel Core i3 | Intel Core i5+ |
| RAM | 4 GB | 8 GB |
| Disk Alanı | 2 GB | 4 GB |
| İnternet | Gerekli | - |

### Linux

| Gereksinim | Minimum | Önerilen |
|------------|---------|----------|
| İşletim Sistemi | Ubuntu 20.04+ | Ubuntu 22.04+ |
| İşlemci | Intel Core i3 | Intel Core i5+ |
| RAM | 4 GB | 8 GB |
| Disk Alanı | 2 GB | 4 GB |

### macOS

| Gereksinim | Minimum | Önerilen |
|------------|---------|----------|
| İşletim Sistemi | macOS 10.15+ | macOS 12+ |
| İşlemci | Intel veya M1/M2 | Apple Silicon |
| RAM | 4 GB | 8 GB |
| Disk Alanı | 2 GB | 4 GB |

---

## Destek ve İletişim

- **X (Twitter):** [@eminarukk](https://x.com/eminarukk)
- **LinkedIn:** [eminaruk](https://www.linkedin.com/in/eminaruk/)
- **E-posta:** byemin00@gmail.com
- **Güncellemeler:** [GitHub Releases](https://github.com/eminaruk/FaceGuardPro/releases)

---

## Lisans

Bu yazılım Cingöz Systems tarafından geliştirilmiştir. Tüm hakları saklıdır.

---

**İyi kullanımlar!**

Son Güncelleme: 2024-12-04 | Versiyon: 3.0
