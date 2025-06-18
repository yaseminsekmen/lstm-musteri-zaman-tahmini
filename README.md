🛒 Müşteri Alışveriş Zaman Dilimi Tahmini (LSTM)
Bu proje, müşterilerin geçmiş alışveriş davranışlarına bakarak gelecekte hangi zaman diliminde alışveriş yapacaklarını tahmin etmeyi amaçlamaktadır. Bu amaçla sıralı veri yapısına uygun bir LSTM (Long Short-Term Memory) modeli geliştirilmiş ve Optuna kütüphanesiyle hiperparametre optimizasyonu gerçekleştirilmiştir.

📊 Proje Hedefi
E-ticaret müşterilerinin;

Saat 🕒
Gün 📅
Kampanya durumu 🎯
Fiyat 💰
Kategori ve yaş 
gibi geçmiş alışveriş verilerine bakılarak, bir sonraki alışverişlerinin haftanın hangi günü ve günün hangi saat diliminde (sabah/akşam) olacağının tahmin edilmesi hedeflenmiştir.

🧾 Kullanılan Teknolojiler
Python 3

TensorFlow (LSTM Modeli)
Optuna (Hiperparametre optimizasyonu)
Scikit-learn (veri ön işleme, metrikler)
Matplotlib & Seaborn (görselleştirme)
Pandas, NumPy (veri işlemleri)


📁 Veri Seti
Veri seti şirket içi bir kaynaktan türetilmiştir ve anonimleştirilmiştir (müşteri adı, şehir, marka, vs. maskelenmiştir).
Toplam 25.000 alışveriş verisi bulunmaktadır.

Özellikler:

saat, gun, kampanya_var_mi, fiyat, kategori_id, yas
Çıktı: zaman_dilimi_label (örneğin: Pazartesi_Sabah, Cuma_Aksam)


🔍 Yöntem
Veri Ön İşleme: Saat dilimleri sabah/akşam olarak ayrıldı. Kategorik etiketler sayısallaştırıldı.
Zaman Serisi Oluşturma: Her müşterinin sıralı alışverişleri LSTM’e uygun hale getirildi (n_steps=3).
Modelleme: LSTM ile sıralı veri eğitildi. EarlyStopping ve sınıf ağırlığı eklendi.
Optimizasyon: Optuna ile en iyi model parametreleri arandı (units, dropout, batch_size, lr).
Değerlendirme: Confusion Matrix ve classification_report ile başarı metrikleri değerlendirildi.


📈 Sonuçlar
Doğruluk (Accuracy): %57.95
Macro F1-score: 0.39
Weighted F1-score: 0.55
En yoğun alışveriş zaman dilimi başarıyla tahmin edilmiştir (örneğin Pazartesi_Aksam). Ancak veri dengesizliğinden dolayı az örnekli sınıflarda başarım düşüktür.

💡 Öneriler ve Geliştirmeler
Veri artırımı ile az örnekli sınıflar dengelenebilir
LSTM yerine GRU, Attention veya Transformer temelli modeller denenebilir
Alternatif kayıplar (focal loss gibi) ile eğitim güçlendirilebilir

