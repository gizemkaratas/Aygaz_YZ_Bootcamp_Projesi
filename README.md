# Fashion MNIST Makine Öğrenimi Modelleri Karşılaştırma Projesi

## Proje Hakkında
  Bu proje, Fashion MNIST veri seti üzerinde çeşitli makine öğrenimi modellerinin performanslarını karşılaştırmak amacıyla yürütülmüştür. Projede kullanılan modeller şunlardır:

- K-Nearest Neighbors (KNN)
- Random Forest
- Decision Tree
- Support Vector Machine (SVM)
- XGBoost
- Gradient Boosting

Her bir modelin eğitim ve test doğruluğu, F1 skoru, hatırlama ve kesinlik gibi metrikler kullanılarak değerlendirilmiştir.


## İçindekiler

- Kurulum
- Veri Seti
- Kullanılan Yöntemler
- Sonuçlar
- Tartışma ve Değerlendirme
- Görseller

## Kurulum

Bu projeyi çalıştırmak için aşağıdaki adımları izleyin:

### 1.Depoyu Klonlayın:

```ruby
git clone https://github.com/sisenn/Aygaz-Yapay-Zeka-Proje-Bootcamp/tree/main
cd fashion-mnist-ml-comparison

```
### 2.Gerekli Kütüphaneleri Yükleyin:

```ruby
pip install -r requirements.txt
```

### 3.Jupyter Notebook'u Başlatın:

```ruby
jupyter notebook
```
### 4.Notebook'u Açın ve Çalıştırın:

fashion_mnist_comparison.ipynb dosyasını açın ve hücreleri sırasıyla çalıştırın.

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

## Kullanılan Yöntemler

### K-Nearest Neighbors (KNN):
KNN, her bir veri noktasını en yakın komşularına göre sınıflandıran basit bir algoritmadır. Bu projede, n_neighbors=5 olarak belirlenmiştir.

### Random Forest:
Random Forest, birden fazla karar ağacından oluşan bir topluluk yöntemidir. Ağaçların çoğunluk kararına göre sınıflandırma yapar.

### Decision Tree:
Decision Tree, verileri özelliklerine göre sınıflandıran ve her dalında kararlar alarak ilerleyen bir yapıdır.

### Support Vector Machine (SVM):
SVM, verileri ayıran en iyi hiper düzlemi bulmaya çalışan bir sınıflandırıcıdır.

### Gradient Boosting:
Gradient Boosting, hata oranını azaltmak için zayıf sınıflandırıcılar ekleyerek çalışan bir topluluk yöntemidir.

### XGBoost:
XGBoost, Gradient Boosting algoritmasının optimize edilmiş bir versiyonudur. Genellikle daha hızlı ve daha performanslıdır.

## Sonuçlar

| Model | Eğitim Doğruluğu | Test Doğruluğu | F1 Skoru | Recall | Precision |
|----------|----------|----------|----------|----------|----------|
| KNN | 0.8998 | 0.8554 | 0.8546 | 0.8554 | 0.8578 |
| Random Forest | 0.9999 | 0.8733 | 0.8717 | 0.8733 | 0.8722 |
| Decision Tree | 1.0000 | 0.7902 | 0.7910 | 0.7902 | 0.7920 |
| Gradient Boosting | 0.9113 | 0.8681 | 0.8677 | 0.8681 | 0.8677 |
| XGBoost | 0.9997 | 0.8985 | 0.8717 | 0.9012 | 0.9013 |
| SVM | 0.9128 | 0.8828 | 0.8823 | 0.8823 | 0.8823 |
