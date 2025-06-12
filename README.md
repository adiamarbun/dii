🧠 Predictive Analytics: Kualitas Appel 
--------------------------------------------

Disusun Oleh: ADISAPUTRA 

📌 Domain Proyek
Proyek ini berada dalam domain Pertanian, dengan fokus pada penerapan Machine Learning untuk memprediksi kualitas buah apel berdasarkan karakteristik visual dan sensorik.

📖 Latar Belakang
--------------------
![images](https://github.com/user-attachments/assets/ec090884-d8b4-47d9-a3d7-7bb6812bfee3)

Indonesia merupakan salah satu negara penghasil apel terbesar di Asia Tenggara, dengan produksi mencapai 1,2 juta ton per tahun. Apel menjadi komoditas penting dalam sektor pertanian dan memiliki kontribusi ekonomi signifikan.

Namun, penurunan kualitas apel akibat faktor seperti ukuran, kematangan, dan kerenyahan menjadi tantangan utama. Hal ini berdampak pada kerugian ekonomi bagi petani dan distributor, serta menurunkan kepuasan konsumen.

* Dengan memanfaatkan pendekatan Predictive Analytics, proyek ini bertujuan untuk:

* Meningkatkan efisiensi dan akurasi penilaian kualitas apel.

* Mendukung petani dan distributor dalam pengambilan keputusan berbasis data.

* Memberikan produk apel yang lebih konsisten dan berkualitas bagi konsumen.

💼 Business Understanding
----------------------------
Model prediksi kualitas apel berpotensi:

* Membantu petani memilah apel berkualitas tinggi untuk dipasarkan dengan harga lebih baik.

* Memfasilitasi distributor dalam proses sortasi dan pengelolaan rantai pasok.

* Meningkatkan kepercayaan konsumen dengan penyediaan produk berkualitas stabil.

❓ Problem Statements
------------------------
1. Bagaimana membangun model machine learning untuk memprediksi kualitas apel berdasarkan fitur visual dan sensorik?

2. Model machine learning apa yang memberikan akurasi prediksi terbaik?

3. Bagaimana model tersebut dapat memberikan dampak nyata bagi petani dan distributor?

🎯 Goals
----------
* Mengembangkan model prediksi kualitas apel menggunakan teknik machine learning.

* Membandingkan performa beberapa algoritma untuk mendapatkan model terbaik.

* Merancang solusi yang dapat digunakan secara praktis oleh pelaku industri pertanian.

💡 Solution Statements
-------------------------
Solusi dikembangkan melalui beberapa tahap:

Melakukan univariate dan multivariate analysis untuk memahami data secara mendalam.

Membersihkan data (data cleaning) dan mengatasi missing value serta outlier.

Mengembangkan berbagai model klasifikasi, seperti:

1. Random Forest: model ensemble berbasis decision tree.
2. Naive Bayes: klasifikasi probabilistik berdasarkan Teorema Bayes.
3. SVC: VC bekerja dengan mencari hyperplane yang memiliki jarak terbesar ke titik-titik data terdekat dari setiap kelas (titik-titik ini disebut "support vectors").

📊 Data Understanding
-------------------------
📄 Informasi Dataset
Dataset digunakan dari Apple Quality Dataset yang tersedia secara publik di Kaggle. Dataset ini berisi data primer dari perusahaan pertanian di Amerika.

| Kolom      | Deskripsi                    |
|------------|---------------------------------|
| Size	     | Ukuran apel                     |
| Weight	| Berat apel
| Sweetness | 	Tingkat kemanisan
| Crunchiness |	Tingkat kerenyahan
| Juiciness |	Tingkat berair
| Ripeness n| Tingkat kematangan
| Acidity	| Tingkat keasaman
| Quality	| Label kualitas (good atau bad)


Dataset yang digunakan dalam proyek ini merupakan data primer yang berasal dari sebuah perusahaan pertanian di Amerika Serikat. Dataset ini tersedia secara publik di platform Kaggle dengan nama Apple Quality Dataset.

Dataset ini berisi berbagai fitur yang mengukur karakteristik apel secara visual dan sensorik, serta label kualitasnya. Fitur-fitur tersebut telah melalui proses standardisasi sehingga nilai-nilainya berbentuk skala standar (mean 0 dan deviasi standar 1). 

![Screenshot 2025-06-12 231123](https://github.com/user-attachments/assets/1aedcff5-2ec9-4600-8f35-065c0052f704)

📊 Tabel 1. EDA Deskripsi Variabel
-----------------------------------
Berdasarkan hasil eksplorasi awal terhadap dataset Apple Quality, dapat disimpulkan bahwa dataset ini telah dibersihkan dan dinormalisasi oleh penyedia data. Hal ini menjadikan dataset sangat ideal dan ramah bagi pemula yang ingin melakukan eksperimen machine learning.

Informasi Umum Dataset:
* Format file: CSV (Comma-Separated Values)
* Jumlah sampel (baris): 4001
* Jumlah fitur (kolom): 9
* Tipe data:
* float64: 7 fitur
* object: 2 fitur

Terdapat 1 nilai kosong (missing value) dalam dataset.

🧾 Deskripsi Setiap Variabel:
----------------------------
| Variabel                  | 	Deskripsi                          -       |
| --------------------------| ---------------------------------------------|
| A_id	                    | Identifikasi unik untuk setiap buah apel     |
| Size                      |	Ukuran buah apel                             |
| Weight	                  | Berat buah apel                              | 
| Sweetness	                | Tingkat kemanisan buah apel
| Crunchiness	              | Tingkat kerenyahan tekstur buah apel
| Juiciness	                | Tingkat kesegaran atau berairnya buah apel
| Ripeness	                | Tahap kematangan buah apel
| Acidity	                  | Tingkat keasaman buah apel
| Quality	                  | Kualitas keseluruhan buah apel (baik = good, buruk = bad)


📈 EDA - Univariate Analysis
------------------------------
Analisis univariat dilakukan untuk memahami distribusi dari masing-masing variabel secara individu. Teknik visualisasi seperti histogram digunakan untuk melihat bentuk distribusi, mendeteksi outlier, dan memeriksa kemungkinan skewness dalam data.

![image](https://github.com/user-attachments/assets/93e74737-a12c-4806-994d-84585bb8d7dd)

Gambar 1a. Analisis Univariat (Data Numerik)

Pada gamabr 1a data numerik memiliki karakteristik, yaitu:

1. Size: Ukuran rata-rata buah berkisar dari -2 hingga 2, dengan nilai rata-rata (mean) sebesar -0.51.
2. Weight: Rata-rata berat apel adalah -0.99, sedangkan nilai maksimum berat mencapai 3.08.
3. Sweetness: Tingkat kemanisan apel memiliki rata-rata sebesar -0.48.
4. Crunchiness: Tekstur kerenyahan apel berkisar dari 0 hingga 2, yang menunjukkan bahwa rata-rata apel dalam dataset ini memiliki kerenyahan yang cukup baik.
5. Juiciness dan Ripeness: Tingkat kesegaran dan kematangan buah memiliki nilai rata-rata masing-masing sebesar 0.50 dan 0.53.
6. Acidity: Tingkat keasaman buah memiliki rata-rata sebesar 0.06.

Nilai-nilai tersebut menunjukkan bahwa seluruh data numerik telah dinormalisasi menggunakan metode z-score normalization. Metode ini bekerja dengan:


1. Mengurangi setiap nilai data dengan rata-rata (mean).
2. Membagi hasilnya dengan standar deviasi (standard deviation) dari data tersebut.

Sebagai contoh, meskipun nilai rata-rata fitur "Size" adalah -0.51, dengan sebaran dari -2 hingga 2, kita dapat mengasumsikan bahwa data telah diubah skalanya sehingga menyerupai distribusi dengan mean mendekati nol dan standar deviasi satu. Fitur numerik lainnya, seperti "Weight", "Sweetness", "Crunchiness", "Juiciness", "Ripeness", dan "Acidity", juga menunjukkan pola distribusi yang serupa dan mengindikasikan telah dinormalisasi dengan teknik yang sama.

EDA - Multivariate Analysis

![image](https://github.com/user-attachments/assets/a258a44f-4b24-4ed5-b017-898bf3e6fb2d)

Gambar 2a. 📈 Pairplot 

* Pairplot menampilkan hubungan antar fitur numerik melalui scatter plot dan distribusi univariat (diagonal).

* Secara umum, sebagian besar fitur tidak menunjukkan pola hubungan linear yang kuat, yang terlihat dari sebaran titik yang menyebar acak.

* Tidak ada multikolinearitas mencolok, karena tidak ada pasangan fitur yang memiliki scatter plot membentuk garis lurus atau pola jelas.

* Distribusi pada diagonal menunjukkan data telah dinormalisasi (mengikuti sebaran normal standar).


![image](https://github.com/user-attachments/assets/6c926426-a18d-4b36-9b4a-144a36b544c8)

Gambar 2b. 🔥 Heatmap Korelasi 

Heatmap korelasi menampilkan hubungan linear antar fitur dalam bentuk nilai korelasi Pearson:
* Nilai berkisar dari -1 (negatif sempurna) hingga 1 (positif sempurna).
* Warna merah = korelasi positif, biru = korelasi negatif, putih = hampir tidak berkorelasi.

Insight utama dari heatmap:

Korelasi negatif sedang antara:
* Size dan Sweetness (-0.34) → semakin besar ukuran, cenderung kurang manis.
* Sweetness dan Ripeness (-0.27) → kemungkinan buah matang tidak selalu manis.

Korelasi positif sedang antara:
* Juiciness dan Acidity (0.24) → buah yang lebih juicy cenderung lebih asam.
* Size dan Acidity (0.18) → ukuran buah sedikit berbanding lurus dengan tingkat keasaman.

Selebihnya, korelasi antar fitur sangat lemah hingga hampir tidak ada korelasi.

🧹 Data Preparation
-----------------------
Dalam tahap Data Preparation, dilakukan beberapa langkah penting untuk memastikan kualitas dan kesiapan data sebelum digunakan dalam proses pemodelan. Tahapan ini mencakup tiga proses utama: Data Gathering, Data Assessing, dan Data Cleaning.

1. 📥 Data Gathering
Data dikumpulkan dan diimpor ke dalam lingkungan kerja menggunakan pustaka Pandas, kemudian disusun dalam bentuk DataFrame agar mudah dianalisis dan diolah. Proses ini memastikan bahwa data dapat dibaca dan digunakan dengan baik oleh alat-alat analisis selanjutnya.

2. 🔍 Data Assessing
Pada tahap ini, dilakukan evaluasi menyeluruh terhadap kualitas dan integritas data. Beberapa pengecekan penting yang dilakukan meliputi:
* Duplicate Data: Mengidentifikasi dan menghapus baris data yang duplikat agar tidak memengaruhi hasil analisis.
* Missing Values: Mengecek adanya nilai yang hilang atau tidak tersedia, lalu diputuskan penanganannya (diisi, dihapus, atau ditandai).
* Outlier Detection: Mendeteksi nilai-nilai ekstrem yang menyimpang jauh dari distribusi umum data menggunakan teknik statistik seperti IQR atau z-score.

3. 🧽 Data Cleaning
Setelah proses asesmen, dilakukan pembersihan data untuk memastikan data dalam kondisi optimal. Proses yang dilakukan antara lain:
* Converting Column Types: Mengubah tipe data kolom agar sesuai dengan kebutuhan analisis (misalnya dari objek ke numerik atau sebaliknya).
* Train-Test Split: Membagi dataset menjadi data latih dan data uji guna menghindari overfitting dan memastikan evaluasi model yang adil.
* Normalization: Melakukan normalisasi data, khususnya menggunakan metode z-score normalization, agar setiap fitur memiliki skala yang sebanding (mean = 0 dan standar deviasi = 1), sehingga model tidak bias terhadap fitur dengan skala besar.

![image](https://github.com/user-attachments/assets/6a8e51e8-e623-4bda-88e9-5ad3330017ef)

Tabel data missing value

🔍 Modeling
-------------
1. Random Forest 
Random Forest adalah algoritma ensemble learning yang membentuk hutan dari banyak pohon keputusan (decision trees) dan menggabungkan hasil prediksi dari setiap pohon untuk meningkatkan akurasi dan menghindari overfitting.

Keuntungan Random Forest:
* Memiliki akurasi tinggi dan tahan terhadap overfitting.
* Dapat menangani data dengan fitur dalam jumlah besar.
* Dapat digunakan untuk data kategorik maupun numerik.

Kelemahan Random Forest:
* Modelnya sulit diinterpretasikan secara langsung.
* Waktu pelatihan bisa lebih lama dibanding model lain, terutama dengan banyak pohon.

2. Support Vector Classifier (SVC)
SVC adalah algoritma klasifikasi yang bekerja dengan mencari hyperplane terbaik yang memisahkan data dari berbagai kelas dengan margin maksimum. Cocok digunakan pada dataset yang memiliki dimensi tinggi.

Keuntungan SVC:

* Efektif pada dataset berdimensi tinggi.Dapat digunakan untuk kasus linear maupun non-linear (dengan kernel trick).
* Memiliki generalisasi yang baik pada data yang belum pernah dilihat.

Kelemahan SVC:
* Kurang efisien pada dataset yang sangat besar.
* Pemilihan kernel yang kurang tepat dapat menurunkan performa.
* Parameter tuning (seperti C dan gamma) cukup sensitif.

3. Naïve Bayes
Naïve Bayes adalah metode klasifikasi berbasis probabilitas yang menggunakan Teorema Bayes. Algoritma ini mengasumsikan bahwa setiap fitur saling independen satu sama lain terhadap kelas target.

Keuntungan Naïve Bayes:
* Sederhana dan mudah diimplementasikan.
* Cepat dalam proses pelatihan dan prediksi.\Efektif untuk dataset berukuran besar dan real-time prediction.

Kelemahan Naïve Bayes:
* Asumsi independensi antar fitur sering kali tidak terpenuhi dalam data nyata.
* Rentan terhadap fitur yang memiliki nilai nol (zero frequency problem).
* Akurasinya bisa menurun pada dataset yang sangat kompleks atau tidak seimbang.


✅ Evaluation
---------------
Pada tahap evaluasi model, metrik utama yang digunakan adalah accuracy. Metrik ini mengukur seberapa sering model melakukan prediksi yang benar terhadap seluruh data uji. Rumus yang digunakan untuk menghitung accuracy adalah sebagai berikut:

                  ![image](https://github.com/user-attachments/assets/51bb3f0b-4e1f-49a5-8afa-3e64c0ad529e)

Penjelasan masing-masing komponen:

* TP (True Positive): Jumlah data aktual positif yang diprediksi dengan benar sebagai positif.
* TN (True Negative): Jumlah data aktual negatif yang diprediksi dengan benar sebagai negatif.
* FP (False Positive): Jumlah data aktual negatif yang secara salah diprediksi sebagai positif (disebut juga kesalahan tipe I).
* FN (False Negative): Jumlah data aktual positif yang secara salah diprediksi sebagai negatif (disebut juga kesalahan tipe II).

Dengan menggunakan rumus ini, kita dapat mengetahui seberapa akurat model dalam mengklasifikasikan data dengan benar. Nilai accuracy dihitung dalam bentuk persentase agar lebih mudah dipahami dan dibandingkan antar model.

| Model       | Accuary   |
| ----------- | ----------| 
| RandomForest| 0.89      |
| Naive Bayes | 0.49      |
| SVC         | 0.89      |

Tabel Hasil Accuracy 


![image](https://github.com/user-attachments/assets/e111fe66-f044-4802-88cd-dcc0bf0b60ef)

📊 Gambar Visualisasi Akurasi Model

Berdasarkan hasil yang ditunjukkan pada Gambar 3, dapat terlihat bahwa model Random Forest dan Support Vector Classifier (SVC) memiliki tingkat akurasi yang cukup tinggi dan hampir setara, masing-masing mencapai sekitar 90%. Sementara itu, model Naive Bayes memiliki performa yang jauh lebih rendah dengan akurasi hanya sekitar 50%.

Dari ketiga model yang diuji, Random Forest dan SVC merupakan kandidat terbaik karena mampu memberikan hasil klasifikasi yang lebih akurat. Di antara keduanya, model Random Forest sedikit lebih unggul dalam akurasi dan cenderung lebih stabil dalam menghadapi data yang kompleks.

Oleh karena itu, model Random Forest dipilih sebagai model utama untuk melakukan prediksi kualitas apel. Model ini dinilai efektif karena mampu menangani variabel dengan hubungan yang kompleks, memiliki toleransi terhadap outlier, dan juga dapat mengatasi overfitting dengan lebih baik dibandingkan model lainnya.

📘 Referensi 

1. Wood, T. (n.d.). What is a Random Forest? DeepAI. https://deepai.org/machine-learning-glossary-and-terms/random-forest

2. Gandhi, R. (2018). Support Vector Machine — Introduction to Machine Learning Algorithms: SVM model from scratch. Towards Data Science. https://towardsdatascience.com/support-vector-machine-introduction-to-machine-learning-algorithms-934a444fca47

3. Gandhi, R. (2018). Naive Bayes Classifier. Towards Data Science. https://towardsdatascience.com/naive-bayes-classifier-81d512f50a7c

4. Brownlee, J. (2016). Data Preparation for Machine Learning. Machine Learning Mastery. https://machinelearningmastery.com/data-preparation-for-machine-learning/

5. Chawla, N. V., Japkowicz, N., & Kotcz, A. (2004). Editorial: Special issue on learning from imbalanced data sets. SIGKDD Explorations, 6(1), 1–6. https://doi.org/10.1145/1007730.1007733
