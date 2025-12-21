☁️ Bulut Tabanlı Duygu Analizi Platformu (Cloud-Based Sentiment Analysis)
Ders: Bulut Bilişim ve Sanallaştırma | Platform: Google Cloud Platform (GCP) | Durum: Yayında 🟢

📖 Proje Özeti
Bu proje, Kocaeli Üniversitesi Bilgisayar Mühendisliği Bölümü, "Bulut Bilişim ve Sanallaştırma" dersi kapsamında geliştirilmiştir. Projenin temel amacı, yerel kaynakları tüketmek yerine bulut altyapısı üzerinde çalışan, ölçeklenebilir ve platform bağımsız bir Yapay Zeka (AI) servisi oluşturmaktır.

Proje, kullanıcıdan alınan metin verilerini Google Cloud Compute Engine üzerinde barındırılan sanal bir sunucuya iletir. Sunucu tarafında çalışan Python tabanlı doğal dil işleme (NLP) algoritmaları, metnin duygu durumunu (Pozitif/Negatif) ve şiddetini analiz ederek milisaniyeler içinde istemciye yanıt döner.

🏗️ Sistem Mimarisi ve Çalışma Mantığı
Proje, klasik İstemci-Sunucu (Client-Server) mimarisine dayanmaktadır ve sanallaştırma teknolojileri üzerine inşa edilmiştir.

İstemci (Client): Kullanıcı, web arayüzü üzerinden metni girer. JavaScript (AJAX), bu veriyi JSON formatında paketler.

Ağ (Network): Veri, HTTP protokolü üzerinden Google Cloud veri merkezindeki (us-central1) sunucunun statik IP adresine iletilir.

Sunucu (Cloud VM): Ubuntu işletim sistemi üzerinde çalışan Flask servisi, gelen isteği karşılar.

İşlem (Processing): NLP motoru metni analiz eder, 0 ile 1 arasında bir Polarite Skoru üretir.

Veri Kalıcılığı: Analiz sonuçları, tarihçe takibi için veritabanına kaydedilir.

🛠️ Kullanılan Teknolojiler ve Araçlar
☁️ Bulut ve Altyapı (Infrastructure)
Google Cloud Platform (GCP): Projenin ana barındırma sağlayıcısı.

Compute Engine (VM): Uygulamanın üzerinde koştuğu sanal makine servisi.

Ubuntu Server (Linux): Kararlılık ve performans için tercih edilen sunucu işletim sistemi.

Docker: Uygulamanın bağımlılıklarını izole etmek ve "her yerde çalışabilir" (containerization) hale getirmek için kullanıldı.

⚙️ Backend (Arka Uç)
Python 3.x: Ana programlama dili.

Flask: Hafif (lightweight) ve hızlı olduğu için tercih edilen Web Framework.

TextBlob / NLTK: Metin madenciliği ve duygu analizi yapan NLP kütüphaneleri.

🎨 Frontend (Ön Yüz)
HTML5 & CSS3: Modern ve responsive (mobil uyumlu) tasarım.

JavaScript (ES6): Asenkron veri iletişimi ve DOM manipülasyonu.

Jinja2: Python verilerini HTML şablonuna dinamik olarak gömmek için kullanılan motor.

🚀 Temel Özellikler
✅ Gerçek Zamanlı Analiz: Girilen metni anlık olarak işleyip sonucu gösterir.

📊 Skorlama Algoritması: Sadece "İyi/Kötü" demez; duygunun şiddetini (Örn: 0.95 - Çok Güçlü Pozitif) sayısal olarak verir.

📝 Geçmiş Kayıtlar: Yapılan son analizleri hafızada tutarak liste halinde sunar.

🌍 Uzaktan Erişim: Bulut tabanlı olduğu için internete bağlı her cihazdan erişilebilir.

📂 Proje Dizin Yapısı
Plaintext

cloud-sentiment-analysis/
├── app.py                # Ana Flask uygulaması ve backend kodları
├── Dockerfile            # Konteynerizasyon ayarları
├── requirements.txt      # Gerekli Python kütüphaneleri
├── static/               # CSS, JavaScript ve Görsel dosyalar
│   ├── style.css
│   └── script.js
└── templates/            # HTML arayüz dosyaları
    └── index.html
