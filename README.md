# Mavi Kalkan Simülatörü

Mavi Kalkan projesinin ("Müsilaj yüzeye çıkmadan önce") tarayıcıda çalışan simülasyonu. Wokwi devresinde potansiyometreyle elle verilen su değerlerinin yerine canlı bir deniz modeli kullanır.

`index.html` dosyasını tarayıcıda açmanız yeterli. Kurulum gerekmez.

## Ne gösterir

- **Karşılaştırmalı deney:** Aynı deniz koşullarında üç kesit yan yana çalışır.
  - **Devre yok:** Müsilaj dipte kuluçkaya yatar, yükselir ve yüzeyde tabaka oluşturur.
  - **Devre çalışıyor:** Şamandıra eşikleri (sıcaklık > 22 °C, azot > 60 mg/L, ÇO < 4 mg/L) 3 günlük trendle doğrular. AFAD'a GPS koordinatlı bildirim gider. USV-01 gelir, santrifüj filtre ve bakteri dozu uygular. Müsilaj yüzeye çıkmaz.
  - **Devre arızalı:** Sensör takılması, USV/röle/servo arızası ya da güç kesintisi seçilebilir. Müsilaj yine oluşur.
- **Tek senaryo:** Tek bir kesitte devreyi simülasyon sürerken kurup kaldırabilir ya da arızalandırabilirsiniz.
- **Seri monitör:** `main.py` çıktısıyla aynı biçimde `[TEKNİK RAPOR]`, `[SİSTEM UYARISI]` ve `[ACİL DURUM]` satırları.
- **Deney sonucu:** Erken uyarı süresi (Mavi Kalkan uyarısı ile devresiz denizde müsilajın yüzeye çıkışı arasındaki fark) ve maliyet karşılaştırması.

Model eğitim amaçlıdır. Katsayılar temsilîdir ve gerçek ölçümlerle kalibre edilmemiştir.
