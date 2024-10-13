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

### Problem Statements

- **Bagaimana model prediksi dapat memberikan informasi yang akurat untuk mendukung perencanaan di sektor pertanian?**
- **Apakah prediksi hujan harian dapat mengurangi risiko dan meningkatkan keamanan dalam operasional transportasi dan infrastruktur?**
- **Seberapa efektif prediksi cuaca yang akurat dalam mendukung mitigasi bencana dan perencanaan perkotaan di Australia?**

### Goals

- Mengurangi risiko kerugian dalam sektor pertanian melalui perencanaan penyiraman dan panen yang lebih baik.
- Meningkatkan keamanan dan efisiensi dalam sektor transportasi dan infrastruktur.
- Menyediakan informasi yang dapat diandalkan untuk perencanaan perkotaan dan mitigasi risiko bencana.

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

Data yang digunakan memliki ukuran **145460, 23**. Terdapat kolom yang berisikan nilai `null` atau `kosong`, Berikut ini adalah jumlah nilai kosong (*missing values*) pada setiap kolom dalam dataset:

| Column          | Missing Values |
|-----------------|----------------|
| Date            | 0              |
| Location        | 0              |
| MinTemp         | 1,485          |
| MaxTemp         | 1,261          |
| Rainfall        | 3,261          |
| Evaporation     | 62,790         |
| Sunshine        | 69,835         |
| WindGustDir     | 10,326         |
| WindGustSpeed   | 10,263         |
| WindDir9am      | 10,566         |
| WindDir3pm      | 4,228          |
| WindSpeed9am    | 1,767          |
| WindSpeed3pm    | 3,062          |
| Humidity9am     | 2,654          |
| Humidity3pm     | 4,507          |
| Pressure9am     | 15,065         |
| Pressure3pm     | 15,028         |
| Cloud9am        | 55,888         |
| Cloud3pm        | 59,358         |
| Temp9am         | 1,767          |
| Temp3pm         | 3,609          |
| RainToday       | 3,261          |
| RainTomorrow    | 3,267          |

Dataset ini memiliki nilai kosong yang signifikan pada beberapa kolom seperti *Evaporation*, *Sunshine*, *Cloud9am*, dan *Cloud3pm*, yang mungkin memerlukan penanganan lebih lanjut seperti imputasi atau penghapusan baris/kolom tergantung pada strategi pengolahan data yang diinginkan.

### correlation matrix heatmap plot
Melihat apakah dari kolom yang ada terdapat korelasi antara kolom lain. ![Korelasi Matrik](/assets/KorelasiMatrik.png)

### Rainfall Over Time
Menganalisis tingkat curah hujan dari tahun 2008 hingga 2018. Dapat diilihat curah hujan selalu naik diawal tahun. ![Rainfall](/assets/Rainfall.png)

## Data Preparation
Pada bagian ini, dijelaskan tahapan-tahapan persiapan data yang dilakukan untuk memastikan data siap digunakan dalam proses pemodelan. Berikut adalah tahapan lengkap dalam *Data Preparation*:

### 1. Data Cleaning
   - **Proses**: Mengatasi nilai kosong (*missing values*) pada dataset. Kolom dengan nilai kosong diisi menggunakan teknik imputasi, seperti mengganti nilai kosong pada kolom numerik dengan nilai median atau rata-rata, dan nilai modus untuk kolom kategorikal.
   - **Alasan**: Mengisi nilai kosong penting untuk menghindari gangguan pada proses pemodelan, karena beberapa algoritma tidak dapat bekerja dengan nilai kosong. Dengan mengatasi *missing values*, data menjadi lebih lengkap dan lebih representatif.

### 2. Outlier Handling dengan Winsorizer
   - **Proses**: Menggunakan teknik *Winsorizing* untuk mengatasi *outliers* pada data numerik. Nilai ekstrem pada ujung distribusi diubah menjadi nilai persentil tertentu (misalnya, 1% dan 99%) agar tidak terlalu memengaruhi model.
   - **Alasan**: Outlier dapat menyebabkan model menjadi kurang akurat, terutama dalam algoritma yang sensitif terhadap nilai ekstrem. Dengan *winsorizing*, distribusi data lebih stabil, dan model dapat belajar dari data dengan lebih efektif.

### 3. Encoding dengan Label Encoder
   - **Proses**: Menggunakan *Label Encoding* untuk mengubah kolom kategorikal menjadi nilai numerik. Kolom seperti `Location` dan `WindGustDir` diubah menjadi label numerik agar model dapat memprosesnya.
   - **Alasan**: Algoritma machine learning tidak bisa bekerja dengan data non-numerik, sehingga encoding diperlukan untuk mengonversi data kategorikal ke dalam bentuk yang bisa dimengerti oleh model.

