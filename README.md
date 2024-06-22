# CNN Derin Öğrenme Modeli İle Beden ve Ürün Tavsiye Sistemi Oluşturma

## Proje Konusu ve Amacı
Kullanıcı tarafından yüklenen fotoğrafın insan olup olmadığının tespitinden sonra beden ölçülerini tahminleyerek incelediği ürünler için beden tavsiyesinde bulunmak, vücut tipine uygun kıyafet önerilerinde bulunmak ve son aşama olarak beğendiği ya da tavsiye edilen kıyafetleri yüklediği fotoğrafa işlenmesini sağlamak amaçlanmıştır. Bu şekilde müşteri memnuniyetini arttırmak, iade oranları düşürmek, müşterinin karar verme ve satın alma hızı arttırmak, yenilik içerdiği için dikkat çekecek bu da site ziyaretlerini ve dolayısıyla satışı arttırmak hedeflenmektedir.

## Proje Adımları:

- 1- Yüklenen fotoğrafın insana ait olup olmadığının tespiti
- 2- Yüklenen fotoğrafta işaretleme yöntemi ile beden ölçülerinin tahmin edilmesi
- 3- Yüklenen fotoğraf analiz edilerek vücut tipinin tahmin edilmesi
- 4- Tavsiye edilen ürünle yüklenen fotoğrafın birleştirilerek müşterinin ürünü direkt kendi üstünde görmesinin sağlanması.

Bu projede Ana Projenin İlk Adımı olan CNN Modeli ile Kullanıcının Yüklediği Fotoğrafın Değerlendirilmesi'ni gerçekleştireceğiz.

# CNN Modeli ile Kullanıcının Yüklediği Fotoğrafın Değerlendirilmesi

## İçindekiler

- Veri Seti
- Metod
- Görselleştirme
- CNN ile Model Eğitimi
- Örnek Uygulama
- Sonuç
- Tartışma ve Değerlendirme
- Kaynakça

## Proje Kurulumu

Proje colab üzerinde yazıldığı için direkt colab üzerinde çalıştırılabilir ya da .ipynb dosyasını indirerek jupiter notebookta çalıştırılabilirsiniz.

## Veri Seti

CIFAR-100 veri kümesi, 100 sınıfa ayrılmış 60.000 görüntüden oluşmaktadır. Her sınıf, eğitim için 500 ve test için 100 olmak üzere 600 görüntü içerir. Görüntüler renkli ve 32x32 piksel boyutundadır.

CIFAR-100 veri kümesindeki tüm üst sınıflar ve o sınıflara ait alt sınıflar şunlardır:

-Suda Yaşayan Memeliler: Kunduz, Yunus, Su samuru, Fok, Balina
-Balık: Akvaryum balıkları, Yassı balık, Işın, Köpekbalığı, Alabalık
-Çiçekler: Orkideler, Gelincikler, Güller, Ayçiçeği, Laleler
-Gıda Kapları: Şişeler, Kaseler, Kutular, Bardaklar, Tabaklar
-Meyve ve Sebzeler: Elmalar, Mantarlar, Portakallar, Armutlar, Tatlı biberler
-Evdeki Elektrikli Cihazlar: Saat, Bilgisayar klavyesi, Lamba, Telefon, Televizyon
-Ev Eşyası: Yatak, Sandalye, Kanepe, Masa, Gardırop
-Haşarat: Arı, Böcek, Kelebek, Tırtıl, Hamamböceği
-Büyük Etoburlar: Ayı, Leopar, Aslan, Kaplan, Kurt
-İnsan Yapımı Büyük Dış Mekan Eşyaları: Köprü, Kale, Ev, Yol, Gökdelen
-Büyük Doğal Dış Mekan Sahneleri: Bulut, Orman, Dağ, Ova, Deniz
-Büyük Omnivorlar ve Otçullar: Deve, Sığır, Şempanze, Fil, Kanguru
-Orta Boy Memeliler: Tilki, Kirpi, Keseli sıçan, Rakun, Kokarca
-Böcek Olmayan Omurgasızlar: Yengeç, Istakoz, Salyangoz, Örümcek, Solucan
-İnsanlar: Bebek, Erkek Çocuk, Kız Çocuk, Erkek , Kadın
-Sürüngenler: Timsah, Dinozor, Kertenkele, Yılan, Kaplumbağa
-Küçük Memeliler: Hamster, Fare, Tavşan, Kır faresi, Sincap
-Ağaçlar: Akçaağaç, Meşe, Palmiye, Çam, Söğüt
-Araçlar 1: Bisiklet, Otobüs, Motosiklet, Kamyonet, Tren
-Araçlar 2: Çim biçme makinesi, Roket, Tramvay, Tank, Traktör

## Metod

## Kullanılan Model

## Kullanılan Değerlendirme Metriği
## Sonuç
## Tartışma ve Değerlendirme
## Kaynakça



## Sonuç

| Model | Eğitim Doğruluğu | Test Doğruluğu | F1 Skoru | Recall | Precision |
|----------|----------|----------|----------|----------|----------|
| CNN | 0.8998 | 0.8554 | 0.8546 | 0.8554 | 0.8578 |
| Random Forest | 0.9999 | 0.8733 | 0.8717 | 0.8733 | 0.8722 |
| Decision Tree | 1.0000 | 0.7902 | 0.7910 | 0.7902 | 0.7920 |
| Gradient Boosting | 0.9113 | 0.8681 | 0.8677 | 0.8681 | 0.8677 |
| XGBoost | 0.9997 | 0.8985 | 0.8717 | 0.9012 | 0.9013 |
| SVM | 0.9128 | 0.8828 | 0.8823 | 0.8823 | 0.8823 |
