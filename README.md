# 📸 CIFAR-10 Veri Setinde CNN ile Görüntü Sınıflandırma

Bu proje, TensorFlow ve Keras kullanarak **CIFAR-10** veri setinde basit bir **Convolutional Neural Network (CNN)** modeli eğitmekte ve sınıflandırma performansını görselleştirmektedir.

---

## 🔍 Proje Özeti

- CIFAR-10 veri seti 10 farklı sınıfa sahip 60,000 renkli görüntü içerir (32x32 piksel).
- Veri seti eğitim ve test olarak ayrılmıştır.
- Görüntü pikselleri 0-1 aralığında normalize edilmiştir.
- 3 katmanlı CNN mimarisi kurulmuştur:
  - 3 adet Conv2D + ReLU aktivasyonlu katman
  - 2 adet MaxPooling katmanı
- Model, `SparseCategoricalCrossentropy` kayıp fonksiyonu ve `Adam` optimizasyon algoritması ile derlenmiştir.
- Model 10 epoch boyunca eğitilmiştir.
- Eğitim ve doğrulama (validation) doğruluk değerleri çizdirilmiştir.

---

## ⚙️ Kullanılan Kütüphaneler

- `tensorflow` (Keras dahil)
- `matplotlib`
- `numpy` (varsayılan olarak TensorFlow ile birlikte)

---

## 🛠️ Kod Akışı

1. **Veri Yükleme ve Hazırlık**
   - CIFAR-10 veri seti indirilir.
   - Görüntüler 0-1 aralığında normalize edilir.
   - Sınıf isimleri tanımlanır.

2. **Veri Görselleştirme**
   - Eğitim verisinden 25 örnek rastgele seçilip sınıf etiketiyle gösterilir.

3. **Model Tanımı**
   - CNN mimarisi oluşturulur:
     - Conv2D(32, (3,3)) + ReLU + MaxPooling
     - Conv2D(64, (3,3)) + ReLU + MaxPooling
     - Conv2D(64, (3,3)) + ReLU
   - Flatten + Dense(64, ReLU) + Dense(10) (output)

4. **Model Derleme**
   - Optimizasyon: Adam
   - Kayıp: SparseCategoricalCrossentropy (from_logits=True)
   - Metrik: Accuracy

5. **Model Eğitimi**
   - 10 epoch boyunca eğitim ve validasyon verisi üzerinde

6. **Performans Görselleştirme**
   - Eğitim ve validasyon doğruluk grafiği çizilir.

---

## 📈 Model Performansı

- Eğitim ve doğrulama doğrulukları her epoch sonunda gösterilir.
- Doğruluk grafiği ile overfitting veya underfitting durumları gözlemlenebilir.

---

## 🚀 Çalıştırma Talimatları

1. Gerekli paketleri yükleyin:

```bash
pip install tensorflow matplotlib
