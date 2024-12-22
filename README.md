# Hayvan Sınıflandırma Projesi 🐾

Bu proje, derin öğrenme teknikleri kullanarak çeşitli manipüle edilmiş görüntüler ile hayvan sınıflandırması yapmayı amaçlamaktadır. Proje, çeşitli model yapılarını ve veri artırma yöntemlerini içermekte olup, farklı model yapılandırmalarının ve hiperparametre optimizasyonunun karşılaştırılmasını sunmaktadır.

## İçerik

- **Model Yapısı ve Mimari**: Konvolüsyonel Sinir Ağı (CNN) kullanılarak geliştirilmiş bir modelle hayvan sınıflandırma yapılmıştır.
- **Veri Seti Manipülasyonu**: Veri seti üzerinde farklı manipülasyonlar (purplish, yellowish, greenish) uygulanarak modelin dayanıklılığı test edilmiştir.
- **Hiperparametre Optimizasyonu**: Hiperparametre ayarları için Bayesyen optimizasyonu gibi yöntemler kullanılmıştır.
- **Model Karşılaştırmaları**: Manuel olarak ayarlanmış model ile hiperparametre optimizasyonu ile ayarlanmış modelin karşılaştırılması yapılmıştır.
- **Sonuçlar**: Sonuçlar, orijinal veri seti ve manipüle edilmiş veri setlerinde modelin performansını gösteren bir şekilde rapor edilmiştir.

## Proje Adımları

### 1. Veri Seti
Proje, hayvan sınıflandırması için çeşitli fotoğraflardan oluşan bir veri seti kullanmaktadır. Bu veri seti, modelin eğitilmesi ve test edilmesi amacıyla iki bölüme ayrılmıştır: **Eğitim Seti (Training Set)** ve **Test Seti (Test Set)**. Test seti üzerinde modelin genel başarımı değerlendirilmektedir.

### 2. Model Yapısı
Model, derin öğrenme tabanlı bir **Konvolüsyonel Sinir Ağı (CNN)** mimarisi kullanılarak inşa edilmiştir. Modelin temel yapı taşları şunlardır:

- **Conv2D Katmanları**: Görüntü özelliklerini öğrenmek için konvolüsyonel katmanlar kullanılmaktadır.
- **MaxPooling Katmanları**: Özellik haritalarını küçültmek ve önemli bilgiyi muhafaza etmek için max pooling işlemi uygulanmaktadır.
- **Dense Katmanlar**: Öğrenilen özellikleri sınıflara dönüştürmek için yoğun (dense) katmanlar kullanılmıştır.
- **Dropout**: Aşırı öğrenmeyi (overfitting) engellemek amacıyla dropout katmanı uygulanmıştır.
  
### 3. Veri Manipülasyonu
Modelin dayanıklılığını test etmek için veri seti üzerinde çeşitli manipülasyonlar yapılmıştır. Bu manipülasyonlar, görüntülerin renk tonları üzerinde değişiklik yaparak (purplish, yellowish, greenish) modelin bu değişimlere ne kadar dayanıklı olduğunu gözlemlemeyi amaçlamaktadır. Ayrıca, görüntülerin **White Balance (WB)** ayarları yapılarak manipülasyonların etkisi azaltılmaya çalışılmıştır.

### 4. Eğitim ve Test Süreci
Eğitim ve test süreçlerinde, modelin **veri artırma (data augmentation)** teknikleriyle eğitilmesi sağlanmıştır. Bu teknikler, modelin farklı veri varyasyonlarına karşı daha esnek olmasını sağlamak için:
- Yatay çevirme
- Döndürme
- Ölçekleme
- Parlaklık değişimi
gibi işlemler içerir.

Model, **Hiperparametre Optimizasyonu** ile daha da iyileştirilmiş ve farklı **epoch** sayıları ve **batch size** değerleri ile test edilmiştir. Ayrıca, Bayesyen optimizasyonu gibi yöntemlerle en uygun hiperparametreler elde edilmeye çalışılmıştır.

### 5. Sonuçlar ve Değerlendirme
Test setlerinde, özellikle manipüle edilmiş veri setlerinde, **Manuel Olarak Ayarlanmış Model** ve **Yeni Model** arasındaki performans farkları değerlendirilmiştir. **Manuel Model** çoğunlukla manipülasyona karşı daha dayanıklı olmuştur. Bununla birlikte, hiperparametre optimizasyonu ile oluşturulan model, bazı test setlerinde daha iyi sonuçlar vermiştir.

