# 🪶 Linux Osmanlıca Transkripsiyon Klavyesi

> Linux'ta Osmanlı Türkçesi transkripsiyon (çeviriyazı) için Türkçe Q tabanlı klavye düzeni — TDV İslam Ansiklopedisi (İA) sistemine uyumlu.

[![Lisans: GPL v3](https://img.shields.io/badge/Lisans-GPL%20v3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![XKB Test](https://github.com/KULLANICI/linux-osmanlica-klavye/actions/workflows/test.yml/badge.svg)](https://github.com/KULLANICI/linux-osmanlica-klavye/actions)
[![Platform: Linux](https://img.shields.io/badge/Platform-Linux-orange.svg)]()

---

## 📖 Bu nedir?

Akademik metinlerde Osmanlıca yazarken kullanılan **ā ē ī ō ū**, **ṣ ḍ ṭ ẓ ḥ ḳ**, **ḫ ġ**, **ʿ ʾ** gibi karakterleri Linux'ta **doğrudan klavyeden** yazmanızı sağlar.

Türkçe Q klavye üzerine **AltGr (sağ Alt) seviyesi** ekler. Türkçe yazımınız (ı, i, ç, ğ, ö, ş, ü) hiçbir şekilde bozulmaz.

```
Normal:  ottoman → osmanlı
AltGr:   ḳāḍı, ʿOs̱mān, ḥadīs̱-i şerīf
```

---

## ⚡ Hızlı Kurulum

```bash
git clone https://github.com/KULLANICI/linux-osmanlica-klavye.git
cd linux-osmanlica-klavye
sudo bash scripts/install.sh
```

Sonra **logout/login** yapın ve klavye ayarlarınızdan ekleyin (aşağıda detay var).

---

## 📋 Sistem Gereksinimleri

| Gereksinim | Açıklama |
|------------|----------|
| **İşletim sistemi** | Linux (X11 veya Wayland) |
| **Dağıtım** | Fedora, Ubuntu, Debian, Arch, openSUSE, Mint vb. |
| **Masaüstü** | GNOME, KDE, XFCE, Cinnamon, MATE, Budgie |
| **Paketler** | `xkeyboard-config`, `python3` (her dağıtımda var) |
| **İsteğe bağlı** | `xkbcomp` (kurulum öncesi syntax testi için) |

---

## 🚀 Adım Adım Kurulum

### 1. Repo'yu indirin

```bash
git clone https://github.com/KULLANICI/linux-osmanlica-klavye.git
cd linux-osmanlica-klavye
```

### 2. (İsteğe bağlı) Önce test edin

Kurulum öncesi XKB dosyasının syntax'ını test etmek için:

```bash
bash scripts/test.sh
```

Çıktı şöyle olmalı:
```
Test: XKB syntax doğrulaması
✓ TEST GEÇTİ
```

### 3. Kurulumu çalıştırın

```bash
sudo bash scripts/install.sh
```

Script otomatik olarak:
- ✅ Sistem dosyalarınızın yedeğini alır
- ✅ XKB syntax'ını test eder
- ✅ Hata olursa otomatik geri alır
- ✅ GUI ayarlarına kayıt yapar

### 4. Logout/Login yapın

XKB değişikliklerinin tanınması için **mutlaka oturum kapatıp tekrar açın**. Bilgisayarı yeniden başlatmaya gerek yok.

### 5. Klavye düzenini etkinleştirin

Masaüstü ortamınıza göre:

<details>
<summary><b>GNOME (Fedora, Ubuntu, Debian)</b></summary>

1. **Settings → Keyboard → Input Sources**
2. **+** butonuna tıklayın
3. **Turkish** → **Turkish (Ottoman, IA transliteration)** seçin
4. **Add** butonuna tıklayın
5. Üst panelde **tr / tr ottoman** göstergesi belirir

</details>

<details>
<summary><b>KDE Plasma</b></summary>

1. **System Settings → Input Devices → Keyboard → Layouts**
2. **Configure Layouts** kutusunu işaretleyin
3. **Add** → **Turkish** → **Ottoman** varyantı seçin
4. **Apply** butonuna tıklayın

</details>

<details>
<summary><b>XFCE / Cinnamon / MATE</b></summary>

1. Klavye Ayarları (Keyboard Settings) → **Düzen** (Layout) sekmesi
2. **Ekle** (Add) → **Turkish** → **Ottoman** varyantı
3. **Tamam** (OK)

</details>

<details>
<summary><b>Sway / Hyprland (manuel)</b></summary>

**Sway** (`~/.config/sway/config`):
```
input * {
    xkb_layout "tr"
    xkb_variant "ottoman"
}
```

**Hyprland** (`~/.config/hypr/hyprland.conf`):
```
input {
    kb_layout = tr
    kb_variant = ottoman
}
```

</details>

### 6. Klavyeler arası geçiş

**Süper + Boşluk** (GNOME) veya masaüstünüzün varsayılan kısayolu ile Türkçe Q ↔ Ottoman arasında geçiş yaparsınız.

---

## ⌨️ Tuş Haritası — Hızlı Bakış

> Tam ve detaylı harita için: **[docs/tus-haritasi.md](docs/tus-haritasi.md)**

### Uzun ünlüler

| Tuş | Karakter |  | Tuş | Karakter |
|:---:|:---:|---|:---:|:---:|
| `AltGr+A` | **ā** | | `AltGr+O` | **ō** |
| `AltGr+E` | **ē** | | `AltGr+U` | **ū** |
| `AltGr+İ` | **ī** | | `AltGr+1/2/3` | **â î û** |

### Vurgulu ünsüzler

| Tuş | Karakter |  | Tuş | Karakter |
|:---:|:---:|---|:---:|:---:|
| `AltGr+S` | **ṣ** | | `AltGr+H` | **ḥ** |
| `AltGr+D` | **ḍ** | | `AltGr+K` | **ḳ** |
| `AltGr+T` | **ṭ** | | `AltGr+X` | **ḫ** |
| `AltGr+Z` | **ẓ** | | `AltGr+Q` | **ġ** |

### Özel karakterler

| Tuş | Karakter | Açıklama |
|:---:|:---:|---|
| `AltGr+W` | **ñ** | sağır kef |
| `AltGr+,` | **ʿ** | ayn (U+02BF) |
| `AltGr+.` | **ʾ** | hemze (U+02BE) |
| `AltGr+5/6/9` | **ẕ ḏ ż** | alt-çizgili / alternatif |

### Bileşik karakterler

Bu karakterler iki adımda yazılır:

| Karakter | Yazım |
|:---:|---|
| **ı̄** | `ı` + `AltGr+4` |
| **s̱** | `s` + `AltGr+7` |

---

## 🎨 Önerilen Yazı Tipi

Transkripsiyon karakterlerinin (özellikle bileşik s̱ ve ı̄) düzgün görünmesi için **Gentium Plus** önerilir:

```bash
# Fedora
sudo dnf install sil-gentium-fonts

# Ubuntu / Debian / Mint
sudo apt install fonts-sil-gentiumplus

# Arch / Manjaro
sudo pacman -S ttf-gentium-plus
```

LibreOffice'te varsayılan yapmak için: **Araçlar → Seçenekler → LibreOffice Writer → Temel Yazı Tipleri**

---

## 🗑️ Kaldırma

```bash
cd linux-osmanlica-klavye
sudo bash scripts/uninstall.sh
```

Sonra logout/login.

---

## 🆘 Sorun mu yaşıyorsunuz?

### Hızlı kontrol listesi

- [ ] Kurulum sonrası **logout/login** yaptınız mı?
- [ ] Üst paneldeki dil göstergesi **"tr ottoman"** mı yoksa sadece **"tr"** mi?
- [ ] **Sağ Alt** tuşunu kullanıyor musunuz? (sol Alt değil)
- [ ] **Caps Lock** kapalı mı?

### Detaylı sorun giderme

**[docs/sorun-giderme.md](docs/sorun-giderme.md)** dosyasına bakın.

### Acil durum: Klavye tamamen bozuldu

Eğer klavyeniz hiç çalışmıyor ve terminale yazamıyorsanız:

1. **Ctrl + Alt + F3** ile TTY'ye geçin (siyah ekran, İngilizce klavye)
2. Kullanıcı adı/şifrenizi girin
3. Şu komutu çalıştırın:

```bash
sudo dnf reinstall -y xkeyboard-config && sudo reboot
# Ubuntu/Debian:
sudo apt install --reinstall -y xkeyboard-config && sudo reboot
```

Bu komut sistemi orijinal hâline döndürür.

---

## 📚 İlgili Belgeler

| Belge | İçerik |
|-------|--------|
| [📑 Tuş Haritası](docs/tus-haritasi.md) | Tüm tuş kombinasyonları |
| [🔤 Transliterasyon Sistemi](docs/transliterasyon-sistemi.md) | İA sistemi açıklaması |
| [💻 Uyumluluk](docs/compatibility.md) | Dağıtım ve masaüstü ortamı listesi |
| [🛠️ Sorun Giderme](docs/sorun-giderme.md) | Yaygın sorunlar ve çözümleri |
| [🤝 Katkı Rehberi](CONTRIBUTING.md) | Geliştirme ve katkı süreci |
| [📜 Değişiklik Geçmişi](CHANGELOG.md) | Sürüm notları |

---

## 🌐 Diğer İşletim Sistemleri İçin

Bu repo Linux'a özeldir. Windows ve macOS için aşağıdaki bağımsız projelere bakın:

### Windows
- **[QHOD/ota-keyboard](https://github.com/QHOD/ota-keyboard)** — IJMES odaklı ama İA için de uyumlu, MSI installer ile gelir
- **[theoknights/ottomandiacs](https://github.com/theoknights/ottomandiacs)** (Windows portu)

### macOS
- **[theoknights/ottomandiacs](https://github.com/theoknights/ottomandiacs)** — Ukelele ile yapılmış, Türkçe Q tabanlı, aktif geliştirme

### Web tabanlı (kurulum gerektirmez)
- **[Lexilogos Ottoman Turkish](https://www.lexilogos.com/keyboard/ottoman_turkish.htm)**

---

## 🤝 Katkıda Bulunma

Hata bildirimi, yeni özellik önerisi veya başka transliterasyon sistemleri (DMG, IJMES, EI3) için varyant ekleme talepleri açıktır.

**[CONTRIBUTING.md](CONTRIBUTING.md)** dosyasına bakın.

Issue açmadan önce [docs/sorun-giderme.md](docs/sorun-giderme.md) ve [açık issue'lar](../../issues) dahil mevcut çözümleri kontrol edin.

---

## 📜 Lisans

Bu proje **GPL-3.0** lisansı altında dağıtılmıştır. Detaylar için [LICENSE](LICENSE) dosyasına bakın.

Kısaca: özgürce kullanabilir, değiştirebilir ve dağıtabilirsiniz; ancak yaptığınız değişiklikleri de aynı lisansla paylaşmanız gerekir.

---

## 🙏 Teşekkür

Bu projenin XKB tasarımı ve kurulum scriptleri **Anthropic'in Claude (Opus 4.7)** asistanıyla yapılan diyaloglar sonucunda geliştirilmiştir. Tasarım kararları, hata ayıklama ve Osmanlıca transliterasyon ihtiyaçlarına özel uyarlamalar bir akademisyen ile Claude arasındaki iş birliğiyle şekillenmiştir. Klavye düzeni, gerçek bir 100+ sayfalık transkripsiyon projesinin ihtiyaçlarına göre optimize edilmiştir.

Aynı zamanda **TDV İslam Ansiklopedisi** ekibine, Osmanlıca için fiilî standart hâline gelen transliterasyon sistemini geliştirdikleri için teşekkürler.

---

<p align="center">
  Türkiye'deki Osmanlıca araştırmacıları ve uluslararası Şarkiyat camiası için ❤️ ile hazırlandı.
</p>
