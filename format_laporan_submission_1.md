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

