# FaceGuardPro 2.0 Güncellemesi Kurulum Rehberi

FaceGuardPro 2.0'a hoş geldiniz! Bu rehber, uygulamayı Windows, Linux ve macOS işletim sistemlerinde kurmanız ve çalıştırmanız için gereken tüm adımları içermektedir.

---

## 📋 İçindekiler

1. [Windows Kurulumu](#windows-kurulumu)
2. [Linux Kurulumu](#linux-kurulumu)
3. [macOS Kurulumu](#macos-kurulumu)
4. [Güvenlik ve İzinler](#güvenlik-ve-izinler)
5. [Sorun Giderme](#sorun-giderme)
6. [Sistem Gereksinimleri](#sistem-gereksinimleri)

---

## 🪟 Windows Kurulumu

### Kurulum Adımları

1. **Setup Dosyasını İndirin**
   - [`windows_faceguard_2.0_19.11.2025_setup.exe`](https://github.com/eminaruk/FaceGuardPro/releases/download/v2.0/windows_faceguard_2.0_19.11.2025_setup.exe) dosyasını indirin

2. **Kurulumu Başlatın**
   - Setup dosyasına çift tıklayın
   - Windows SmartScreen uyarısı alırsanız:
     - "More info" (Daha fazla bilgi) seçeneğine tıklayın
     - "Run anyway" (Yine de çalıştır) butonuna basın

3. **Kurulum Sihirbazı**
   - Kurulum konumunu seçin (varsayılan bırakmanız önerilir)
   - "Next" butonlarına tıklayarak kurulumu tamamlayın
   - Masaüstü kısayolu oluşturulmasını tercih edebilirsiniz

4. **İlk Çalıştırma**
   - Kurulum tamamlandığında "Launch FaceGuardPro" seçeneğini işaretleyip "Finish" butonuna basın
   - VEYA Masaüstü kısayolundan veya Başlat Menüsünden çalıştırın

### Windows Defender SmartScreen Uyarısı Çözümü

**Seçenek 1: Geçici Olarak İzin Verme**

    "More info" (Daha fazla bilgi) linkine tıklayın
    "Run anyway" (Yine de çalıştır) butonuna basın


**Seçenek 2: Dosyayı Güvenli Listesine Ekleme**

    Setup dosyasına sağ tıklayın
    "Properties" (Özellikler) seçin
    En altta "Unblock" (Engeli kaldır) kutucuğunu işaretleyin
    "Apply" → "OK" butonlarına basın
    Setup dosyasını çalıştırın


### Kaldırma

**Seçenek 1: Kontrol Paneli Üzerinden**

    Kontrol Paneli → Programs → Programs and Features
    "FaceGuardPro" uygulamasını bulun
    Sağ tıklayıp "Uninstall" seçeneğine basın


**Seçenek 2: Ayarlar Üzerinden (Windows 10/11)**

    Settings (Ayarlar) → Apps → Apps & features
    "FaceGuardPro" uygulamasını bulun
    "Uninstall" butonuna basın


---

## 🐧 Linux Kurulumu

### Kurulum Adımları

1. **ZIP Dosyasını İndirin**
   - [`linux_faceguard_2.0_20.11.2025_setup.zip`](https://github.com/eminaruk/FaceGuardPro/releases/download/v2.0/linux_faceguard_2.0_20.11.2025_setup.zip) dosyasını indirin

2. **ZIP'i Açın**
   ```bash
   unzip FaceGuardPro_v2_Linux.zip
   cd FaceGuardPro_v2/

    Kurulum Script'ini Çalıştırın

    # Script'e çalışma izni verin
    chmod +x install.sh

    # Kurulumu başlatın (sudo gerekebilir)
    sudo ./install.sh

    Kurulum Script'i Şunları Yapar:
        Gerekli izinleri ayarlar
        Uygulama dosyalarını /opt/FaceGuardPro/ dizinine kopyalar
        Masaüstü kısayolu oluşturur
        Sistem menüsüne ekler

    Uygulamayı Başlatın

    # Komut satırından
    /opt/FaceGuardPro/FaceGuardPro_v2

    # VEYA Uygulama menüsünden
    # Applications → FaceGuardPro

Alternatif: Manuel Kurulum

Eğer install.sh kullanmak istemezseniz:

1. Klasöre girin

        cd FaceGuardPro_v2/

2. Çalışma izni verin

        chmod +x FaceGuardPro_v2

3. Doğrudan çalıştırın

        ./FaceGuardPro_v2

### Kaldırma

Kurulum klasöründeki uninstall.sh'yi çalıştırın

    cd FaceGuardPro_v2/

    sudo ./uninstall.sh

### Manuel kaldırma için
    sudo rm -rf /opt/FaceGuardPro/
    sudo rm /usr/share/applications/faceguardpro.desktop

## Linux Güvenlik İzinleri

### Kamera İzni Problemi:

Kullanıcınızı video grubuna ekleyin

    sudo usermod -a -G video $USER

Oturumu kapatıp tekrar açın

VEYA sistemi yeniden başlatın

### Firewall İzni (Firebase bağlantısı için):

#### UFW kullanıyorsanız
    sudo ufw allow out 443/tcp
    sudo ufw allow out 80/tcp

#### Firewalld kullanıyorsanız
    sudo firewall-cmd --permanent --add-service=https
    sudo firewall-cmd --reload

# 🍎 macOS Kurulumu

## Kurulum Adımları

ZIP Dosyasını İndirin: 
    [`macos_faceguard_2.0_20.11.2025_setup.zip`](https://github.com/eminaruk/FaceGuardPro/releases/download/v2.0/macos_faceguard_2.0_20.11.2025_setup.zip)

ZIP'i Açın

Terminal'de veya Finder'da çift tıklayarak
    
    unzip FaceGuardPro_v2_macOS.zip

Quarantine Özniteliğini Kaldırın ⚠️ ÖNEMLİ

Bu adım olmadan uygulama çalışmayacaktır!

    xattr -cr FaceGuardPro_v2

Uygulamayı Başlatın

    Seçenek 1: Finder Üzerinden
        FaceGuardPro_v2.app veya FaceGuardPro_v2 dosyasına SAĞ TIKLAYIN
        "Open" (Aç) seçeneğine tıklayın
        Çıkan uyarıda tekrar "Open" butonuna basın

    Seçenek 2: Terminal Üzerinden
    cd ./FaceGuardPro_v2
    ./FaceGuardPro_v2

## macOS "Unidentified Developer" Uyarısı Çözümü

#### Yöntem 1: Sağ Tıklayarak Açma (Önerilen)

1. Uygulamaya SAĞ TIKLAYIN (çift tıkla YAPMA!)
2. "Open" (Aç) seçeneğine tıklayın
3. Çıkan güvenlik uyarısında "Open" butonuna basın
4. Bu işlemi sadece ilk açılışta yapmanız yeterli

#### Yöntem 2: System Preferences Üzerinden

1. Uygulamayı çift tıklayarak açmayı deneyin (engellenecek)
2. System Preferences → Security & Privacy → General
3. "FaceGuardPro_v2 was blocked..." mesajının yanında
4. "Open Anyway" butonuna tıklayın
5. Admin şifrenizi girin
6. Tekrar çalıştırın ve "Open" butonuna basın

#### Yöntem 3: Terminal ile Quarantine Kaldırma

## En hızlı ve etkili yöntem
    xattr -cr /path/to/FaceGuardPro_v2.app

VEYA

    xattr -cr FaceGuardPro_v2/

## macOS Kamera ve Mikrofon İzinleri

İlk çalıştırmada macOS otomatik olarak izin isteyecektir:

    Kamera İzni
        "FaceGuardPro would like to access the camera" uyarısı gelir
        "OK" butonuna basın

    Manuel İzin Verme:

    System Preferences → Security & Privacy → Privacy → Camera
    ✓ FaceGuardPro'yu işaretleyin

    Mikrofon İzni (gerekirse):

    System Preferences → Security & Privacy → Privacy → Microphone
    ✓ FaceGuardPro'yu işaretleyin

## Kaldırma

Terminal'den

    rm -rf /Applications/FaceGuardPro_v2.app

VEYA klasördeki dosyayı

    rm -rf FaceGuardPro_v2/

## Finder'dan

Uygulamayı Trash'e sürükleyin ve Trash'i boşaltın

# 🔒 Güvenlik ve İzinler

## Windows

### Windows Defender:

    FaceGuardPro dijital olarak imzalanmamış olabilir
    Bu durum virüs anlamına GELMEZ
    Microsoft SmartScreen'i yukarıdaki adımlarla geçebilirsiniz

### Antivirus Yazılımları:

    Bazı antivirus programları false-positive (yanlış pozitif) uyarısı verebilir
    FaceGuardPro'yu güvenli yazılımlar listesine ekleyin
    Tarama sırasında FaceGuardPro klasörünü hariç tutabilirsiniz

### Firewall İzni:

    Windows Firewall FaceGuardPro için izin isteyebilir
    Firebase bağlantısı için "Allow access" (İzin ver) seçeneğine tıklayın

## Linux

### AppArmor/SELinux:

SELinux kullanıyorsanız ve problem yaşıyorsanız

    sudo setenforce 0  # Geçici olarak devre dışı bırak

Kalıcı değişiklik için /etc/selinux/config düzenleyin

### Kamera İzinleri:

Video cihazlarına erişim için

    ls -l /dev/video*

Eğer erişim sorunu varsa

    sudo chmod 666 /dev/video0

## macOS

### Gatekeeper:

    macOS Gatekeeper, sadece App Store'dan veya tanımlı geliştiricilerden uygulamaları kabul eder
    Yukarıdaki "Unidentified Developer" adımlarını izleyin

### Notarization:

    FaceGuardPro Apple tarafından notarize edilmemiş olabilir
    Bu güvenlik riski DEĞILDIR, sadece Apple'ın dağıtım politikasıdır

### Full Disk Access (Gerekirse):

System Preferences → Security & Privacy → Privacy → Full Disk Access
Eğer gerekirse FaceGuardPro'yu buraya ekleyin

# 🔧 Sorun Giderme

## Genel Problemler

### Problem: Uygulama açılmıyor

✅ Çözüm:
- Antivirüs yazılımınızı geçici olarak devre dışı bırakın
- Dosyaları tekrar indirin (bozuk indirme olabilir)
- Sistem yeniden başlatın
- Yönetici/root olarak çalıştırmayı deneyin

### Problem: "No camera found" hatası

✅ Çözüm:
- Kameranın başka bir uygulama tarafından kullanılmadığını kontrol edin
- Sistem ayarlarından kamera iznini kontrol edin
- Kamera sürücülerini güncelleyin
- USB kamera kullanıyorsanız, farklı bir USB portuna takın

### Problem: Firebase bağlantı hatası

✅ Çözüm:
- İnternet bağlantınızı kontrol edin
- Firewall ayarlarını kontrol edin (443 ve 80 portları açık olmalı)
- VPN kullanıyorsanız devre dışı bırakmayı deneyin
- DNS ayarlarını değiştirmeyi deneyin (Google DNS: 8.8.8.8)

## Windows Özel Problemler

### Problem: "VCRUNTIME140.dll not found"

✅ Çözüm:
Microsoft Visual C++ Redistributable indirin ve kurun:
https://aka.ms/vs/17/release/vc_redist.x64.exe

### Problem: "Application failed to start (0xc000007b)"

✅ Çözüm:
- .NET Framework 4.7.2 veya üzerini kurun
- Windows'u güncelleyin
- DirectX'i güncelleyin

## Linux Özel Problemler

### Problem: "Permission denied" hatası

✅ Çözüm:
    chmod +x FaceGuardPro_v2
    sudo ./FaceGuardPro_v2

### Problem: "libGL.so.1 not found"

✅ Çözüm:
#### Ubuntu/Debian
    sudo apt-get install libgl1-mesa-glx

#### Fedora/RHEL
    sudo dnf install mesa-libGL

#### Arch
    sudo pacman -S mesa

### Problem: "error while loading shared libraries"

✅ Çözüm:
    ldd FaceGuardPro_v2  # Eksik kütüphaneleri göster

Eksik kütüphaneleri paket yöneticinizle kurun

## macOS Özel Problemler

### Problem: "Damaged and can't be opened"

✅ Çözüm:

    xattr -cr FaceGuardPro_v2.app

    sudo spctl --master-disable  # Gatekeeper'ı geçici olarak kapat

Uygulamayı başlat, sonra tekrar aç:

    sudo spctl --master-enable

### Problem: Kamera çalışmıyor

✅ Çözüm:
1. System Preferences → Security & Privacy → Privacy → Camera
2. FaceGuardPro'nun yanındaki kutuyu işaretleyin
3. Uygulamayı yeniden başlatın
4. Hala çalışmıyorsa, Mac'i yeniden başlatın

### Problem: "App is not optimized for this Mac"

✅ Çözüm:
Bu mesaj Apple Silicon (M1/M2) Mac'lerde görülebilir.
Uygulama Rosetta 2 ile çalışacaktır.
Rosetta 2 kurulu değilse:
softwareupdate --install-rosetta

# 💻 Sistem Gereksinimleri

## Windows

    İşletim Sistemi: Windows 10 (64-bit) veya üzeri
    İşlemci: Intel Core i3 veya eşdeğeri
    RAM: 4 GB minimum, 8 GB önerilen
    Disk Alanı: 1.5 GB boş alan
    Kamera: RTSP erişimli güvenlik kamerası
    İnternet: Aktif internet

## Linux

    İşletim Sistemi: Ubuntu 20.04+, Fedora 35+, Debian 11+ veya uyumlu
    İşlemci: Intel Core i3 veya eşdeğeri
    RAM: 4 GB minimum, 8 GB önerilen
    Disk Alanı: 1.5 GB boş alan
    Kamera: RTSP erişimli güvenlik kamerası
    Kütüphaneler: libGL, libX11, libXrandr
    İnternet: Aktif internet

## macOS

    İşletim Sistemi: macOS 10.15 Catalina veya üzeri
    İşlemci: Intel x86_64 veya Apple Silicon (M1/M2) + Rosetta 2
    RAM: 4 GB minimum, 8 GB önerilen
    Disk Alanı: 1.5 GB boş alan
    Kamera: RTSP erişimli güvenlik kamerası
    İnternet: Aktif internet

# 📞 Destek ve İletişim

## Teknik Destek:

Sorunlarınız için : https://x.com/eminarukk

E-posta desteği: info@eminaruk.com

## Güncelleme Kontrolü:

    Yeni sürümler için düzenli olarak https://github.com/eminaruk/FaceGuardPro adresini ziyaret edin

## Geri Bildirim:

    Önerilerinizi ve hata raporlarınızı bizimle paylaşın

## ⚖️ Lisans ve Yasal Bilgiler

### Kullanım Koşulları:

    Bu yazılım yalnızca yetkili kullanıcılar tarafından kullanılmalıdır
    Yasal düzenlemelere uygun olarak kullanın



# İyi kullanımlar! 🚀

Son Güncelleme: 2025-11-20

Versiyon: 2.0

Belge Versiyonu: 1.0


---