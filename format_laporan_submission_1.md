# Laporan Proyek Machine Learning - Mutasar

## Domain Proyek

Proyek ini berfokus pada peramalan jumlah penjualan produk untuk GlobalMart. Dalam industri ritel yang sangat dinamis, kemampuan untuk memprediksi permintaan produk secara akurat adalah krusial. Tantangan utama yang dihadapi oleh banyak bisnis, termasuk GlobalMart, adalah ketidakpastian dalam menentukan jumlah stok yang tepat. Kelebihan stok dapat meningkatkan biaya penyimpanan dan risiko kadaluarsa, sementara kekurangan stok dapat menyebabkan kehilangan peluang penjualan dan mengecewakan pelanggan.

Peramalan penjualan yang akurat memungkinkan GlobalMart untuk mengoptimalkan manajemen inventaris, merencanakan rantai pasok dengan lebih efisien, mengalokasikan sumber daya (seperti staf dan anggaran promosi) dengan lebih baik, serta merespons perubahan pasar dengan cepat. Penerapan model peramalan penjualan berbasis data diharapkan dapat meminimalkan kerugian akibat ketidakseimbangan stok dan memaksimalkan pendapatan. Beberapa studi menunjukkan bahwa akurasi peramalan penjualan yang meningkat dapat secara signifikan mengurangi biaya operasional dan meningkatkan profitabilitas bisnis ritel [1].

