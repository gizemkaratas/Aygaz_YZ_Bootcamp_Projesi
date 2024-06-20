# Ecom Beden Tavsiye Sistemi Projesi / cifar100 ile CNN Derin Öğrenme Modeli Değerlendirme

## Proje Konusu ve Amacı
cifar100 veri seti iüzerinde görsel veriler için en uygun modellerden biri olan CNN modelini kullanarak değerlendirildi. Amaç


Her bir modelin eğitim ve test doğruluğu, F1 skoru, hatırlama ve kesinlik gibi metrikler kullanılarak değerlendirilmiştir.


## İçindekiler

- Kurulum
- Veri Seti
- Görseller
- CNN ile Model Eğitimi
- Tartışma ve Değerlendirme
- Örnek Uygulama
- Sonuç

## Proje Çalıştırma 

Proje colab üzerinde yazıldığı için ipy dosyasını tıklayarak direkt colab üzerinde aç sekmesinde çalıştırabilirsiniz.


## Veri Seti

Fashion MNIST, 10 farklı moda ürünü sınıfına ait 70,000 gri tonlamalı görüntüden oluşan bir veri setidir. Görüntüler 28x28 piksel boyutundadır. Veri seti, eğitim için 60,000 ve test için 10,000 görüntü içermektedir. Sınıflar aşağıdaki gibidir:

- Tişört/Üst
- Pantolon
- Kazak
- Elbise
- Ceket
- Sandalet
- Gömlek
- Spor Ayakkabı
- Çanta
- Çizme

## Kullanılan Yöntem

### K-Nearest Neighbors (CNN):
KNN, her bir veri noktasını en yakın komşularına göre sınıflandıran basit bir algoritmadır. Bu projede, n_neighbors=5 olarak belirlenmiştir.



## Sonuçlar

| Model | Eğitim Doğruluğu | Test Doğruluğu | F1 Skoru | Recall | Precision |
|----------|----------|----------|----------|----------|----------|
| KNN | 0.8998 | 0.8554 | 0.8546 | 0.8554 | 0.8578 |
| Random Forest | 0.9999 | 0.8733 | 0.8717 | 0.8733 | 0.8722 |
| Decision Tree | 1.0000 | 0.7902 | 0.7910 | 0.7902 | 0.7920 |
| Gradient Boosting | 0.9113 | 0.8681 | 0.8677 | 0.8681 | 0.8677 |
| XGBoost | 0.9997 | 0.8985 | 0.8717 | 0.9012 | 0.9013 |
| SVM | 0.9128 | 0.8828 | 0.8823 | 0.8823 | 0.8823 |
