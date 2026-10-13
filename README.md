# Mavi Kalkan Simülatörü

Mavi Kalkan projesinin ("Müsilaj yüzeye çıkmadan önce") tarayıcıda çalışan simülasyonu. Wokwi devresinde potansiyometreyle elle verilen su değerlerinin yerine canlı bir deniz modeli kullanır.

`index.html` dosyasını tarayıcıda açmanız yeterli. Kurulum gerekmez.

## Ne gösterir

- **Dört deniz, gerçek değerler:** Marmara (İzmit Körfezi), Karadeniz (Ordu açığı), Ege (İzmir Körfezi) ve Akdeniz (Mersin Körfezi). Her denizin tuzluluğu, aylık yüzey suyu sıcaklığı ve azot düzeyi bilimsel yayınlardan ve ÇŞB izleme raporlarından alındı. Kaynaklar sayfadaki "Denizlerin gerçek değerleri" tablosunda.
- **Canlı devre şeması:** Wokwi devresi (Raspberry Pi Pico, 3 potansiyometre, HC-SR04, röle, servo) simülasyonla birlikte çalışır. Düğmeler sensör değerine göre döner, acil durumda röle ışığı yanar ve servo 90°'ye döner.

- **Karşılaştırmalı deney:** Aynı deniz koşullarında üç kesit yan yana çalışır.
  - **Devre yok:** Müsilaj dipte kuluçkaya yatar, yükselir ve yüzeyde tabaka oluşturur.
  - **Devre çalışıyor:** Şamandıra eşikleri (sıcaklık > 22 °C, azot > 60 mg/L, ÇO < 4 mg/L) 3 günlük trendle doğrular. Ekibe GPS koordinatlı haber verilir. USV-01 gelir, santrifüj filtre ve bakteri dozu uygular. Müsilaj yüzeye çıkmaz.
  - **Devre arızalı:** Sensör takılması, USV/röle/servo arızası ya da güç kesintisi seçilebilir. Müsilaj yine oluşur.
- **Tek senaryo:** Tek bir kesitte devreyi simülasyon sürerken kurup kaldırabilir ya da arızalandırabilirsiniz.
- **Seri monitör:** `main.py` çıktısıyla aynı biçimde `[TEKNİK RAPOR]`, `[SİSTEM UYARISI]` ve `[ACİL DURUM]` satırları.
- **Deney sonucu:** Erken uyarı süresi (Mavi Kalkan uyarısı ile devresiz denizde müsilajın yüzeye çıkışı arasındaki fark) ve maliyet karşılaştırması.

Azot gerçek deniz birimiyle (çözünmüş anorganik azot, µmol/L) ölçülür ve simülasyondaki eşik 5 µmol/L'dir. Wokwi kodundaki `azot > 60.0` (mg/L) deniz suyunda görülmeyecek kadar yüksektir; bu düzey ancak arıtılmamış atık suda görülür.

Model eğitim amaçlıdır. Katsayılar temsilîdir ve gerçek ölçümlerle kalibre edilmemiştir.
