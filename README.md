# FaceGuardPro v4.0 Kurulum Rehberi

FaceGuardPro v4.0'a hoş geldiniz! Yapay zeka destekli akıllı güvenlik sistemi ile ev, ofis ve işyeri güvenliğinizi üst seviyeye taşıyın.

---

## Yeni Özellikler (v4.0)

| Özellik | Açıklama |
|---------|----------|
| **REST API Server** | Yerel API ile dış sistemlere entegrasyon (FastAPI) |
| **NVR/IP Kamera Desteği** | RTSP stream ile profesyonel kamera sistemleri |
| **Multi-Camera Görünümü** | Aynı anda 4-16 kamera izleme |
| **Sistem Kaynak İzleme** | CPU, RAM, GPU kullanımı takibi |
| **Event Broker** | Gerçek zamanlı olay yönetim sistemi |
| **Gelişmiş Kamera Ayarları** | Kamera bazlı mod ve hassasiyet ayarları |
| **Kullanıcı Geri Bildirimi** | Uygulama içi feedback sistemi |
| **Recognition Pool** | Paralel tanıma ile yüksek performans |

### Önceki Sürümlerden Gelen Özellikler

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
4. [REST API Kullanımı](#rest-api-kullanımı)
5. [NVR/IP Kamera Kurulumu](#nvrip-kamera-kurulumu)
6. [Özellikler](#özellikler)
7. [Sorun Giderme](#sorun-giderme)
8. [Sistem Gereksinimleri](#sistem-gereksinimleri)

---

## Windows Kurulumu

### Kurulum Adımları

1. **Setup Dosyasını İndirin**
   - [`windows_faceguard_4.0_setup.exe`](https://github.com/eminaruk/FaceGuardPro/releases/download/v4.0/windows_faceguard_4.0_09.01.2026_setup.exe) dosyasını indirin

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

### Güncelleme (v3.0'dan v4.0'a)

Eğer FaceGuardPro v3.0 veya önceki sürüm yüklüyse:
- Setup dosyasını çalıştırın
- "Güncellemek istiyor musunuz?" sorusuna "Evet" deyin
- v4.0 yeni özellikleri size listelenecektir
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

> **Not:** Linux v4.0 build'i yakında yayınlanacaktır. Şu anda v3.0 sürümünü kullanabilirsiniz.

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

> **Not:** macOS v4.0 build'i yakında yayınlanacaktır. Şu anda v3.0 sürümünü kullanabilirsiniz.

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

## REST API Kullanımı

v4.0 ile gelen REST API özelliği, FaceGuardPro'yu dış sistemlerle entegre etmenizi sağlar.

### API Sunucusunu Başlatma

1. Uygulama içinden: **Ayarlar → API Yönetimi → API'yi Başlat**
2. Varsayılan adres: `http://localhost:8000`

### Örnek API Endpoint'leri

| Endpoint | Metod | Açıklama |
|----------|-------|----------|
| `/api/v1/system/status` | GET | Sistem durumu |
| `/api/v1/cameras` | GET | Kamera listesi |
| `/api/v1/cameras/{id}/snapshot` | GET | Anlık görüntü |
| `/api/v1/persons` | GET | Kayıtlı kişiler |
| `/api/v1/detection/status` | GET | Algılama durumu |
| `/api/v1/logs` | GET | Olay kayıtları |
| `/api/v1/events/stream` | GET | SSE event stream |

### API Dokümantasyonu

API çalışırken otomatik dokümantasyon:
- Swagger UI: `http://localhost:8000/docs`
- ReDoc: `http://localhost:8000/redoc`

### Örnek Kullanım (Python)

```python
import requests

# Sistem durumu
response = requests.get("http://localhost:8000/api/v1/system/status")
print(response.json())

# Kayıtlı kişiler
response = requests.get("http://localhost:8000/api/v1/persons")
for person in response.json():
    print(f"- {person['name']}")
```

### Örnek Kullanım (cURL)

```bash
# Sistem durumu
curl http://localhost:8000/api/v1/system/status

# Kamera listesi
curl http://localhost:8000/api/v1/cameras

# Anlık görüntü
curl http://localhost:8000/api/v1/cameras/0/snapshot --output snapshot.jpg
```

---

## NVR/IP Kamera Kurulumu

v4.0 ile profesyonel NVR ve IP kamera sistemlerinizi bağlayabilirsiniz.

### Desteklenen Protokoller

| Protokol | Format | Örnek |
|----------|--------|-------|
| RTSP | `rtsp://user:pass@ip:port/path` | `rtsp://admin:123456@192.168.1.100:554/stream1` |
| HTTP | `http://ip:port/path` | `http://192.168.1.100:8080/video` |
| HTTPS | `https://ip:port/path` | `https://192.168.1.100/live` |

### NVR Ekleme

1. **Ayarlar → NVR Yönetimi → Yeni NVR Ekle**
2. NVR bilgilerini girin:
   - Ad: NVR sisteminin adı
   - IP Adresi: NVR'nin IP'si
   - Port: Genellikle 554 (RTSP) veya 8000
   - Kullanıcı adı ve şifre
3. **Kanalları Tara** butonuna tıklayın
4. İstediğiniz kameraları seçin

### Popüler NVR Markaları RTSP Formatları

| Marka | RTSP URL Formatı |
|-------|------------------|
| Hikvision | `rtsp://user:pass@ip:554/Streaming/Channels/101` |
| Dahua | `rtsp://user:pass@ip:554/cam/realmonitor?channel=1&subtype=0` |
| Uniview | `rtsp://user:pass@ip:554/media/video1` |
| Reolink | `rtsp://user:pass@ip:554/h264Preview_01_main` |

### Multi-Camera Görünümü

1. Ana ekranda **Multi-Camera** butonuna tıklayın
2. Grid düzeni seçin: 2x2, 3x3, veya 4x4
3. Her hücreye kamera atayın
4. Gerçek zamanlı tüm kameraları izleyin

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
| NVR Sistemi | Çoklu kanal desteği |
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

### IP Kamera bağlanmıyor

- RTSP URL formatını kontrol edin
- Kullanıcı adı ve şifrenin doğru olduğunu kontrol edin
- Kameranın aynı ağda olduğunu kontrol edin
- Firewall'un 554 portunu engellemediğini kontrol edin

### API çalışmıyor

- Port 8000'in başka uygulama tarafından kullanılmadığını kontrol edin
- Firewall ayarlarını kontrol edin
- API'nin aktif olduğunu Ayarlar → API Yönetimi'nden kontrol edin

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

### macOS: Apple Silicon (M1/M2/M3)

```bash
softwareupdate --install-rosetta
```

---

## Sistem Gereksinimleri

### Windows

| Gereksinim | Minimum | Önerilen |
|------------|---------|----------|
| İşletim Sistemi | Windows 10 (64-bit) | Windows 11 |
| İşlemci | Intel Core i3 / AMD Ryzen 3 | Intel Core i5+ / AMD Ryzen 5+ |
| RAM | 4 GB | 8 GB |
| Disk Alanı | 2 GB | 4 GB |
| İnternet | Gerekli | - |

### Linux

| Gereksinim | Minimum | Önerilen |
|------------|---------|----------|
| İşletim Sistemi | Ubuntu 20.04+ | Ubuntu 22.04+ |
| İşlemci | Intel Core i3 / AMD Ryzen 3 | Intel Core i5+ / AMD Ryzen 5+ |
| RAM | 4 GB | 8 GB |
| Disk Alanı | 2 GB | 4 GB |

### macOS

| Gereksinim | Minimum | Önerilen |
|------------|---------|----------|
| İşletim Sistemi | macOS 11.0+ | macOS 13+ |
| İşlemci | Intel veya Apple Silicon | Apple Silicon (M1/M2/M3) |
| RAM | 4 GB | 8 GB |
| Disk Alanı | 2 GB | 4 GB |

---

## Sürüm Geçmişi

| Sürüm | Tarih | Öne Çıkan Özellikler |
|-------|-------|---------------------|
| v4.0 | 2026-01-09 | REST API, NVR desteği, Multi-Camera |
| v3.0 | 2024-12-04 | Hibrit tanıma, 6 dil desteği |
| v2.0 | 2024-11-19 | Obje tespiti, Bebek bakıcılığı |
| v1.0 | 2024-11-14 | İlk sürüm |

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

Son Güncelleme: 2026-01-09 | Versiyon: 4.0
