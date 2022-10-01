### Repository ini merupakan media penyimpanan file Final Project dari Kelompok 4-Mother Of Dataset untuk kelas Data Science Bootcamp Batch 25 di Rakamin Academy 

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
Sebuah perusahaan ecommerce ingin  memprediksi churn rate dan mempertahankan konsumen agar mereka tetap setia membeli barang dari perusahaan mereka.

### Goal:
Pelanggan adalah aset yang paling penting dari semua jenis bisnis. Prospek usaha hanya mungkin dapat dilakukan dengan kehadiran pelanggan yang puas yang selalu setia dengan perusahaan. Untuk alasan ini, perusahaan harus merencanakan dan menerapkan strategi untuk menciptakan pelanggan,umumnya dikenal sebagai Customer Relationship Management (CRM).
Customer Relationship Management (CRM) merupakan strategi bisnis yang bertujuan untuk mengelola hubungan dengan pelanggan yang memadukan proses antara manusia dan teknologi. Sistem CRM bertujuan untuk membantu, mempertahankan, mengelola, dan meningkatkan hubungan pelanggan setia dan langgeng atau di sebut juga dengan proses manejemen Churn.
Perusahaan perlu melakukan prediksi untuk menentukan mana pelanggan yang loyal dan tidak loyal, sehingga nantinya perusahaan dapat menentukan strategi yang tepat untuk mengatasi churn rate yang tinggi dan bagaimana mempertahankan pelanggan.

### Business metric:
Customer Churn (Churn) mengacu pada hilangnya pelanggan yang mendaftar ke paket berbasis langganan. Atau bisa juga berlaku untuk pelanggan yang sering membeli dari perusahaan lalu berhenti membeli.
Churn rate adalah persentase pelanggan yang tidak memperpanjang langganan atau berhenti membeli selama periode waktu tertentu, seperti sebulan, triwulan atau setahun.

### Objective:
Churn prediction bertujuan untuk memprediksi peluang seorang pelanggan untuk churn sebelum pelanggan tersebut benar-benar melakukannya, dengan demikian perusahaan bisa memberikan treatment untuk meminimalisir kemungkinan mereka beralih ke perusahaan lain. Prediksi akan dilakukan dengan menggunakan machine learning dengan sebuah algoritma supervised learning yang akan mengklasifikasikan pelanggan menjadi churn atau tidak churn di masa mendatang.
Tujuan akhir adalah mengurangi jumlah pelanggan yang beralih ke perusahaan lain atau berhenti membeli produk dari perusahaan dengan menggunakan machine learning untuk melakukan prediksi churn. Ini penting karena semakin tinggi churn rate, semakin kecil revenue yang akan perusahaan dapatkan.

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