### 4. Normalization dengan RobustScaler
   - **Proses**: Menerapkan *RobustScaler* untuk menormalkan data numerik dengan mengurangi nilai median dan membaginya dengan IQR (Interquartile Range). Ini membantu dalam menstabilkan distribusi data tanpa terpengaruh oleh outliers.
   - **Alasan**: Normalisasi diperlukan agar semua fitur berada pada skala yang sama, terutama untuk algoritma yang sensitif terhadap perbedaan skala fitur. RobustScaler dipilih karena lebih tahan terhadap outliers dibandingkan scaler lainnya.

### 5. Split Data (70:30)
   - **Proses**: Memisahkan data menjadi data latih (*train*) dan data uji (*test*) dengan perbandingan 70:30. Data latih digunakan untuk melatih model, sedangkan data uji digunakan untuk mengevaluasi performa model.
   - **Alasan**: Split data diperlukan untuk memastikan model tidak hanya belajar dari data latih, tetapi juga mampu bekerja dengan baik pada data baru yang belum pernah dilihat sebelumnya. Pembagian ini juga membantu mengevaluasi generalisasi model pada data uji.
   
Setiap tahapan di atas dilakukan secara berurutan untuk memastikan data siap digunakan dalam proses pemodelan.

## Modeling
Bagian ini menjelaskan proses definisi dan pelatihan dua model machine learning untuk memprediksi kemungkinan hujan, yaitu Logistic Regression dan Support Vector Machine (SVM). Berikut adalah penjelasan masing-masing model beserta parameter yang digunakan:

### 1. Logistic Regression Model
   - **Cara Kerja**: Logistic Regression adalah algoritma klasifikasi linier yang digunakan untuk memperkirakan probabilitas suatu data termasuk dalam kategori tertentu (hujan/tidak hujan). Algoritma ini menggunakan fungsi logistik atau sigmoid untuk memetakan nilai output ke dalam rentang 0 hingga 1. Logistic Regression cocok untuk kasus klasifikasi biner seperti ini.
   - **Parameter yang Digunakan**:
     - `solver='liblinear'`: Solver ini cocok untuk dataset kecil hingga menengah, khususnya untuk klasifikasi biner.
     - `C=0.001`: Nilai regularisasi yang lebih rendah (kekuatan regularisasi yang lebih besar), bertujuan untuk mencegah *overfitting*.
     - `random_state=42`: Seed untuk memastikan hasil eksperimen konsisten.
     - `max_iter=100`: Batas maksimum iterasi untuk konvergensi model.
  
### 2. Support Vector Machine (SVM) Model
   - **Cara Kerja**: SVM bekerja dengan mencari garis batas terbaik (hyperplane) yang memisahkan dua kelas dengan margin maksimal. SVM sangat kuat dalam menangani data yang memiliki batasan kelas yang tidak linier dan cocok untuk kasus klasifikasi pada data yang kompleks seperti data cuaca. Dengan memilih kernel linear, SVM berusaha memaksimalkan jarak antara dua kelas pada ruang fitur.
   - **Parameter yang Digunakan**:
     - `kernel='linear'`: Kernel linear dipilih karena sering efektif pada data yang distribusinya dapat dipisahkan secara linear.
     - `C=1.0`: Parameter ini mengontrol keseimbangan antara memaksimalkan margin dan meminimalkan kesalahan klasifikasi.
     - `random_state=42`: Seed untuk memastikan hasil yang konsisten.
     - `gamma=0.1`: Parameter yang mengontrol ukuran *influence* dari contoh tunggal. Gamma rendah berarti radius pengaruh besar, gamma tinggi berarti radius pengaruh kecil.

### **Kelebihan dan Kekurangan Algoritma yang Digunakan**

- **Logistic Regression**:
   - **Kelebihan**: Efisien, cepat dalam pelatihan, dan mudah diinterpretasi karena model linier. Logistic Regression cenderung bekerja baik pada data yang dapat dipisahkan secara linier.
   - **Kekurangan**: Kurang optimal pada data yang tidak memiliki pola linier atau data dengan interaksi kompleks.

- **Support Vector Machine (SVM)**:
   - **Kelebihan**: Sangat baik dalam memisahkan data pada batas kelas yang kompleks dan menangani data yang tidak linier.
   - **Kekurangan**: Membutuhkan lebih banyak komputasi pada dataset besar dan waktu pelatihan lebih lama dibandingkan Logistic Regression.

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


