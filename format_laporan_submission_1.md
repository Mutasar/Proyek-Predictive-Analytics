# Laporan Proyek Machine Learning - Mutasar

## Domain Proyek

Pada bagian ini, kamu perlu menuliskan latar belakang yang relevan dengan proyek yang diangkat.

Latar Belakang Proyek Analisis Prediktif: Studi Kasus GlobalMart
Dalam lanskap bisnis ritel modern yang sangat kompetitif dan dinamis, kemampuan untuk memprediksi permintaan pelanggan, mengelola inventaris secara efisien, dan merencanakan strategi pemasaran yang efektif adalah kunci keberhasilan. Perusahaan ritel besar seperti GlobalMart, dengan jangkauan operasional global dan volume transaksi yang masif, secara inheren menghadapi tantangan kompleks dalam mengoptimalkan operasi mereka.

Secara tradisional, banyak perusahaan ritel mengandalkan metode perkiraan permintaan yang bersifat reaktif atau berdasarkan intuisi dan pengalaman masa lalu. Pendekatan ini seringkali menyebabkan beberapa masalah krusial:

Manajemen Inventaris yang Tidak Efisien:

Kelebihan Stok (Overstocking): Menyebabkan peningkatan biaya penyimpanan, risiko kerusakan atau kadaluarsa produk, dan penurunan nilai aset. Modal yang terikat dalam stok berlebih juga menghambat investasi di area lain.

Kekurangan Stok (Understocking): Mengakibatkan kehilangan peluang penjualan, ketidakpuasan pelanggan, dan potensi beralihnya pelanggan ke pesaing. Ini juga merusak reputasi merek.

Efektivitas Promosi yang Rendah:

Kampanye promosi yang tidak didasarkan pada pemahaman mendalam tentang perilaku pelanggan dan tren pasar cenderung tidak tepat sasaran. Hal ini menyebabkan pemborosan anggaran pemasaran dan ROI (Return on Investment) yang minimal.

Kesulitan dalam mengidentifikasi produk yang tepat untuk dipromosikan, pada waktu yang tepat, dan kepada segmen pelanggan yang tepat.

Kesulitan dalam Perencanaan Sumber Daya:

Perencanaan staf, logistik, dan rantai pasokan menjadi tidak optimal tanpa perkiraan permintaan yang akurat. Hal ini dapat menyebabkan inefisiensi operasional, biaya tenaga kerja yang tidak perlu, atau kekurangan kapasitas saat dibutuhkan.

Menyadari keterbatasan metode konvensional dan potensi besar dari data yang mereka miliki, GlobalMart mengidentifikasi kebutuhan mendesak untuk beralih ke pendekatan yang lebih proaktif dan berbasis data. Analisis prediktif muncul sebagai solusi strategis yang dapat mengubah data historis (penjualan, harga, promosi, cuaca, tren ekonomi, demografi pelanggan) menjadi wawasan yang dapat ditindaklanjuti untuk memprediksi peristiwa di masa depan.

Proyek analisis prediktif ini bertujuan untuk memberdayakan GlobalMart agar dapat membuat keputusan yang lebih cerdas dan tepat waktu, sehingga meningkatkan efisiensi operasional, mengurangi biaya, dan pada akhirnya, meningkatkan kepuasan serta loyalitas pelanggan. Dengan mengimplementasikan model prediktif, GlobalMart berupaya untuk tidak hanya bereaksi terhadap pasar, tetapi juga membentuk masa depannya melalui perencanaan yang cerdas dan antisipatif.

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
- Pernyataan Masalah 1
- Pernyataan Masalah 2
- Pernyataan Masalah n

### Goals

Menjelaskan tujuan dari pernyataan masalah:
- Jawaban pernyataan masalah 1
- Jawaban pernyataan masalah 2
- Jawaban pernyataan masalah n

Semua poin di atas harus diuraikan dengan jelas. Anda bebas menuliskan berapa pernyataan masalah dan juga goals yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Menambahkan bagian “Solution Statement” yang menguraikan cara untuk meraih goals. Bagian ini dibuat dengan ketentuan sebagai berikut: 

    ### Solution statements
    - Mengajukan 2 atau lebih solution statement. Misalnya, menggunakan dua atau lebih algoritma untuk mencapai solusi yang diinginkan atau melakukan improvement pada baseline model dengan hyperparameter tuning.
    - Solusi yang diberikan harus dapat terukur dengan metrik evaluasi.

## Data Understanding
Paragraf awal bagian ini menjelaskan informasi mengenai data yang Anda gunakan dalam proyek. Sertakan juga sumber atau tautan untuk mengunduh dataset. Contoh: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Restaurant+%26+consumer+data).

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

