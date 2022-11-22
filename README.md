# Project Data Analysis : Analyzing eCommerce Business Performance with SQL

**Work Environment :**
> Tools : PostgreSQL <br> 
Visualization : Microsoft Excel

## ✏️ Rumusan Masalah
Mengukur performa bisnis merupakan suatu hal yang sangat penting bagi sebuah perusahaan. Ini akan membantu dalam memantau, dan menilai keberhasilan atau kegagalan dari berbagai proses bisnis. Pengukuran performa bisnis dapat dilakukan dengan memperhitungkan beberapa metrik bisnis. Dalam poyek ini akan dilakukan analisis performa bisnis suatu perusahaan eCommerce dengan dengan metrik bisnis yaitu pertumbuhan pelanggan, kualitas produk, dan tipe pembayaran berdasarkan historical data selama tiga tahun.

## ✏️ Objektif
Mengumpulkan insight dari analisis dan dengan visualisasi berupa :
- Pertumbuhan aktivitas pelanggan tahunan (**Annual Customer Activity Growth**)
- Kualitas kategori produk tahunan (**Annual Product Category Quality**)
- Penggunaan jenis pembayaran tahunan (**Annual Payment Type Usage**)

## ✏️ Data Preparation
Data preparation merupakan langkah yang harus dipenuhi ketika akan melakukan pengolahan
data. Pada tahap ini dilakukan penyiapan data mentah menjadi data yang terstruktur dan siap di 
proses.

Dataset yang digunakan adalah dataset sebuah perusahaan eCommerce Brasil yang memiliki informasi pesanan dengan jumlah 99441 dari tahun 2016 hingga 2018. Terdapat fitur-titur yang membuat informasi seperti status pemesanan, lokasi, rincian item, jenis pembayaran, serta ulasan.

📌 Tabel yang digunakan:
- customers_dataset
- sellers_dataset
- product_dataset
- geolocation_dataset
- orders_dataset
- order_items_dataset
- order_payments_dataset
- order_reviews_dataset

📌 Langkah-langkah yang dilakukan meliputi:
1. Membuat workspace database di dalam pgAdmin dan membuat tabel menggunakan `CREATE TABLE` statement
2. Melakukan import data csv kedalam database
3. Menentukan Primary Key atau Foreign Key enggunakan statement `ALTER TABLE`
4. Membuat dan mengeksport ERD (Entity Relationship Diagram) 

**Hasil ERD :** <br>
<p align="center">
  <img src="asset/gambar_1_ERD.png" width=60% height=60%> <br>
  Gambar 1. Entity Relationship Diagram
</p>

## ✏️ Analisis
#### 1. Annual Customer Activity Growth
Pertumbuhan aktivitas pelanggan tahunan dapat dianalisis dari Monthly active user (MAU), pelanggan baru, pelanggan dengan repeat order, dan rata-rata order oleh pelanggan.

<p align="center">
Tabel 1. Hasil Analisis Pertumbuhan Aktivitas Customer (lihat query)
</p>

<div align="center">

| year | avg_mau | total_new_customer | total_customer_repeat | avg_frequency | 
|------|---------|--------------------|-----------------------|---------------|
|2016	 |108	     |326	              | 3	                    | 1.009         |
|2017	 |3694     |43708	              | 1256	              | 1.032         |
|2018	 |5338     |52062	              | 1167	              | 1.024         |

</div>

<br>
<p align="center">
  <img src="asset/gambar_2_mau_x_newcust.png" width=60% height=60%> <br>
  Gambar 2. Grafik Rata-rata MAU dan Pelanggan Baru
</p>

📌 **Insight :** <br>
Secara keseluruhan perusahaan mengalami peningkakatan Monthly Active User serta pelanggan baru setiap tahunnya. Peningkatan yang signifikan terjadi pada tahun 2016 hingga 2017, hal ini dikarenakan data transaksi pada tahun 2016 dimulai pada bulan September. <br>
<br>

<p align="center">
  <img src="asset/gambar_3_repeat order.png" width=60% height=60%> <br>
  Gambar 3. Grafik Jumlah Pelanggan yang Melakukan Repeat Order
</p>

📌 **Insight :** <br>
Peningkatan yang signifikan juga terjadi pada jumlah pelanggan yang melakukan repeat order pada tahun 2016 hingga 2017. Namun pada tahun 2018 mengalami sedikit penurunan, artinya diduga pelanggan kebanyakan hanya melakukan satu kali. <br>
<br>

<p align="center">
  <img src="asset/gambar_4_freq_order.png" width=60% height=60%> <br>
  Gambar 4. Grafik Rata-rata Frekuensi Order Pelanggan
</p>

📌 **Insight :** <br>
Dari analisis dan grafik diatas dapat dibuktikan bahwa rata-rata pelanggan setiap tahunnya memang hanya melakukan order satu kali. <br>
<br>

#### 2. Annual Product Category Quality

Kualitas kategori produk tahuan dapat dianalisis dari total pendapatan, total pembatalan pesanan, kategori top produk dan kategori produk yang paling banyak dibatalkan.

