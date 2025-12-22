# ☁️ Bulut Tabanlı Duygu Analizi Platformu (Cloud-Based Sentiment Analysis)

> **Ders:** Bulut Bilişim ve Sanallaştırma  
> **Platform:** Google Cloud Platform (GCP)  
> **Durum:** Yayında 🟢  

## 📖 Proje Özeti
Bu proje, **Kocaeli Üniversitesi** Bilgisayar Mühendisliği Bölümü, "Bulut Bilişim ve Sanallaştırma" dersi kapsamında geliştirilmiştir. Projenin temel amacı, yerel kaynakları tüketmek yerine bulut altyapısı üzerinde çalışan, **ölçeklenebilir** ve **platform bağımsız** bir Yapay Zeka (AI) servisi oluşturmaktır.

Proje, kullanıcıdan alınan metin verilerini **Google Cloud Compute Engine** üzerinde barındırılan sanal bir sunucuya iletir. Sunucu tarafında çalışan Python tabanlı doğal dil işleme (NLP) algoritmaları, metnin duygu durumunu (Pozitif/Negatif) ve şiddetini analiz ederek anlık yanıt döner.

---

## 🏗️ Sistem Mimarisi ve Çalışma Mantığı
Proje, klasik **İstemci-Sunucu (Client-Server)** mimarisine dayanmaktadır.

1.  **İstemci (Client):** Kullanıcı web arayüzü üzerinden metni girer. JavaScript (AJAX) bu veriyi paketler.
2.  **Ağ (Network):** Veri, HTTP protokolü üzerinden Google Cloud veri merkezindeki sunucunun statik IP adresine iletilir.
3.  **Sunucu (Cloud VM):** Ubuntu işletim sistemi üzerinde çalışan Flask servisi isteği karşılar.
4.  **İşlem (Processing):** NLP motoru metni analiz eder, 0 ile 1 arasında bir **Polarite Skoru** üretir.
5.  **Kalıcılık:** Sonuçlar veritabanına kaydedilir ve geçmiş analiz tablosunda listelenir.

---

## 🛠️ Kullanılan Teknolojiler

### ☁️ Bulut ve Altyapı (Infrastructure)
* **Google Cloud Platform (GCP):** Projenin ana barındırma sağlayıcısı.
* **Compute Engine (VM):** Uygulamanın üzerinde koştuğu sanal makine (Ubuntu Linux).

### ⚙️ Backend (Arka Uç)
* **Python 3.x:** Ana programlama dili.
* **Flask:** Hafif (lightweight) ve hızlı Web Framework.
* **TextBlob / NLTK:** Duygu analizi yapan NLP kütüphaneleri.

### 🎨 Frontend (Ön Yüz)
* **HTML5 & CSS3:** Modern ve responsive tasarım.
* **JavaScript (ES6):** Asenkron veri iletişimi ve DOM manipülasyonu.
* **Jinja2:** Python verilerini HTML şablonuna gömmek için kullanılan motor.

---

## 🚀 Temel Özellikler
* ✅ **Gerçek Zamanlı Analiz:** Girilen metni anlık olarak işleyip sonucu gösterir.
* 📊 **Skorlama Algoritması:** Sadece "İyi/Kötü" demez; duygunun şiddetini (Örn: 0.95 - Çok Güçlü Pozitif) sayısal olarak verir.
* 📝 **Geçmiş Kayıtlar:** Yapılan son analizleri hafızada tutarak liste halinde sunar.
* 🌍 **Uzaktan Erişim:** Bulut tabanlı olduğu için internete bağlı her cihazdan erişilebilir.

---

## 📂 Proje Dizin Yapısı

```text
cloud-sentiment-analysis/
├── app.py                # Ana Flask uygulaması ve backend kodları
├── Dockerfile            # Konteynerizasyon ayarları
├── requirements.txt      # Gerekli Python kütüphaneleri
├── static/               # CSS, JavaScript ve Görsel dosyalar
│   ├── style.css
│   └── script.js
└── templates/            # HTML arayüz dosyaları
    └── index.html
