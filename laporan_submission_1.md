# Laporan Proyek Machine Learning - Ilman Gifari

## Domain Proyek
Pada kondisi sekarang di Indonesia telah mengalami musim kemarau, hujan tidak turun selama beberapa bulan sedangkan mahluk hidup termasuk tumbuhan dan hewan memerlukan air. Tetapi air yang seperti apa ? yaitu air yang layak untuk digunakan untuk kehidupan. Air sangatlah penting untuk menunjang kehidupan mahluk hidup tapi bagaimana jika air yang gunakan tidak layak pakai, apalagi saat ini sedang musim kemarau di Indonesia, disalah satu berita menyiarkan telah terjadi kekeringan dan kelangkaan air bersih bagaimana bahwa air itu layak atau tidak ? sehingga perlu adanya teknologi untuk mengetahui air itu layak atau tidak digunakan. [1]
  
## Business Understanding
Air sangat berguna bagi kehidupan tetapi alangkah baiknya menggunakan air yang bersih dan tidak tercemar oleh lingkungan. Bagaimana membedakan air yang dapat gunakan oleh manusia untuk kehidupan sehari-hari ?. Maka dari itu, penting sekali bahwa air itu layak untuk digunakan dan bagaimana cara membedakannya yaitu membuat suatu prediksi air yang layak untuk digunakan.

### Problem Statements
Berdasarkan kondisi di atas perusahaan akan membuat sebuah sistem prediksi air untuk menjawab permasalahan berikut.
- Apa yang paling mempengaruhi air itu layak digunakan ?
- Apakah air ini layak digunakan ?


### Goals

Untuk menjawab pertanyaan tersebut, tujuan kami membuat prediksi model
- Mengetahui apa saja yang mempengaruhi kelayakan air
- Membuat model *machine learning* yang dapat memprediksi kelayakan air dari variabel-variabel yang ada

**Rubrik**:
- Pada kali ini menggunakan beberapa saja jenis model yaitu *Random Forest*, *k-NN* dan *Boosting* dan masing-masing akan uji sekaligus memilih model dari hasil evaluasinya.

