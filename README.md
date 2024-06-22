# CNN Derin Öğrenme Modeli İle Beden ve Ürün Tavsiye Sistemi Oluşturma

## Proje Konusu ve Amacı
Kullanıcı tarafından yüklenen fotoğrafın insan olup olmadığının tespitinden sonra beden ölçülerini tahminleyerek incelediği ürünler için beden tavsiyesinde bulunmak, vücut tipine uygun kıyafet önerilerinde bulunmak ve son aşama olarak beğendiği ya da tavsiye edilen kıyafetleri yüklediği fotoğrafa işlenmesini sağlamak amaçlanmıştır. Bu şekilde müşteri memnuniyetini arttırmak, iade oranları düşürmek, müşterinin karar verme ve satın alma hızı arttırmak, yenilik içerdiği için dikkat çekecek bu da site ziyaretlerini ve dolayısıyla satışı arttırmak hedeflenmektedir.

## Proje Adımları:

- 1- Yüklenen fotoğrafın insana ait olup olmadığının tespiti
- 2- Yüklenen fotoğrafta işaretleme yöntemi ile beden ölçülerinin tahmin edilmesi
- 3- Yüklenen fotoğraf analiz edilerek vücut tipinin tahmin edilmesi
- 4- Tavsiye edilen ürünle yüklenen fotoğrafın birleştirilerek müşterinin ürünü direkt kendi üstünde görmesinin sağlanması.

Bu projede Ana Projenin İlk Adımı olan CNN Modeli ile Kullanıcının Yüklediği Fotoğrafın Değerlendirilmesini gerçekleştireceğiz.

# CNN Modeli ile Kullanıcının Yüklediği Fotoğrafın Değerlendirilmesi

## İçindekiler

- Veri Seti
- Metod
- Model
- Sonuç

## Proje Kurulumu

Proje colab üzerinde yazıldığı için direkt colab üzerinde çalıştırılabilir ya da .ipynb dosyasını indirerek jupiter notebookta çalıştırılabilirsiniz.

## Veri Seti

CIFAR-100 veri kümesi, 100 sınıfa ayrılmış 60.000 görüntüden oluşmaktadır. Her sınıf, eğitim için 500 ve test için 100 olmak üzere 600 görüntü içerir. Görüntüler renkli ve 32x32 piksel boyutundadır.

CIFAR-100 veri kümesindeki tüm üst sınıflar ve o sınıflara ait alt sınıflar şunlardır:

- Suda Yaşayan Memeliler: Kunduz, Yunus, Su samuru, Fok, Balina
- Balık: Akvaryum balıkları, Yassı balık, Işın, Köpekbalığı, Alabalık
- Çiçekler: Orkideler, Gelincikler, Güller, Ayçiçeği, Laleler
- Gıda Kapları: Şişeler, Kaseler, Kutular, Bardaklar, Tabaklar
- Meyve ve Sebzeler: Elmalar, Mantarlar, Portakallar, Armutlar, Tatlı biberler
- Evdeki Elektrikli Cihazlar: Saat, Bilgisayar klavyesi, Lamba, Telefon, Televizyon
- Ev Eşyası: Yatak, Sandalye, Kanepe, Masa, Gardırop
- Haşarat: Arı, Böcek, Kelebek, Tırtıl, Hamamböceği
- Büyük Etoburlar: Ayı, Leopar, Aslan, Kaplan, Kurt
- İnsan Yapımı Büyük Dış Mekan Eşyaları: Köprü, Kale, Ev, Yol, Gökdelen
- Büyük Doğal Dış Mekan Sahneleri: Bulut, Orman, Dağ, Ova, Deniz
- Büyük Omnivorlar ve Otçullar: Deve, Sığır, Şempanze, Fil, Kanguru
- Orta Boy Memeliler: Tilki, Kirpi, Keseli sıçan, Rakun, Kokarca
- Böcek Olmayan Omurgasızlar: Yengeç, Istakoz, Salyangoz, Örümcek, Solucan
- İnsanlar: Bebek, Erkek Çocuk, Kız Çocuk, Erkek , Kadın
- Sürüngenler: Timsah, Dinozor, Kertenkele, Yılan, Kaplumbağa
- Küçük Memeliler: Hamster, Fare, Tavşan, Kır faresi, Sincap
- Ağaçlar: Akçaağaç, Meşe, Palmiye, Çam, Söğüt
- Araçlar 1: Bisiklet, Otobüs, Motosiklet, Kamyonet, Tren
- Araçlar 2: Çim biçme makinesi, Roket, Tramvay, Tank, Traktör

