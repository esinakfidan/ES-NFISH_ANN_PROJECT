# ES-NFISH_ANN_PROJECT
# Fish Species Classification with Deep Learning

Bu proje, çeşitli balık türlerini tanımlamak için derin öğrenme modellerini kullanır. Kaggle'daki bir balık veri setini kullanarak, veri artırma (data augmentation) teknikleri ve önceden eğitilmiş bir model olan VGG16 ile balık türlerini sınıflandıran bir model geliştirilmiştir.

## İçerik
- **Veri Yükleme ve Hazırlık:** Kaggle'dan indirilen veri seti yüklenmiş ve görselleştirilmiştir.
- **Veri Artırma (Data Augmentation):** Görsellerin çeşitlendirilmesi için ImageDataGenerator kullanılarak veri artırma teknikleri uygulanmıştır.
- **Model Eğitimi:**
  - **Yapay Sinir Ağı (ANN):** Giriş katmanı, tam bağlı katmanlar ve çıkış katmanı içeren bir ANN modeli geliştirilmiştir.
  - **Transfer Öğrenme:** Önceden eğitilmiş VGG16 modeli kullanılarak sınıflandırma performansı artırılmıştır.
- **Model Performansı:** Eğitim ve doğrulama kaybı, doğruluğu gibi metrikler görselleştirilmiştir.
- **Erken Durdurma ve Öğrenme Hızı Azaltma:** Eğitim sırasında modelin overfitting yapmasını önlemek için early stopping ve learning rate scheduler kullanılmıştır.

## Kullanılan Kütüphaneler
- `tensorflow.keras`
- `matplotlib`
- `pandas`, `numpy`

## Kullanılan Teknikler ve Modeller
Bu projede, görüntü sınıflandırma için transfer öğrenme yaklaşımını kullanarak VGG16 modeli uygulandı. Aşağıda kullanılan temel teknikler ve modellerin açıklamaları bulunmaktadır:

1. **Transfer Öğrenme:**
   - Önceden eğitilmiş VGG16 modelini kullanarak, daha az veriye ihtiyaç duyarak ve daha hızlı bir şekilde modelimizi eğitildi. Bu, özellikle sınırlı veri setlerinde etkili bir yöntemdir.

2. **VGG16 Modeli:**
   - VGG16, ImageNet veriseti üzerinde eğitilmiş bir konvolüsyonel sinir ağıdır. Derin mimarisi sayesinde yüksek doğruluk oranlarına ulaşabilmekte. Bu projede, VGG16'nın temel özelliklerini kullanarak özel bir sınıflandırma problemi çözmeyi hedeflendi.

3. **Veri Artırma (Data Augmentation):**
   - Modelin genel performansını artırmak için görüntülerin dönmesi, kaydırılması, kesilmesi ve diğer dönüşümleri ile veri artırma işlemleri gerçekleştirildi. Bu sayede modelin aşırı öğrenmesini (overfitting) engellemeyi amaçlandı.

4. **Yapay Sinir Ağı (Artificial Neural Network - ANN):**
   - VGG16 modelinin çıkış katmanının üzerine, görüntü sınıflandırma için tam bağlı (dense) katmanlar eklendi. Bu katmanlar, modelin öğrendiği özellikleri kullanarak son sınıflandırmayı gerçekleştirildi.

5. **Eğitim Süreci:**
   - Modeli, kayıp fonksiyonu olarak "binary_crossentropy" kullanarak ve doğruluk metriği ile eğitildi. Erken durdurma (Early Stopping) ve öğrenme oranı azaltma (ReduceLROnPlateau) gibi callback fonksiyonları ile modelin eğitim süreci optimize edildi.

Bu teknikler ve modeller, projemin başarıyla tamamlanmasına yardımcı oldu ve görüntü sınıflandırma görevini etkili bir şekilde gerçekleştirildi.

### Veri Artırma (Data Augmentation)
Aşağıdaki veri artırma teknikleri uygulanmıştır:
- Döndürme, kaydırma, kesme ve yakınlaştırma
- Yatay çevirme
- Piksel değerlerinin normalize edilmesi
