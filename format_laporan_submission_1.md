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

- Kami akan mengembangkan dan mengevaluasi beberapa model regresi yang berbeda (Linear Regression, Random Forest, Gradient Boosting, XGBoost) untuk mengidentifikasi model terbaik yang mampu memprediksi jumlah penjualan. Performa model akan diukur menggunakan metrik standar seperti Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), dan R-squared (R2). Model dengan metrik evaluasi terbaik (misalnya, R2 tertinggi dan RMSE/MAE terendah) akan dipilih sebagai model terbaik.

                        Ukuran X_train: (42640, 11), y_train: (42640,)
                        Ukuran X_test: (10660, 11), y_test: (10660,)
                        
                        Melatih model: Linear Regression
                          MAE: 46.73
                          MSE: 3294.60
                          RMSE: 57.40
                          R2: 0.23
                        
                        Melatih model: Random Forest
                          MAE: 45.45
                          MSE: 3041.66
                          RMSE: 55.15
                          R2: 0.29
                        
                        Melatih model: Gradient Boosting
                          MAE: 44.48
                          MSE: 2874.71
                          RMSE: 53.62
                          R2: 0.32
                        
                        Melatih model: XGBoost
                          MAE: 44.70
                          MSE: 2920.89
                          RMSE: 54.05
                          R2: 0.31
                        
                        --- Ringkasan Hasil Evaluasi Model ---
                        
                        Model: Linear Regression
                          MAE: 46.73
                          MSE: 3294.60
                          RMSE: 57.40
                          R2: 0.23
                        
                        Model: Random Forest
                          MAE: 45.45
                          MSE: 3041.66
                          RMSE: 55.15
                          R2: 0.29
                        
                        Model: Gradient Boosting
                          MAE: 44.48
                          MSE: 2874.71
                          RMSE: 53.62
                          R2: 0.32
                        
                        Model: XGBoost
                          MAE: 44.70
                          MSE: 2920.89
                          RMSE: 54.05
                          R2: 0.31
  
- Analisis Faktor Pengaruh Penjualan: Setelah model terbaik dipilih, kami akan menganalisis pentingnya fitur (feature importance) dari model tersebut (jika didukung) untuk mengidentifikasi faktor-faktor kunci yang paling berkontribusi pada jumlah penjualan. Hal ini akan memberikan wawasan yang dapat digunakan GlobalMart untuk strategi bisnis, seperti perencanaan promosi dan penentuan harga.

