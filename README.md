# Ariva Discord Şikayet Aracı Pro

**Ariva Discord Şikayet Aracı Pro**, Discord platformuna yönelik şikayetlerinizi otomatikleştirmek için tasarlanmış güçlü ve kullanıcı dostu bir araçtır. E-posta veya Discord destek formu üzerinden şikayet gönderme işlemlerini kolaylaştırır. Türkçe ve İngilizce dil desteği ile hem bireysel kullanıcılar hem de profesyoneller için uygundur.

**Not:** Bu araç yalnızca yasal ve etik amaçlarla kullanılmalıdır. Discord Topluluk Kuralları'na uygun olmayan kullanımlar yasaktır.

---

## Özellikler

- **Çift Mod Desteği**: E-posta (Gmail SMTP) veya Discord destek formu üzerinden şikayet gönderme.
- **Çoklu Dil Desteği**: Türkçe ve İngilizce arayüz seçenekleri.
- **Otomatik Modül Kurulumu**: Gerekli Python modülleri (`fake_useragent`, `tqdm`, `pystyle`, `requests`) otomatik olarak yüklenir.
- **Yapılandırma Kaydetme**: E-posta ayarlarını `config.json` dosyasına kaydedip tekrar kullanma.
- **Rastgele Veri Üretimi**: Sahte e-posta ve telefon numaraları oluşturma (yalnızca Discord şikayet modunda).
- **Proxy Desteği**: Discord şikayetleri için proxy kullanımı ile anonimlik.
- **Kullanıcı Dostu Arayüz**: Renkli konsol çıktıları ve ilerleme çubuğu (`tqdm`) ile kolay kullanım.
- **Platform Uyumluluğu**: Kali Linux, Termux ve Windows üzerinde çalışır.

---

## Kurulum

Aşağıda, **Kali Linux** ve **Termux** için adım adım kurulum talimatları verilmiştir. Lütfen platformunuza uygun bölümü takip edin.

### Kali Linux Üzerinde Kurulum

1. **Sistemi Güncelleyin**:
   ```bash
   sudo apt update && sudo apt upgrade -y
   ```

2. **Gerekli Araçları Yükleyin**:
   Python ve `pip` kurulu değilse yükleyin:
   ```bash
   sudo apt install python3 python3-pip -y
   ```

3. **Depoyu Klonlayın**:
   ```bash
   git clone https://github.com/siberdunyaniz/arivadcrep.git
   cd Ariva-Discord-Complaint-Tool
   ```

4. **Bağımlılıkları Yükleyin**:
   Depo içerisindeki script, gerekli modülleri otomatik olarak yükler, ancak manuel yükleme için:
   ```bash
   pip3 install fake-useragent tqdm pystyle requests
   ```

5. **Aracı Çalıştırın**:
   ```bash
   python3 discord.py
   ```

### Termux Üzerinde Kurulum

1. **Termux'u Güncelleyin**:
   ```bash
   pkg update && pkg upgrade -y
   ```

2. **Gerekli Araçları Yükleyin**:
   Python ve `git` kurun:
   ```bash
   pkg install python git -y
   ```

3. **Depoyu Klonlayın**:
   ```bash
   git clone https://github.com/siberdunyaniz/arivadcrep.git
   cd discord.py
   ```

4. **Bağımlılıkları Yükleyin**:
   Termux'ta `pip` varsayılan olarak gelir. Gerekli modülleri yükleyin:
   ```bash
   pip install fake-useragent tqdm pystyle requests
   ```

5. **Aracı Çalıştırın**:
   ```bash
   python ariva_discord_complaint_tool_pro.py
   ```

**Not:** Termux'ta `webbrowser` modülü, Telegram bağlantısını açmak için `am start` komutunu kullanır. Termux'un `termux-api` paketinin yüklü olduğundan emin olun:
   ```bash
   pkg install termux-api -y
   ```

---

## Kullanım

1. **Aracı Başlatın**:
   ```bash
   python3 ariva_discord_complaint_tool_pro.py
   ```

2. **Dil Seçimi**:
   - `[1] Türkçe`
   - `[2] İngilizce`
   - Varsayılan: Türkçe

3. **Mod Seçimi**:
   - `[1] E-posta Şikayet`: Gmail SMTP üzerinden şikayet gönderir.
   - `[2] Discord Şikayet`: Discord destek formuna şikayet gönderir.
   - `[3] Temizle`: Konsolu temizler ve banner'ı yeniden gösterir.
   - `[4] Çıkış`: Aracı kapatır.