<p align="center">
Tabel 2. Hasil Analisis Total Kategori Produk (lihat query)
</p>

<div align="center">

| year | total_revenue | top_product    | total_revenue_top_product | total_canceled | top_canceled_product | total_top_canceled_product |
|------|---------------|----------------|---------------------------|----------------|----------------------|-----------------------------
|2016	 |46653.74	     |furniture_decor |6899.35	              | 26	       | toys	            |3                           |
|2017	 |6921535.24     |bed_bath_table  |569964.78	              | 265	       | sports_leisure	      |24                          |
|2018	 |8451584.77     |health_beauty   |877065.73	              | 334	       | health_beauty	      |27                          |

</div>

<br>
<p align="center">
  <img src="asset/gambar_5_total_revenue.png" width=60% height=60%> <br>
  Gambar 5. Grafik Total Revenue Pertahun
</p>

📌 **Insight :** <br>
Secara keseluruhan revenue perusahaan meningkat setiap tahun. <br>
<br>

<p align="center">
  <img src="asset/gambar_6_top.png" width=60% height=60%> <br>
  Gambar 6. Grafik Total Revenue Top Produk Pertahun
</p>

📌 **Insight :** <br>
Revenue yang dihasilkan dari top produk juga meningkat untuk setiap tahunnya dan setiap tahun memiliki kategori top produk yang berbeda. Tahun 2018 memiliki pendapatan revenue tertinggi dengan top produk kategori kesehatan dan kecantikan. <br>
<br>

<p align="center">
  <img src="asset/gambar_7_cenceled.png" width=60% height=60%> <br>
  Gambar 6. Grafik Total Revenue Top Produk Pertahun
</p>

📌 **Insight :** <br>
Produk yang sering dibatalkan oleh pelanggan untuk setiap tahunnya juga memiliki kategori yang berbeda dan mengalami kenaikan setiap tahunnya. Tahun 2018 memiliki jumlah produk yang dibatalkan paling banyak, namun disisi lain memiliki kategori yang sama dengan top produk 2018 yaitu kesehatan dan kcantikan. Hal tersebut diduga bahwa kategori kesehatan dan kecantikan sedang mendominasi pasar.  <br>
<br>

#### 3. Annual Payment Type Usage

<p align="center">
    Tabel 3. Hasil Analisis Total Tipe Pembayran yang Digunakan (lihat query)
</p>

<div align="center">
            
|  payment_type  |  2016  |  2017  |  2018  | sum_payment_type_usage |
|----------------|--------|--------|--------|------------------------|
| credit_card    | 258	  | 34568  | 41969  |	76795                |
| boleto         | 63	  | 9508   | 10213  |	19784                |
| voucher        | 23	  | 3027   | 2725   |	5775                 |
| debit_card     | 2	  | 422    | 1105   |	1529                 |

</div>

<br>
<p align="center">
  <img src="asset/gambar_8_tipe_pembayaran.png" width=60% height=60%> <br>
  Gambar 6. Grafik Tipe Pembayaran yang Digunakan Pelanggan Pertahun
</p>

📌 **Insight :** <br>
Mayoritas pelanggan melakukan pembayaran menggunakan kartu kredit setiap tahunnya dan cenderung mengalami peningkatan, lalu disusul dengan boleto. Pembayaran menggunakan voucher meningkat pada tahun 2017, namun menurun pada tahun 2018. Hal tersebut dapat diduga karena ketersediaan voucher yang diberikan perusahaan lebih sedikit dari tahun lalu. Disisi lain, pelanggan yang melakukan pembayaran dengan kartu debit meningkat secara signifikan pada tahun 2018. Hal tersebut dapat diduga kemungkinan terdapat promosi pembayaran dengan kartu debit sehingga banyak pelanggan yang tertarik untuk menggunakan metode tersebut.

<br>

## ✏️ Kesimpulan

- Dilihat dari analisis pertumbuhan tahunan pelanggan dapat disimpulkan bahwa jumlah pelanggan baru dan aktif (MAU) meningkat setiap tahunnya, namun pelanggan cenderung tidak *repeat order* atau hanya melakukan pembelian satu kali. Dari hal tersebut perlu adanya strategi bisnis untuk meningkatkan minat pelanggan agar melakukan pembelian misalnya dengan pemberian promo, call to action, dan lain sebagainya.
- Dari analisis kualitas produk tahunan, revenue terus meningkat dengan kategori produk yang berbeda setiap tahunnya. Kategori **kesehatan dan kecantikan** menjadi produk best seller dan yang paling sering dibatalkan oleh pelanggan pada tahun 2018. Berdasarkan hasil top produk ini dapat dilakukan strategi bisnis terkait riset produk apa yang akan menjadi trend di tahun selanjutnya, sehingga diharapkan dapat memperbesar peluang perusahaan mendapatkan revenue.
- Kartu kredit merupakan tipe pembayaran yang dominan digunakan pelanggan.
