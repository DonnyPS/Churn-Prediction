# Churn-Prediction
### Oleh Kelompok MOD (Mother of Dataset):
 * Ashadah (ashadah44@gmail.com)
 * Christoforus Venus (venus001@binus.ac.id)
 * Dicky Novanda Syaifullah (dr.dicno@gmail.com)
 * Donny Prayudha Stannia (donny2ndgen@gmail.com)
 * Jason Joseph Tjiadi (jasonjosephtjiadi@gmail.com)
 * Ryan Setiawan (koalaozzie15@gmail.com)
 * Syafiqa Pramunadipta (syafiqapramuna@gmail.com)
 * Tri Oktavia Saraswati (strioktavia@gmail.com)
 
## Business Understanding
### Problem Statement: 
Dari data pelanggan suatu perusahaan ecommerce terdapat 17% pelanggan yang melakukan churn. Oleh karena itu perusahaan ingin  dapat mempertahankan konsumen agar mereka tetap setia membeli barang dari perusahaan mereka. 

### Goal:
Perusahaan perlu melakukan prediksi untuk menentukan mana pelanggan yang loyal dan tidak loyal, sehingga nantinya perusahaan dapat menentukan strategi yang tepat untuk meningkatkan loyalitas dan menurunkan churn rate.

### Business metric:
Metrik yang digunakan adalah Customer Churn Rate (Churn Rate).
Churn rate adalah persentase pelanggan yang tidak memperpanjang langganan atau berhenti membeli selama periode waktu tertentu, seperti sebulan, triwulan atau setahun.

### Objective:
*  Mengurangi jumlah pelanggan yang beralih ke perusahaan lain atau berhenti membeli produk dari perusahaan dengan membangun model machine learning untuk melakukan prediksi pelanggan yang churn.
*  Memberikan rekomendasi bisnis sehingga perusahaan dapat mencapai meningkatkan loyalitas dan menurunkan churn rate.

### Kesimpulan tahap eksplorasi dataset:
*  Dataset memiliki 20 kolom dan 5630 baris, dari kolom tersebut kita bisa melakukan penghapusan kolom untuk kolom CustomerID (kolom ID) karena tidak dibutuhkan dalam pembuatan model.
*  Tipe data pada dataset tidak ada anomali.
*  Pada dataset untuk variabel kategori tidak ada masalah.
*  Pada kolom PreferredPaymentMode, ada nilai Cash on Delivery dan COD, untuk value bisa dipilih COD sedangkan yang lain bisa diubah menjadi COD. Sedangkan untuk value CC diasumsikan sebagai Credit Card, sehingga nilainya bisa diubah menjadi Credit Card.
*  Pada kolom PreferredLoginDevice, ada nilai Phone yang bisa diubah menjadi Mobile Phone.
*  Pada kolom PreferedOrderCat, ada nilai Mobile yang bisa diubah menjadi Mobile Phone
*  Terdapat 7 kolom yang mempunyai nilai data null, yaitu: 
   1.  Tenure dengan total nilai 264, 
   2.  WarehouseToHome dengan total nilai 251, 
   3.  HourSpendOnApp dengan total nilai 255, 
   4.  OrderAmountHikeFromlastYear dengan total nilai 265, 
   5.  CouponUsed dengan total nilai 256, 
   6.  OrderCount dengan total nilai 258, 
   7.  DaySinceLastOrder dengan total nilai 307.

### Kesimpulan hasil EDA:
*  Sebaran data secara kesuluruhan pelanggan tidak melakukan churn, dengan detil Churn sebanyak 17% dan No Churn sebanyak 83%.
*  Untuk tenure, pelanggan berlangganan  paling sebentar mempunyai kecenderungan untuk melakukan Churn.
*  Ada kecenderungan semakin tinggi kupon yang digunakan, semakin tinggi juga kecenderungan untuk melakukan Churn. 
*  Dilihat dari perangkat yang digunakan untuk login, mobile phone merupakan pilihan orang yang melakukan churn.
* Dilihat dari metode pembayaran, yang sering digunakan oleh pelanggan yang churn adalah debit card.
*  Orang melakukan churn dilihat dari faktor jenis kelamin (gender), pria lebih sering melakukan churn.
*  Pelanggan dengan status single merupakan pelanggan yang sering melakukan churn.
*  Kolom Churn adalah variabel target yang menunjukkan apakah pelanggan pergi (yaitu meninggalkan perusahaan).
*  Korelasi yang perlu diperhatikan adalah CouponUsed dan OrderCount → 0.75

### Business Insight
Bersumber dari laman CleverTap, mendapatkan pelanggan baru umumnya akan lebih mahal sebanyak 5 hingga 25 kali lipat jika dibandingkan dengan mempertahankan pelanggan yang sudah ada. Selain itu, mempertahankan pelanggan juga diklaim mampu memberikan dampak yang sangat besar pada growth rate daripada mendapatkan pelanggan baru.
Hal pertama yang harus Anda ketahui untuk  meminimalisir persentase churn rate adalah penyebab utama dari presentase tersebut bisa di atasi. 
-  Hal tersebut bisa datang dari UI atau UX Anda yang kurang ramah untuk pengguna, keterbatasan fitur, ini perlu dilakukan pengembangan lebih lanjut karena hasil EDA menunjukan pelanggan paling banyak menggunakan mobile phone untuk mengakses layanan.
-  Member dengan waktu paling singkat menunjukan churn yang tinggi mungkin juga disebabkan factor UI/UX seperti yang disebutkan diatas. Disarankan juga memperbanyak penawaran menarik agar masa berlangganan pelanggan bisa bertahan lama
Perusahaan juga perlu memperbanyak jumlah cashback untuk pelanggan setia atau pelanggan yang melakukan pembelanjaan dengan nominal tertentu
-  Memperbanyak pilihan produk pada kategori mobile phone dengan harga yang bersaing
-  Membuat diskon tambahan bagi pemegang kartu debit
-  Membuat acara live event yang dapat membuat pelanggan terutama pria untuk tetap setia jadi pelanggan perusahaan kita.
-  Memperbaiki Journey Map pelanggan, agar perusahaan dapat memperbaiki langkah-langkah yang menyebabkan pelanggan menjadi churn, seperti sulitnya untuk mengakses menu diaplikasi, dan perusahaan dapat mendefinisikan Kembali pelanggan ideal untuk perusahaan agar bagian marketing/sales tidak salah dalam mendapatkan pelanggan.