[1] Fildes, R., & Goodwin, P. (2007). Against the Rules: How Expectations Affect Forecasts and What Can Be Done. International Journal of Forecasting, 23(1), 11-17.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Jelaskan mengapa dan bagaimana masalah tersebut harus diselesaikan
- Menyertakan hasil riset terkait atau referensi. Referensi yang diberikan harus berasal dari sumber yang kredibel dan author yang jelas.
- Format Referensi dapat mengacu pada penulisan sitasi [IEEE](https://journals.ieeeauthorcenter.ieee.org/wp-content/uploads/sites/7/IEEE_Reference_Guide.pdf), [APA](https://www.mendeley.com/guides/apa-citation-guide/) atau secara umum seperti [di sini](https://penerbitdeepublish.com/menulis-buku-membuat-sitasi-dengan-mudah/)
- Sumber yang bisa digunakan [Scholar](https://scholar.google.com/)

## Business Understanding

Pada bagian ini, kamu perlu menjelaskan proses klarifikasi masalah.

Bagian laporan ini mencakup:

### Problem Statements
Menjelaskan pernyataan masalah latar belakang:
- Ketidakpastian Permintaan: GlobalMart kesulitan dalam memprediksi jumlah pasti produk yang akan terjual di masa mendatang, yang berdampak pada efisiensi operasional.
- Manajemen Inventaris yang Tidak Optimal: Kurangnya prediksi penjualan yang akurat menyebabkan tantangan dalam menjaga keseimbangan stok, seringkali mengakibatkan kelebihan atau kekurangan persediaan.
- Alokasi Sumber Daya yang Kurang Efektif: Tanpa pemahaman yang jelas tentang permintaan di masa depan, GlobalMart kesulitan mengalokasikan anggaran promosi, staf, dan sumber daya logistik secara efisien.

### Goals

Menjelaskan tujuan dari pernyataan masalah:
- Meningkatkan Akurasi Peramalan Penjualan: Mengembangkan model prediktif yang dapat memprediksi jumlah penjualan produk dengan tingkat akurasi yang tinggi.
- Mengoptimalkan Manajemen Inventaris: Memberikan perkiraan penjualan yang andal untuk membantu GlobalMart menentukan tingkat stok yang optimal.
- Mendukung Pengambilan Keputusan Berbasis Data: Memberikan wawasan tentang faktor-faktor yang paling memengaruhi penjualan untuk membantu dalam perencanaan promosi dan alokasi sumber daya.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Menambahkan bagian “Solution Statement” yang menguraikan cara untuk meraih goals. Bagian ini dibuat dengan ketentuan sebagai berikut: 

    ### Solution statements
    - untuk mencapai tujuan yang telah ditetapkan, kami mengajukan beberapa pendekatan:

Pengembangan dan Evaluasi Model Prediktif Berganda: Kami akan mengembangkan dan mengevaluasi beberapa model regresi yang berbeda (Linear Regression, Random Forest, Gradient Boosting, XGBoost) untuk mengidentifikasi model terbaik yang mampu memprediksi jumlah penjualan. Performa model akan diukur menggunakan metrik standar seperti Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), dan R-squared (R2). Model dengan metrik evaluasi terbaik (misalnya, R2 tertinggi dan RMSE/MAE terendah) akan dipilih sebagai model terbaik.
Analisis Faktor Pengaruh Penjualan: Setelah model terbaik dipilih, kami akan menganalisis pentingnya fitur (feature importance) dari model tersebut (jika didukung) untuk mengidentifikasi faktor-faktor kunci yang paling berkontribusi pada jumlah penjualan. Hal ini akan memberikan wawasan yang dapat digunakan GlobalMart untuk strategi bisnis, seperti perencanaan promosi dan penentuan harga.

## Data Understanding
Data yang digunakan dalam proyek ini adalah data penjualan produk GlobalMart. Data ini disimulasikan untuk merepresentasikan karakteristik data penjualan ritel yang mencakup informasi seperti tanggal, ID produk, jumlah penjualan, harga satuan, biaya promosi, suhu rata-rata, indikator hari libur, bulan, tahun, dan hari dalam seminggu. Simulasi data ini juga mencakup faktor-faktor seperti musiman, tren, promosi, hari libur, dan pengaruh cuaca untuk menciptakan dataset yang kaya dan realistis untuk tujuan peramalan.
sumber dataset yang kami ambil adalah : ([https://www.kaggle.com/datasets])([(https://www.kaggle.com/datasets/downshift/city-bike-travels-dataset]).Sumber data ini adalah dataset simulasi yang dibuat langsung dalam notebook ini.

Informasi awal mengenai struktur data dapat dilihat dari output df.info() :
<class 'pandas.core.frame.DataFrame'>
Index: 53300 entries, 1500 to 54799
Data columns (total 14 columns):
 #   Column                   Non-Null Count  Dtype         
---  ------                   --------------  -----         
 0   tanggal                  53300 non-null  datetime64[ns]
 1   id_produk                53300 non-null  object        
 2   jumlah_penjualan         53300 non-null  int64         
 3   harga_satuan             53300 non-null  float64       
 4   biaya_promosi            53300 non-null  int64         
 5   suhu_rata2               53300 non-null  float64       
 6   hari_libur               53300 non-null  int64         
 7   bulan                    53300 non-null  int64         
 8   tahun                    53300 non-null  int64         
 9   hari_dalam_minggu        53300 non-null  int64         
 10  hari_dalam_tahun         53300 non-null  int32         
 11  minggu_dalam_tahun       53300 non-null  int64         
 12  jumlah_penjualan_lag_7   53300 non-null  float64       
 13  jumlah_penjualan_lag_30  53300 non-null  float64       
dtypes: datetime64[ns](1), float64(4), int32(1), int64(7), object(1)
memory usage: 5.9+ MB

df.head() 
tanggal	id_produk	jumlah_penjualan	harga_satuan	biaya_promosi	suhu_rata2	hari_libur	bulan	tahun	hari_dalam_minggu	hari_dalam_tahun	minggu_dalam_tahun	jumlah_penjualan_lag_7	jumlah_penjualan_lag_30
1500	2022-01-31	PROD_000	166	164800.0	990	34.4	0	1	2022	0	31	5	51.0	172.0
1550	2022-02-01	PROD_000	103	394600.0	0	34.3	0	2	2022	1	32	5	55.0	100.0
1600	2022-02-02	PROD_000	131	382800.0	0	28.6	0	2	2022	2	33	5	175.0	225.0
1650	2022-02-03	PROD_000	137	101500.0	0	30.2	0	2	2022	3	34	5	159.0	120.0
1700	2022-02-04	PROD_000	211	456000.0	0	30.4	0	2	2022	4	35	5	122.0	51.0


yang menunjukkan tipe data setiap kolom dan beberapa baris pertama data. Ukuran dataset, jumlah baris dan kolom, juga ditampilkan.

Selanjutnya uraikanlah seluruh variabel atau fitur pada data. Sebagai contoh:  

### Variabel-variabel pada Restaurant UCI dataset adalah sebagai berikut:
- accepts : merupakan jenis pembayaran yang diterima pada restoran tertentu.
- cuisine : merupakan jenis masakan yang disajikan pada restoran.
- dst

**Rubrik/Kriteria Tambahan (Opsional)**:
- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data atau exploratory data analysis.

## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan. Anda perlu menjelaskan tahapan dan parameter yang digunakan pada proses pemodelan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan kelebihan dan kekurangan dari setiap algoritma yang digunakan.
- Jika menggunakan satu algoritma pada solution statement, lakukan proses improvement terhadap model dengan hyperparameter tuning. **Jelaskan proses improvement yang dilakukan**.
- Jika menggunakan dua atau lebih algoritma pada solution statement, maka pilih model terbaik sebagai solusi. **Jelaskan mengapa memilih model tersebut sebagai model terbaik**.

## Evaluation
Pada bagian ini anda perlu menyebutkan metrik evaluasi yang digunakan. Lalu anda perlu menjelaskan hasil proyek berdasarkan metrik evaluasi yang digunakan.

Sebagai contoh, Anda memiih kasus klasifikasi dan menggunakan metrik **akurasi, precision, recall, dan F1 score**. Jelaskan mengenai beberapa hal berikut:
- Penjelasan mengenai metrik yang digunakan
- Menjelaskan hasil proyek berdasarkan metrik evaluasi

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.

