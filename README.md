# 🌸 SVM ile Iris Çiçek Türü Sınıflandırma ve Görselleştirme

  Bu projede, **Support Vector Machine (SVM)** algoritmasının makine öğrenmesinde tam olarak **ne işe yaradığını**, parametrelerinin (kernel, C, gamma, degree, margin) pratikte ne fark yarattığını ve Iris veri setinde nasıl kullanıldığını hem kod hem de çıktılar ve grafiklerle gösterilmişti.

  ---

  ## 1️⃣ SVM (Support Vector Machine) Nedir? 🧠

  - SVM, en iyi ayrım sınırını (hiperdüzlem) bulmaya çalışan bir algoritmadır.
  - Komşulara bakarak değil, tüm veri kümesinin geometrisini dikkate alır.
  - Sınır, iki sınıfı ayıran “en geniş marjlı çizgidir.
  - Çoklu sınıflar için “one-vs-rest” tekniğiyle otomatik uyarlanır.
  - 🔎 Ne demek? 
    Her çiçek türünü mümkün olan en “keskin” şekilde ayırır. Ezberci değil, gerçekten genelleyen bir modeldir.

  ---

  ## 2️⃣ SVM Parametreleri ve Kavramları

  - Kernel Seçimi🌀  
    - `linear` ➡️ Düz çizgiyle ayırma (en sade, doğrudan)
    - `poly` ➿ Polinom eğriyle ayırma (karmaşıklık ekler)
    - `rbf` 🥨 Dairesel/dalgalı sınırlar (karmaşık yapı)
    - 🔎 Kullanımı:  
      Karmaşık veri için `rbf` veya `poly`, basit ayrılabilen veri için `linear`.

  - C (Ceza Katsayısı) ⚖️  
    - Büyük C → Sert sınır (hata kabul etmez, aşırı öğrenir)
    - Küçük C → Esnek sınır (bazı hataları tolere eder, genellemeye açık)
    - 🔎 **Taktik:**  
      Overfitting riskinde C’yi küçült, veri çok net ayrılıyorsa büyütebilirsin.

  - Gamma 🔬  
    - Düşük gamma: Sınır daha düz, uzak noktalar dikkate alınır.
    - Yüksek gamma: Sınır çok kıvrımlı, sadece yakın noktalar etkili.
    - Sadece `rbf` ve `poly` kernelde etkili.

  - Degree 2️⃣3️⃣4️⃣  
    - Polinomun derecesi. Sadece `poly` kernelde önemli.

  - Soft/Hard Margin 
    - Soft margin ➡️ Gerçek veriyle uyumlu, pratikte en çok kullanılan.
    - Hard margin ➡️ Teoride sıfır hata, ama gürültülü veride anlamlı değil.

  ---

  ## 3️⃣ Veri Hazırlığı, Eğitim ve Test Ayrımı

  - Her türden eşit miktarda test verisi ayırmak, modelin tüm sınıfları adilce öğrenmesini sağlar.
  - Eğitim seti: Modelin gördüğü, öğrendiği veriler  
    Test seti: Modelin hiç görmediği, gerçekten tahmin yapmak zorunda olduğu veriler  
  - 🔎 Neden önemli? 
    Sadece eğitim setinde yüksek doğruluk "ezber" olabilir. Gerçek başarı test setinde ölçülür.
    kernel, C, gamma gibi parametreleri değiştirerek çıktıda farklı sınırlara ve başarı oranlarına ulaşabilirsin.

🔎 Gözlem:
Linear kernel ile veri net ayrılıyorsa, doğruluk %100 olur. Karmaşık veri için rbf veya polinom deneyebilirsin.

ÇIKTILARIN YORUMLANMASI:
Precision 🎯: Modelin tahminlerinin ne kadar isabetli olduğunu gösterir.

Recall 🔍: Modelin gerçek değerleri ne kadar bulduğunu ölçer.

f1-score 🏆: Precision ve recall'un dengesi.

Support 👥: O sınıftaki test örneği sayısı.


PCA ile 2 Boyuta İndir ve Karar Sınırı Çiz
PCA, 4 boyutlu veri uzayını 2 boyuta indirger ve modeli görsel olarak anlaşılır kılar.

SVM’in karar sınırları, eğitim ve test verilerinin dağılımı net olarak görülebilir.

Grafikte:

Kırmızı/Yeşil/Mavi noktalar: 3 farklı türün eğitim örnekleri

X işaretleri: Test örnekleri

⭐ Siyah yıldız: Yeni tahmin edilen çiçek (yeni bir giriş)

Açık renkli bölgeler: Modelin karar sınırı (hangi alan hangi tür?)

🔎 Sezgisel Yorum:
Eğer yıldız “kırmızı” bölgeye düşerse model onu o tür olarak sınıflandırır.
Sınırın karmaşıklığı kernel/gamma/C ile değişir.

7️⃣ Farklı Kernel ve Parametrelerin Etkisi
kernel='linear': Net çizgi, veriler net ayrılıyorsa harika.

kernel='rbf', gamma=5: Sınır çok kıvrılır, modelin karmaşıklığı artar, overfitting olabilir.

kernel='poly', degree=3: Sınır parabol veya kübik eğri olur.

C çok büyükse: Model hata yapmaz ama testte düşük başarıya inebilir (overfit).

C çok küçükse: Model biraz hata kabul eder, sınır yumuşar (underfit riski).

🔎 İpucu:
Modelin başarısını, görselliğini ve genelleme yeteneğini en iyi bu parametrelerle oynayarak görebilirsin.

8️⃣ Sonuç
SVM ile Iris veri setinde çok yüksek başarı elde ediliyor.

Parametrelerle oynayarak modelin karar sınırlarını ve performansını doğrudan gözlemleyebiliyorsun.

Görsel çıktılar ile “hangi veri nerede, model nasıl karar veriyor?” her şey açıkça anlaşılıyor.

