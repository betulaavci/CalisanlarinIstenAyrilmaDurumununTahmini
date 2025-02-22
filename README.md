# CalisanlarinIstenAyrilmaDurumununTahmini

1. PROBLEM TANIMI
Çalışan insanların işi bırakma nedenleri üzerine bir makine öğrenmesi projesi gerçekleştirildi. Geliştirilen projenin amacı, çalışanların işten ayrılma nedenlerini analiz ederek, bu süreçte etkili olan faktörleri anlamak ve işletmelerin çalışan memnuniyetini artırmaya yönelik stratejiler geliştirmelerine yardımcı olmaktır. Ayrıca bu sistem, hem çalışanların ihtiyaçlarına daha iyi cevap verebilmek hem de iş gücü kayıplarını azaltarak işletmelerin verimliliğini artırmak için önemli bir araç sunmaktadır.

2.VERİ SETİNİN SEÇİMİ VE HAZIRLANMASI
Proje kapsamında kullanılan veri seti, yapılan araştırmalar sonucunda Kaggle platformundan temin edilmiştir. Bu veri seti, çalışanların demografik bilgileri, iş seyahati, departman, işten ayrılma durumları gibi çeşitli özellikleri içermektedir. Veri seti, makine öğrenmesi modellerinin eğitimi ve analizi için uygun bir yapı sunarak projenin temelini oluşturmuştur.

3.VERİ ANALİZİ (EDA)
Verinin dağılımı ve yapısı, kodlarla detaylı bir şekilde analiz edildi. Grafikler ve istatistiksel yöntemler, kod aracılığıyla uygulanarak veriden anlamlı sonuçlar çıkarıldı.

4. MODEL GELİŞTİRME
Projede, çalışanların işten ayrılma nedenlerini tahmin etmek amacıyla GradientBoostingClassifier algoritması kullanılmıştır. Modelin performansını optimize etmek ve en uygun hiperparametreleri belirlemek için GridSearchCV yöntemi uygulanmıştır. GridSearchCV, belirlenen hiperparametre aralıklarını sistematik bir şekilde tarayarak, modelin doğruluğunu ve genel başarısını artıracak en iyi kombinasyonu seçmiştir. Bu yöntem, modelin hem tahmin doğruluğunu artırmış hem de genelleştirme kabiliyetini güçlendirmiştir.

5.SONUÇLARIN DEĞERLENDİRİLMESİ VE RAPORLAMA
GradientBoostingClassifier Kullanımı:
Bu model, karar ağaçları üzerine kurulu bir topluluk öğrenme (ensemble learning) yöntemidir. Her ardışık model, bir önceki modelin hatalarını düzeltmeyi hedefler. Sağlanan %87,07'lik doğruluk, modelin test seti üzerinde güçlü bir şekilde çalıştığını gösteriyor.
Hiperparametre Optimizasyonu (GridSearchCV):
      GridSearchCV yöntemi, modelin en iyi parametre kombinasyonlarını bulmak için kullanıldı.
      Elde edilen parametreler (max_depth=4, max_features=0.2, n_estimators=20), modelin test seti üzerindeki doğruluğunu optimize etmek için etkili bir şekilde ayarlandı.
      En iyi doğrulama skoru %85,23 olarak belirlendi, bu da modelin genel olarak tutarlı bir performans gösterdiğini işaret eder.
Yeni Veriler Üzerindeki Tahmin :
      Eğitimli model, yeni veriler üzerinde uygulanarak sonuçlar "prediction" sütunu olarak kaydedildi.
      Tahmin sonuçları, modelin farklı durumlar için sınıflandırma yapabildiğini gösteriyor.
              Tahmin sonucu 0 ; bir çalışanın işten ayrılmayacağını
              Tahmin sonucu 1; bir çalışanın işten ayrılacağı
              
Güçlü Yönleri :
      1.Doğruluk Oranı: %87,07 doğruluk, genellikle başarılı bir sınıflandırma modeli için iyi bir değerdir.
      2.Hiperparametre Optimizasyonu: GridSearchCV'nin uygulanması, modelin en uygun parametrelerle çalışmasını sağlamış.
      3.Özellik Ön İşleme: Veriler üzerinde sayısal ve kategorik özellikler için farklı boru hatları (pipelines) oluşturulmuş. Bu, modelin daha iyi genelleştirme yapmasını sağlar.

Eksiklikler ve İyileştirme Önerileri :
      1.Ek Metrik Analizi: Yalnızca doğruluğa bakmak yanıltıcı olabilir. Kesinlik, geri çağırma, F1 skoru gibi ek metriklerle modeli daha kapsamlı değerlendirebilirsiniz.
      2.Overfitting Riski:Test doğruluğu (%86,85) ve çapraz doğrulama doğruluğu (%85,23) birbirine yakın olsa da, modelin eğitim setindeki doğruluğu kontrol edilmeli. Eğitim setinde çok daha yüksek doğruluk varsa aşırı uyum (overfitting) riski olabilir.
      3.Daha Fazla Özellik Analizi:Modelin hangi özelliklere daha fazla ağırlık verdiğini belirlemek için özellik önemini (feature importance) inceleyebilirsiniz. Bu, daha fazla iyileştirme yapmanıza yardımcı olabilir.
      4.Daha Fazla Veri ve Çeşitlilik: Modelin performansını artırmak için daha fazla veri toplayabilir veya mevcut veri setindeki çeşitliliği artırabilirsiniz.

SONUÇLARIN DEĞERLENDİRMESİ
Model, genel anlamda başarılı bir performans sergiliyor ve hem test seti hem de yeni veriler üzerinde güçlü tahminler yapabiliyor. Ancak daha kapsamlı bir değerlendirme için ek metriklerin incelenmesi ve aşırı uyum riskinin önlenmesi adına daha fazla test yapılabilir. Özellik ön işleme ve hiperparametre optimizasyonu, modelin başarısını destekleyen önemli bir faktör olarak öne çıkıyor.
