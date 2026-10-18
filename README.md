# 💧 Akıllı Su Tüketim Tahmini ve Anomali Tespit Sistemi

![izsu2](https://github.com/user-attachments/assets/b8aa0fef-e691-447d-a6cb-1dedca44c85a)

> **Manisa Celal Bayar Üniversitesi - Yazılım Mühendisliği Bitirme Projesi**

Sürdürülebilir su yönetimi, özellikle büyük şehirlerde kaynak verimliliği ve kayıp-kaçakların önlenmesi açısından kritik bir problemdir. Bu proje, gerçek su tüketim verileri üzerinden çalışarak geleceğe yönelik tüketim tahmini yapan, anomalileri tespit eden ve yöneticiler için veriye dayalı karar destek mekanizması (DSS) sunan entegre bir yazılım sistemi olarak geliştirilmiştir.

Proje; **Veri Mühendisliği**, **Makine Öğrenmesi**, **Servis Odaklı Mimari (SOA)** ve **Modern Web Teknolojilerinin** bir arada kullanıldığı, uçtan uca çalışan bir sistem sunmayı hedefler.

---

## 🚀 Projenin Amacı

* 📅 **Geleceğe Yönelik Tahmin:** Geçmiş su tüketim verilerinden yararlanarak şehir ve ilçe bazlı tüketim tahminleri üretmek.
* 🚨 **Anomali / Kaçak Tespiti:** Beklenmedik tüketim artışlarını analiz ederek olası su kaçaklarını otomatik tespit etmek.
* 📊 **Karar Destek Sistemi (DSS):** Su yönetiminde görevli birimler için anlık izleme ve analiz yapılabilen bir altyapı sunmak.
* 🏗️ **Entegre Mimari:** Farklı teknolojilerin entegre çalıştığı ölçeklenebilir ve modüler bir mimari ortaya koymak.

---

## 🧠 Makine Öğrenmesi ve Tahmin Modeli

Sistem, **İZSU Açık Veri Portalı**'ndan alınan 2020–2024 yılları arasına ait 4900+ satırlık veri seti ile eğitilmiştir. Baraj doluluk oranları ve ilçe bazlı tüketim verileri **Lineer Regresyon** modeli ile işlenerek anlık tahminler üretilir.

![izsu3](https://github.com/user-attachments/assets/36587c8d-1534-4a02-a3f5-858764e2f01c)

*Grafikteki yeşil çizgi gerçek tüketimi, mavi kesikli çizgi ise modelimizin tahminini göstermektedir.*

* **Denenen Algoritmalar:** Random Forest, SVR, KNN, Decision Tree.
* **Seçilen Model:** En düşük hata oranını (**RMSE: 43.34**) veren Lineer Regresyon.
* **Servis:** Model, Python Flask API üzerinden mikroservis olarak sunulmaktadır.

---

## 🚨 Anomali ve Kaçak Tespiti

Sistem, olağan dışı tüketim artışlarını (örneğin; gece yarısı ani su kullanımı) tespit ederek yönetici paneline "Kritik Durum" veya "Olası Kaçak" uyarısı düşer.

![izsu7](https://github.com/user-attachments/assets/4cf7a9a4-a4f9-4b13-8d34-389d42e7e452)

---

## 🏗️ Sistem Mimarisi ve Teknoloji Yığını

Proje, **Loose Coupling** (gevşek bağlılık) prensibine uygun 6 katmanlı bir mimari üzerine kuruludur.

| Bileşen | Teknoloji / Açıklama |
| :--- | :--- |
| **Backend (Gateway)** | **Node.js**: Sistemin orkestra şefi, tüm servis akışını yönetir. |
| **ML Servisi** | **Python (Flask)**: Tahmin ve analiz işlemleri. |
| **Frontend** | **ASP.NET Core MVC**: Bootstrap ile responsive tasarım, Chart.js görselleştirme. |
| **Veritabanı** | **MSSQL**: Operasyonel veriler ve ilişkisel tablolar. |
| **ETL & OLAP** | **SSIS & SSAS**: Veri ambarı süreçleri ve küp tabanlı çok boyutlu analiz. |
| **İletişim** | **REST, SOAP, gRPC**: Farklı ihtiyaçlara göre optimize edilmiş protokoller. |

---

## 📊 Veri Analizi ve Raporlama

Kullanıcılar ve yöneticiler, ilçe bazlı karşılaştırmaları ve geçmişe dönük tüketim trendlerini detaylı grafiklerle inceleyebilir.
![izsu6](https://github.com/user-attachments/assets/ac889329-6ca4-49e7-b2fe-324b56f035a5)


### Sayaç Yönetimi
Sisteme yeni akıllı sayaçların eklenmesi ve yönetilmesi için tam yetkili bir CRUD arayüzü bulunur.

![izsu8](https://github.com/user-attachments/assets/3769b139-6fdc-44eb-b253-ad8c294e18a3)

---

## ⚙️ Kurulum ve Çalıştırma

Projeyi yerel ortamınızda ayağa kaldırmak için:

1.  **Repoyu Klonlayın:**
    ```bash
    git clone [https://github.com/busratekdemir/AkillisuTuketimi.git](https://github.com/busratekdemir/AkillisuTuketimi.git)
    ```

2.  **Veritabanı:**
    * MSSQL scriptlerini çalıştırarak veritabanı ve veri ambarını oluşturun.

3.  **ML Servisi (Python):**
    ```bash
    cd ml-service
    pip install -r requirements.txt
    python app.py  # Port 5001'de çalışır
    ```

4.  **Backend API (Node.js):**
    ```bash
    cd api-gateway
    npm install
    npm start  # Port 5000'de çalışır
    ```

5.  **Web Arayüzü:**
    * Visual Studio ile ASP.NET Core MVC projesini açın ve `IIS Express` üzerinden çalıştırın.

---

## 👥 Proje Ekibi

* **Büşra Tekdemir** – Veri Tabanı Mimarisi, ETL & OLAP, Makine Öğrenmesi
* **Busenur Çam** – Backend, SOA Mimarisi, Servis İletişimi
* **Eylül Zengin** – ML Veri Hazırlığı, Web Frontend

---
*Manisa Celal Bayar Üniversitesi - 2025/2026 Güz Dö
