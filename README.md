# Churn-Prediction
### Oleh Kelompok MOD (Mother of Dataset):
 * Ashadah
 * Christoforus Venus
 * Dicky Novanda Syaifullah
 * Donny Prayudha Stannia
 * Jason Joseph Tjiadi
 * Ryan Setiawan
 * Syafiqa Pramunadipta
 * Tri Oktavia Saraswati
 
## Business Understanding
### Problem Statement: 
Dari data pelanggan suatu perusahaan ecommerce terdapat 16,84% pelanggan yang melakukan churn. Oleh karena itu perusahaan ingin  dapat mempertahankan konsumen agar mereka tetap setia membeli barang dari perusahaan mereka. 

### Goal:
Perusahaan perlu melakukan prediksi untuk menentukan mana pelanggan yang loyal dan tidak loyal, sehingga nantinya perusahaan dapat menentukan strategi yang tepat untuk meningkatkan loyalitas dan menurunkan churn rate.

### Business metric:
Metrik yang digunakan adalah Customer Churn Rate (Churn Rate).
Churn rate adalah persentase pelanggan yang tidak memperpanjang langganan atau berhenti membeli selama periode waktu tertentu, seperti sebulan, triwulan atau setahun.

### Objective:
*  Menentukan faktor yang membuat pelanggan churn
*  Membangun model machine learning untuk melakukan prediksi pelanggan yang churn.
*  Memberikan rekomendasi bisnis sehingga perusahaan dapat meningkatkan loyalitas sehingga menurunkan churn rate.

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
*  Variabel numerik yang distribusinya cenderung skew positif (atau menceng ke kanan) karena mean < median < mode dan mempunyai nilai Outlier
   *  Tenure
   *  WarehouseToHome
   *  NumberOfAddress
   *  OrderAmountHikeFromlastYear
   *  CouponUsed
   *  OrderCount
   *  DaySinceLastOrder
   *  CashbackAmount
*  Sebaran data secara kesuluruhan mayoritas pelanggan tidak melakukan churn, dengan detil Churn sebanyak 16,84% dan No Churn sebanyak 83,16%.
*  Untuk tenure, pelanggan berlangganan  paling sebentar mempunyai kecenderungan untuk melakukan churn.
*  Ada kecenderungan semakin tinggi kupon yang digunakan, semakin tinggi juga kecenderungan untuk melakukan churn. 
*  Dilihat dari perangkat yang digunakan untuk login, mobile phone merupakan pilihan favorit pelanggan yang melakukan churn.
*  Dilihat dari metode pembayaran, yang sering digunakan oleh pelanggan yang churn adalah debit card.
*  Pelanggan melakukan churn dilihat dari faktor jenis kelamin (gender), pria lebih sering melakukan churn.
*  Pelanggan dengan status single merupakan pelanggan yang sering melakukan churn.
*  Churn rate tinggi pada pelanggan yang komplain.
* Rata-rata customer menggunakan applikasi selama 2 sampai 4 jam. Kebanyakan customer menggunakan applikasi selama 3 jam yaitu sekitar 50% costumer dan 8,6% diantaranya churn.
*  Kolom Churn adalah variabel target
*  Churn memiliki kolerasi positif lemah dengan CityTier, WarehouseToHome, NumberOfDeviceRegistered, SatisfactionScore, Complain
*  Terdapat multicollinearity pada kolom CouponUsed dan OrderCount terlihat dari chart heatmap memiliki nilai 0.75. Multicollinearity adalah konsep statistik di mana beberapa variabel independen dalam suatu model dikorelasikan. Dua variabel dikatakan kolinear sempurna jika koefisien korelasinya +/- 1,0. Multikolinearitas antar variabel independen akan menghasilkan inferensi statistik yang kurang reliabel.

### Business Insight
Mendapatkan pelanggan baru umumnya akan lebih mahal jika dibandingkan dengan mempertahankan pelanggan yang sudah ada. Selain itu, mempertahankan pelanggan juga mampu memberikan dampak yang sangat besar pada *growth rate* daripada mendapatkan pelanggan baru.
Hal pertama yang harus diketahui untuk  meminimalisir persentase churn rate adalah dengan mengetahui penyebab utama dari presentase churn tersebut agar bisa di atasi oleh perusahaan. 
-  Hal tersebut bisa datang dari UI atau UX Anda yang kurang ramah untuk pengguna, keterbatasan fitur pada aplikasi, dll. Dalam hal ini UI atau UX perlu dilakukan pengembangan lebih lanjut karena hasil EDA menunjukan pelanggan paling banyak menggunakan mobile phone untuk mengakses layanan.
-  Member dengan waktu paling singkat menunjukan churn yang tinggi mungkin juga disebabkan faktor UI/UX seperti yang disebutkan diatas. Disarankan juga memperbanyak penawaran menarik agar masa berlangganan pelanggan bisa bertahan lama
- Perusahaan juga perlu memperbanyak jumlah cashback (ie. cashback points) untuk pelanggan setia atau pelanggan yang melakukan pembelanjaan dengan nominal tertentu
-  Memperbanyak pilihan produk pada kategori mobile phone dengan harga yang bersaing dan memberikan promo diskon (ie. free assesoris hp, free ongkir)
-  Membuat diskon tambahan bagi pemegang kartu debit (ie. cashback points, free ongkir dengan menggunakan kartu debit bank yang bekerjasama)
-  Membuat acara live event dan menambah produk yang sedang trend yang dapat membuat pelanggan terutama pria untuk tetap setia jadi pelanggan perusahaan kita.
-  Memperbaiki Journey Map pelanggan, agar perusahaan dapat memperbaiki langkah-langkah yang menyebabkan pelanggan menjadi churn, seperti sulitnya untuk mengakses menu diaplikasi, dan perusahaan dapat mendefinisikan Kembali pelanggan ideal untuk perusahaan agar bagian marketing/sales tidak salah dalam mendapatkan pelanggan.
