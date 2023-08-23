# Laporan Proyek Machine Learning - Ilman Gifari

## Domain Proyek
Pada kondisi sekarang di Indonesia telah mengalami musim kemarau, hujan tidak turun selama beberapa bulan sedangkan kita sebagai mahluk hidup ternasuk tumbuhan dan hewan memerlukan air. Tetapi air yang seperti apa ? yaitu air yang layak untuk digunakan untuk kehidupan. Air sangatlah penting untuk menunjang kehidupan mahluk hidup tapi bagaimana jika air yang kita gunakan tidak layak pakai, apalagi saat ini sedang musim kemarau di Indonesia, kita lihat disalah satu berita menyiarkan telah terjadi kekeringan dan kelangkaan air bersih bagaimana kita tahu bahwa air itu layak atau tidak ? sehingga perlu adanya teknologi untuk mengetahui air itu layak atau tidak digunakan.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Air merupakan zat yang diperlukan mahluk hidup sehingga membutuhkannya 
- Adapun berita yang menyiarkan [BBC Indonesia - Kelangkaan Air Bersih](https://www.bbc.com/indonesia/articles/cydgj76p626o)
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
- Dikarenakan model algoritma machine learning banyak, maka kita akan menggunakan beberapa saja yaitu Random Forest, KNN dan Boosting dan masing-masing akan kita uji sekaligus memilih model dari hasil evaluasinya.

## Data Understanding
Paragraf awal bagian ini menjelaskan informasi mengenai data yang Anda gunakan dalam proyek. Sertakan juga sumber atau tautan untuk mengunduh dataset. [dataset water potability](https://www.kaggle.com/datasets/adityakadiwal/water-potability).

### Variabel-variabel pada water potability adalah sebagai berikut:
1. Nilai pH (ph):
pH adalah parameter penting dalam mengevaluasi keseimbangan asam-basa air. Ini juga merupakan indikator kondisi asam atau basa dari status air. WHO telah merekomendasikan batas maksimum yang diizinkan untuk pH dari 6,5 hingga 8,5. Rentang investigasi saat ini adalah 6,52–6,83 yang berada dalam kisaran standar WHO.

2. Kekerasan (hardnees):
Kekerasan terutama disebabkan oleh garam kalsium dan magnesium. Garam-garam ini larut dari endapan geologis yang dilalui oleh air. Lamanya air bersentuhan dengan bahan pembentuk kekerasan membantu menentukan seberapa banyak kekerasan yang ada dalam air mentah. Kekerasan awalnya didefinisikan sebagai kapasitas air untuk mengendapkan sabun yang disebabkan oleh Kalsium dan Magnesium.

3. Padatan (Total dissolved solids - TDS) / (Solids):
Air memiliki kemampuan untuk melarutkan berbagai mineral atau garam anorganik dan beberapa senyawa organik seperti kalium, kalsium, natrium, bikarbonat, klorida, magnesium, sulfat, dll. Mineral-mineral ini menghasilkan rasa yang tidak diinginkan dan warna yang tereduksi pada tampilan air. Ini adalah parameter penting untuk penggunaan air. Nilai TDS yang tinggi pada air menunjukkan bahwa air sangat termineralisasi. Batas yang diinginkan untuk TDS adalah 500 mg/l dan batas maksimumnya adalah 1000 mg/l yang direkomendasikan untuk tujuan minum.

4. Kloramina (Chloramines) :
Klorin dan kloramina adalah disinfektan utama yang digunakan dalam sistem air minum umum. Kloramina umumnya terbentuk ketika amonia ditambahkan ke klorin untuk mengolah air minum. Konsentrasi klorin hingga 4 miligram per liter (mg/L atau 4 bagian per juta (ppm)) dianggap aman dalam air minum.

5. Sulfat (Sulfate):
Sulfat adalah zat yang terjadi secara alami yang ditemukan dalam mineral, tanah, dan batuan. Mereka hadir di udara ambient, air tanah, tanaman, dan makanan. Penggunaan utama dari sulfat adalah dalam industri kimia. Konsentrasi sulfat dalam air laut sekitar 2.700 miligram per liter (mg/L). Rentangnya adalah 3 hingga 30 mg/L dalam sebagian besar pasokan air tawar, meskipun konsentrasi yang lebih tinggi (1000 mg/L) ditemukan di beberapa lokasi geografis.

6. Konduktivitas (Conductivity):
Air murni bukan penghantar arus listrik yang baik, tetapi lebih sebagai isolator yang baik. Peningkatan konsentrasi ion meningkatkan konduktivitas listrik air. Secara umum, jumlah padatan terlarut dalam air menentukan konduktivitas listrik. Konduktivitas listrik (EC) sebenarnya mengukur proses ionik dari larutan yang memungkinkannya menghantarkan arus. Menurut standar WHO, nilai EC tidak boleh melebihi 400 μS/cm.

7. Karbon Organik Total (TOC) / (Organic_carbon) :
Total Organic Carbon (TOC) dalam air sumber berasal dari bahan organik alami yang membusuk (NOM) serta sumber-sumber sintetis. TOC adalah ukuran jumlah total karbon dalam senyawa organik dalam air murni. Menurut US EPA, <2 mg/L sebagai TOC dalam air yang diolah/minum, dan <4 mg/Lit dalam air sumber yang digunakan untuk pengolahan.

8. Trihalometana (Trihalomethanes) :
THM adalah bahan kimia yang dapat ditemukan dalam air yang diolah dengan klorin. Konsentrasi THM dalam air minum bervariasi tergantung pada tingkat bahan organik dalam air, jumlah klorin yang diperlukan untuk mengolah air, dan suhu air yang sedang diolah. Tingkat THM hingga 80 ppm dianggap aman dalam air minum.

9. Kekeruhan (Turbidity) :
Kekeruhan air tergantung pada jumlah zat padat yang hadir dalam keadaan tergantung. Ini adalah ukuran sifat emisi cahaya air dan tes ini digunakan untuk mengindikasikan kualitas pembuangan limbah dengan mengacu pada materi koloid. Nilai kekeruhan rata-rata yang diperoleh untuk Kampus Wondo Genet (0,98 NTU) lebih rendah dari nilai yang direkomendasikan oleh WHO yaitu 5,00 NTU.

10. Kepotabelan (Potability) : Menunjukkan apakah air aman untuk dikonsumsi manusia, di mana 1 berarti Layak Minum dan 0 berarti Tidak Layak Minum
    
**Rubrik/Kriteria Tambahan (Opsional)**
- Sebelum melakukan modeling, kita akan melihat insight apa saja yang didapat dari Proses Explanatory Data Analysis, yaitu bahwa kita mengecek data dan cleaning data terlebih dahulu dengan cara mengecek missing value, duplikasi data dan outlier
- Setelah kita mengecek, beberapa data yang missing kita inputkan dan untuk outlier kita pisahkan dikarenakan mengantisipasi terjadinya bias.
- Ketika sudah clean datanya maka kita bisa lihat insigt apa saja dengan melihat dari visualisasinya

## Data Preparation
Pada bagian ini Kami menerapkan teknik split data dan standarisasi data untuk preparation yang dilakukan sebagai berikut.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Pembagian dataset dengan fungsi train_test_split dari library sklearn. Ini dilakukan untuk memisahkan/split data yaitu data train, dan data test
- Standarisasi. Ini dilakukan karena satuan pada tiap-tiap variabel berbeda sehingga perlu adanya standarisasi agar menyamakan satuan

## Modeling
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan. Anda perlu menjelaskan tahapan dan parameter yang digunakan pada proses pemodelan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Karena kita memilih model Random Forest, yaitu modelnya sederhana, mampu untuk data besar dan mereduksi overviting karena hasilnya tunggal, kekurangannya adalah membutuhkan waktu lama untuk train modelnya dan kurang fleksibel dalam beberapa parameter.
- Model yang akan kita pilih ada dengan melihat mse nya, semakin msenya kecil maka semakin baik model tersebut

## Evaluation
Untuk mengevaluasi model Random forest regresi yang kita pilih menggunakan mse atau Mean Squared Error
- Metrik ini mengukur rata-rata perbedaan kuadrat antara nilai prediksi dan nilai aktual (ground truth) dari variabel target. Dengan kata lain, metrik ini menghitung rata-rata dari kesalahan kuadrat antara nilai prediksi dan nilai aktual.
- Hasil dari metriksnya yaitu 0.061537. artinya 1 - 0.061537 = 93,9% akurasinya benar dan erorr sebesar 6,1% terjadi erorr

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- ![](https://www.i2tutorials.com/wp-content/media/2019/11/Differences-between-MSE-and-RMSE-1-i2tutorials.jpg)
Di mana:
n : adalah jumlah titik data (sampel).
​y : mewakili nilai aktual dari variabel target untuk titik data ke-i
y^ : mewakili nilai prediksi dari variabel target untuk titik data ke-i.
**---Ini adalah bagian akhir laporan---**

