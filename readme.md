# California Housing Prices - Konut Fiyat Tahmini

## Proje İsmi:
California Housing Price Correlation & Prediction

## Projenin Amacı:
Bu projenin amacı, California'daki konut özelliklerini (lokasyon, oda sayısı, nüfus vb.) kullanarak evlerin medyan değerlerini tahmin eden regresyon modelleri geliştirmektir. Projede XGBoost, Random Forest, AdaBoost ve Gradient Boosting gibi algoritmaların performansları karşılaştırılarak en iyi tahminleyiciyi belirlemek hedeflenmiştir.

## Yapılan İşlemler:
1. **Veri Yükleme ve Keşif:** `housing.csv` dosyası yüklendi ve verinin yapısı (`info`, `describe`, `isnull`) incelendi.
2. **Veri Temizleme:** `total_bedrooms` sütunundaki eksik değerler medyan ile dolduruldu. Veri setinde yinelenen kayıt olmadığı doğrulandı.
3. **Aykırı Değer Analizi:** `median_house_value` sütunundaki aykırı değerler IQR yöntemi kullanılarak tespit edildi ve temizlendi.
4. **Özellik Mühendisliği:** Kategorik bir değişken olan `ocean_proximity` sütunu One-Hot Encoding yöntemi ile sayısal hale getirildi.
5. **Veri Görselleştirme:** Verilerin dağılımını anlamak için histogramlar (`plot_histogram`) çizildi.
6. **Veri Ön İşleme:**
    - Veri seti eğitim ve test olarak ikiye ayrıldı.
    - Hedef değişken (`y_train`) Box-Cox dönüşümü ile normalize edildi.
    - Özellikler `StandardScaler` kullanılarak ölçeklendirildi.
7. **Model Eğitimi ve Karşılaştırma:** Random Forest, AdaBoost, Gradient Boosting, XGBoost, Linear Regression, SVR ve Decision Tree modelleri eğitildi.
8. **Hiperparametre Optimizasyonu:** `GridSearchCV` kullanılarak Random Forest ve XGBoost modelleri için en iyi parametreler arandı.

## Sonuçlar:
Yapılan testler sonucunda elde edilen R2 skorları:
- **XGBoost R2 Skoru:** 0.8132
- **Random Forest R2 Skoru:** 0.8032
(Not: Bu değerler `GridSearchCV` sonrası elde edilen yaklaşık sonuçlardır.)

XGBoost modeli, California konut fiyatlarını tahmin etmede diğer modellerden biraz daha yüksek performans göstermiştir.

## Kullanılan Dataset:
[California Housing Prices - Kaggle](https://www.kaggle.com/datasets/camnugent/california-housing-prices)
