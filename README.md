# Laporan Proyek Machine Learning - Mahesa Tirta Panjalu

## Domain Proyek

# Prediksi Hujan di Australia

### Latar Belakang
Cuaca yang sulit diprediksi, khususnya hujan, memengaruhi banyak sektor seperti pertanian, transportasi, dan perencanaan perkotaan. Di Australia, perubahan cuaca yang ekstrem sering menyebabkan banjir atau kekeringan, berdampak pada kehidupan masyarakat dan aktivitas bisnis. Prediksi hujan sehari sebelumnya dapat membantu perencanaan yang lebih baik dalam berbagai bidang yang terdampak oleh kondisi cuaca.

### Mengapa dan Bagaimana Masalah Ini Harus Diselesaikan
Memecahkan masalah prediksi hujan harian penting karena:
1. Mengurangi risiko operasional dan biaya dalam sektor pertanian dan transportasi.
2. Meminimalkan dampak cuaca ekstrem dengan membantu masyarakat dan organisasi dalam membuat keputusan berdasarkan data.

Dengan memanfaatkan data historis cuaca, model pembelajaran mesin dapat dibangun untuk memprediksi apakah akan turun hujan keesokan harinya. Algoritma seperti *Random Forest*, *Logistic Regression*, atau *Gradient Boosting* dapat digunakan untuk melatih model ini. Teknik *feature engineering* yang relevan, seperti distribusi suhu, tekanan, dan kelembaban, penting untuk meningkatkan akurasi prediksi.

### Hasil Riset Terkait
Beberapa studi mendukung pendekatan ini:
- *Animas, A., et al.* (2022) menunjukkan bahwa algoritma seperti *Random Forest* dan *XGBoost* mampu mencapai akurasi prediksi hingga 80% untuk prediksi hujan harian.
- *Malathi Thangavel.* (2020) menekankan pentingnya pemilihan fitur yang tepat untuk meningkatkan akurasi dan mencegah overfitting pada data cuaca yang kompleks.

**Referensi:**
1. Animas, A., et al. (2022). "Rainfall prediction: A comparative analysis of modern machine learning algorithms for time-series forecasting."
2. Malathi Thangavel. (2020). "FEATURE SELECTION TECHNIQUES FOR WEATHER FORECASTING MODELS USING MACHINE LEARNING TECHNIQUES."


## Business Understanding

Perubahan cuaca yang ekstrem di Australia, khususnya hujan yang sulit diprediksi, mempengaruhi berbagai sektor yang bergantung pada kondisi cuaca, seperti pertanian, transportasi, dan infrastruktur. Ketidakpastian dalam pola hujan mengakibatkan risiko kerugian ekonomi dan keamanan, seperti banjir yang tiba-tiba dan kekeringan berkepanjangan. Mampu memprediksi hujan sehari sebelumnya akan membantu sektor-sektor ini dalam melakukan perencanaan yang lebih baik, mengurangi risiko, dan meningkatkan efisiensi.

Bagian laporan ini mencakup:

### Problem Statements

Menjelaskan pernyataan masalah latar belakang:
- **Bagaimana model prediksi dapat memberikan informasi yang akurat untuk mendukung perencanaan di sektor pertanian?**
- **Apakah prediksi hujan harian dapat mengurangi risiko dan meningkatkan keamanan dalam operasional transportasi dan infrastruktur?**
- **Seberapa efektif prediksi cuaca yang akurat dalam mendukung mitigasi bencana dan perencanaan perkotaan di Australia?**

### Goals

Menjelaskan tujuan dari pernyataan masalah:
- Mengurangi risiko kerugian dalam sektor pertanian melalui perencanaan penyiraman dan panen yang lebih baik.
- Meningkatkan keamanan dan efisiensi dalam sektor transportasi dan infrastruktur.
- Menyediakan informasi yang dapat diandalkan untuk perencanaan perkotaan dan mitigasi risiko bencana.

Semua poin di atas harus diuraikan dengan jelas. Anda bebas menuliskan berapa pernyataan masalah dan juga goals yang diinginkan.