## Data Understanding
Data yang digunakan dalam proyek ini adalah data penjualan produk GlobalMart. Data ini disimulasikan untuk merepresentasikan karakteristik data penjualan ritel yang mencakup informasi seperti tanggal, ID produk, jumlah penjualan, harga satuan, biaya promosi, suhu rata-rata, indikator hari libur, bulan, tahun, dan hari dalam seminggu. Simulasi data ini juga mencakup faktor-faktor seperti musiman, tren, promosi, hari libur, dan pengaruh cuaca untuk menciptakan dataset yang kaya dan realistis untuk tujuan peramalan.
sumber dataset yang kami ambil adalah : ([https://www.kaggle.com/datasets])([(https://www.kaggle.com/datasets/downshift/city-bike-travels-dataset]).Sumber data ini adalah dataset simulasi yang dibuat langsung dalam notebook ini.

  Informasi awal mengenai struktur data dapat dilihat dari output df.info() :
                      <class 'pandas.core.frame.DataFrame'>
                      data terdiri dari 548350 baris dan 8 kolom:
                       #   Column                  Non-Null Count   Dtype  
                      ---  ------                  --------------   -----  
                       0   departure_time          548350 non-null  object 
                       1   return_time             548350 non-null  object 
                       2   departure_station_id    548350 non-null  int64  
                       3   departure_station_name  548350 non-null  object 
                       4   return_station_id       548350 non-null  int64  
                       5   return_station_name     548350 non-null  object 
                       6   distance                547608 non-null  float64
                       7   duration                548350 non-null  int64  
                      dtypes: float64(1), int64(3), object(4)
                      memory usage: 33.5+ MB


df.head() 
tanggal	id_produk	jumlah_penjualan	harga_satuan	biaya_promosi	suhu_rata2	hari_libur	bulan	tahun	hari_dalam_minggu	hari_dalam_tahun	minggu_dalam_tahun	jumlah_penjualan_lag_7	jumlah_penjualan_lag_30
1500	2022-01-31	PROD_000	166	164800.0	990	34.4	0	1	2022	0	31	5	51.0	172.0
1550	2022-02-01	PROD_000	103	394600.0	0	34.3	0	2	2022	1	32	5	55.0	100.0
1600	2022-02-02	PROD_000	131	382800.0	0	28.6	0	2	2022	2	33	5	175.0	225.0
1650	2022-02-03	PROD_000	137	101500.0	0	30.2	0	2	2022	3	34	5	159.0	120.0
1700	2022-02-04	PROD_000	211	456000.0	0	30.4	0	2	2022	4	35	5	122.0	51.0
Variabel/Fitur dalam Dataset:

Berikut adalah deskripsi dari setiap kolom atau fitur yang ada dalam DataFrame (df) yang digunakan dalam analisis Anda:

tanggal:

Tipe Data: datetime64[ns]
Deskripsi: Merepresentasikan tanggal transaksi atau pengamatan penjualan. Merupakan elemen kunci untuk analisis deret waktu.
id_produk:

Tipe Data: object (kemungkinan string)
Deskripsi: Identifier unik untuk setiap produk. Digunakan untuk mengelompokkan data penjualan berdasarkan produk tertentu.
jumlah_penjualan:

Tipe Data: int64
Deskripsi: Jumlah unit produk yang terjual pada tanggal tertentu untuk id_produk tertentu. Ini adalah variabel target yang ingin kita prediksi.
harga_satuan:

Tipe Data: float64
Deskripsi: Harga per unit produk. Merupakan faktor yang dapat memengaruhi jumlah penjualan.
biaya_promosi:

Tipe Data: int64
Deskripsi: Biaya yang dikeluarkan untuk promosi terkait produk pada tanggal tersebut. Promosi diharapkan dapat meningkatkan jumlah penjualan.
suhu_rata2:

Tipe Data: float64
Deskripsi: Suhu rata-rata lingkungan pada tanggal pengamatan. Ini adalah contoh fitur eksternal yang mungkin memengaruhi perilaku pembelian, terutama untuk produk tertentu.
hari_libur:

Tipe Data: int64
Deskripsi: Variabel biner (0 atau 1) yang menunjukkan apakah tanggal tersebut merupakan hari libur atau bukan. Hari libur seringkali berkorelasi dengan perubahan pola penjualan.
bulan:

Tipe Data: int64
Deskripsi: Angka bulan dari tanggal pengamatan (1 untuk Januari, 12 untuk Desember). Digunakan untuk menangkap pola musiman bulanan.
tahun:

Tipe Data: int64
Deskripsi: Angka tahun dari tanggal pengamatan. Digunakan untuk menangkap tren jangka panjang atau perubahan tahunan.
hari_dalam_minggu:

Tipe Data: int64
Deskripsi: Angka yang merepresentasikan hari dalam seminggu (0 untuk Senin, 6 untuk Minggu). Digunakan untuk menangkap pola mingguan atau harian dalam penjualan.
hari_dalam_tahun:

Tipe Data: int64
Deskripsi: Angka yang merepresentasikan hari ke berapa dalam setahun (1 hingga 365/366). Fitur hasil rekayasa dari kolom tanggal, digunakan untuk menangkap pola siklus dalam setahun yang mungkin tidak hanya bulanan.
minggu_dalam_tahun:

Tipe Data: int64
Deskripsi: Angka yang merepresentasikan minggu ke berapa dalam setahun. Fitur hasil rekayasa dari kolom tanggal, mirip dengan hari_dalam_tahun untuk menangkap pola siklus tahunan pada skala mingguan.
jumlah_penjualan_lag_7:

Tipe Data: float64
Deskripsi: Jumlah penjualan produk yang sama 7 hari sebelumnya. Fitur lag ini sangat penting dalam peramalan deret waktu karena penjualan saat ini seringkali sangat berkorelasi dengan penjualan di masa lalu.
jumlah_penjualan_lag_30:

Tipe Data: float64
Deskripsi: Jumlah penjualan produk yang sama 30 hari sebelumnya. Fitur lag ini juga penting untuk menangkap pola penjualan dalam periode yang lebih panjang.

### Variabel-variabel pada dataset adalah sebagai berikut:
tanggal: Merepresentasikan tanggal pengamatan penjualan. Berformat datetime, vital untuk analisis deret waktu.
id_produk: Kode unik untuk setiap produk yang dijual. Digunakan untuk membedakan data antar produk.
jumlah_penjualan: Kuantitas produk yang terjual pada tanggal dan untuk produk tertentu. Ini adalah target peramalan kita. Berupa nilai integer.
harga_satuan: Harga per unit produk. Merupakan faktor ekonomi yang dapat memengaruhi volume penjualan. Berupa nilai float.
biaya_promosi: Jumlah uang yang diinvestasikan dalam kegiatan promosi untuk produk pada hari tersebut. Diharapkan berkorelasi positif dengan penjualan. Berupa nilai integer.
suhu_rata2: Suhu rata-rata harian. Contoh fitur eksternal yang mungkin memiliki pengaruh musiman atau kontekstual terhadap penjualan produk tertentu. Berupa nilai float.
hari_libur: Indikator biner (1 jika hari libur, 0 jika bukan). Hari libur cenderung mengubah pola konsumsi. Berupa nilai integer.
bulan: Angka bulan (1-12) dari tanggal pengamatan. Menangkap pola musiman bulanan. Berupa nilai integer.
tahun: Angka tahun dari tanggal pengamatan. Menangkap tren jangka panjang. Berupa nilai integer.
hari_dalam_minggu: Angka yang mewakili hari dalam seminggu (0=Senin, ..., 6=Minggu). Menangkap pola penjualan harian dalam seminggu. Berupa nilai integer.
hari_dalam_tahun: Hari ke berapa dalam setahun (1-366). Fitur turunan dari tanggal untuk menangkap siklus tahunan yang lebih halus. Berupa nilai integer.
minggu_dalam_tahun: Minggu ke berapa dalam setahun. Fitur turunan dari tanggal, berguna untuk menangkap pola mingguan dalam setahun. Berupa nilai integer.
jumlah_penjualan_lag_7: Jumlah penjualan produk yang sama 7 hari sebelumnya. Fitur lag penting untuk model deret waktu, mencerminkan ketergantungan penjualan saat ini pada penjualan di masa lalu. Berupa nilai float.
jumlah_penjualan_lag_30: Jumlah penjualan produk yang sama 30 hari sebelumnya. Fitur lag untuk menangkap pola penjualan dalam jangka waktu bulanan. Berupa nilai float.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data atau exploratory data analysis.

## Data Preparation

Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.
Tahap persiapan data (data preparation) merupakan langkah krusial sebelum melatih model prediktif. Pada tahap ini, data dibersihkan, ditransformasi, dan direkayasa agar siap untuk digunakan dalam proses pemodelan. Langkah-langkah yang dilakukan mencakup:

Memuat Data: Data penjualan dimuat ke dalam DataFrame Pandas. Dalam kasus ini, data dimuat dari file CSV.

Pembersihan Data:

- Penanganan Nilai Null:
  Diperiksa keberadaan nilai null menggunakan isnull().sum().
  Dalam proses pembersihan, baris yang memiliki nilai null pada kolom 'jumlah_penjualan_lag_7' dan 'jumlah_penjualan_lag_30' dihapus (dropna) karena fitur lag ini penting untuk model    dan sulit untuk diimputasi tanpa memperkenalkan bias signifikan, terutama pada data deret waktu.

- Penanganan Duplikasi:
  Diperiksa keberadaan baris duplikat menggunakan duplicated().sum().
  Baris duplikat kemudian dihapus (drop_duplicates) untuk memastikan keunikan setiap observasi.

- Transformasi Tipe Data:
  Kolom tanggal dikonversi ke tipe data datetime untuk memfasilitasi ekstraksi fitur berbasis waktu.

- Rekayasa Fitur (Feature Engineering):
  Fitur-fitur baru yang relevan diekstraksi dari kolom tanggal untuk menangkap pola temporal:

  hari_dalam_tahun: Menangkap posisi hari dalam setahun.
  minggu_dalam_tahun: Menangkap posisi minggu dalam setahun.
  
  Fitur Lag:

  Dibuat fitur lag untuk menangkap ketergantungan temporal penjualan. jumlah_penjualan_lag_7 (penjualan 7 hari sebelumnya) dan jumlah_penjualan_lag_30 (penjualan 30 hari sebelumnya)
  dihitung menggunakan fungsi shift() setelah data diurutkan berdasarkan produk dan tanggal. Penggunaan groupby('id_produk') memastikan fitur lag dihitung secara terpisah untuk setiap
  produk.
  - Pemilihan Fitur dan Target:
    Variabel independen (fitur, X) yang akan digunakan untuk prediksi dan variabel dependen (target, y) yaitu jumlah_penjualan diidentifikasi.
  - Pemisahan Data Training dan Testing:
    Dataset dibagi menjadi set pelatihan (training set) dan set pengujian (testing set) menggunakan train_test_split dengan proporsi 80% untuk pelatihan dan 20% untuk pengujian.
    Pemisahan ini dilakukan setelah fitur lag dibuat dan baris null dihapus, untuk menghindari kebocoran data (data leakage) dari set pengujian ke set pelatihan.
  - Standardisasi Fitur Numerik:
    Untuk fitur numerik, digunakan StandardScaler dalam ColumnTransformer untuk menstandardisasi nilainya (mengubah skala data sehingga memiliki rata-rata 0 dan standar deviasi 1).
    Standardisasi ini penting untuk model yang sensitif terhadap skala fitur, seperti Linear Regression atau model berbasis jarak. ColumnTransformer memastikan transformasi hanya
    diterapkan pada kolom numerik yang dipilih.

- Penanganan Fitur Kategorikal (Opsional/Dikomunikasikan):
  Meskipun ada kolom id_produk yang bersifat kategorikal, dalam pipeline pre-processing yang diaktifkan pada kode, fitur kategorikal tidak di-encode (bagian OneHotEncoder
  dikomentari). Hal ini menyiratkan bahwa model yang digunakan diharapkan dapat menangani fitur kategorikal secara internal (misalnya, beberapa model tree-based) atau bahwa id_produk
  tidak disertakan sebagai fitur dalam model yang dilatih. (Sesuaikan bagian ini jika Anda mengaktifkan OneHotEncoder atau menggunakan 'id_produk' sebagai fitur kategorikal).

**Rubrik/Kriteria Tambahan (Opsional)**: 
Tahap persiapan data (data preparation) adalah fase esensial dalam alur kerja machine learning yang bertujuan untuk mengubah data mentah menjadi format yang sesuai dan berkualitas tinggi untuk analisis dan pemodelan. Proses ini sangat penting karena kualitas data input secara langsung memengaruhi performa model. Dalam proyek ini, langkah-langkah data preparation dilakukan dengan urutan dan alasan sebagai berikut:

1. Memuat Data

Proses: Data penjualan dimuat dari sumber eksternal (dalam hal ini, disimulasikan dan diakses melalui URL Google Drive yang dikonfigurasi untuk mengunduh file CSV) ke dalam struktur DataFrame menggunakan pustaka Pandas.
Alasan: Memuat data adalah langkah pertama untuk membawa data mentah ke dalam lingkungan kerja (Python) agar dapat diakses dan dimanipulasi. Pandas DataFrame menyediakan struktur data yang fleksibel dan alat yang kuat untuk menangani data tabular. Pemilihan pemisah (;) saat membaca CSV disesuaikan dengan format file sumber.

2. Pembersihan Data

Proses: Dilakukan pemeriksaan terhadap keberadaan nilai yang hilang (null) dan baris yang terduplikasi. Baris yang memiliki nilai null pada kolom jumlah_penjualan_lag_7 dan jumlah_penjualan_lag_30 dihapus. Baris yang merupakan duplikat juga dihapus.
Alasan:
Nilai Null: Nilai null dapat menyebabkan error pada banyak algoritma machine learning atau menghasilkan prediksi yang tidak akurat. Kolom jumlah_penjualan_lag_7 dan 
jumlah_penjualan_lag_30 sangat krusial untuk model peramalan deret waktu, dan mengimputasi nilai yang hilang pada fitur lag dapat sangat menyesatkan, terutama untuk data di awal deret 
waktu. Oleh karena itu, menghapus baris yang nilai lag-nya tidak tersedia (terutama di awal deret waktu setelah pengurutan) adalah pendekatan yang lebih aman dalam konteks ini.
Duplikasi: Baris duplikat dapat menyebabkan bias dalam pelatihan model karena data yang sama dipertimbangkan lebih dari sekali, yang secara artifisial dapat meningkatkan bobot 
observasi tersebut dan mengarah pada overestimasi atau underestimasi pola data. Menghapus duplikat memastikan setiap observasi adalah unik.

3. Transformasi Tipe Data

Proses: Kolom tanggal yang awalnya mungkin berupa string atau objek diubah menjadi tipe data datetime.
Alasan: Mengubah tipe data menjadi datetime memungkinkan ekstraksi komponen waktu seperti tahun, bulan, hari, dll., dengan mudah. Ini penting untuk membuat fitur berbasis waktu yang 
relevan untuk model deret waktu dan juga untuk memastikan operasi berbasis tanggal (seperti pengurutan) dilakukan dengan benar.

4. Rekayasa Fitur (Feature Engineering)

Proses: Fitur-fitur baru dibuat dari data yang sudah ada untuk memberikan informasi tambahan kepada model. Ini termasuk mengekstraksi hari_dalam_tahun, minggu_dalam_tahun dari kolom 
tanggal, serta membuat jumlah_penjualan_lag_7 dan jumlah_penjualan_lag_30 dengan menggunakan fungsi shift setelah data diurutkan berdasarkan produk dan tanggal.
Alasan:
Fitur seperti bulan, tahun, hari_dalam_minggu, hari_dalam_tahun, dan minggu_dalam_tahun menangkap pola musiman (misalnya, penjualan lebih tinggi di bulan tertentu atau hari tertentu 
dalam seminggu) dan tren. Model tidak dapat secara otomatis 'memahami' siklus waktu hanya dari kolom tanggal mentah.
Fitur lag (jumlah_penjualan_lag_7, jumlah_penjualan_lag_30) sangat penting untuk peramalan deret waktu. Mereka memberikan informasi historis langsung tentang penjualan produk 
tersebut, yang seringkali menjadi prediktor terbaik untuk penjualan di masa depan. Model dapat belajar dari ketergantungan temporal ini. Penggunaan groupby('id_produk') sebelum shift 
memastikan bahwa lag dihitung dalam deret waktu setiap produk, bukan di seluruh dataset.

5. Pemilihan Fitur dan Target

Proses: Kolom yang akan digunakan sebagai variabel independen (fitur, X) dan kolom yang menjadi variabel dependen (target, y, yaitu jumlah_penjualan) dipilih dan dipisahkan.
Alasan: Dengan jelas memisahkan fitur dan target, kita mendefinisikan input (X) dan output (y) yang akan digunakan untuk melatih model pembelajaran mesin. Ini adalah format standar 
yang dibutuhkan oleh sebagian besar algoritma supervised learning.

6. Pemisahan Data Training dan Testing

Proses: Dataset yang sudah bersih dan memiliki fitur lengkap dibagi menjadi dua subset: data pelatihan (X_train, y_train) dan data pengujian (X_test, y_test). Umumnya proporsi 80:20 
atau 70:30 digunakan.
Alasan: Memisahkan data menjadi set pelatihan dan pengujian adalah praktik standar untuk mengevaluasi performa model secara objektif. Model hanya dilatih menggunakan data pelatihan 
dan kemudian dievaluasi menggunakan data pengujian yang belum pernah dilihat sebelumnya. Ini memberikan perkiraan yang lebih realistis tentang seberapa baik model akan berkinerja pada 
data baru di dunia nyata dan membantu mendeteksi overfitting (di mana model hanya bekerja baik pada data pelatihan tetapi buruk pada data baru). Penting untuk melakukan pemisahan ini 
setelah semua rekayasa fitur yang melibatkan data historis (seperti fitur lag) selesai, tetapi sebelum standardisasi atau encoding yang dilakukan oleh pipeline, untuk menghindari data 
leakage.

7. Standardisasi Fitur Numerik

Proses: Nilai dari semua fitur numerik diskalakan menggunakan StandardScaler sehingga setiap fitur memiliki rata-rata nol dan varians satu. Proses ini diintegrasikan ke dalam 
ColumnTransformer dan pipeline.
Alasan: Banyak algoritma machine learning (terutama yang berbasis jarak atau gradien, seperti Linear Regression, Support Vector Machines, atau Neural Networks) sangat sensitif 
terhadap skala fitur input. Fitur dengan rentang nilai yang besar dapat mendominasi fitur lain dengan rentang kecil. Standardisasi memastikan bahwa setiap fitur berkontribusi secara 
proporsional pada perhitungan model dan membantu algoritma konvergen lebih cepat dan lebih stabil. ColumnTransformer digunakan untuk menerapkan transformasi ini hanya pada kolom 
numerik yang relevan.


## Modeling
Pada tahap ini, beberapa model machine learning regresi dipilih dan dilatih untuk memprediksi jumlah penjualan. Tujuan dari membandingkan beberapa model adalah untuk mengidentifikasi 
algoritma mana yang paling sesuai dan memberikan performa terbaik pada dataset ini untuk tugas peramalan penjualan.

Proses pemodelan melibatkan tahapan berikut:

- Pemilihan Model Regresi: Berdasarkan sifat masalah (memprediksi nilai kontinu, yaitu jumlah penjualan) dan praktik umum dalam peramalan, beberapa model regresi yang populer dan kuat
  dipilih:

Linear Regression: Model linier sederhana yang berguna sebagai baseline dan memberikan interpretasi yang mudah tentang hubungan antara fitur dan target.
Random Forest Regressor: Model ensemble berbasis tree yang kuat, kurang rentan terhadap overfitting dibandingkan single decision tree, dan dapat menangani interaksi non-linier antar 
fitur.
Gradient Boosting Regressor: Model ensemble lain yang secara iteratif membangun tree secara sekuensial, di mana setiap tree mencoba mengoreksi kesalahan dari tree sebelumnya. Model
ini sering memberikan performa tinggi.
XGBoost Regressor: Implementasi yang dioptimalkan dari gradient boosting yang terkenal karena kecepatannya dan performa terbaik di berbagai kompetisi machine learning.
Pembuatan Pipeline Modeling: Untuk memastikan bahwa langkah pre-processing (standardisasi fitur numerik) diterapkan secara konsisten pada data pelatihan dan pengujian sebelum data 
dimasukkan ke dalam model, dibuat Pipeline untuk setiap model. Pipeline ini menggabungkan ColumnTransformer (yang berisi StandardScaler untuk fitur numerik) dengan estimator model 
regresi yang dipilih. Penggunaan pipeline mencegah kebocoran data dari set pengujian selama standardisasi dan menyederhanakan alur kerja.

- Konfigurasi Parameter Model: Setiap model diinisialisasi dengan parameter tertentu. Parameter ini adalah hyperparameter model yang mengontrol proses pembelajaran algoritma [1, 2].
Linear Regression: Menggunakan parameter default.

Random Forest Regressor:

n_estimators=100: Jumlah pohon dalam forest. Nilai 100 adalah jumlah yang umum digunakan sebagai titik awal.
random_state=42: Mengunci seed untuk menghasilkan hasil yang reproducible.
n_jobs=-1: Menggunakan semua core prosesor yang tersedia untuk mempercepat pelatihan.
Gradient Boosting Regressor:
n_estimators=100: Jumlah tahap boosting (jumlah tree yang dibangun).
learning_rate=0.1: Mengontrol kontribusi setiap tree terhadap model akhir. Nilai yang lebih kecil memerlukan lebih banyak estimator tetapi bisa menghasilkan model yang lebih kuat.
random_state=42: Mengunci seed untuk reproducibility.
XGBoost Regressor:
n_estimators=100: Jumlah boosting rounds (jumlah tree).
learning_rate=0.1: Tingkat pembelajaran, serupa dengan Gradient Boosting.
random_state=42: Mengunci seed untuk reproducibility.
n_jobs=-1: Menggunakan semua core prosesor yang tersedia.
Parameter ini dipilih berdasarkan nilai default yang umum dan dipertimbangkan sebagai titik awal yang baik. Penyetelan hyperparameter lebih lanjut (hyperparameter tuning) dapat 
dilakukan di masa mendatang untuk mengoptimalkan performa model secara lebih mendalam [1].

Pelatihan Model: Setiap pipeline, yang berisi langkah pre-processing dan model, dilatih menggunakan data pelatihan (X_train, y_train) menggunakan metode .fit(). Selama pelatihan, 
model belajar pola dan hubungan antara fitur dan target dari data training.

Prediksi: Setelah dilatih, setiap model digunakan untuk membuat prediksi (y_pred) pada data pengujian (X_test) menggunakan metode .predict(). Data X_test melalui pipeline pre-
processing yang sama sebelum dimasukkan ke dalam model.

Evaluasi Model: Hasil prediksi (y_pred) dibandingkan dengan nilai aktual (y_test) dari data pengujian. Proses evaluasi ini akan dibahas lebih lanjut pada bagian selanjutnya.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan kelebihan dan kekurangan dari setiap algoritma yang digunakan.
- Jika menggunakan satu algoritma pada solution statement, lakukan proses improvement terhadap model dengan hyperparameter tuning.


**Jelaskan proses improvement yang dilakukan**.
Dalam pendekatan ini, proses improvement berfokus pada pemilihan model regresi yang paling efektif di antara beberapa algoritma yang telah diimplementasikan dan dievaluasi. Daripada 
melakukan hyperparameter tuning mendalam pada setiap model (yang bisa menjadi langkah perbaikan selanjutnya), strategi yang diterapkan di sini adalah membandingkan performa awal dari 
model-model yang dipilih dengan pengaturan parameter standar atau umum.

Proses improvement ini dilakukan melalui tahapan berikut:
- Melatih Beberapa Model: Seperti dijelaskan di bagian "Modeling", empat model regresi yang berbeda (Linear Regression, Random Forest Regressor, Gradient Boosting Regressor, dan- XGBoost Regressor) dilatih menggunakan data pelatihan yang sama dan melalui pipeline pre-processing yang konsisten.
- Mengevaluasi Setiap Model: Setelah setiap model dilatih, performanya diukur menggunakan metrik evaluasi standar pada data pengujian (X_test, y_test). Metrik yang digunakan mencakup Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE), dan R-squared (R2).
- Membandingkan Hasil Evaluasi: Metrik performa dari keempat model dikumpulkan dan dibandingkan. Visualisasi (seperti bar plot R2 dan RMSE) digunakan untuk memudahkan perbandingan
  visual.
- Memilih Model Terbaik: Model yang menunjukkan performa terbaik berdasarkan metrik evaluasi yang relevan (dalam kasus regresi, umumnya R2 tertinggi dan RMSE/MAE terendah) dipilih sebagai solusi terbaik untuk tugas peramalan penjualan ini. Kode secara eksplisit mengidentifikasi model dengan R2 tertinggi sebagai model terbaik.
  
Alasan Pendekatan Ini:

Memulai dengan membandingkan beberapa algoritma umum memberikan wawasan awal tentang jenis model mana yang paling cocok untuk dataset dan masalah yang dihadapi. Beberapa model mungkin secara inheren lebih mampu menangani kompleksitas data (seperti non-linearitas atau interaksi antar fitur) dibandingkan yang lain. Dengan membandingkan performa awal, kita dapat dengan cepat mengidentifikasi kandidat model yang menjanjikan sebelum menginvestasikan waktu dan sumber daya untuk fine-tuning (penyetelan hyperparameter) yang lebih lanjut. Dalam konteks proyek awal, memilih model terbaik dari beberapa pilihan adalah bentuk improvement performa yang efektif.



**Jelaskan mengapa memilih model tersebut sebagai model terbaik**.

Setelah semua model dilatih dan dievaluasi, langkah improvement selanjutnya adalah memilih model yang memberikan performa terbaik. Berdasarkan hasil evaluasi yang ditunjukkan oleh metrik (MAE, MSE, RMSE, R2) pada data pengujian, model dengan R2 score tertinggi dan RMSE (atau MAE) terendah dianggap sebagai model terbaik.

Mengapa R2 dan RMSE?
R2 (R-squared): Koefisien determinasi ini mengukur proporsi varians dalam variabel dependen (jumlah penjualan) yang dapat diprediksi dari variabel independen (fitur). Nilai R2 berkisar antara 0 hingga 1. Nilai R2 yang lebih tinggi menunjukkan bahwa model mampu menjelaskan variabilitas data target dengan lebih baik, yang berarti model memiliki kemampuan prediksi yang lebih kuat.
RMSE (Root Mean Squared Error): RMSE adalah akar kuadrat dari rata-rata selisih kuadrat antara nilai aktual dan nilai prediksi. Metrik ini mengukur ukuran rata-rata kesalahan prediksi model dalam unit yang sama dengan variabel target. RMSE yang lebih rendah menunjukkan bahwa prediksi model secara rata-rata lebih dekat dengan nilai aktual.

Berdasarkan hasil evaluasi:
Linear Regression: R2 = 0.23, RMSE = 57.40
Random Forest: R2 = 0.29, RMSE = 55.15
Gradient Boosting: R2 = 0.32, RMSE = 53.62
XGBoost: R2 = 0.31, RMSE = 54.05

Model Gradient Boosting menunjukkan performa terbaik dengan R2 score tertinggi sebesar 0.32 dan RMSE terendah sebesar 53.62. MAE-nya (44.48) juga merupakan yang terendah. Tingginya nilai R2 menunjukkan bahwa Gradient Boosting paling efektif dalam menjelaskan variasi jumlah penjualan dibandingkan model lain yang diuji, dan rendahnya nilai RMSE mengindikasikan bahwa kesalahan prediksinya secara rata-rata adalah yang terkecil. Ini menjadikan Gradient Boosting kandidat paling kuat untuk digunakan dalam peramalan penjualan GlobalMart berdasarkan data dan model yang diuji.

Catatan: Meskipun R2 = 0.32 menunjukkan bahwa model masih hanya dapat menjelaskan sekitar 32% variabilitas dalam jumlah penjualan, ini merupakan peningkatan signifikan dibandingkan Linear Regression (R2 = 0.23) dan sedikit lebih baik dari Random Forest dan XGBoost. Ini mengindikasikan bahwa ada faktor-faktor lain yang mungkin memengaruhi penjualan yang belum ditangkap oleh fitur-fitur yang ada, atau model yang lebih kompleks atau tuning lebih lanjut diperlukan untuk mencapai R2 yang lebih tinggi. Namun, berdasarkan model yang diuji dalam eksperimen ini, Gradient Boosting adalah yang terbaik.

## Evaluation
Tahap evaluasi dilakukan untuk mengukur seberapa baik model-model yang telah dilatih mampu memprediksi jumlah penjualan pada data yang belum pernah dilihat sebelumnya (data pengujian). Metrik evaluasi yang tepat sangat penting untuk memahami performa model regresi dan membandingkan model yang berbeda secara objektif.

Metrik Evaluasi yang Digunakan:

Dalam proyek peramalan penjualan ini (yang merupakan masalah regresi), metrik evaluasi yang relevan dan digunakan adalah:

Mean Absolute Error (MAE):

Penjelasan: MAE mengukur rata-rata besar kesalahan antara prediksi model dan nilai aktual, tanpa mempertimbangkan arah kesalahan. MAE dihitung sebagai rata-rata dari nilai absolut selisih antara setiap nilai prediksi dan nilai aktual.
Interpretasi: MAE memberikan gambaran langsung tentang seberapa besar, rata-rata, prediksi model menyimpang dari nilai sebenarnya dalam unit variabel target (jumlah penjualan). MAE yang lebih rendah menunjukkan performa yang lebih baik.
Mean Squared Error (MSE):

Penjelasan: MSE mengukur rata-rata dari kuadrat kesalahan antara prediksi model dan nilai aktual. Dengan mengkuadratkan kesalahan, MSE memberikan bobot yang lebih besar pada kesalahan yang besar (outlier).
Interpretasi: MSE sering digunakan karena sifat matematisnya yang baik dalam optimalisasi. Namun, nilainya berada dalam unit kuadrat dari variabel target, sehingga interpretasi langsungnya kurang intuitif dibandingkan MAE atau RMSE. MSE yang lebih rendah menunjukkan performa yang lebih baik.
Root Mean Squared Error (RMSE):

Penjelasan: RMSE adalah akar kuadrat dari MSE. Ini mengembalikan metrik kesalahan kembali ke unit yang sama dengan variabel target.
Interpretasi: RMSE sangat populer karena memberikan ukuran rata-rata kesalahan dalam unit yang dapat langsung dibandingkan dengan nilai target. Seperti MSE, RMSE memberikan bobot lebih pada kesalahan besar. RMSE yang lebih rendah menunjukkan performa yang lebih baik.
R-squared (R2):

Penjelasan: R2, atau koefisien determinasi, mengukur proporsi varians dalam variabel dependen (jumlah penjualan) yang dapat dijelaskan oleh model menggunakan variabel independen (fitur). Nilainya berkisar antara 0 hingga 1. R2 = 1 berarti model menjelaskan 100% varians, sementara R2 = 0 berarti model tidak menjelaskan varians sama sekali (prediksi tidak lebih baik dari menggunakan rata-rata target).
Interpretasi: R2 memberikan pemahaman tentang seberapa baik model "cocok" dengan data. Nilai R2 yang lebih tinggi menunjukkan bahwa model memiliki kemampuan yang lebih baik untuk menangkap pola dalam data dan memprediksi variasi dalam jumlah penjualan.
Hasil Proyek Berdasarkan Metrik Evaluasi:

Setelah melatih dan mengevaluasi keempat model pada data pengujian, diperoleh hasil metrik sebagai berikut:

Model	MAE	MSE	RMSE	R2
Linear Regression	46.73	3294.60	57.40	0.23
Random Forest	45.45	3041.66	55.15	0.29
Gradient Boosting	44.48	2874.71	53.62	0.32
XGBoost	44.70	2920.89	54.05	0.31
Berdasarkan tabel hasil evaluasi dan visualisasi perbandingan metrik (seperti yang ditunjukkan di notebook), dapat disimpulkan:

Model Gradient Boosting menunjukkan performa terbaik di antara model-model yang diuji. Ini terlihat dari:
R2 tertinggi (0.32): Menunjukkan bahwa model Gradient Boosting paling efektif dalam menjelaskan variabilitas jumlah penjualan pada data pengujian.
RMSE terendah (53.62): Mengindikasikan bahwa rata-rata kesalahan prediksi model Gradient Boosting adalah yang terkecil dalam unit jumlah penjualan.
MAE terendah (44.48): Menunjukkan bahwa rata-rata besar kesalahan prediksi model Gradient Boosting juga yang terkecil.
Model Linear Regression memiliki performa terendah dengan R2 hanya 0.23 dan RMSE tertinggi 57.40. Ini menunjukkan bahwa model linier sederhana kurang mampu menangkap pola kompleks dalam data penjualan dibandingkan model ensemble.
Model Random Forest dan XGBoost memberikan performa yang lebih baik dari Linear Regression tetapi sedikit di bawah Gradient Boosting dalam hal R2 dan RMSE pada data ini.
Meskipun R2 sebesar 0.32 menunjukkan bahwa masih ada sebagian besar variabilitas dalam jumlah penjualan yang tidak dapat dijelaskan oleh model dengan fitur-fitur yang ada, Gradient Boosting memberikan dasar terbaik untuk peramalan berdasarkan eksperimen ini. Rata-rata kesalahan prediksi (RMSE sekitar 53.62 unit penjualan) memberikan gambaran konkret tentang tingkat akurasi model dalam memprediksi jumlah penjualan harian produk

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.