## Hasil Evaluasi dan Pembahasan Terhadap Problem Statement dan Goals Proyek

### Hasil Proyek Berdasarkan Metrik Evaluasi
Berdasarkan hasil evaluasi performa kedua model, yaitu Support Vector Machine (SVM) dan Logistic Regression (LR), berikut adalah ringkasan skor akurasi dan metrik evaluasi lainnya dari masing-masing model setelah dilakukan oversampling menggunakan SMOTE serta pengaturan class_weight:

| Model          | Oversampling | class_weight | Akurasi Training | Akurasi Uji | Precision (0) | Recall (0) | F1-score (0) | Precision (1) | Recall (1) | F1-score (1) |
|----------------|--------------|--------------|-------------------|-------------|---------------|------------|--------------|---------------|------------|--------------|
| SVM            | SMOTE        | Balanced     | 0.787            | 0.786       | 0.92          | 0.80       | 0.85         | 0.51          | 0.75       | 0.61         |
| Logistic Reg.  | SMOTE        | Balanced     | 0.785            | 0.783       | 0.92          | 0.79       | 0.85         | 0.51          | 0.75       | 0.61         |

### Pembahasan Goal Utama Berdasarkan Hasil Prediksi
Model SVM menunjukkan performa lebih unggul dibandingkan Logistic Regression, terutama setelah dioptimalkan dengan oversampling menggunakan SMOTE dan pengaturan class_weight. Berdasarkan hasil ini, model SVM dapat dipilih sebagai model final untuk mendukung kebutuhan prediksi cuaca yang akurat. Berikut adalah pembahasan hasil model dalam konteks tujuan proyek dan relevansi untuk mendukung operasional transportasi, infrastruktur, mitigasi bencana, dan perencanaan perkotaan:

1. **Apakah prediksi hujan harian dapat mengurangi risiko dan meningkatkan keamanan dalam operasional transportasi dan infrastruktur?**
   - Dengan precision yang lebih tinggi (0.92) pada kelas negatif (tidak hujan), model SVM dapat mengurangi risiko prediksi positif palsu yang tidak akurat, yang berarti sistem tidak perlu memberikan peringatan atau penjadwalan ulang transportasi jika tidak diperlukan.
   - Recall yang relatif tinggi pada kelas positif (hujan) menunjukkan bahwa model dapat mengidentifikasi mayoritas situasi hujan yang sebenarnya, sehingga prediksi ini dapat digunakan sebagai bagian dari mitigasi risiko untuk pengaturan operasional transportasi yang aman.

2. **Seberapa efektif prediksi cuaca yang akurat dalam mendukung mitigasi bencana dan perencanaan perkotaan di Australia?**
   - Dengan akurasi 0.79 dan F1-score pada kelas hujan sebesar 0.61, model dapat membantu pemerintah lokal dan badan terkait dalam mengambil keputusan mitigasi bencana yang lebih proaktif. Keseimbangan antara recall dan precision ini menunjukkan bahwa prediksi cuaca dapat memberi gambaran yang memadai mengenai kemungkinan hujan, mendukung kesiapsiagaan bencana banjir, serta memberi masukan pada pengelolaan drainase dan pembangunan fasilitas publik.
   - Precision tinggi pada prediksi tidak hujan juga mendukung perencanaan perkotaan di mana kegiatan konstruksi dan pengelolaan infrastruktur dapat direncanakan dengan lebih efisien, meminimalkan gangguan yang tidak perlu karena peringatan cuaca yang kurang akurat.

3. **Goal Proyek Secara Keseluruhan**
   - Dengan ketepatan prediksi cuaca yang ditunjukkan oleh model SVM, proyek ini berhasil mencapai tujuannya untuk memberikan prediksi cuaca yang andal sebagai alat bantu dalam operasional transportasi, perencanaan perkotaan, dan mitigasi risiko cuaca di Australia. Model ini memberikan keseimbangan performa yang cukup baik untuk memenuhi tujuan tersebut, meskipun performa pada kelas positif (hujan) masih bisa ditingkatkan dengan eksplorasi fitur lebih lanjut atau tuning tambahan untuk skenario cuaca ekstrem.

Kesimpulannya, model SVM yang dioptimalkan ini telah mencapai sebagian besar tujuan proyek dengan hasil yang cukup memadai, khususnya dalam mendukung operasional transportasi dan mitigasi bencana berbasis prediksi cuaca. Ke depannya, pengembangan lebih lanjut dapat difokuskan untuk meningkatkan recall pada kelas hujan, memastikan prediksi lebih akurat pada kondisi cuaca yang lebih sulit diidentifikasi.


