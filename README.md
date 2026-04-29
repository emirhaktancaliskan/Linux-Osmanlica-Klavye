Linux Osmanlıca Transkripsiyon Klavyesi 
Linux'ta Osmanlı Türkçesi transkripsiyon (çeviriyazı) için Türkçe Q tabanlı klavye düzeni — TDV İslam
Ansiklopedisi (İA) sistemine uyumlu. 
Lisans: GPL v3 XKB Test Platform: Linux 
 Nedir? 
Akademik metinlerde Osmanlıca yazarken kullanılan ā ē ī ō ū, ṣ ḍ ṭ ẓ ḥ ḳ, ḫ ġ, ʿ ʾ gibi karakterleri Linux'ta doğrudan klavyeden
yazmanızı sağlar. 
Türkçe Q klavye üzerine AltGr (sağ Alt) seviyesi ekler. Türkçe yazımınız (ı, i, ç, ğ, ö, ş, ü) hiçbir şekilde bozulmaz. 
Normal: ottoman → osmanlı
AltGr: ḳāḍı, ʿOs̱mān, ḥadīs̱-i şerīf

 ⚡ Hızlı Kurulum 
git clone https://github.com/KULLANICI/linux-osmanlica-klavye.git
cd linux-osmanlica-klavye
sudo bash scripts/install.sh

Sonra logout/login yapın ve klavye ayarlarınızdan ekleyin (aşağıda detay var). 
 📋 Sistem GereksinimleriGereksinim Açıklamaİşletim sistemi Linux (X11 veya Wayland)Dağıtım Fedora, Ubuntu, Debian, Arch, openSUSE, Mint vb.Masaüstü GNOME, KDE, XFCE, Cinnamon, MATE, BudgiePaketler xkeyboard-config, python3 (her dağıtımda var)İsteğe bağlı xkbcomp (kurulum öncesi syntax testi için) 
 🚀 Adım Adım Kurulum 
1. Repo'yu indirin 
git clone https://github.com/KULLANICI/linux-osmanlica-klavye.git
cd linux-osmanlica-klavye

2. (İsteğe bağlı) Önce test edin 
Kurulum öncesi XKB dosyasının syntax'ını test etmek için: 
bash scripts/test.sh

Çıktı şöyle olmalı: Test: XKB syntax doğrulaması ✓ TEST GEÇTİ 
3. Kurulumu çalıştırın 
sudo bash scripts/install.sh

Script otomatik olarak: - ✅ Sistem dosyalarınızın yedeğini alır - ✅ XKB syntax'ını test eder - ✅ Hata olursa otomatik geri alır
- ✅ GUI ayarlarına kayıt yapar4. Logout/Login yapın 
XKB değişikliklerinin tanınması için mutlaka oturum kapatıp tekrar açın. Bilgisayarı yeniden başlatmaya gerek yok. 
5. Klavye düzenini etkinleştirin 
Masaüstü ortamınıza göre: 
GNOME (Fedora, Ubuntu, Debian) 
Settings → Keyboard → Input Sources
+ butonuna tıklayın
Turkish → Turkish (Ottoman, IA transliteration) seçin
Add butonuna tıklayın
Üst panelde tr / tr ottoman göstergesi belirir 
KDE Plasma 
System Settings → Input Devices → Keyboard → Layouts
Configure Layouts kutusunu işaretleyin
Add → Turkish → Ottoman varyantı seçin
Apply butonuna tıklayın 
XFCE / Cinnamon / MATE 
Klavye Ayarları (Keyboard Settings) → Düzen (Layout) sekmesi
Ekle (Add) → Turkish → Ottoman varyantı
Tamam (OK) 
Sway / Hyprland (manuel) 
Sway (~/.config/sway/config): input * { xkb_layout "tr" xkb_variant "ottoman" } 
Hyprland (~/.config/hypr/hyprland.conf): input { kb_layout = tr kb_variant = ottoman } 
6. Klavyeler arası geçiş 
Süper + Boşluk (GNOME) veya masaüstünüzün varsayılan kısayolu ile Türkçe Q ↔ Ottoman arasında geçiş yaparsınız. 
 ⌨️ Tuş Haritası — Hızlı Bakış 
