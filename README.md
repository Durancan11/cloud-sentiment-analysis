# Cloud-Based Sentiment Analysis Platform ☁️

Bu proje, Bulut Bilişim ve Sanallaştırma dersi kapsamında **Google Cloud Platform (GCP)** üzerinde geliştirilmiştir. Python ve Docker teknolojileri kullanılarak, metinlerin duygu durumunu (Pozitif/Negatif) analiz eden ölçeklenebilir bir web servisi oluşturulmuştur.

## 🛠️ Kullanılan Teknolojiler
* **Google Cloud Compute Engine:** Sanal sunucu altyapısı.
* **Docker:** Uygulama konteynerizasyonu.
* **Python (Flask):** Backend ve yapay zeka mantığı.
* **HTML/CSS:** Kullanıcı arayüzü.
* **Linux (Ubuntu):** Sunucu işletim sistemi.

## 🚀 Proje Kurulumu
Bu projeyi kendi bilgisayarınızda çalıştırmak için:

1. Repoyu klonlayın:
   `git clone https://github.com/KULLANICI_ADIN/cloud-sentiment-analysis.git`

2. Docker imajını oluşturun:
   `docker build -t duygu-analizi .`

3. Konteyneri başlatın:
   `docker run -p 5000:5000 duygu-analizi`
