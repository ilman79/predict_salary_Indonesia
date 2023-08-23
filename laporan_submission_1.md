# Laporan Proyek Machine Learning - Ilman Gifari

## Domain Proyek

Pada bagian ini, kamu perlu menuliskan latar belakang yang relevan dengan proyek yang diangkat.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Jelaskan mengapa dan bagaimana masalah tersebut harus diselesaikan
- Menyertakan hasil riset terkait atau referensi. Referensi yang diberikan harus berasal dari sumber yang kredibel dan author yang jelas.
  [referensi 1](https://bisnis.tempo.co/read/1759061/anies-baswedan-sebut-prioritas-cetak-lapangan-kerja-kepada-kaum-milenial?tracking_page_direct)
  [referensi 2](https://finance.detik.com/berita-ekonomi-bisnis/d-5651000/kesulitan-bayar-gaji-karyawan-pengusaha-minta-pemerintah-subsidi-50)
  [referensi 3](https://www.kompas.com/global/read/2023/08/05/180000470/laporan-terbaru-terkait-fenomena-wfh--gaji-kurang-kesejahteraan-nomor)
  [referensi 4](https://www.antaranews.com/berita/1491480/viral-gaji-karyawan-rp20-juta-masih-kurang-lakukan-ini-saat-pandemi)
  [referensi 5](http://eprints.undip.ac.id/28737/1/Jurnal.pdf)
  [referensi 6](http://eprints.undip.ac.id/15830/1/Rita_Andini.pdf)

  
  Format Referensi: [Judul Referensi](https://scholar.google.com/) 

## Business Understanding

Air sangat berguna bagi kehidupan tetapi alangkah baiknya kita menggunakan air yang bersih dan tidak tercemar oleh lingkungan. Bagaimana kita membedakan air yang dapat gunakan oleh kita sebagai manusia untuk kehidupan sehari-hari ? susah bukan untuk membedakannya. Maka dari itu, penting sekali kita tahu bahwa air itu layak untuk digunakan dan bagaimana cara membedakannya ? yaitu kita membuat suatu prediksi air yang layak untuk digunakan

### Problem Statements
Berdasarkan kondisi di atas perusahaan akan membuat sebuah sistem prediksi air untuk menjawab permasalahan berikut.
- Apa yang paling mempengaruhi air itu layak digunakan ?
- Apakah air ini layak digunakan ?


### Goals

Untuk menjawab pertanyaan tersebut, tujuan kami membuat prediksi model
- Mengetahui apa saja yang mempengaruhi kelayakan air
- Membuat model machine learning yang dapat memprediksi kelayakan air dari variabel-variabel yang ada

**Rubrik/Kriteria Tambahan (Opsional)**:
- Menambahkan bagian “Solution Statement” yang menguraikan cara untuk meraih goals. Bagian ini dibuat dengan ketentuan sebagai berikut: 

    ### Solution statements
    - Mengajukan 2 atau lebih solution statement. Misalnya, menggunakan dua atau lebih algoritma untuk mencapai solusi yang diinginkan atau melakukan improvement pada baseline model dengan hyperparameter tuning.
    - Solusi yang diberikan harus dapat terukur dengan metrik evaluasi.

## Data Understanding
Paragraf awal bagian ini menjelaskan informasi mengenai data yang Anda gunakan dalam proyek. Sertakan juga sumber atau tautan untuk mengunduh dataset. [dataset water potability](https://www.kaggle.com/datasets/adityakadiwal/water-potability).

### Variabel-variabel pada water potability adalah sebagai berikut:
1. Nilai pH:
pH adalah parameter penting dalam mengevaluasi keseimbangan asam-basa air. Ini juga merupakan indikator kondisi asam atau basa dari status air. WHO telah merekomendasikan batas maksimum yang diizinkan untuk pH dari 6,5 hingga 8,5. Rentang investigasi saat ini adalah 6,52–6,83 yang berada dalam kisaran standar WHO.

2. Kekerasan:
Kekerasan terutama disebabkan oleh garam kalsium dan magnesium. Garam-garam ini larut dari endapan geologis yang dilalui oleh air. Lamanya air bersentuhan dengan bahan pembentuk kekerasan membantu menentukan seberapa banyak kekerasan yang ada dalam air mentah. Kekerasan awalnya didefinisikan sebagai kapasitas air untuk mengendapkan sabun yang disebabkan oleh Kalsium dan Magnesium.

3. Padatan (Total dissolved solids - TDS):
Air memiliki kemampuan untuk melarutkan berbagai mineral atau garam anorganik dan beberapa senyawa organik seperti kalium, kalsium, natrium, bikarbonat, klorida, magnesium, sulfat, dll. Mineral-mineral ini menghasilkan rasa yang tidak diinginkan dan warna yang tereduksi pada tampilan air. Ini adalah parameter penting untuk penggunaan air. Nilai TDS yang tinggi pada air menunjukkan bahwa air sangat termineralisasi. Batas yang diinginkan untuk TDS adalah 500 mg/l dan batas maksimumnya adalah 1000 mg/l yang direkomendasikan untuk tujuan minum.

4. Kloramina:
Klorin dan kloramina adalah disinfektan utama yang digunakan dalam sistem air minum umum. Kloramina umumnya terbentuk ketika amonia ditambahkan ke klorin untuk mengolah air minum. Konsentrasi klorin hingga 4 miligram per liter (mg/L atau 4 bagian per juta (ppm)) dianggap aman dalam air minum.

5. Sulfat:
Sulfat adalah zat yang terjadi secara alami yang ditemukan dalam mineral, tanah, dan batuan. Mereka hadir di udara ambient, air tanah, tanaman, dan makanan. Penggunaan utama dari sulfat adalah dalam industri kimia. Konsentrasi sulfat dalam air laut sekitar 2.700 miligram per liter (mg/L). Rentangnya adalah 3 hingga 30 mg/L dalam sebagian besar pasokan air tawar, meskipun konsentrasi yang lebih tinggi (1000 mg/L) ditemukan di beberapa lokasi geografis.

6. Konduktivitas:
Air murni bukan penghantar arus listrik yang baik, tetapi lebih sebagai isolator yang baik. Peningkatan konsentrasi ion meningkatkan konduktivitas listrik air. Secara umum, jumlah padatan terlarut dalam air menentukan konduktivitas listrik. Konduktivitas listrik (EC) sebenarnya mengukur proses ionik dari larutan yang memungkinkannya menghantarkan arus. Menurut standar WHO, nilai EC tidak boleh melebihi 400 μS/cm.

7. Karbon Organik Total (TOC):
Total Organic Carbon (TOC) dalam air sumber berasal dari bahan organik alami yang membusuk (NOM) serta sumber-sumber sintetis. TOC adalah ukuran jumlah total karbon dalam senyawa organik dalam air murni. Menurut US EPA, <2 mg/L sebagai TOC dalam air yang diolah/minum, dan <4 mg/Lit dalam air sumber yang digunakan untuk pengolahan.

8. Trihalometana:
THM adalah bahan kimia yang dapat ditemukan dalam air yang diolah dengan klorin. Konsentrasi THM dalam air minum bervariasi tergantung pada tingkat bahan organik dalam air, jumlah klorin yang diperlukan untuk mengolah air, dan suhu air yang sedang diolah. Tingkat THM hingga 80 ppm dianggap aman dalam air minum.

9. Kekeruhan:
Kekeruhan air tergantung pada jumlah zat padat yang hadir dalam keadaan tergantung. Ini adalah ukuran sifat emisi cahaya air dan tes ini digunakan untuk mengindikasikan kualitas pembuangan limbah dengan mengacu pada materi koloid. Nilai kekeruhan rata-rata yang diperoleh untuk Kampus Wondo Genet (0,98 NTU) lebih rendah dari nilai yang direkomendasikan oleh WHO yaitu 5,00 NTU.

10. Kepotabelan:
Menunjukkan apakah air aman untuk dikonsumsi manusia, di mana 1 berarti Layak Minum dan 0 berarti Tidak Layak Minum.
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