Tam ve detaylı harita için: docs/tus-haritasi.md 
Uzun ünlülerTuş Karakter Tuş KarakterAltGr+A ā AltGr+O ōAltGr+E ē AltGr+U ūAltGr+İ ī AltGr+1/2/3 â î û 
Vurgulu ünsüzlerTuş Karakter Tuş KarakterAltGr+S ṣ AltGr+H ḥAltGr+D ḍ AltGr+K ḳAltGr+T ṭ AltGr+X ḫAltGr+Z ẓ AltGr+Q ġ 
Özel karakterlerTuş Karakter AçıklamaAltGr+W ñ sağır kefAltGr+, ʿ ayn (U+02BF)AltGr+. ʾ hemze (U+02BE)AltGr+5/6/9 ẕ ḏ ż alt-çizgili / alternatif 
Bileşik karakterlerBu karakterler iki adımda yazılır:Karakter Yazımı̄ ı + AltGr+4s̱ s + AltGr+7 
 🎨 Önerilen Yazı Tipi 
Transkripsiyon karakterlerinin (özellikle bileşik s̱ ve ı̄) düzgün görünmesi için Gentium Plus önerilir: 
# Fedora
sudo dnf install sil-gentium-fonts
 # Ubuntu / Debian / Mint
sudo apt install fonts-sil-gentiumplus
 # Arch / Manjaro
sudo pacman -S ttf-gentium-plus

LibreOffice'te varsayılan yapmak için: Araçlar → Seçenekler → LibreOffice Writer → Temel Yazı Tipleri 
 🗑️ Kaldırma 
cd linux-osmanlica-klavye
sudo bash scripts/uninstall.sh

Sonra logout/login. 
 🆘 Sorun mu yaşıyorsunuz? 
Hızlı kontrol listesi 
[ ] Kurulum sonrası logout/login yaptınız mı?
[ ] Üst paneldeki dil göstergesi “tr ottoman” mı yoksa sadece “tr” mi?
[ ] Sağ Alt tuşunu kullanıyor musunuz? (sol Alt değil)
[ ] Caps Lock kapalı mı? 
Detaylı sorun giderme 
docs/sorun-giderme.md dosyasına bakın. 
Acil durum: Klavye tamamen bozuldu 
Eğer klavyeniz hiç çalışmıyor ve terminale yazamıyorsanız: 
Ctrl + Alt + F3 ile TTY'ye geçin (siyah ekran, İngilizce klavye)
Kullanıcı adı/şifrenizi girin
Şu komutu çalıştırın: 
sudo dnf reinstall -y xkeyboard-config && sudo reboot
# Ubuntu/Debian:
sudo apt install --reinstall -y xkeyboard-config && sudo reboot

Bu komut sistemi orijinal hâline döndürür. 
 📚 İlgili BelgelerBelge İçerik📑 Tuş Haritası Tüm tuş kombinasyonları🔤 Transliterasyon Sistemi İA sistemi açıklaması💻 Uyumluluk Dağıtım ve masaüstü ortamı listesi🛠️ Sorun Giderme Yaygın sorunlar ve çözümleri🤝 Katkı Rehberi Geliştirme ve katkı süreci📜 Değişiklik Geçmişi Sürüm notları 
Bu repo Linux'a özeldir. 
 🤝 Katkıda Bulunma 
Hata bildirimi, yeni özellik önerisi veya başka transliterasyon sistemleri (DMG, IJMES, EI3) için varyant ekleme talepleri açıktır. 
CONTRIBUTING.md dosyasına bakın. 
Issue açmadan önce docs/sorun-giderme.md ve açık issue'lar dahil mevcut çözümleri kontrol edin. 
 📜 Lisans 
Bu proje GPL-3.0 lisansı altında dağıtılmıştır. Detaylar için LICENSE dosyasına bakın. 
Kısaca: özgürce kullanabilir, değiştirebilir ve dağıtabilirsiniz; ancak yaptığınız değişiklikleri de aynı lisansla paylaşmanız
gerekir. 
