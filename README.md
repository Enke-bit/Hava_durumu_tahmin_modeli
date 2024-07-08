# 🌤️ WeatherWise: Hava Durumu Tahmin Sistemi
## 📋 Proje Tanımı
WeatherWise projesi, hava durumu tahminlerini daha isabetli hale getirmek için geliştirilmiş bir sınıflandırma modelidir. Hava durumu tahminleri, tarım, ulaşım, enerji yönetimi gibi birçok alanda kritik öneme sahiptir. Bu proje, hava durumu verilerini kullanarak doğru tahminler yapabilen bir model oluşturmayı amaçlamaktadır.

## 📁 Veri Seti
Bu proje kapsamında kullanılan veri seti aşağıdaki sütunları içermektedir:

- 🌡️ Sıcaklık (Temperature)
- 💧 Nem (Humidity)
- 🌬️ Rüzgar Hızı (Wind Speed)
- ☔ Yağış Oranı (Precipitation %)
- ☁️ Bulut Örtüsü (Cloud Cover)
- 📈 Atmosfer Basıncı (Atmospheric Pressure)
- 🌞 UV İndeksi (UV Index)
- 🌿 Mevsim (Season)
- 👁️ Görüş Mesafesi (Visibility)
- 📍 Konum (Location)
- 🌦️ Hava Türü (Weather Type - Hedef Değişken)
## 🔍 Veri Hazırlama
Veri seti üzerinde öncelikle eksik veriler kontrol edilmiştir. Kategorik sütunlar sayısal verilere dönüştürülmüş ve veri seti eğitim ve test setlerine ayrılmıştır.

## 🧠 Model Geliştirme
Random Forest sınıflandırıcısı kullanılarak model geliştirilmiştir. Modelin performansı doğruluk oranı (accuracy), sınıflandırma raporu (classification report) ve karışıklık matrisi (confusion matrix) kullanılarak değerlendirilmiştir.

## 🎯 Performans Sonuçları
Modelin performansı aşağıdaki gibi elde edilmiştir:

Accuracy: 0.91
## Classification Report

            precision    recall  f1-score   support

         0       0.87      0.89      0.88       651
         1       0.91      0.91      0.91       647
         2       0.93      0.94      0.94       701
         3       0.93      0.90      0.91       641

  accuracy                           0.91      2640
 macro avg       0.91      0.91      0.91      2640

## weighted avg 0.91 0.91 0.91 2640


## 📚 Kullanılan Teknolojiler
- **Python**: Veri işleme, model geliştirme ve değerlendirme süreçlerinde kullanılan temel programlama dili.
- **Pandas**: Veri okuma, işleme ve analiz için kullanılan kütüphane.
- **Scikit-Learn**: Makine öğrenmesi modellerini oluşturmak ve değerlendirmek için kullanılan kütüphane.
- **Matplotlib ve Seaborn**: Veri görselleştirme için kullanılan kütüphaneler.

## 🚀 Gelecek Çalışmalar
Bu çalışmanın sonuçları umut verici olmakla birlikte, gelecekte aşağıdaki geliştirmeler planlanmaktadır:

1. **Model Performansının İyileştirilmesi**: Farklı makine öğrenmesi algoritmaları (örn. Gradient Boosting, Neural Networks) kullanılarak model performansı iyileştirilebilir.
2. **Daha Fazla Veri**: Daha geniş ve çeşitli veri setleri kullanarak modelin genelleme yeteneği artırılabilir.
3. **Gerçek Zamanlı Tahmin**: Gerçek zamanlı hava durumu verilerini kullanarak anlık tahminler yapılabilir.
4. **Özellik Mühendisliği**: Daha fazla özellik eklenerek modelin tahmin gücü artırılabilir. Örneğin, geçmiş hava durumu verileri, mevsimsel döngüler ve coğrafi faktörler gibi.
5. **Modelin Kullanılabilirliği**: Geliştirilen modelin web veya mobil uygulamalar üzerinden kullanıcılara sunulması, pratik bir kullanım imkanı sağlayacaktır.

## 📈 Rastgele Gün Tahmini
Aşağıdaki kod, rastgele bir gün seçerek tahmin yapar ve bu tahmini gerçek değer ile karşılaştırır:

```python
import random

###  Rastgele bir indeks seçin
random_index = random.randint(0, len(X_test) - 1)

###  Seçilen günün özelliklerini alın
random_day_features = X_test.iloc[random_index]
random_day_actual = y_test.iloc[random_index]

### Tahmin yapın
random_day_prediction = rf_classifier.predict([random_day_features])

### Sonuçları karşılaştırın
print(f"Seçilen günün özellikleri: \n{random_day_features}")
print(f"Gerçek Hava Türü: {label_encoder.inverse_transform([random_day_actual])[0]}")
print(f"Tahmin Edilen Hava Türü: {label_encoder.inverse_transform(random_day_prediction)[0]}")


# Lisans ve destek vermek için:
## 🤝 Katkıda Bulunma
Projeye katkıda bulunmak isterseniz, lütfen bir pull request oluşturun veya bir issue açın. Her türlü geri bildirime açığız.

## Lisans Bu proje MIT Lisansı altında lisanslanmıştır. Lisans detaylarını LICENSE dosyasından görebilirsiniz.