### Solution Statement
Untuk mencapai tujuan di atas, beberapa solusi dapat diterapkan:

1. **Modeling dengan Algoritma Pembelajaran Mesin**
   - Menggunakan dua atau lebih algoritma untuk membangun model prediksi, seperti *Logistic Regression*, atau *Support Vector Machine*. Masing-masing algoritma memiliki kelebihan dalam menangani data cuaca yang kompleks, dan hasilnya dapat dibandingkan untuk memilih model terbaik.
   - Metrik evaluasi: Akurasi, Precision, Recall, dan F1-Score.

2. **Improvement pada Dataset dengan Metode Oversampling**
   - Mengatasi masalah ketidakseimbangan kelas dalam data menggunakan metode *oversampling* dengan *SMOTE (Synthetic Minority Over-sampling Technique)* dan *class_weight* pada model. *SMOTE* menghasilkan sampel baru dari kelas minoritas, sedangkan *class_weight* membantu model untuk lebih mempertimbangkan kelas yang kurang dominan. Kedua metode ini bertujuan meningkatkan kemampuan model dalam memprediksi kelas hujan yang langka.
   - Metrik evaluasi: Akurasi, Precision, Recall, dan F1-Score akan digunakan untuk mengevaluasi perbaikan kinerja model setelah penyeimbangan kelas.

Solusi ini diharapkan memberikan model prediksi yang akurat, dengan evaluasi berbasis metrik yang jelas sehingga performa model dapat terukur secara kuantitatif.