## Metod
cifar100 veri seti çok fazla sınıf barındırdığı için bu kadar sınıf ile eğitilen modelin spesifik tek bir alt ya da üst sınıfı tahminleme doğruluk oranının çok düşük olmasını bekleriz, hem eğitilmesi uzun zamanımızı alır hem de sonuçları güven vermeyecek kadar düşük olacaktır . Bu sebeple veri seti projenin amacı doğrultusunda yeniden sınıflandırıldı. Projenin ilk adımındaki amaç kullanıcı tarafından yüklenen görselin insan olup olmadığının tahminlemesini yapmaktır. Bu sebeple veri seti aşağıdaki şekilde bölünmüştür:
- 1 : İnsan Olanlar ==> [2, 11, 35, 41, 46, 98] kız bebek, erkek bebek, kız çocuk,erkek çocuk,kadın,erkek 
  
- 0 : İnsan Olmayanlar ==> insan labelları haricindeki tüm label etiketleri

bu şekilde ikiye ayrılan veri setinin insan olan ve olmayan olarak sınıflandırarak doğruluk oranının çok daha yüksek çıkmasını sağlanmıştır. İnsan verileri ve diğer veriler arasındaki dengesizlik giderilerek yüksek tahmin kabiliyeti elde edilmiştir.

## Kullanılan Model

### CNN (Convolutional Neural Network)
Özellikle görsel verilerle çalışmak için tasarlandığı için bu projede CNN derin öğrenme modeli kullanılmıştır.
- CNN Nedir?
CNN, görsel veri analizi için tasarlanmış bir yapay sinir ağı türüdür. Görüntü işleme problemlerinde başarılı olan bu model, özellikle görüntü sınıflandırma, nesne tanıma, yüz tanıma, çizgi çekme gibi görevlerde kullanılır. CNN'ler, verilerdeki hiyerarşik özellikleri öğrenme yeteneğine sahiptir.

- Neden Görsel Verilerde Kullanılır?
Yapısal Özelliklerin İncelenmesi: Görüntülerdeki yapısal özellikler (kenarlar, köşeler, desenler vb.) CNN'ler tarafından öğrenilebilir. Bu özellikler, nesne tanıma ve sınıflandırmada önemlidir.
Ölçek Uyumlu Modelleme: CNN'ler, görüntülerdeki özelliklerin ölçek değişikliklerine karşı dayanıklıdır. Bu, farklı boyutlardaki nesneleri tanımak için idealdir.
Bölgesel Özelliklerin İncelenmesi: CNN'ler, görüntülerin farklı bölgelerindeki özellikleri öğrenebilir. Bu, nesne tespiti gibi görevler için gereklidir.
Karmaşık Modelleme: Görüntüler genellikle karmaşık yapılar içerir. CNN'ler, bu karmaşıklığı öğrenebilir ve yüksek doğrulukla tahminlerde bulunabilir.
- Önemi
Yüksek Doğruluk: CNN'ler, genellikle görüntü işleme görevlerinde yüksek doğruluk sağlar. Bu nedenle, sınıflandırma, tanıma ve tespit gibi alanlarda tercih edilirler.
Otomatik Özellik Çıkarma: CNN'ler, özellikleri otomatik olarak çıkarabilir, bu da veri mühendisliği gereksinimini azaltır ve modelin daha genelleştirilmiş olmasını sağlar.
Genelleme Yeteneği: CNN'ler, verilerdeki genel desenleri öğrenebilir ve farklı görüntülerde benzer desenleri tanıyabilir. Bu, farklı veri setleriyle çalışırken genelleme yeteneği sağlar.

## Kullanılan Değerlendirme Metriği
Bu projede F1 Score ve Accuracy değerlendirme metrikleri kullanılmıştır.
## Sonuç

Kullanıcıdan alınan insan ve insan olmayan örnek görselleri doğru tahmin etmiştir. 

| Model | Eğitim Doğruluğu | Test Doğruluğu | F1 Skoru | Recall | Precision |
|----------|----------|----------|----------|----------|----------|
| CNN |0.9730 | 0.9754 | 0.9722 | 0.9754 | 0.9778 |