## Data Understanding
Paragraf awal bagian ini menjelaskan informasi mengenai data yang Anda gunakan dalam proyek. Sertakan juga sumber atau tautan untuk mengunduh dataset. [dataset water potability](https://www.kaggle.com/datasets/adityakadiwal/water-potability).

- Dataset yang gunakan yaitu Dataset Water Potability
### Variabel-variabel pada water potability adalah sebagai berikut:
1. Nilai pH (ph):
pH adalah parameter penting dalam mengevaluasi keseimbangan asam-basa air. Ini juga merupakan indikator kondisi asam atau basa dari status air. WHO telah merekomendasikan batas maksimum yang diizinkan untuk pH dari 6,5 hingga 8,5. Rentang investigasi saat ini adalah 6,52–6,83 yang berada dalam kisaran standar WHO.

2. Kekerasan (*hardnees*):
Kekerasan terutama disebabkan oleh garam kalsium dan magnesium. Garam-garam ini larut dari endapan geologis yang dilalui oleh air. Lamanya air bersentuhan dengan bahan pembentuk kekerasan membantu menentukan seberapa banyak kekerasan yang ada dalam air mentah. Kekerasan awalnya didefinisikan sebagai kapasitas air untuk mengendapkan sabun yang disebabkan oleh Kalsium dan Magnesium.

3. Padatan / (*Solids*):
Air memiliki kemampuan untuk melarutkan berbagai mineral atau garam anorganik dan beberapa senyawa organik seperti kalium, kalsium, natrium, bikarbonat, klorida, magnesium, sulfat, dll. Mineral-mineral ini menghasilkan rasa yang tidak diinginkan dan warna yang tereduksi pada tampilan air. Ini adalah parameter penting untuk penggunaan air. Nilai TDS yang tinggi pada air menunjukkan bahwa air sangat termineralisasi. Batas yang diinginkan untuk TDS adalah 500 mg/l dan batas maksimumnya adalah 1000 mg/l yang direkomendasikan untuk tujuan minum.

4. Kloramina (*Chloramines*) :
Klorin dan kloramina adalah disinfektan utama yang digunakan dalam sistem air minum umum. Kloramina umumnya terbentuk ketika amonia ditambahkan ke klorin untuk mengolah air minum. Konsentrasi klorin hingga 4 miligram per liter (mg/L atau 4 bagian per juta (ppm)) dianggap aman dalam air minum.

5. Sulfat (*Sulfate*):
Sulfat adalah zat yang terjadi secara alami yang ditemukan dalam mineral, tanah, dan batuan. Mereka hadir di udara ambient, air tanah, tanaman, dan makanan. Penggunaan utama dari sulfat adalah dalam industri kimia. Konsentrasi sulfat dalam air laut sekitar 2.700 miligram per liter (mg/L). Rentangnya adalah 3 hingga 30 mg/L dalam sebagian besar pasokan air tawar, meskipun konsentrasi yang lebih tinggi (1000 mg/L) ditemukan di beberapa lokasi geografis.

6. Konduktivitas (*Conductivity*):
Air murni bukan penghantar arus listrik yang baik, tetapi lebih sebagai isolator yang baik. Peningkatan konsentrasi ion meningkatkan konduktivitas listrik air. Secara umum, jumlah padatan terlarut dalam air menentukan konduktivitas listrik. Konduktivitas listrik (EC) sebenarnya mengukur proses ionik dari larutan yang memungkinkannya menghantarkan arus. Menurut standar WHO, nilai EC tidak boleh melebihi 400 μS/cm.

7. Karbon Organik Total / (*Organic_carbon*) :
Total Organic Carbon (TOC) dalam air sumber berasal dari bahan organik alami yang membusuk (NOM) serta sumber-sumber sintetis. TOC adalah ukuran jumlah total karbon dalam senyawa organik dalam air murni. Menurut US EPA, <2 mg/L sebagai TOC dalam air yang diolah/minum, dan <4 mg/Lit dalam air sumber yang digunakan untuk pengolahan.

8. Trihalometana (*Trihalomethanes*) :
THM adalah bahan kimia yang dapat ditemukan dalam air yang diolah dengan klorin. Konsentrasi THM dalam air minum bervariasi tergantung pada tingkat bahan organik dalam air, jumlah klorin yang diperlukan untuk mengolah air, dan suhu air yang sedang diolah. Tingkat THM hingga 80 ppm dianggap aman dalam air minum.

9. Kekeruhan (*Turbidity*) :
Kekeruhan air tergantung pada jumlah zat padat yang hadir dalam keadaan tergantung. Ini adalah ukuran sifat emisi cahaya air dan tes ini digunakan untuk mengindikasikan kualitas pembuangan limbah dengan mengacu pada materi koloid. Nilai kekeruhan rata-rata yang diperoleh untuk Kampus Wondo Genet (0,98 NTU) lebih rendah dari nilai yang direkomendasikan oleh WHO yaitu 5,00 NTU.

10. Kepotabelan (*Potability*) : Menunjukkan apakah air aman untuk dikonsumsi manusia, di mana 1 berarti Layak Minum dan 0 berarti Tidak Layak Minum
    
- Jumlah Data set yang digunakan 3276 rows × 10 columns
- Sebelum melakukan modeling, Dengan melihat insight apa saja yang didapat dari Proses *Explanatory Data Analysis*, yaitu bahwa mengecek data dan cleaning data terlebih dahulu dengan cara mengecek *missing value*, duplikasi data dan *outlier*
- Cara untuk mengatasi *outlier* adalah dengan mencari Q1 dan Q3 atau batas atas dan batas bawah dari dataset tersebut lalu apabila data tersebut berada melebihi batas atas maka akan dipisahkan dan begitu juga untuk untuk yang tidak berada dibatas bawah maka akan dipisahkan. Kemudian, mengambil data yang berada pada range batas atas dan batas bawah. Hal ini bisa divisualisasikan dengan *boxplot*.
- Setelah mengecek, beberapa data yang missing yang diinputkan dan untuk outlier lalu pisahkan dikarenakan mengantisipasi terjadinya bias.
- Ketika sudah clean datanya memiliki insigt apa saja dengan melihat dari visualisasinya
![Gambar 1. Korelasi antaar variabel](https://raw.githubusercontent.com/ilman79/predict_salary_Indonesia/main/documentasi/gambar%201.png)
- Dilihat dari korelasi antar varibel yaitu sangat rendah. Tetapi *Hardness*/kepadatan berkorelasi positif dengan ph untuk sisanya korelasinya rendah.
![Gambar 2. Distribusi tiap variabel](https://raw.githubusercontent.com/ilman79/predict_salary_Indonesia/main/documentasi/gambar%202.png)
- Dilihat dari distribusi tiap variabelnya sudah normal atau berbentuk lonceng.
- Tidak ada *outlier* yang terlalu *signifikan*
## Data Preparation
Pada bagian ini Kami menerapkan teknik *split data* dan *standarisasi* data untuk preparation yang dilakukan sebagai berikut.

- Pembagian dataset dengan fungsi *train_test_split* dari *library sklearn*. Ini dilakukan untuk memisahkan/split data yaitu *data train*, dan *data test*. Untuk memisahkan data seumumnya menggunakan rasio 80:20, yaitu 80% data untuk train model, dan 20% untuk *testing model*. Data yang dipilih secara acak dari dataset
- *Standarisasi*. Ini dilakukan karena satuan pada tiap-tiap variabel berbeda sehingga perlu adanya standarisasi agar menyamakan satuan contohnya besaran ph dan kadar sulfat itu berbeda satuannya ph batasnya sampai 13 tetapi kadar sulfat sampai 200. Sehingga terjadi ketimpangan. Rumusnya adalah mencari rata-rata dari seluruh dataset kemudian dibagi dengan standar deviasinya. Contohnya jika menggunakan *algoritma k-NN*, yaitu mengukur jarak antar amatan jika dengan standarisasi membantu dalam mengukur jarak dengan konsisten dan akurat.

## Modeling
Tahapan ini membahas mengenai model *machine learning* yang digunakan untuk menyelesaikan permasalahan adalah *Random Forest*, *k-NN*,*Boosting*. 
- Cara kerja *algoritma Random Forest* ini adalah menggabungkan banyak pohon keputusan yang dibangun dari dataset pelatihan yang diambil secara acak dengan penggantian. Setiap pohon memutuskan pemisahan berdasarkan kriteria seperti Gini Impurity atau Entropy. Proses ini menghasilkan berbagai pohon yang beragam. Selain itu, pada setiap langkah pemisahan, hanya sejumlah fitur yang dipilih secara acak untuk menghindari korelasi yang berlebihan antara pohon-pohon. Setelah pohon-pohon terbentuk, prediksi dari setiap pohon dihitung, dan prediksi akhir diambil berdasarkan mayoritas suara untuk masalah klasifikasi atau rata-rata prediksi untuk masalah regresi.
- Cara kerja *boosting* dimulai dengan memberikan bobot awal yang setara pada semua sampel data. Selanjutnya, iterasi dimulai dengan membangun weak learner, yaitu model yang sedikit di atas peluang acak, seperti decision stump. Model ini dibangun dengan memperhatikan bobot pada masing-masing sampel, memberikan fokus lebih pada sampel yang sulit diklasifikasikan. Setelah model dibangun, error pada setiap sampel dihitung, dan bobot sampel-sampel yang salah diklasifikasikan diatur ulang agar diberi bobot lebih tinggi.
- cara kerja *k-NN* mencari k-neighbors (k tetangga terdekat) berdasarkan jarak euclidean atau metrik lainnya, di antara data latihan yang telah ada. Kemudian, mayoritas kelas atau rata-rata nilai dari tetangga-tetangga ini akan ditetapkan sebagai prediksi untuk sampel yang ingin diprediksi. Nilai k yang dipilih akan mempengaruhi sensitivitas model terhadap noise: k yang lebih besar cenderung membuat prediksi lebih stabil, sementara k yang lebih kecil lebih rentan terhadap fluktuasi pada data. K-NN bekerja baik untuk data yang memiliki pola terlihat dalam ruang fitur, tetapi bisa kurang efektif dalam data dengan dimensi yang tinggi atau ketika data memiliki noise yang signifikan.

**Rubrik**: 
- Dengan memilih model *Random Forest*, yaitu modelnya sederhana, dapat digunakan untuk data besar, dan kekurangannya adalah memerlukan waktu lama karena untuk mendapatkan model terbaik
- parameternya
  - n_estimators=20, Banyaknya pohon yang menjadi awalan
  - max_depth=16, Banyak percabangan hingga menjadi perindividu
  - _jobs=-1 Disini menggunakan -1 untuk cara kerjanya pararel
  - *random_state*: digunakan untuk mengontrol random number generator yang digunakan. Disini *random_state=25*

- Dengan memilih model *Boosting*, yaitu modelnya sederhana, dapat digunakan untuk data besar, dan kekurangannya adalah memerlukan waktu lama karena untuk mendapatkan model terbaik
- parameternya
  - learning_rate=0.05, diberikan nilai 0.05, yang mengontrol sejauh mana setiap model lemah (weak learner) memberikan kontribusi terhadap prediksi akhir.
  - *random_state*: digunakan untuk mengontrol random number generator yang digunakan. Disini *random_state=25*
    
- Dengan memilih model *k-NN*, yaitu modelnya sederhana, dapat digunakan untuk data besar, dan kekurangannya adalah memerlukan waktu lama karena untuk mendapatkan model terbaik
- parameternya
  - n_neighbors=10, 10 tetangga terdekat saat melakukan prediksi
- Model yang akan pilih adalah dengan melihat msenya, semakin msenya kecil maka semakin baik model tersebut

## Evaluation
![](https://raw.githubusercontent.com/ilman79/predict_salary_Indonesia/main/documentasi/gambar%203.png)

Hasil dari gambar 3 diatas merupakan mse dari masing-masing *algoritma* yang terkecil adalah *Random FOrest* dan terbesar adalah *Boosting*.

- Hasil prediksi tiap-tiap *algoritma*
  
|      | y_true | prediksi_KNN | Prediksi_RF | Prediksi_Boosting |
|------|--------|--------------|-------------|-------------------|
| 424  | 0      | 0            | 1           | 0                 |
| 301  | 1      | 1            | 0           | 0                 |
| 1813 | 0      | 0            | 0           | 0                 |

Hasil prediksi dari tiap-tiap *algoritma machine learning*nya. Yang menjadi acuannya adalah y_true, apabila ia bernilai 1 maka air layak digunakan, jika bernilai 0 maka air tidak layak digunakan. lalu lihat berapa *probabilitas* prediksi pada masing-masing model

- Hasil probabilitas kebenaran

|          | correct_predictions   | incorrect_predictions   | probabilitas_true |
|----------|-----------------------|-------------------------|-------------------|
| KNN      |          328          |            206          |      0.614232     |
| RF       |          336          |            198          |      0.629213     |
| Boosting |          339          |            195          |      0.634831     |

Dihasilkan bahwa jumlah yang sesuai dengan y_true adalah algoritma Boosting sebesar 0.634831 dan hasil probabilitas terkecil yaitu KNN sebesar 0.614232. Maka dari itu evaluasi model terbaik yang akan digunakan adalah algoritma Random Forest yang memiliki nilai mse lebih kecil dari yang lain. Tujuan kali ini adalah memprediksi dan memilih model berdasarkan hasil nilai mse yang lebih rendah walaupun dilihat dari probabilitas_truenya lebih kecil dari Boosting.

Untuk mengevaluasi model *Random Forest* regresi yang dipilih menggunakan mse atau *Mean Squared Error* Walaupun msenya terkecil tetapi jika dilihat *probabilitas* kebenaran antara aktual dan prediksi lebih kecil yang *algoritma Boosting*
- Metrik ini mengukur rata-rata perbedaan kuadrat antara nilai prediksi dan nilai aktual dari variabel target. Dengan kata lain, metrik ini menghitung rata-rata dari kesalahan kuadrat antara nilai prediksi dan nilai aktual.
- Hasil dari metriksnya yaitu 0.061537. artinya 1 - 0.061537 = 93,9% akurasinya benar dan erorr sebesar 6,1% terjadi erorr. 

**Rubrik**: 

$$ MSE = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2 $$

Di mana:
- n : adalah jumlah titik data (sampel).
- y : mewakili nilai aktual dari variabel target untuk titik data ke-i
- y^ : mewakili nilai prediksi dari variabel target untuk titik data ke-i.

**Kesimpulan**:
- Banyak *missing value* dan *outlier* pada dataset sehingga perlu ada *cleaning* dan memisahkan sekitar 600 data tidak digunakan
- Dataset sudah berdistribusi normal ditandai dengan grafik seperti lonceng
- Model yang dipilih adalah *Random Forest* walaupun untuk msenya terbesar saat train tetapi untuk probabilitasnya tertinggi daripada yang lain.
- Sudah bisa memprediksi kelayakan air dan juga masyarakat mengetahui yang mempengaruhi kelayakan air adalah kepadatan
- Diharapkan pada saat kondisi seperti musim kemarau masyarakat bisa terbantu dalam memilih air yang layak digunakan


**Daftar Referensi**

[1] PENERAPAN ALGORITMA MACHINE LEARNIN G UNTUK DETEKSI KUALITAS AIR | PERPUSTAKAAN UNIVERSITAS HASANUDDIN.” Accessed August 25, 2023. http://digilib.unhas.ac.id/opac/detail-opac?id=7541.


**---Ini adalah bagian akhir laporan---**

