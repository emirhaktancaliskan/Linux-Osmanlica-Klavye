# Linux-Osmanlica-Klavye
Linux'ta Osmanlı Türkçesi transkripsiyon (çeviriyazı) için Türkçe Q klavye tabanlı XKB varyantı.
Türkçe Q klavyenizin üzerine AltGr (sağ Alt) seviyesi ekler. Tüm normal Türkçe yazım (ı, i, ç, ğ, ö, ş, ü) aynen çalışır;
transkripsiyon karakterlerini AltGr ile yazarsınız. 
Desteklenen karakterler 
Uzun ünlüler: ā ē ī ō ū ve büyükleri Şapkalı ünlüler: â î û ve büyükleri Vurgulu ünsüzler: ṣ ḍ ṭ ẓ ḥ ḳ ve büyükleri Hırıltılı: ḫ ġ ve
büyükleri Alt-çizgili: ẕ ḏ ż s̱ ı̄ ve büyükleri Diğer: ñ ʿ ʾ 
Tam tuş haritası için: docs/tus-haritasi.md 
Hızlı kurulum 
git clone https://github.com/KULLANICI/linux-osmanlica-klavye.git
cd linux-osmanlica-klavye
sudo bash scripts/install.sh

Logout/login yapın. Sonra: 
GNOME: Settings → Keyboard → Input Sources → + → Turkish → “Turkish (Ottoman, IA transliteration)”
KDE Plasma: System Settings → Input Devices → Keyboard → Layouts → Add → Turkish → Ottoman varyantı
XFCE/Cinnamon/MATE: Klavye ayarları → Düzenler → Ekle 
Klavyeler arasında geçiş için Süper + Boşluk (GNOME) veya masaüstünüzün varsayılan kısayolu. 
Kaldırma 
sudo bash scripts/uninstall.sh

Logout/login yapın. 
Sistem gereksinimleri 
Linux (X11 veya Wayland)
xkeyboard-config paketi (zaten her dağıtımda var)
xkbcomp (test için, çoğu sistemde mevcut)
Python 3 (kurulum scripti için) 
Test edilmiş dağıtımlar: Fedora 43+, Ubuntu 24.04+, Debian 12+, Arch Linux, openSUSE Tumbleweed, Linux Mint 22+. 
Detaylı uyumluluk tablosu: docs/compatibility.md 
Önerilen yazı tipi 
Transkripsiyon karakterlerinin (özellikle bileşik s̱ ve ı̄) düzgün görünmesi için Gentium Plus veya Charis SIL kullanın: 
# Fedora
sudo dnf install sil-gentium-fonts
 # Ubuntu/Debian
sudo apt install fonts-sil-gentiumplus
 # Arch
sudo pacman -S ttf-gentium-plus

LibreOffice'te varsayılan yazı tipi olarak ayarlamak için: Araçlar → Seçenekler → LibreOffice Writer → Temel Yazı Tipleri. 
Transliterasyon sistemiBu klavye TDV İslam Ansiklopedisi (İA) transliterasyon sistemine göre tasarlanmıştır. Ayn için ʿ (U+02BF), hemze için ʾ
(U+02BE) kullanılır. 
Sistem detayları için: docs/transliterasyon-sistemi.md 
Sorun mu yaşıyorsunuz? 
Önce docs/sorun-giderme.md dosyasına bakın. Çözüm bulamazsanız Issues sekmesinden bildirin. 
Acil durum: Klavye bozulduysa ve terminale yazamıyorsanız, Ctrl + Alt + F3 ile TTY'ye geçin (orada İngilizce klavye çalışır),
kullanıcı adı/şifre girin ve şu komutu çalıştırın: 
sudo dnf reinstall -y xkeyboard-config && sudo reboot
# Ubuntu/Debian:
# sudo apt install --reinstall -y xkeyboard-config && sudo reboot

Katkıda bulunma 
Yeni karakter ekleme, hata düzeltme veya başka transliterasyon sistemleri (DMG, IJMES) için varyant ekleme talepleri açıktır.
CONTRIBUTING.md dosyasına bakın. 
Lisans 
GPL-3.0. Detaylar için LICENSE dosyasına bakın. 