## Data Understanding
Dataset yang digunakan berasal dari kaggle bernama [Rain in Australia](https://www.kaggle.com/datasets/jsphyg/weather-dataset-rattle-package) yang berisikan kumpulan data ini terdiri dari sekitar 10 tahun pengamatan cuaca harian dari berbagai lokasi di seluruh Australia.

### Dataset ini berisi informasi seputar cuaca di Australia dengan kolom-kolom sebagai berikut:

1. **Date:** Tanggal pengamatan cuaca.
2. **Location:** Nama lokasi/tempat pengamatan cuaca.
3. **MinTemp:** Temperatur minimum pada hari itu (dalam derajat Celsius).
4. **MaxTemp:** Temperatur maksimum pada hari itu (dalam derajat Celsius).
5. **Rainfall:** Jumlah curah hujan dalam milimeter pada hari itu.
6. **Evaporation:** Penguapan air dari permukaan tanah dan tanaman pada hari itu (dalam milimeter).
7. **Sunshine:** Jumlah jam sinar matahari pada hari itu.
8. **WindGustDir:** Arah angin saat terjadi angin kencang.
9. **WindGustSpeed:** Kecepatan angin maksimum yang tercatat pada hari itu (dalam kilometer per jam).
10. **WindDir9am:** Arah angin pada pukul 9 pagi.
11. **WindDir3pm:** Arah angin pada pukul 3 sore.
12. **WindSpeed9am:** Kecepatan angin pada pukul 9 pagi (dalam kilometer per jam).
13. **WindSpeed3pm:** Kecepatan angin pada pukul 3 sore (dalam kilometer per jam).
14. **Humidity9am:** Kelembaban udara pada pukul 9 pagi (dalam persen).
15. **Humidity3pm:** Kelembaban udara pada pukul 3 sore (dalam persen).
16. **Pressure9am:** Tekanan udara pada pukul 9 pagi (dalam hectopascals).
17. **Pressure3pm:** Tekanan udara pada pukul 3 sore (dalam hectopascals).
18. **Cloud9am:** Jumlah awan pada pukul 9 pagi (dalam okta, 0-8).
19. **Cloud3pm:** Jumlah awan pada pukul 3 sore (dalam okta, 0-8).
20. **Temp9am:** Temperatur pada pukul 9 pagi (dalam derajat Celsius).
21. **Temp3pm:** Temperatur pada pukul 3 sore (dalam derajat Celsius).
22. **RainToday:** Apakah hujan terjadi hari ini (Yes/No).
23. **RainTomorrow:** Apakah diharapkan hujan besok (Yes/No).

### correlation matrix heatmap plot
Melihat apakah dari kolom yang ada terdapat korelasi antara kolom lain. ![Korelasi Matrik](/assets/KorelasiMatrik.png)

### Rainfall Over Time
Menganalisis tingkat curah hujan dari tahun 2008 hingga 2018. Dapat diilihat curah hujan selalu naik diawal tahun. ![Rainfall](/assets/Rainfall.png)

## Data Preparation
### Data Cleaning

1. **RainTomorrow**
    - Karena kolom ini adalah target untuk diprediksi maka nilai kosong yang ada pada kolom ini akan dihapus.

2. **Numeric Columns**
    - Membagi menjadi 3 cara yaitu imputasi menggunakan mean untuk distribusi normal, median untuk distribusi skewed dan random data untuk kolom `Cloud9am` dan `Cloud3pm`.
    - Kolom dipisah sesuai jenis distribusinya kecuali kolom `Cloud9am` dan `Cloud3pm`.
    - Membuat fungsi untuk masing-masing cara imputasinya.

3. **Object Columns**
    - Melakukan imputasi pada nilai `NaN` dengan cara mengisinya dengan mode.

4. **Correlation Columns**
    - Melihat kolom apakah memiliki korelasi terhadap kolom lainnya menggunakan Correlation matrix.

**NOTE:** <br>
Kolom yang memiliki distribusi Normal : `MinTemp`, `MaxTemp`, `WindGustSpeed`, `WindSpeed9am`, `WindSpeed3pm`, `Humidity3pm`, `Pressure9am`, `Pressure3pm`, `Cloud9am`, `Cloud3pm`, `Temp9am`, `Temp3pm`. <br><br>
Kolom yang memiliki distribusi skewed : `Rainfall`, `Evaporation` <br> <br>

#### Handling NaN Value
- Kolom dengan jenis object akan di imputasi dengan `mode`
- Kolom yang memiliki distribusi `Normal` akan di imputasi dengan `Mean`
- Kolom yang memiliki distribusi `Skewed` akan di imputasi dengan `Median`
- Khusus untuk kolom `Cloud9am` dan `Cloud3pm` akan di imputasi dengan `Random sample`

### Outlier Handling
1. **Inisialisasi Winsorizer untuk Distribusi Gaussian:**
   - `handling_outlier_gaussian`: Menggunakan Winsorizer dengan metode distribusi gaussian untuk beberapa kolom numerik tertentu.
   - `fold=3`: Menerapkan Winsorizing dengan menggantikan nilai outlier yang melebihi batas tiga kali deviasi standar.

2. **Handling Outlier dengan Distribusi Gaussian:**
   - Proses handling outlier dengan menggunakan Winsorizer pada distribusi gaussian.
   - Membuat boxplot sebelum dan setelah handling outlier untuk kolom 'Pressure3pm' sebagai contoh.

3. **Inisialisasi Winsorizer untuk Distribusi IQR:**
   - `handling_outlier_skewed`: Menggunakan Winsorizer dengan metode distribusi IQR (Interquartile Range) untuk beberapa kolom numerik tertentu.

4. **Handling Outlier dengan Distribusi IQR:**
   - Proses handling outlier dengan menggunakan Winsorizer pada distribusi IQR.
   - Membuat boxplot sebelum dan setelah handling outlier untuk kolom 'Rainfall' sebagai contoh.

### Encoding
1. **Menyimpan Nama Kolom Bertipe Objek:**
   - `object_columns = df_ho.select_dtypes(include='object').columns.tolist()`: Menyimpan nama kolom bertipe objek.

2. **Encoding Kolom Kategori menggunakan LabelEncoder:**
   - `label_encoder = LabelEncoder()`: Inisialisasi objek LabelEncoder.
   - Melakukan iterasi pada kolom-kolom bertipe objek dan melakukan encoding.
   - Menyimpan dataset yang sudah diencode ke dalam variabel `df_encoded`.

### Normalization
1. **Definisi Feature Matrix dan Target Variable:**
   - `fiture = df_encoded.drop(columns='RainTomorrow')`: Mengambil seluruh kolom kecuali 'RainTomorrow' sebagai feature matrix.
   - `target = df_encoded['RainTomorrow']`: Mengambil kolom 'RainTomorrow' sebagai target variable.

2. **Inisialisasi dan Scaling Data menggunakan RobustScaler:**
   - `fiture_scalar = RobustScaler()`: Inisialisasi objek RobustScaler untuk melakukan scaling data.

3. **Melakukan Scaling pada Data Fitur:**
   - `fiture_scalar.fit(fiture)`: Melakukan fitting pada data fitur untuk menghitung median dan IQR.
   - `scaled_fiture = fiture_scalar.transform(fiture)`: Melakukan scaling pada data fitur menggunakan RobustScaler.

4. **Konversi Hasil Scaling Menjadi DataFrame:**
   - `fiture = pd.DataFrame(scaled_fiture, columns=fiture.columns)`: Mengonversi hasil scaling menjadi DataFrame dengan nama kolom yang sesuai.

### Split Data
Ini bertanggung jawab untuk membagi dataset menjadi set pelatihan dan pengujian, langkah dasar dalam pengembangan model machine learning. Pembagian ini memungkinkan pelatihan dan evaluasi model pada set data yang berbeda.

- Fungsi `train_test_split` dari modul `sklearn.model_selection` digunakan untuk melakukan pembagian data. Fungsi ini memiliki parameter sebagai berikut:
   - `fiture`: Matriks fitur.
   - `target`: Variabel target.
   - `test_size`: Proporsi data yang dialokasikan untuk set pengujian. Dalam kasus ini, diatur menjadi 30% (0,3).
   - `random_state`: Seed untuk generator angka acak untuk memastikan reproduktibilitas.

### Alasan Menggunakan Tahapan Tersebut
1. **Handling Missing Values:**
   - Dilakukan pengecekan dan penanganan nilai yang hilang pada kolom-kolom tertentu, seperti menggunakan imputasi dengan mean, median, atau modus.
2. **Outlier Handling:**
   - Untuk menghandle outlier menggunakan winsorizer dengan foldnya 3.
   - Yang bertujuan untuk menjaga tetap adanya outlier dengan batas tertentu.
   - Yang bermaksud data cuaca memiliki rentan data yang mempunyai kelonjakan atau perubahan secara ekstrem contohnya seperti badai.

3. **Data Encoding:**
   - Data dibuat dari objek menjadi numerik menggunakan `LabelEncoder`.

4. **Data Normalisasi:**
   - Bertujuan untuk menyamakan skala data yang digunakan.

## Modeling
ini bertanggung jawab untuk mendefinisikan dan melatih dua model machine learning, yaitu Logistic Regression dan Support Vector Machine (SVM).

**Penjelasan Kode**:

1. **Logistic Regression Model**:
   - Model Logistic Regression dibuat menggunakan kelas `LogisticRegression` dari modul `sklearn.linear_model`.
   - Parameter yang digunakan:
     - `solver='liblinear'`: Algoritma solver yang digunakan untuk melatih model.
     - `C=0.001`: Kebalikan dari kekuatan regularisasi; nilai yang lebih rendah mengindikasikan regularisasi yang lebih kuat.
     - `random_state=42`: Seed untuk generator angka acak untuk memastikan reproduktibilitas.
     - `max_iter=100`: Jumlah iterasi maksimum dalam melatih model.

2. **Support Vector Machine (SVM) Model**:
   - Model SVM dibuat menggunakan kelas `SVC` dari modul `sklearn.svm`.
   - Parameter yang digunakan:
     - `kernel='linear'`: Jenis kernel yang digunakan, dalam hal ini, kernel linear.
     - `C=1.0`: Parameter ketegangan yang mengontrol tingkat toleransi terhadap kesalahan pelatihan.
     - `random_state=42`: Seed untuk generator angka acak untuk memastikan reproduktibilitas.
     - `gamma=0.1`: Parameter kernel SVM, gamma.

### **Kelebihan dan Kekurangan Algoritma yang Digunakan:**

- *Logistic Regression*:  
  Kelebihan: Efisien, cepat, dan mudah diinterpretasi, khususnya pada dataset linier.  
  Kekurangan: Tidak optimal untuk dataset yang kompleks atau tidak linier.

- *Support Vector Machine (SVM)*:  
  Kelebihan: Kuat dalam menangani dataset yang kompleks dan baik dalam memisahkan data pada batas kelas yang tidak linier.  
  Kekurangan: Membutuhkan waktu komputasi lebih tinggi pada dataset besar.

**Pemilihan Model Terbaik:**
Berdasarkan hasil evaluasi, *SVM* dipilih sebagai model terbaik karena memberikan akurasi yang lebih tinggi dibandingkan *Logistic Regression*. SVM juga lebih mampu memisahkan kelas secara efektif pada data yang kompleks seperti data cuaca.

### Improvement pada Data
Peningkatan akurasi model dilakukan dengan teknik penyeimbangan data menggunakan *SMOTE* dan *class_weight* pada model SVM:
- **SMOTE (Synthetic Minority Over-sampling Technique)**: Digunakan untuk menangani ketidakseimbangan kelas dengan membuat sampel sintetis dari kelas minoritas.
- **class_weight='balanced'**: Mengatur bobot kelas secara otomatis untuk memperhitungkan ketidakseimbangan, sehingga model lebih memperhatikan kelas yang kurang dominan.


## Evaluation
Pada bagian ini, kami menggunakan beberapa metrik evaluasi untuk menilai kinerja model prediksi hujan harian yang dibangun menggunakan algoritma *Support Vector Machine (SVM)* dan *Logistic Regression*. Evaluasi dilakukan berdasarkan metrik *Accuracy*, *Precision*, *Recall*, dan *F1-Score*, yang dipilih karena relevan dengan konteks klasifikasi biner dalam data cuaca yang tidak seimbang.

### Metrik Evaluasi yang Digunakan

1. **Accuracy**  
   Akurasi adalah proporsi prediksi yang benar dari seluruh prediksi. Akurasi dihitung dengan rumus:  
   `Accuracy = (True Positives + True Negatives) / Total Observations`

2. **Precision**  
   Precision mengukur akurasi prediksi positif dengan rumus:  
   `Precision = True Positives / (True Positives + False Positives)`

3. **Recall**  
   Recall mengukur kemampuan model dalam mendeteksi semua kejadian positif (hujan) dengan rumus:  
   `Recall = True Positives / (True Positives + False Negatives)`

4. **F1-Score**  
   F1-Score adalah rata-rata harmonik dari precision dan recall, yang memberikan keseimbangan di antara keduanya, khususnya berguna pada data yang tidak seimbang.  
   `F1-Score = 2 * (Precision * Recall) / (Precision + Recall)`


### Hasil Proyek Berdasarkan Metrik Evaluasi

Dari hasil evaluasi, model *Support Vector Machine (SVM)* menunjukkan performa terbaik dibandingkan dengan model *Logistic Regression* setelah dilakukan oversampling dengan *SMOTE* dan pengaturan *class_weight*. Berikut adalah hasil evaluasi berdasarkan metrik yang digunakan:
- **Akurasi**: Model SVM memiliki akurasi yang lebih tinggi dibanding Logistic Regression, mengindikasikan prediksi yang lebih akurat secara keseluruhan.
- **Precision dan Recall**: Model SVM memiliki precision yang tinggi, mengurangi risiko prediksi positif palsu, serta recall yang memadai, menangkap sebagian besar kasus hujan yang sebenarnya terjadi.
- **F1-Score**: Dengan nilai F1-Score yang lebih tinggi pada SVM, model ini berhasil mencapai keseimbangan antara precision dan recall, yang ideal untuk kasus prediksi hujan yang sensitif terhadap kesalahan positif dan negatif.

Secara keseluruhan, model SVM yang telah dioptimalkan dengan *SMOTE* dan *class_weight* menunjukkan kinerja terbaik untuk memprediksi kemungkinan hujan keesokan harinya dengan akurasi dan keseimbangan metrik yang sesuai.

