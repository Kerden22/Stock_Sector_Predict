
# 📊 Sektörel Benzerlik Analizi ve Sınıflandırma Projesi

Bu proje, Sanayi ve Teknoloji Bakanlığı'nın Yapay Zeka Uzmanlık Programı kapsamında, TÜBİTAK’ta görev yapan İsmail Güzel hocamızın verdiği eğitim doğrultusunda, Veri Yoğun Uygulamalar dersi çerçevesinde gerçekleştirilmiştir.

## 📌 Proje Açıklaması

Bu proje, **hisse senetlerinin sektörel benzerliklerini analiz etmek ve belirli hisselerin hangi sektöre daha çok benzediğini tespit etmek** amacıyla geliştirilmiştir. **Makine öğrenimi, zaman serisi analizi ve veri madenciliği teknikleri** kullanılarak sektör bazında finansal analizler gerçekleştirilmiştir. Model, farklı sektörlerde işlem gören hisseler arasındaki ilişkileri analiz ederek **yatırım kararlarına yardımcı olacak öngörüler sağlamayı** hedeflemektedir.

----------

## 🚀 Kullanılan Teknolojiler ve Kütüphaneler

### **🔹 Python Standart Kütüphaneleri:**

-   `os`, `time`, `warnings` → Dosya işlemleri, zaman ölçümü ve hata yönetimi
-   `StringIO` → Hafızada veri işleme

### **🔹 Veri Analizi ve Görselleştirme:**

-   `numpy`, `pandas` → Veri manipülasyonu ve analiz
-   `matplotlib`, `seaborn` → Veri görselleştirme ve trend analizi

### **🔹 Web Scraping ve Veri Toplama:**

-   `requests`, `yfinance`, `BeautifulSoup` → Web'den hisse senedi ve sektör verilerini çekmek için

### **🔹 Makine Öğrenimi ve Modelleme:**

-   `scikit-learn` → Model eğitimi, hiperparametre optimizasyonu, çapraz doğrulama
-   `tsfresh` → Zaman serisi öznitelik çıkarımı
-   `xgboost`, `catboost` → Alternatif sınıflandırma modelleri
-   `GridSearchCV`, `RandomizedSearchCV` → Hiperparametre optimizasyonu

----------

## 📌 Proje Adımları

### **1️⃣ Veri Toplama ve Web Scraping**

-   Web scraping teknikleriyle farklı sektörlerin hisse senetleri hakkında **finansal veriler** toplandı.
-   Yahoo Finance API kullanılarak hisse senetlerinin fiyat, getiri ve sektör bilgileri çekildi.
-   **Aylık bazda fiyat hareketleri analiz edildi.**
-   Toplanan veriler **CSV formatında kaydedildi** ve işlenmeye hazır hale getirildi.

### **2️⃣ Veri Temizleme ve Ön İşleme**

-   Eksik veriler **istatistiksel yöntemlerle** dolduruldu.
-   Sayısal değişkenler **log dönüşümü** uygulanarak normalize edildi.
-   Kategorik değişkenler **Label Encoding** yöntemiyle modele uygun hale getirildi.

### **3️⃣ Öznitelik Çıkarımı ve Seçimi**

-   **tsfresh kütüphanesi** kullanılarak zaman serisi verilerinden **özellik çıkarıldı**.
-   `Lasso` yöntemi ile en önemli özellikler belirlenerek **gereksiz özellikler filtrelendi**.
-   Öznitelik mühendisliği ile **ek göstergeler** (volatilite, hareketli ortalama, RSI vb.) türetildi.

### **4️⃣ Makine Öğrenimi Modelleri ile Sınıflandırma**

-   `RandomForest`, `XGBoost` ve `CatBoost` modelleri kullanılarak sınıflandırma yapıldı.
-   **GridSearchCV** ve **RandomizedSearchCV** kullanılarak en iyi hiperparametreler belirlendi.
-   **Çapraz doğrulama** ile modelin doğruluk ve genelleme başarısı test edildi.

### **5️⃣ Sektörel Benzerlik Analizi**

-   Eğitilen model, **bir hissenin hangi sektöre en çok benzediğini tahmin etmek için kullanıldı**.
-   **Benzerlik oranları yüzdesel olarak hesaplandı ve görselleştirildi.**
-   **Yatırım stratejileri için öneriler sunuldu.**

### **6️⃣ Eğitilen Sektörler ile Test İşlemi**

-   Eğitilen modeller, belirlenen sektörlerdeki hisse senetleri ile **gerçek piyasa verileri üzerinden** test edildi.
-   Modelin tahmin gücü, farklı veri kümeleriyle karşılaştırılarak **genelleme yeteneği** değerlendirildi.
-   **Sektörel bazda model performansı analiz edildi.**

### **7️⃣ Parametre Güncellemeleri ile Model Optimizasyonu**

-   `ComprehensiveFCParameters`  parametresi kullanılarak **doğruluk** yükseltildi.
-   Son optimizasyon sonucunda model doğruluğu **%65’in üzerine çıkarıldı**.

----------

## 📊 Çıktılar ve Sonuçlar

-   Model, **hisse senetlerinin sektörel benzerliklerini analiz edebilir** ve hangi sektöre daha yakın olduğunu belirleyebilir.
-   Model doğruluk oranları:
    -   **RandomForest** → ~61%
    -   **XGBoost** → ~60%
    -   **CatBoost** → ~61%
    -   **RandomForest (ComprehensiveFCParameters)** → ~68%
-   **Sektörel benzerlik oranları görselleştirilerek analiz yapılabilir.**
-   **Yatırım stratejileri, belirlenen sektör benzerlik oranlarına göre oluşturulabilir.**

----------

## ⚙️ Kullanım

1.  **CSV dosyalarının yolunu ayarlayın:**
    
2.  **Sonuçları görselleştirin ve analiz yapın.**

----------

## 🔮 Eklenebilir Geliştirmeler

✅ **Daha fazla sektör eklenmesi** → Farklı piyasa segmentlerinden daha geniş veri ekleme. 
✅ **Alternatif öznitelik seçim yöntemleri** → Lasso yerine farklı yöntemlerle önemli özelliklerin belirlenmesi. 
✅ **Derin öğrenme ile optimizasyon** → Daha yüksek doğruluk elde etmek için LSTM veya Transformer tabanlı modellerin kullanılması.
✅ **Gerçek zamanlı veri analizi** → API tabanlı sistemlerle **canlı piyasa verileriyle tahmin yapılması**. 
✅ **Özelleştirilmiş yatırım önerileri** → Modele ek olarak **yatırımcı profiline uygun öneri algoritmalarının geliştirilmesi**.

Bu proje, **yatırım stratejileri geliştirmek, hisse senedi analizinde sektörel benzerlikleri daha iyi anlamak ve finansal öngörüler sağlamak için** kullanılabilir. 🚀

## Mahmut Kerem Erden - k.erden03@gmail.com
