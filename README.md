Laporan Proyek Machine Learning Terapan 
Disusun oleh: Adisaputra

Ini adalah proyek akhir sistem rekomendasi untuk memenuhi submission dicoding. Proyek ini membangun model berbasis content based filtering yang dapat menentukan top-N rekomendasi anime dan model K-Nearest Neighbor.

![image](https://github.com/user-attachments/assets/7a8d158b-d79a-4704-b3d2-c1f8ec1fce18)

Project Overview
-----------------------
Anime, animasi khas Jepang yang digemari banyak orang dari berbagai kalangan usia, kini tersedia di berbagai platform streaming seperti Netflix, Crunchyroll, dan lainnya. Namun, banyaknya pilihan anime yang tersedia justru membuat sebagian pengguna merasa kewalahan dalam menentukan pilihan tontonan yang sesuai dengan preferensi mereka. Untuk mengatasi permasalahan ini, penelitian ini mengusulkan penerapan sistem rekomendasi berbasis teknologi kecerdasan buatan.
Sistem rekomendasi ini dirancang untuk menganalisis riwayat tontonan pengguna, genre favorit, serta rating yang diberikan pada anime sebelumnya. Dengan pendekatan ini, sistem dapat memberikan saran tontonan yang lebih relevan dan personal. Selain itu, sistem juga mempertimbangkan faktor lain seperti tingkat popularitas suatu anime, ulasan dari pengguna lain, serta rekomendasi yang muncul dalam komunitas pecinta anime, sehingga hasil rekomendasi menjadi lebih akurat dan sesuai kebutuhan pengguna.
Manfaat dari sistem ini sangat signifikan, baik bagi pengguna maupun penyedia layanan streaming. Bagi pengguna, sistem ini dapat membantu mereka menemukan anime baru yang menarik, mengeksplorasi genre yang belum pernah ditonton sebelumnya, hingga menyesuaikan pilihan tontonan berdasarkan suasana hati. Di sisi lain, perusahaan penyedia layanan dapat memanfaatkan sistem ini untuk meningkatkan jumlah penonton, memperluas cakupan distribusi konten, meningkatkan kepuasan pelanggan, dan memperoleh wawasan lebih dalam tentang preferensi pengguna terkait anime yang paling diminati.
Singkatnya, sistem rekomendasi anime berbasis data ini tidak hanya menjadi solusi praktis dalam membantu pengguna menemukan tontonan yang sesuai selera, tetapi juga memberikan nilai tambah dalam meningkatkan pengalaman menonton secara menyeluruh. Sistem ini menjadi jembatan antara keberagaman konten anime dengan kebutuhan unik setiap individu pengguna.

Business Understanding 
------------------------
Pengembangan sistem rekomendasi anime memiliki potensi strategis yang besar dalam industri hiburan digital, khususnya platform streaming anime. Di tengah pertumbuhan jumlah konten anime yang sangat cepat, pengguna sering mengalami kesulitan dalam memilih tontonan yang sesuai dengan preferensi mereka. Dalam konteks ini, sistem rekomendasi hadir sebagai solusi yang dapat memberikan pengalaman pengguna yang lebih personal, efisien, dan memuaskan.
Dari sisi pengguna, sistem ini memungkinkan mereka menemukan anime yang sesuai dengan minat dan kebiasaan menonton secara lebih cepat dan akurat. Dengan mengandalkan data riwayat tontonan, genre favorit, rating yang diberikan, dan interaksi lain, sistem ini mampu menyajikan daftar rekomendasi yang relevan dan disesuaikan secara individual. Hal ini tidak hanya meningkatkan kepuasan pengguna, tetapi juga memperkaya pengalaman menonton secara keseluruhan.
Sementara dari sisi bisnis, sistem rekomendasi memainkan peran penting dalam meningkatkan user engagement dan retensi pengguna. Platform streaming dapat mengurangi tingkat churn (penghentian langganan), meningkatkan waktu tonton rata-rata pengguna, serta mendorong eksplorasi konten yang lebih luas. Selain itu, data dari sistem ini dapat dimanfaatkan untuk memahami tren penonton, menyusun strategi pemasaran, serta merancang konten baru yang sesuai dengan permintaan pasar. 

Problem Statements
----------------------
* Dengan menggunakan data rating yang dimiliki pengguna, bagaimana perusahaan jasa streaming dapat merekomendasikan anime yang belum pernah ditonton pengguna?
* Bagaimanna cara mengukur nilai perfoma model sistem rekomendasi yang telah dibangun?
* Bagaimana cara membuat sistem rekomendasi anime yang merekomendasikan pengguna berdasarkan genre anime?
* Bagimana membuat model sistem rekomendasi Cosine Similarity dan K-Nearest Neighbor?

Goals
-------
1. Mengukur perfoma model sistem rekomendasi dengan menggunakan metrik evaluasi
2. Menghasilkan rekomendasi anime sebanyak Top-N Rekomendasi kepada pengguna berdasarkan genre.
3. Menghasilkan beberapa rekomendasi anime yang sesuai dengan preferensi pengguna dan belum pernah ditonton.
4. Untuk menjawab permasalahan tersebut dibuatlah sistem rekomendasi dengan tujuan sebagai berikut:
5. Membuat model sistem rekomendasi Cosine Similarity dan K-Nearest Neighbor berdasarkan fitur yang telah dipilih dari dataset

Solution Approach
-------------------
Pendekatan solusi dalam membangun sistem rekomendasi anime dimulai dengan menganalisis data melalui proses Exploratory Data Analysis (EDA). Proses ini dilakukan untuk memahami pola, distribusi, dan hubungan antar variabel dalam dataset, serta untuk mengidentifikasi potensi permasalahan pada data. Setelah itu, dilakukan pembersihan data atau data cleaning untuk memastikan data yang digunakan memiliki kualitas yang baik. Tahapan ini mencakup penghapusan nilai kosong (missing value), pemeriksaan dan penghapusan data duplikat, serta pembersihan data teks dari karakter alfanumerik yang tidak relevan, tanda baca, dan tautan (URL) yang tidak memberikan informasi penting terhadap konten.

Selanjutnya, data kategorikal seperti genre atau tipe anime dikonversi menjadi data numerik menggunakan teknik One-Hot Encoding. Konversi ini bertujuan agar algoritma pembelajaran mesin dapat memproses data tersebut dengan optimal. Setelah data dipersiapkan sepenuhnya, proses pelatihan model rekomendasi dilakukan dengan menggunakan algoritma yang sesuai, tergantung pada pendekatan yang digunakan, misalnya clustering, content-based filtering, atau collaborative filtering.

Untuk mengevaluasi performa dari model rekomendasi yang dibangun, digunakan beberapa metrik evaluasi seperti Precision, Calinski-Harabasz Score, dan Davies-Bouldin Score. Precision digunakan untuk mengukur relevansi rekomendasi yang diberikan kepada pengguna, sedangkan Calinski-Harabasz Score dan Davies-Bouldin Score digunakan untuk mengevaluasi kualitas dan keakuratan hasil clustering dalam pendekatan berbasis kelompok. Melalui pendekatan ini, diharapkan sistem rekomendasi yang dibangun mampu memberikan hasil yang relevan dan personal sesuai preferensi pengguna, serta meningkatkan pengalaman menonton secara keseluruhan.

Data Understanding 
-------------------------
Dalam proyek ini, data yang digunakan berasal dari dataset berjudul Anime Dataset 2023 yang tersedia secara publik di platform Kaggle. Dataset ini dikelola oleh pengguna bernama Sajid dan dilisensikan dengan ketentuan Open Database License. Dataset ini bersifat terbuka dan ditujukan untuk keperluan publik, dengan fokus pada topik seni dan hiburan, khususnya dalam kategori film, acara televisi, anime, manga, dan budaya populer Jepang. Dataset ini berasal dari MyAnimeList, sebuah platform komunitas online yang populer dan berfungsi sebagai basis data bagi para penggemar anime dan manga. Platform tersebut menyediakan informasi lengkap tentang berbagai judul anime, termasuk skor dan ulasan dari pengguna.

Secara keseluruhan, dataset ini tersedia dalam enam file berformat CSV (Comma-Separated Values), yaitu: anime-dataset-2023.csv, anime-filtered.csv, final_animedataset.csv, user-filtered.csv, users-details-2023.csv, dan users-score-2023.csv. Namun, dalam pengembangan model pada proyek ini, hanya digunakan file anime-filtered.csv.

File anime-filtered.csv berisi 14.952 sampel data dengan total 25 fitur. Dari keseluruhan fitur tersebut, terdapat 15 fitur bertipe object, 8 fitur bertipe int64, dan 2 fitur bertipe float64. Dalam analisis awal melalui Exploratory Data Analysis (EDA), ditemukan bahwa terdapat nilai kosong (missing values) pada fitur synopsis sebanyak 1.350 dan pada fitur ranked sebanyak 1.721. Selain itu, tidak ditemukan adanya data yang bersifat duplikat dalam dataset ini, sehingga data dapat langsung digunakan setelah melalui proses pembersihan lanjutan.

Variable pada dataset 
---------------------------

Kolom datasets anime memiliki informasi berikut:

* anime_id: ID unik untuk setiap anime (angka atau kode pengenal).
* Name: Judul anime dalam bahasa aslinya.
* Score: Skor atau rating yang diberikan kepada anime.
* Genres: Genre anime, dipisahkan dengan koma (misalnya, Aksi, Komedi, Fantasi).
* English name: Judul anime dalam bahasa Inggris (jika tersedia).
* Japanese name: Judul anime dalam bahasa Jepang (jika tersedia).
* Synopsis: Deskripsi singkat atau ringkasan plot anime.
* Type: Jenis anime (misalnya, TV Series, Movie, OVA, dll.).
* Episodes: Jumlah episode dalam anime.
* Aired: Tanggal penayangan anime.
* Premiered: Musim dan tahun penayangan perdana anime.
* Producers: Perusahaan produksi atau produser anime.
* Licensors: Pihak yang memiliki lisensi anime (misalnya, platform streaming).
* Studios: Studio animasi yang mengerjakan anime.
* Source: Sumber materi anime (misalnya, manga, light novel, original).
* Duration: Durasi setiap episode anime.
* Rating: Batasan usia untuk menonton anime.
* Ranked: Peringkat anime berdasarkan popularitas atau kriteria lain.
* Popularity: Peringkat popularitas anime.
* Members: Jumlah anggota yang telah menambahkan anime ke daftar mereka di platform.
* Favorites: Jumlah pengguna yang menandai anime sebagai favorit.
* Watching: Jumlah anime yang sedang ditonton oleh pengguna.
* Completed: Jumlah anime yang telah selesai ditonton oleh pengguna.
* On Hold: Jumlah anime yang ditunda oleh pengguna.
* Dropped: Jumlah anime yang dihentikan oleh pengguna.

![image](https://github.com/user-attachments/assets/6f9f82de-2aa5-4f5e-a064-1d89c3a7f9db)

Gambar 1.Anime Categories Distribusion

![image](https://github.com/user-attachments/assets/ec57393d-7b9a-464d-96fd-c85fd264c2ab)

Gambar 2.Rating Distribusion
Berdasarkan Gambar 2. Categories distribution anime terdiri dari 6 tipe berupa TV, OVA, Movie, Special, ONA, Music. TV (Television Series) yang ditayangkan di televisi dengan episode yang bervariasi, OVA (Original Video Animation) yang dirilis untuk media rumahan, seperti DVD, Movie yang dirilis di bioskop dengan durasi yang lebih panjang, Special yang seringkali menjadi bonus atau tambahan dari seri TV atau film, ONA (Original Net Animation) yang didistribusikan secara daring, dan Music yang dibuat untuk menyoroti perilisan album musik atau single dan berdasarkan Gambar 2. Rating dapat kita lihat rata-rata Rating adalah 6.5, minimal rating adalah 1.8, dan maxsimal rating adalah 9.1. Dan 

![image](https://github.com/user-attachments/assets/8a176c24-83a8-4b9a-a587-9e4c1a086751)

Gambar 3.Top 10 Anime 

![image](https://github.com/user-attachments/assets/15ebba06-9d6e-4091-8ce2-942f88602695)

Gambar 4.Top 10 Anime Rating 

Berdasarkan Gambar 3. Top 10 Anime Community dapat dilihat Top 10 Komunitas anime Death Note menjadi komunitas terbanyak pertama, disusul dengan Shingeki no Kyojin kedua, Fullmetal Alchemist: Brotherhood ketiga, Sword Art Online keempat, One Punch Man kelima, Boku no Hero Academia keenam, Tokyo Ghoul ketujuh, Naruto kedelapan, Steins Gate kesembilan, dan No Game No Life kesepuluh. Informasi ini dapat digunakan pengembang sistem dalam merekomendasikan anime yang populer kepada penggunanya. Banyaknya anggota komunitas anime menandakan bahwa anime cukup favorit dan populer di kalangan pengguna.

Dan pada Gambar 4. Top Rating Tertinggi dapat dilihat rating tertinggi pertama adalah Fullmetal Alchemist: Brotherhood, dan kedua Shingeki no Kyojin: Final Season, ketiga Steins Gate, keempat Shingeki no Kyojin Season 3 Part 2, kelima Hunter x Hunter(2011), keenam Gintama°, ketujuh Gintama', kedelapan Ginga Eiyuu Densetsu, kesembilan Gintama': Enchousen dan kesepuluh adalah 3-gatsu no Lion 2nd Season. Informasi ini dapat digunakan pengembang sistem dalam merekomendasikan anime yang populer kepada penggunanya. Hal ini dikarenakan semakin banyaknya kontribusi peringkat, semakin banyak pula pengguna yang menonton anime tersebut (populer).


Modeling 
-----------------
Dalam proyek sistem rekomendasi anime ini, proses pemodelan dilakukan dengan menggunakan dua pendekatan utama, yaitu algoritma Cosine Similarity dan K-Nearest Neighbor (KNN). Kedua algoritma ini dipilih karena mampu mengukur kemiripan antar item atau antar pengguna berdasarkan fitur-fitur yang relevan dalam dataset, sehingga dapat menghasilkan rekomendasi yang sesuai dengan preferensi pengguna

Cosine Similarity
---------------------
Algoritma Cosine Similarity digunakan untuk mengukur tingkat kesamaan antar anime berdasarkan vektor fitur tertentu, seperti genre, skor pengguna, dan sinopsis. Cosine Similarity bekerja dengan menghitung sudut antara dua vektor dalam ruang multidimensi, dan nilai kemiripannya berada dalam rentang 0 hingga 1, di mana nilai 1 menunjukkan dua item yang sangat mirip. Dengan pendekatan ini, sistem dapat merekomendasikan anime yang secara konten atau karakteristik memiliki kesamaan dengan anime yang sebelumnya disukai atau ditonton oleh pengguna. Pendekatan ini cocok untuk sistem berbasis content-based filtering karena fokus pada karakteristik dari item itu sendiri.

Cosine Similarity dituliskan dalam rumus:

                                       _CosineSimilarity_(A,B)_=_(A·B)/(||A||∗||B||)__

dimana:
(A·B)menyatakan produk titik dari vektor A dan B.
||A|| mewakili norma Euclidean (magnitudo) dari vektor A.
||B|| mewakili norma Euclidean (magnitudo) dari vektor B.

Untuk melakukan pengujian model, digunakan potongan kode berikut.

![image](https://github.com/user-attachments/assets/aee9a84b-aae4-4f7f-a7e4-55dcfa0a63b5)

Gambar 5. Hasil Pengujian Model Content Based Filtering (dengan Filter Genres).

Berdasarkan Gambar 5. Hasil Pengujian Model Content Based Filtering (dengan Filter Genres). Sistem telah berhasil merekomendasikan top 5 persen anime yang mirip dengan One Piece, yang termasuk beberapa film dan seri dari One Piece itu sendiri. Ini berarti bahwa jika seorang pengguna menyukai One Piece, maka sistem dapat memberikan rekomendasi untuk seri atau film lain dalam waralaba One Piece. Dengan pendekatan ini, sistem mengidentifikasi anime-anime yang memiliki kemiripan dalam genre dengan One Piece, sehingga memungkinkan pengguna untuk menemukan konten yang sesuai dengan preferensi mereka berdasarkan kesukaan mereka terhadap One Piece.

Kelebihan Cosine Similarity:
* Kompleksitas yang rendah, membuatnya efisien dalam perhitungan.
* Cocok digunakan pada dataset dengan dimensi yang besar karena tidak terpengaruh oleh jumlah dimensi.

Kekurangan Cosine Similarity:
* Hanya memperhitungkan arah dari vektor, tanpa memperhitungkan magnitudo (besarnya).
* Perbedaan dalam magnitudo vektor tidak sepenuhnya diperhitungkan, yang berarti nilai-nilai yang sangat berbeda dapat dianggap mirip jika arah vektornya sama.

K-Nearest Neighbor (KNN)
--------------------------
Selain Cosine Similarity, digunakan juga algoritma K-Nearest Neighbor (KNN) yang berfungsi untuk mengidentifikasi sejumlah tetangga terdekat (k-nearest neighbors) dari suatu anime atau pengguna berdasarkan kemiripan fitur. Dalam konteks sistem rekomendasi, KNN digunakan untuk mencari anime yang paling mirip dengan anime target, atau mencari pengguna dengan preferensi serupa, kemudian menghasilkan rekomendasi berdasarkan pola kesamaan tersebut. KNN sangat efektif dalam menangani data yang memiliki pola keterkaitan dan dapat digunakan untuk pendekatan collaborative filtering.
Dengan menggabungkan kedua algoritma ini, sistem rekomendasi yang dibangun mampu menghasilkan saran tontonan yang relevan, baik berdasarkan konten maupun pola kesukaan pengguna lain. Pemilihan model ini juga mempertimbangkan kesederhanaan implementasi dan interpretasi hasil, serta performa yang cukup baik dalam konteks data yang digunakan.

K-Nearest Neighbor dituliskan dalam rumus:

                                      _EuclideanDistance_(P,Q) = sqrt (∑(Pi−Qi)2)__

dimana:
* Pi mewakili fitur ke-i dari titik data P.
* Qi mewakili fitur ke-i dari titik data Q (titik data dari kumpulan data D).
* ∑ merupakan simbol penjumlahan pada semua fitur titik data.

berikut merupakan hasil pengujian model K-Nearest Neighbor dengan metrik Euclidean Distance:
Apabila pengguna menyukai aplikasi:Neon Genesis Evangelion Death Rebirth

![image](https://github.com/user-attachments/assets/d79e2766-7ded-4217-9e42-9dba187fea8e)

Gambar 6.Hasil Pengujian Model K-Nearest Neighbor

Berdasarkan Gambar 6. Hasil Pengujian Model K-Nearest Neighbor, kita dapat melihat bahwa model K-Nearest Neighbor memberikan rekomendasi Anime berdasarkan kemiripan fitur-fitur seperti 'Name', 'Score', 'Type', dan 'Studios'. Hasil rekomendasi untuk Anime yang mirip dengan Neon Genesis Evangelion Death  Rebirth berdasarkan berdasarkan fitur-fitur yang dipelajari memberikan hasil rekomendasi aplikasi serupa yaitu: Neon Genesis Evangelion Death Rebirth, Neon Genesis Evangelion The End of Evangelion, Kekkaishi TV, Doraemon Doraemon Comes Back, Dr Slump Aralechan. Seperti tampak gambar 6. Hasil Pengujian Model K-Nearest Neighbor dengan tingkat kemiripan dalam persentase berturut-turut senilai 100.0%, 98.94%, 98.59%, 98.59%, 98.59% . Tentunya model ini akan sangat membantu pengguna menemukan aplikasi yang mirip dengan Neon Genesis Evangelion Death Rebirth.

Kelebihan KNN:
* Tahan terhadap data pelatihan yang memiliki derau.
* Pelatihan sangat cepat.
* Sederhana dan mudah dipelajari.
* Efektif jika data pelatihan besar.

Kekurangan KNN:
* Penentuan nilai k menjadi bias dalam model.
* Komputasi yang kompleks, terutama pada data besar atau dimensi fitur tinggi.
* Keterbatasan memori karena harus menyimpan semua data pelatihan.
* Rentan terhadap atribut yang tidak relevan yang dapat memengaruhi hasil klasifikasi.


Evaluation
------------------
Evaluasi model dilakukan untuk mengetahui seberapa baik sistem rekomendasi bekerja dalam memberikan hasil yang akurat dan relevan bagi pengguna. Dalam proyek ini, beberapa metrik evaluasi yang digunakan meliputi Precision, Calinski-Harabasz Score, dan Davies-Bouldin Score. Metrik-metrik ini memberikan gambaran seberapa efektif model dalam mengenali pola data, baik dalam proses klasifikasi maupun pengelompokan.

Precision
--------------
Precision merupakan salah satu metrik penting untuk mengukur ketepatan sistem dalam memberikan rekomendasi yang benar-benar sesuai. Metrik ini menunjukkan seberapa banyak hasil yang direkomendasikan oleh sistem ternyata memang relevan bagi pengguna. Semakin tinggi nilai precision, semakin akurat sistem dalam memberikan saran yang tepat sasaran.

Rumus untuk menghitung precision adalah sebagai berikut: 

                                                           Precision= True Positive (TP)+False Positive (FP) True Positive (TP)
​Keterangan:

* True Positive (TP) adalah jumlah item yang direkomendasikan dan benar-benar sesuai dengan preferensi pengguna.
* False Positive (FP) adalah jumlah item yang direkomendasikan, tetapi sebenarnya tidak relevan.

Sebagai contoh, pada pengujian model Content-Based Filtering yang menggunakan filter genre, diperoleh nilai precision sebesar 100% untuk rekomendasi Top-5. Artinya, dari lima anime yang direkomendasikan, semuanya sesuai dengan karakteristik anime yang disukai pengguna, seperti dalam kasus rekomendasi anime yang mirip dengan One Piece. Anime-anime yang direkomendasikan memiliki genre yang serupa, seperti Action, Adventure, Comedy, Drama, Fantasy, Shounen, dan Super Power.

Calinski-Harabasz Score
----------------------
Calinski-Harabasz Score merupakan salah satu metrik evaluasi yang umum digunakan dalam algoritma pengelompokan (clustering). Metrik ini digunakan untuk menilai kualitas hasil pengelompokan dengan cara mengukur seberapa baik model memisahkan data ke dalam kelompok-kelompok yang kompak di dalam (intra-cluster) dan terpisah dengan baik antar kelompok (inter-cluster). Nilai skor Calinski-Harabasz (CH) yang tinggi mengindikasikan bahwa kelompok-kelompok yang terbentuk memiliki batas yang jelas dan jarak antar cluster yang besar, sekaligus kedekatan antar anggota dalam satu cluster. Hal ini menjadikan CH score sangat cocok digunakan ketika tidak tersedia label kebenaran (ground truth), karena sifatnya yang unsupervised.

Rumus Calinski-Harabasz Score adalah sebagai berikut:

                                              ![image](https://github.com/user-attachments/assets/e97baf7b-9959-4e76-84fa-b944cfde25ac)

Dengan keterangan: 
* B: Sebaran antar cluster (between-cluster scatter),
* 𝑊 W: Sebaran dalam cluster (within-cluster scatter),
* 𝑁 N: Jumlah total data, 𝑘 k: Jumlah total cluster.
Semakin besar nilai CH, semakin baik kualitas pengelompokan yang dihasilkan. Nilai ini menjadi indikator penting dalam menentukan apakah model telah berhasil mengelompokkan data secara efektif. Untuk menghitung metrik ini pada model yang dikembangkan, digunakan potongan kode Python tertentu yang akan dijalankan setelah proses pengelompokan selesai.

Untuk melakukan pengujian model, digunakan potongan kode berikut.

![image](https://github.com/user-attachments/assets/c4464a06-86f8-4115-982a-623024c3a329) 

Dan didapatkan score dari pengujian model.

![image](https://github.com/user-attachments/assets/8b2477c9-3d62-4434-a2b4-38ca9ef1d1d1)

Hasil evaluasi menunjukkan bahwa kluster dalam model ini masih belum terpisahkan dengan baik, yang tercermin dari nilai skor Calinski-Harabasz (CH) yang relatif rendah sebesar 3.1613291729405617. Kondisi ini mengindikasikan adanya potensi untuk rekomendasi yang kurang sesuai pada beberapa aplikasi, yang mungkin tidak sepenuhnya sesuai dengan preferensi pengguna. Oleh karena itu, perlu dilakukan peninjauan lebih lanjut atau penyesuaian pada model untuk meningkatkan pemisahan kluster dan akurasi rekomendasi.

Davies Bouldin Score
Davies Bouldin Score (DB) adalah metrik evaluasi kinerja pengelompokan yang mengukur rata-rata kesamaan setiap cluster dengan cluster yang paling mirip dengan membandingkan jarak dalam cluster terhadap jarak antar cluster. Dengan skor minimum nol, semakin rendah nilai DB, semakin baik kinerja pengelompokannya, menunjukkan cluster yang lebih dekat satu sama lain dan kurang tersebar. Berbeda dari sebagian besar metrik, DB tidak memerlukan pengetahuan apriori tentang label kebenaran dasar, mirip dengan Silhouette Score, namun memiliki formulasi yang lebih sederhana, memberikan cara efisien untuk mengevaluasi pengelompokan tanpa memerlukan pengetahuan tambahan tentang struktur data.

Rumus Davies-Bouldin Score (DB) adalah:

![image](https://github.com/user-attachments/assets/119a6be4-8144-42e3-90e5-cde38c95820c)

Di mana:
* ( k ) adalah jumlah cluster.
* ( R_i ) adalah radius dalam cluster ke-i.
* ( d(c_i, c_j) ) adalah jarak antara pusat cluster ke-i (( c_i )) dan pusat cluster ke-j (( c_j )).
  
Davies-Bouldin didefinisikan sebagai rata-rata dari nilai-nilai R, di mana setiap nilai R adalah rasio antara jumlah dari radius dalam cluster (dalam pengertian jarak, misalnya Euclidean distance) dan jarak antara pusat cluster, dengan pusat-pusat yang lain. Rasio ini digunakan untuk mengevaluasi kemiripan setiap cluster dengan cluster lain.

 Untuk melakukan pengujian model, digunakan potongan kode berikut.
 
![image](https://github.com/user-attachments/assets/116e83a6-b0c0-4afd-9306-9915f0af0e8f)

Dan didapatkan score dari pengujian model.

![image](https://github.com/user-attachments/assets/48c83790-0bb8-4a27-ae19-495844ca3b12)

Hasil evaluasi Davies-Bouldin (DB) menunjukkan bahwa model ini memiliki skor yang relatif cukup kecil, dengan nilai DB sebesar 0.7864266764751376 Hal ini menandakan bahwa model sudah memiliki separasi kluster yang cukup baik. Sebagai hasilnya, rekomendasi anime memiliki kualitas yang baik, mempertimbangkan bahwa pengelompokan kluster dalam model sudah cukup efektif dalam memisahkan data.

Refrensi 
-----------------
1. Nazhif Muafa Roziqiin & M. Faisal. (2024). Sistem Rekomendasi Pemilihan Anime Menggunakan User‑Based Collaborative Filtering.
2. Helmy Dianty Putri & Muhammad Faisal. (2023). Analyzing the Effectiveness of Collaborative Filtering and Content‑Based Filtering Methods in Anime Recommendation Systems.
3. Vynska Amalia Permadi & Rezky P. Raharjo. (2023). Improvement of KNN Collaborative Filtering Model in User‑based Approach on Anime Recommendation System.
4. Hemdani R. Herlianto. (2023). Pemfilteran Berbasis Konten yang Dapat Menentukan Top‑N Rekomendasi Anime Bagi Pengguna.