Sonuçlar, grafikler ve tablolarda görselleştirilmiş olup, modelin genel başarımı ve manipülasyona karşı dayanıklılığı detaylı bir şekilde karşılaştırılmıştır.

### 6. Yöntemler
- **Veri Arttırma (Data Augmentation)**: Eğitim sırasında kullanılan veri arttırma yöntemleri, modelin genel başarısını artırmak için kullanılmıştır.
- **Transfer Öğrenme**: Önceden eğitilmiş modellerin (pre-trained models) kullanımı önerilmiş, böylece modelin daha geniş veri setlerine adapte olma yeteneği artırılmıştır.
- **Hiperparametre Optimizasyonu**: Modelin hiperparametre ayarları için Bayesyen optimizasyonu kullanılmıştır. Bu, manuel ayarlarla karşılaştırıldığında daha yüksek doğruluklar elde edilmesine olanak tanımıştır.

## Kullanılan Kütüphaneler
- TensorFlow ve Keras: Modelin oluşturulması ve eğitilmesi için kullanılmıştır.
- OpenCV: Görüntü manipülasyonları ve veri ön işleme işlemleri için kullanılmıştır.
- Matplotlib: Sonuçların görselleştirilmesi için kullanılmıştır.
- Scikit-learn: Karışıklık matrisi ve diğer değerlendirme metrikleri için kullanılmıştır.

## Kurulum

Proje için gerekli bağımlılıkları yüklemek için aşağıdaki komutları kullanabilirsiniz:

```bash
pip install -r requirements.txt
```

### Gerekli Dosyalar:

**Veri Seti**: Hayvan sınıflandırma veri setine ihtiyacınız olacak. Veri setine [Kaggle](https://www.kaggle.com/datasets/rrebirrth/animals-with-attributes-2/data) üzerinden erişebilirsiniz.

## Sonuçlar

Model, orijinal test seti üzerinde %75 doğruluk oranına ulaşırken, manipüle edilmiş veri setlerinde doğruluk oranı düşüş göstermiştir. White balance uygulaması ile manipüle edilmiş verilere daha yakın sonuçlar elde edilmiştir. Veri arttırma ve transfer öğrenme yöntemleriyle modelin performansının artırılması sağlanabilir.

### Model Performansı Sonuçları

| Model                                        | Veri Seti                      | Test Loss | Test Accuracy |
|----------------------------------------------|--------------------------------|-----------|---------------|
| Manuel Olarak Ayarlanmış Model              | Original Test                  | 0.719893  | 0.752308      |
| Hiper Parametre Optimizasyonu ile Ayarlanmış Model | Original Test                  | 0.824464  | 0.730769      |
| Manuel Olarak Ayarlanmış Model              | Purplish Test Set              | 2.752260  | 0.246154      |
| Manuel Olarak Ayarlanmış Model              | Yellowish Test Set             | 2.207090  | 0.326154      |
| Manuel Olarak Ayarlanmış Model              | Greenish Test Set              | 5.729993  | 0.110769      |
| Manuel Olarak Ayarlanmış Model              | Purplish Test Set WB uygulanmış | 0.762759  | 0.731538      |
| Manuel Olarak Ayarlanmış Model              | Yellowish Test Set WB uygulanmış | 0.772819  | 0.731538      |
| Manuel Olarak Ayarlanmış Model              | Greenish Test Set WB uygulanmış | 0.776333  | 0.734615      |
| Yeni Model                                   | Purplish Test Set              | 0.810721  | 0.733077      |
| Yeni Model                                   | Yellowish Test Set             | 0.873816  | 0.723077      |
| Yeni Model                                   | Greenish Test Set              | 0.890619  | 0.708462      |
| Yeni Model                                   | Purplish Test Set WB uygulanmış | 1.067673  | 0.655385      |
| Yeni Model                                   | Yellowish Test Set WB uygulanmış | 0.992056  | 0.677692      |
| Yeni Model                                   | Greenish Test Set WB uygulanmış | 1.067876  | 0.657692      |

---

📈 **Sonraki Adımlar**: 
1. Modelin farklı manipülasyonlar ile daha fazla test edilmesi.
2. Daha büyük veri setleri ile modelin eğitilmesi.
3. Transfer öğrenme ve daha karmaşık ağ mimarileri kullanarak modelin iyileştirilmesi.


**Kaggle Linki**

[Kaggle Proje Linki](https://www.kaggle.com/code/muhammetalivarlik/animalclassification)