### E-posta Şikayet Modu
- **Gönderici Bilgileri**: `email:şifre` formatında (örn. `kullanici@gmail.com:sifre123`). Gmail için [Uygulama Şifresi](https://support.google.com/accounts/answer/185833) kullanın.
- **Alıcılar**: Discord destek e-postaları (örn. `abuse@discord.com`).
- **Konu ve Mesajlar**: Her satırda bir konu/mesaj, boş satırla sonlandırın.
- **Gecikme**: E-postalar arası saniye cinsinden gecikme (örn. `0` için gecikmesiz).
- **Yapılandırma**: Ayarları `config.json`’a kaydetme/yükleme seçeneği.

### Discord Şikayet Modu
- **Şikayet Türü**: 
  - `[1] Spam mesajlar`
  - `[2] Taciz`
  - `[3] Kural ihlali`
  - `[4] Hesap çalındı`
  - `[5] Sahte etkileşimler`
  - `[6] Ekranı temizle`
  - `[7] Çıkış`
- **Bilgiler**: Kullanıcı adı (örn. `Kullanıcı#1234`), Discord ID, şikayet sayısı, telefon (yalnızca `[4]` için, `+` ile).
- **Otomatik**: Rastgele e-posta ve telefon numaraları (ülke kodları: `+90`, `+994`, `+995`).
- **Proxy**: Her şikayet için rastgele proxy kullanılır.

4. **Navigasyon**:
   - İşlem sonrası: `[1]` menüye dön, `[0]` çık.
   - Geçersiz seçimlerde çıkış uyarısı.

---

## Örnek Kullanım (Türkçe)

```plaintext
[*] ARİVA Discord Şikayet Aracı başlatıldı.
=======================================================
Merhaba! Ariva Discord Şikayet Aracına Hoş Geldiniz! 📧
Dil seçin:
[1] Türkçe
[2] İngilizce
Seçiminiz ([n]): 1
Güncellemeler ve destek için t.me/ArivaTools açılıyor... 🌐

[*] ARİVA Discord Şikayet Aracı başlatıldı.
=======================================================
Mod seçin: [1] E-posta Şikayet, [2] Discord Şikayet, [3] Temizle, [4] Çıkış: 2
[1] Spam mesajlar
[2] Taciz
[3] Kural ihlali
[4] Hesap çalındı
[5] Sahte etkileşimler
[6] Ekranı temizle
[7] Çıkış
Şikayet türünü seçin (1-7): 1
Discord kullanıcı adını girin (# ile, örn. Kullanıcı#1234): Kullanıcı#1234
Discord kullanıcı ID'sini girin: 123456789012345678
Şikayet sayısını girin: 2
Şikayet gönderiliyor: abcdefgh@gmail.com +901234567890... 📤
Şikayet gönderildi: abcdefgh@gmail.com 1 ✅
Şikayet gönderiliyor: stuvwxyz@yahoo.com +994123456789... 📤
Şikayet gönderildi: stuvwxyz@yahoo.com 2 ✅
Menüye dönmek için 1, çıkmak için 0 girin: 0
Ariva Discord Şikayet Aracı kapatılıyor. Görüşürüz! 👋
```

---

## Önemli Notlar

- **Güvenlik**: E-posta şikayetleri için Gmail Uygulama Şifresi kullanın. Proxy’ler başarısız olabilir; gerekirse güncel proxy listesiyle değiştirin.
- **Discord Formu**: Form alanları (`field_11232094`, vb.) Mayıs 2025 itibarıyla geçerlidir. Hata alırsanız, `https://support.discord.com/hc/en-us/requests/new` adresindeki formu kontrol edin.
- **Etik Kullanım**: Discord Topluluk Kuralları’na ve Gmail gönderim limitlerine uyun. Kötüye kullanım, hesap yasaklamalarına yol açabilir.
- **Hata Ayıklama**: Hatalar için konsol çıktısını kontrol edin veya [t.me/ArivaTools](https://t.me/ArivaTools) üzerinden destek alın.

---

## Katkıda Bulunma

Katkılarınızı bekliyoruz! Yeni özellikler, hata düzeltmeleri veya çeviriler için:
1. Depoyu forklayın.
2. Değişikliklerinizi yeni bir branch’te yapın (`git checkout -b ozellik/yeni-ozellik`).
3. Değişiklikleri commit edin (`git commit -m 'Yeni özellik eklendi'`).
4. Pull request gönderin.

Lütfen kod stilini koruyun ve değişiklikleri açıklayın.

---

## Lisans

Bu proje MIT Lisansı altında lisanslanmıştır. Ayrıntılar için `LICENSE` dosyasına bakın.

---

## İletişim

- **Kanal**: [t.me/ArivaTools](https://t.me/ArivaTools)
- **Tasarımcı**: [@AtahananArslan](https://t.me/AtahanArslan)
- **Destek**: Sorularınız için GitHub Issues veya Telegram kanalını kullanın.

**Ariva Discord Şikayet Aracı Pro** ile şikayet süreçlerinizi kolaylaştırın! 🚀