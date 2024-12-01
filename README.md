# Laporan Proyek Machine Learning - Hollanda Arief Kusuma

## Project Overview

Di era digital yang ditandai dengan ledakan informasi, jumlah publikasi ilmiah terus meningkat secara eksponensial. Hal ini membawa tantangan bagi para peneliti, terutama dalam domain Internet of Things (IoT), untuk menemukan artikel yang relevan dengan bidang kajian mereka. IoT, sebagai bidang interdisipliner yang berkembang pesat, menghasilkan volume data penelitian yang besar dan kompleks, sehingga sulit bagi individu untuk menyaring informasi yang relevan. Akibatnya, banyak peneliti menghadapi kendala dalam mengakses literatur ilmiah yang tepat waktu dan berkualitas, yang dapat memperlambat kemajuan penelitian dan inovasi.

Sistem rekomendasi berbasis kecerdasan buatan (AI) dan pembelajaran mesin (machine learning) menjadi solusi potensial untuk mengatasi tantangan ini. Dengan memanfaatkan teknik seperti Content-Based Filtering dan Collaborative Filtering, sistem ini dapat memberikan rekomendasi artikel ilmiah yang personal dan relevan berdasarkan kebutuhan pengguna. Sistem yang dirancang tidak hanya mendukung efisiensi dalam menemukan informasi tetapi juga membuka peluang kolaborasi antarpeneliti dengan menghubungkan mereka ke karya-karya terbaru dan relevan. Selain itu, penyesuaian dinamis yang memungkinkan sistem belajar dari riwayat interaksi pengguna semakin meningkatkan pengalaman pengguna dalam menemukan literatur ilmiah.

Penelitian terkini mendukung relevansi sistem rekomendasi dalam ranah ilmiah dengan menggunakan content-based filtering dan collaborative filtering. Sistem ini membantu pengguna menavigasi sejumlah besar informasi dengan memberikan saran yang dipersonalisasi (Prasetya, 2017; Wiputra & Shandi, 2021). Content-based filtering memanfaatkan atribut item, seperti deskripsi buku atau fitur produk, untuk menghasilkan rekomendasi (Ardiansyah et al., 2023). Collaborative filtering, di sisi lain, bergantung pada peringkat dan preferensi pengguna untuk mengidentifikasi pengguna yang serupa dan merekomendasikan item (Wijaya & Alfian, 2018). Beberapa penelitian menggabungkan kedua metode dalam pendekatan hibrida untuk meningkatkan akurasi rekomendasi (Wijaya & Alfian, 2018). Berbagai algoritma digunakan dalam sistem ini, termasuk k-nearest neighbor (Prasetya, 2017), TF-IDF, dan cosine similarity (Ardiansyah et al., 2023). Sistem rekomendasi ini telah berhasil diterapkan dalam berbagai domain, seperti saran produk e-commerce (Prasetya, 2017), rekomendasi film (Wiputra & Shandi, 2021), dan rekomendasi buku perpustakaan (Ardiansyah et al., 2023).

Melalui proyek ini, diharapkan tercipta solusi inovatif yang dapat mendukung peneliti dalam mengakses literatur ilmiah dengan lebih cepat, relevan, dan personal. Hal ini tidak hanya berkontribusi pada efisiensi penelitian, tetapi juga mempercepat pengembangan ilmu pengetahuan dan inovasi di bidang IoT.

**DAFTAR PUSTAKA**

Ardiansyah, R., Ari Bianto, M., & Saputra, B. D. (2023). Sistem Rekomendasi Buku Perpustakaan Sekolah menggunakan Metode Content-Based Filtering. Jurnal CoSciTech (Computer Science and Information Technology), 4(2), 510–518. https://doi.org/10.37859/coscitech.v4i2.5131

Prasetya, C. S. D. (2017). Sistem Rekomendasi Pada E-Commerce Menggunakan K-Nearest Neighbor. Jurnal Teknologi Informasi Dan Ilmu Komputer, 4(3), 194. https://doi.org/10.25126/jtiik.201743392

Wijaya, A. E., & Alfian, D. (2018). Sistem Rekomendasi Laptop Menggunakan Collaborative Filtering Dan Content-Based Filtering. Jurnal Computech & Bisnis, 12(1), 11–27. Retrieved from https://www.academia.edu/76523293/Sistem_Rekomendasi_Laptop_Menggunakan_Collaborative_Filtering_Dan_Content_Based_Filtering?hb-g-sw=69284787

Wiputra, M. M., & Shandi, Y. J. (2021). Perancangan Sistem Rekomendasi Menggunakan Metode Collaborative Filtering dengan Studi Kasus Perancangan Website Rekomendasi Film. Media Informatika, 20(1), 1–18. https://doi.org/10.37595/mediainfo.v20i1.54

----

## Business Understanding

Di dunia akademik, para peneliti dan akademisi sering kali menghadapi tantangan dalam menemukan artikel ilmiah yang relevan dan berkualitas tinggi yang dapat mendukung penelitian mereka. Dengan jumlah artikel ilmiah yang sangat besar dan terus berkembang, pencarian manual melalui database artikel atau jurnal dapat menjadi waktu yang sangat memakan. Oleh karena itu, diperlukan sistem rekomendasi yang efektif untuk menyaring artikel-artikel yang relevan berdasarkan minat atau kata kunci tertentu.

### Problem Statements
**1. Kurangnya Personalisasi dalam Rekomendasi**

Sistem pencarian yang ada biasanya hanya mengandalkan kata kunci untuk menemukan artikel terkait, tanpa mempertimbangkan minat atau pola kolaborasi antara peneliti. Hal ini mengarah pada rekomendasi yang terlalu umum dan kurang relevan dengan kebutuhan spesifik peneliti.

**2. Kualitas Rekomendasi yang Tidak Konsisten**

Artikel yang disarankan berdasarkan kata kunci sering kali memiliki relevansi yang bervariasi, karena tidak mempertimbangkan konteks yang lebih luas, seperti kolaborasi antara peneliti atau kualitas artikel berdasarkan sitasi. Sebaliknya, sistem yang mengandalkan rekomendasi berbasis kolaborasi terkadang kurang memperhitungkan kesamaan konten teks.

### Goals
**1. Mengembangkan Sistem Rekomendasi Berbasis Konten:**  Menyediakan rekomendasi artikel berdasarkan kesamaan teks yang ada pada judul artikel dengan kata kunci pencarian yang diberikan oleh pengguna. Hal ini bertujuan untuk memberikan rekomendasi yang relevan dengan topik penelitian pengguna.

**2. Meningkatkan Relevansi Rekomendasi Melalui *Collaborative Filtering*:**
Menerapkan teknik collaborative filtering untuk memberikan rekomendasi yang berdasarkan pada pola interaksi dan kesamaan minat antar pengguna, serta menggunakan informasi seperti jumlah sitasi artikel untuk memperkuat relevansi rekomendasi.

**3. Pendekatan Hybrid:** Menggabungkan kedua pendekatan ini untuk menghasilkan rekomendasi yang lebih kuat dan komprehensif. Dengan pendekatan hybrid, sistem dapat menghasilkan artikel yang tidak hanya relevan secara teks (*content-based*) tetapi juga relevan berdasarkan pola kolaborasi antar peneliti dan kesamaan interaksi (*collaborative*).


### Solution Approach
**1. Content-Based Filtering**

Pendekatan ini akan mengandalkan konten artikel itu sendiri, khususnya judul artikel, untuk menentukan seberapa relevan artikel tersebut dengan kata kunci pencarian yang dimasukkan oleh pengguna. Proses ini akan melibatkan:

*    Menyaring artikel yang judulnya mengandung kata kunci yang diberikan oleh pengguna.
*    Menghitung kesamaan antara kata kunci dan judul artikel menggunakan teknik TF-IDF (Term Frequency-Inverse Document Frequency) untuk menilai kepentingan setiap kata dalam judul.
*    Mengurutkan artikel berdasarkan cosine similarity untuk memberikan rekomendasi yang paling relevan.

**2. Collaborative Filtering**

Pendekatan ini menggunakan data interaksi antar pengguna dan artikel untuk mengidentifikasi artikel yang mungkin relevan berdasarkan pola kesamaan antar pengguna atau artikel. Dalam hal ini, artikel yang banyak dirujuk oleh peneliti dengan minat yang sama atau penulis yang sering berkolaborasi akan lebih diprioritaskan.

*    Sistem ini menggunakan Item-Based Collaborative Filtering, yang mengidentifikasi artikel serupa berdasarkan item yang telah dipilih atau diberikan rating oleh pengguna lain.
*    Artikel yang memiliki jumlah sitasi tinggi juga akan menjadi prioritas dalam rekomendasi, mengingat artikel yang sering dirujuk biasanya memiliki kualitas yang lebih diakui di komunitas akademik.

**3. Hybrid Approach**

Dengan menggabungkan kedua pendekatan di atas, sistem rekomendasi ini akan menghasilkan rekomendasi yang lebih lengkap dan terintegrasi. Kombinasi content-based dan collaborative filtering akan memanfaatkan kekuatan masing-masing pendekatan untuk memberikan rekomendasi yang lebih akurat dan relevan.

*    Pendekatan hybrid ini akan memprioritaskan artikel berdasarkan kesamaan teks serta interaksi pengguna dan jumlah sitasi, sehingga dapat memberikan rekomendasi yang lebih berbobot dan bervariasi.
*    Sistem ini bertujuan untuk menghasilkan artikel-artikel yang tidak hanya relevan dengan topik riset pengguna tetapi juga dihargai oleh komunitas akademik.    

----
## Data Understanding

Dataset yang digunakan dalam proyek ini berasal dari kumpulan data artikel penelitian ilmiah yang berhubungan dengan Internet of Things (IoT). Dataset ini diperoleh menggunakan Software [Publish or Perish](https://harzing.com/resources/publish-or-perish). Dataset ini terdiri dari informasi tentang artikel ilmiah, termasuk atribut seperti judul, tipe artikel, dan jumlah sitasi artikel tersebut. Dataset tersebut dirancang untuk mendukung implementasi sistem rekomendasi berbasis *content-based filtering* dan *collaborative filtering*.

### Sumber Dataset
Dataset ini dapat diakses dari tautan berikut: [Sumber Dataset Ilmiah](https://github.com/hollandakusuma/recommendationSystemIoT/blob/main/Artikel%20IoT.xlsx). Dataset telah diformat untuk keperluan penelitian dengan memperhatikan kualitas dan relevansi atribut.

### Struktur dan Fitur Dataset
Dataset memiliki 1000 entri dengan beberapa kolom utama yang relevan. Berikut adalah deskripsi dari kolom-kolom yang akan digunakan:

-    **Title:** Judul artikel, digunakan untuk sistem content-based filtering.
-    **Type:** Jenis artikel (contoh: Journal, Conference Paper), yang menjadi salah satu atribut dalam analisis berbasis konten.
-    **Cites:** Jumlah kutipan yang diterima artikel, merepresentasikan tingkat pengaruh artikel.
-    **Authors:** Daftar penulis yang terlibat dalam artikel.
-    **Year:** Tahun publikasi artikel, berguna untuk mengidentifikasi relevansi berdasarkan waktu.
-    **CitesPerYear:** Rasio jumlah kutipan per tahun sejak artikel diterbitkan.
-    **AuthorCount:** Jumlah penulis yang berkontribusi pada artikel.
-    **DOI:** Digital Object Identifier, yang berfungsi untuk memberikan identitas unik bagi setiap artikel.

### Variabel yang Digunakan untuk Sistem Rekomendasi

**1. Content-Based Filtering:**

- **'Title':** Judul artikel yang digunakan untuk menemukan artikel berdasarkan kata kunci yang diberikan oleh pengguna.
- **'Title_cleaned':** Judul artikel setelah dibersihkan, yang digunakan dalam TF-IDF Vectorizer untuk membangun representasi numerik dari teks.
- **'Authors':** Nama penulis artikel yang digunakan dalam hasil rekomendasi.
- **'Cites':** Jumlah sitasi artikel yang digunakan dalam rekomendasi untuk memberikan bobot lebih pada artikel yang lebih banyak disitasi.
- **'Type':** Jenis artikel yang digunakan dalam rekomendasi.
- **'DOI':** Digital Object Identifier, yang digunakan untuk memberikan referensi unik pada artikel.

**2. Hybrid Method:**

- **'Cites':** Jumlah sitasi artikel yang digunakan sebagai fitur utama dalam Item-Based Collaborative Filtering.
- **'CitesPerYear':** Jumlah sitasi per tahun yang digunakan sebagai fitur utama dalam Collaborative Filtering.
- **'Type':** Jenis artikel yang diubah menjadi variabel dummy (one-hot encoding) untuk membantu menemukan kesamaan artikel berdasarkan kategori artikel.
- **'Similarity':** Kesamaan artikel yang dihitung berdasarkan fitur yang telah dinormalisasi dan dihitung menggunakan metode KNN (K-Nearest Neighbors).

### Exploratory Data Analysis (EDA)

**1.    Distribusi Kutipan:** Histogram jumlah kutipan (Cites) untuk melihat persebaran pengaruh artikel.

![image](https://github.com/user-attachments/assets/0b2f1962-15ef-4e0a-9c7a-52d5e70871ae)


**2.    Distribusi Tipe Artikel:** Melihat proporsi artikel berdasarkan Type (Article, Review, Book Chapter, Conference Paper, Short Survey, Retracted, Editorial).

![image](https://github.com/user-attachments/assets/6780663d-ff9b-4f99-a144-ba8c303b9962)


**3.    Frekuensi Sumber Artikel:** Mengetahui beberapa sebaran **tempat** Artikel Ilmiah dipublikasikan.

![image](https://github.com/user-attachments/assets/3bd90eb0-8281-4d86-8c0d-b5d8be069f04)

**4.    Penulis dengan Artikel Terbanyak:** Mengetahui beberapa **Author** yang memiliki artikel ilmiah terbanyak.

![image](https://github.com/user-attachments/assets/2b36cd31-d7de-4b31-8b3e-544ec14a61df)

----
## Data Preparation
Tahapan Data Preparation bertujuan untuk membersihkan dan mengorganisasi data agar siap digunakan dalam proses analisis dan pengembangan sistem rekomendasi. Dalam proyek ini, langkah-langkah berikut dilakukan untuk memastikan data relevan:

**1. Penghapusan Kolom Tidak Relevan**

Pada dataset asli, terdapat beberapa kolom yang kosong atau tidak relevan dengan tujuan proyek. Kolom-kolom ini dihapus untuk mengurangi kompleksitas data dan meningkatkan efisiensi pemrosesan. Berikut adalah kolom yang dihapus:

-    Publisher: Kolom ini sepenuhnya kosong sehingga tidak memberikan informasi yang berguna.
-    ECC: Informasi ini tidak relevan dengan pengembangan sistem rekomendasi.
-    Abstract: Tidak memiliki data yang terisi dan tidak digunakan dalam analisis.
-    FullTextURL: Kolom ini tidak berkontribusi pada fitur rekomendasi.
-    RelatedURL, CitesURL, dan CitationURL: Kolom ini kosong dan tidak memiliki relevansi.
-    Volume, GSRank, ISSN, Age, QueryDate, Issue, StartPage, dan EndPage: Detail teknis publikasi ini tidak memiliki kontribusi langsung terhadap model rekomendasi yang dirancang.

**Alasan Penghapusan**

-    **Efisiensi:** Menghapus kolom yang tidak diperlukan mengurangi kompleksitas dataset, membuat model lebih efisien dalam proses perhitungan dan memori.
-    **Relevansi:** Dengan hanya menyisakan kolom yang relevan untuk analisis, seperti 'Title', 'Authors', dan 'Cites', model dapat bekerja dengan data yang lebih terfokus dan lebih bermakna untuk rekomendasi.
-    **Menghindari Kebingungannya Model:** Kolom-kolom yang mengandung informasi tidak relevan atau berlebihan dapat mengganggu kinerja model dan menyebabkan overfitting atau kurangnya interpretasi yang jelas.
    
## Modeling and Result
Pengembangan model sistem rekomendasi dibagi menjadi dua pendekatan utama: Content-Based Filtering dan Hybrid Method. Berikut penjelasan dari masing-masing pendekatan yang diterapkan.

### Content-Based Filtering

**Content-Based Filtering** memberikan rekomendasi berdasarkan kesamaan isi konten, terutama pada **Title** artikel. Sistem ini mengandalkan representasi teks dari artikel yang telah dibersihkan dan diproses untuk mengidentifikasi kesamaan antara artikel berdasarkan kata-kata yang terkandung dalam judul.

#### **Proses Content-Based Filtering:**

-    **Data Cleaning:** Kolom judul artikel ("Title") dibersihkan dari karakter khusus, tanda baca, dan stopwords untuk memperoleh teks yang lebih murni.
-    **TF-IDF Vectorization:** Menggunakan TF-IDF Vectorizer untuk mengubah teks judul menjadi representasi numerik yang dapat dihitung jarak kesamaannya.
-    **Cosine Similarity:** Menghitung cosine similarity antar artikel berdasarkan representasi numerik untuk menemukan artikel yang paling relevan dengan artikel yang dicari pengguna.

#### **Kelebihan Content-Based Filtering:**

-    **Relevansi Berdasarkan Isi:** Rekomendasi artikel didasarkan langsung pada kata-kata yang ada di judul, memastikan kesamaan yang relevan dengan topik.
-    **Independen dari Pengguna Lain:** Sistem ini tidak memerlukan informasi dari pengguna lain, sehingga cocok untuk kasus di mana data pengguna terbatas.

#### **Kekurangan Content-Based Filtering:**

-    **Keterbatasan pada Teks:** Pendekatan ini hanya bergantung pada teks judul, sehingga bisa kehilangan konteks yang lebih dalam yang terdapat dalam artikel.
-    **Masalah dengan Artikel Baru:** Sistem mungkin kesulitan memberikan rekomendasi yang baik jika artikel baru tidak memiliki kata kunci atau teks yang sesuai dengan data yang ada.

#### **Output:**

Top-N artikel yang relevan berdasarkan keyword yang diberikan oleh pengguna, yang ditampilkan dengan urutan kesamaan tertinggi berdasarkan cosine similarity.

**Contoh Output:**

Keyword : health

|index|Artikel ID|Authors|Title|Cites|Type|DOI|Similarity|
|---|---|---|---|---|---|---|---|
|744|744|H\.R\. Chi|Healthcare 5\.0: In the Perspective of Consumer Internet-of-Things-Based Fog/Cloud Computing|36|Article|10\.1109/TCE\.2023\.3293993|1\.0|
|805|805|A\. Abbas|Blockchain-assisted secured data management framework for health information analysis based on Internet of Medical Things|44|Article|10\.1007/s00779-021-01583-8|0\.7623200113283101|
|681|681|A\.A\. Khan|Data Security in Healthcare Industrial Internet of Things With Blockchain|49|Article|10\.1109/JSEN\.2023\.3273851|0\.6034141277556289|
|828|828|C\. Chakraborty|FC-SEEDA: fog computing-based secure and energy efficient data aggregation scheme for Internet of healthcare Things|20|Article|10\.1007/s00521-023-08270-0|0\.421421198323368|
|873|873|J\.K\. Samriya|Adversarial ML-Based Secured Cloud Architecture for Consumer Internet of Things of Smart Healthcare|12|Article|10\.1109/TCE\.2023\.3341696|0\.27158636254570656|
|528|528|J\. Zhang|An Efficient Blockchain-Based Hierarchical Data Sharing for Healthcare Internet of Things|66|Article|10\.1109/TII\.2022\.3145851|-0\.10272237433010534|
|525|525|L\.K\. Ramasamy|Secure Smart Wearable Computing through Artificial Intelligence-Enabled Internet of Things and Cyber-Physical Systems for Health Monitoring|67|Article|10\.3390/s22031076|-0\.11319916778405092|
|508|508|J\. Shahid|Data Protection and Privacy of the Internet of Healthcare Things \(IoHTs\)|70|Review|10\.3390/app12041927|-0\.5813165594459233|
|338|338|B\.D\. Deebak|Smart Mutual Authentication Protocol for Cloud Based Medical Healthcare Systems Using Internet of Medical Things|95|Article|10\.1109/JSAC\.2020\.3020599|-0\.6057570696334511|
|349|349|S\. Shukla|Identification and Authentication in Healthcare Internet-of-Things Using Integrated Fog Computing Based Blockchain Model|90|Article|10\.1016/j\.iot\.2021\.100422|-0\.616200170529646|

---

### **Hybrid Method**

Pada sistem rekomendasi ini, Hybrid Method menggabungkan dua pendekatan yang berbeda untuk meningkatkan akurasi dan relevansi hasil rekomendasi artikel: Content-Based Filtering dan Collaborative Filtering. Proses ini akan memberikan rekomendasi yang lebih relevan berdasarkan konten artikel serta kesamaan antar artikel berdasarkan interaksi data. 

#### **Proses Hybrid**
1. Content-Based Filtering (CBF):

-    Pada langkah pertama, sistem akan menggunakan pendekatan Content-Based Filtering untuk menghasilkan rekomendasi. Di sini, artikel-artikel dipilih berdasarkan kesamaan judul dengan kata kunci yang dimasukkan oleh pengguna.
-    TF-IDF Vectorization digunakan untuk mengubah judul artikel menjadi representasi numerik. Ini dilakukan untuk mengukur seberapa penting suatu kata dalam judul artikel terkait dengan kata kunci yang diberikan.
-    Setelah itu, cosine similarity dihitung untuk menilai seberapa mirip artikel yang relevan dengan kata kunci yang diberikan.
-    Artikel-artikel yang memiliki nilai cosine similarity tinggi dianggap relevan dan dipilih untuk disarankan kepada pengguna.

2. Collaborative Filtering (CF):

-    Setelah mendapatkan artikel-artikel yang relevan berdasarkan Content-Based Filtering, langkah selanjutnya adalah menggunakan Collaborative Filtering.
-    Collaborative Filtering berfokus pada kesamaan artikel berdasarkan fitur-fitur tambahan yang ada, seperti jumlah Cites (sitasi) dan CitesPerYear (jumlah sitasi per tahun).
-    Selain itu, informasi tentang jenis artikel (Type) diubah menjadi variabel dummy menggunakan One-Hot Encoding untuk memperhitungkan kategori artikel.
-    Data fitur ini kemudian dinormalisasi menggunakan StandardScaler, dan model K-Nearest Neighbors (KNN) digunakan untuk menemukan kesamaan antar artikel berdasarkan fitur-fitur tersebut.
-    Artikel-artikel yang memiliki jarak cosine distance kecil dari artikel relevan dianggap sebagai rekomendasi yang baik dan dipilih untuk ditampilkan kepada pengguna.

3. Penggabungan Kedua Metode:

-    Setelah kedua pendekatan ini dijalankan, sistem akan menggabungkan hasilnya untuk memberikan rekomendasi yang lebih baik.
-    Artikel yang relevan berdasarkan Content-Based Filtering akan diproses lebih lanjut menggunakan Collaborative Filtering untuk menilai kesamaan antara artikel-artikel tersebut.
-    Rekomendasi akhir akan disusun berdasarkan artikel yang memiliki similarity tertinggi, dengan memperhitungkan kedua metode tersebut secara bersamaan.


#### **Kelebihan Hybrid Method**

1.    Mengatasi Keterbatasan Masing-Masing Pendekatan:

-  Content-Based Filtering dapat memberikan hasil yang sangat spesifik berdasarkan konten artikel (judul), namun ia memiliki keterbatasan dalam hal keberagaman rekomendasi, terutama jika artikel yang relevan berdasarkan kata kunci terbatas.
-  Collaborative Filtering dapat memberikan rekomendasi yang lebih beragam berdasarkan pola interaksi pengguna atau atribut lain seperti sitasi, tetapi ia bergantung pada data interaksi yang lebih banyak dan mungkin tidak efektif jika data interaksi tidak tersedia (cold start problem).
-  Dengan menggabungkan kedua metode, Hybrid Method dapat mengatasi keterbatasan masing-masing dan memberikan rekomendasi yang lebih akurat dan relevan.

2.    Peningkatan Relevansi:
- Dengan menggabungkan Content-Based Filtering yang mempertimbangkan kesamaan judul dan Collaborative Filtering yang mempertimbangkan kesamaan berdasarkan fitur lain seperti sitasi, sistem ini dapat memberikan rekomendasi yang lebih komprehensif dan relevan, baik berdasarkan konten maupun interaksi antar artikel.

3.    Pengurangan Overfitting:
-  Pendekatan ini juga mengurangi risiko overfitting yang mungkin terjadi jika hanya satu metode yang digunakan, karena data dianalisis dari berbagai sudut pandang (konten dan interaksi).

#### **Kekurangan Hybrid Method**

1.    Kompleksitas yang Lebih Tinggi:
- Hybrid Method membutuhkan pemrosesan yang lebih rumit karena menggabungkan dua metode yang berbeda. Ini meningkatkan kompleksitas dalam hal implementasi dan waktu komputasi, karena kedua pendekatan perlu diterapkan secara terpisah dan kemudian digabungkan.
- Waktu komputasi bisa lebih lama, terutama jika jumlah data sangat besar.

2.    Data yang Lebih Banyak Diperlukan:
-  Untuk menerapkan Collaborative Filtering secara efektif, sistem memerlukan data yang lebih banyak, seperti jumlah sitasi dan interaksi antar artikel. Jika data yang tersedia terbatas, terutama pada artikel baru atau artikel yang jarang disitasi, maka hasilnya mungkin kurang optimal.
-  Cold start problem masih menjadi tantangan jika data yang cukup tidak tersedia untuk artikel baru atau artikel dengan sedikit interaksi.

3.    Pemeliharaan dan Pembaruan yang Lebih Rumit:
-  Karena melibatkan dua pendekatan yang berbeda, Hybrid Method memerlukan pemeliharaan dan pembaruan yang lebih sering dan lebih kompleks. Pembaruan data atau perubahan dalam satu metode bisa mempengaruhi hasil rekomendasi secara keseluruhan.

#### **Output dari Sistem Rekomendasi**

Output dari sistem rekomendasi menggunakan **Hybrid Method** adalah daftar **Top-N artikel** yang paling relevan berdasarkan gabungan dari kedua metode rekomendasi tersebut. Output ini terdiri dari beberapa informasi terkait setiap artikel, seperti:

1.    Artikel ID: ID unik untuk artikel yang dapat digunakan untuk merujuk artikel dalam database.
2.    Authors: Nama-nama penulis artikel yang relevan.
3.    Title: Judul artikel yang relevan dengan kata kunci yang dimasukkan oleh pengguna.
4.    Cites: Jumlah sitasi yang diterima oleh artikel, menunjukkan seberapa berpengaruh artikel tersebut.
5.    Type: Tipe artikel (misalnya, jurnal, konferensi, laporan, dll.).
6.    DOI: Digital Object Identifier (DOI) artikel yang digunakan untuk mengidentifikasi artikel secara unik.
7.    Similarity: Skor kesamaan antara artikel yang direkomendasikan dengan artikel relevan berdasarkan Collaborative Filtering. Semakin tinggi skor, semakin mirip artikel tersebut dengan artikel yang dicari.

Rekomendasi ini disusun berdasarkan similarity tertinggi, yang mencerminkan artikel-artikel yang paling relevan dengan preferensi pengguna baik berdasarkan konten maupun fitur interaksi artikel. Artikel-artikel ini diurutkan dengan cara yang memudahkan pengguna untuk menemukan artikel yang relevan dan bermanfaat bagi kebutuhan mereka.


**Contoh Output:**

Keyword : Health

|index|Artikel ID|Authors|Title|Cites|Type|DOI|Similarity|
|---|---|---|---|---|---|---|---|
|744|744|H\.R\. Chi|Healthcare 5\.0: In the Perspective of Consumer Internet-of-Things-Based Fog/Cloud Computing|36|Article|10\.1109/TCE\.2023\.3293993|1\.0|
|805|805|A\. Abbas|Blockchain-assisted secured data management framework for health information analysis based on Internet of Medical Things|44|Article|10\.1007/s00779-021-01583-8|0\.7623200113283101|
|681|681|A\.A\. Khan|Data Security in Healthcare Industrial Internet of Things With Blockchain|49|Article|10\.1109/JSEN\.2023\.3273851|0\.6034141277556289|
|828|828|C\. Chakraborty|FC-SEEDA: fog computing-based secure and energy efficient data aggregation scheme for Internet of healthcare Things|20|Article|10\.1007/s00521-023-08270-0|0\.421421198323368|
|873|873|J\.K\. Samriya|Adversarial ML-Based Secured Cloud Architecture for Consumer Internet of Things of Smart Healthcare|12|Article|10\.1109/TCE\.2023\.3341696|0\.27158636254570656|
|528|528|J\. Zhang|An Efficient Blockchain-Based Hierarchical Data Sharing for Healthcare Internet of Things|66|Article|10\.1109/TII\.2022\.3145851|-0\.10272237433010534|
|525|525|L\.K\. Ramasamy|Secure Smart Wearable Computing through Artificial Intelligence-Enabled Internet of Things and Cyber-Physical Systems for Health Monitoring|67|Article|10\.3390/s22031076|-0\.11319916778405092|
|508|508|J\. Shahid|Data Protection and Privacy of the Internet of Healthcare Things \(IoHTs\)|70|Review|10\.3390/app12041927|-0\.5813165594459233|
|338|338|B\.D\. Deebak|Smart Mutual Authentication Protocol for Cloud Based Medical Healthcare Systems Using Internet of Medical Things|95|Article|10\.1109/JSAC\.2020\.3020599|-0\.6057570696334511|
|349|349|S\. Shukla|Identification and Authentication in Healthcare Internet-of-Things Using Integrated Fog Computing Based Blockchain Model|90|Article|10\.1016/j\.iot\.2021\.100422|-0\.616200170529646|

---

## **Evaluation**

Pada bagian ini, evaluasi dilakukan untuk mengukur kinerja model yang telah dibangun, baik untuk pendekatan **Content-Based Filtering** maupun **Hybrid Method**. Berikut adalah penjelasan mengenai metrik evaluasi yang digunakan serta hasil yang diperoleh.

Dalam sistem rekomendasi, Precision@K adalah metrik evaluasi yang umum digunakan untuk mengukur seberapa relevan hasil rekomendasi berdasarkan peringkat yang diberikan. Precision mengukur seberapa banyak artikel yang relevan dari top-K rekomendasi yang dihasilkan oleh sistem.

Precision pada K (Precision@K) diukur dengan rumus berikut:

$${P@K} = \frac{A​}{K}
$$

Di mana:
- $A$ adalah Jumlah artikel relevan dalam K rekomendasi.
- $K$ adalah Jumlah rekomendasi yang diberikan (misalnya, 10 artikel teratas).

Precision@K memberikan nilai antara 0 dan 1, dimana:

-    Nilai 1 berarti semua artikel yang direkomendasikan pada top-K adalah relevan.
-    Nilai 0 berarti tidak ada artikel yang relevan di dalam top-K rekomendasi.
    
#### **Hasil Evaluasi**

Berdasarkan nilai Precision@K maka diperoleh nilai sebesar 1 untuk kedua metode dengan kata kunci yang digunakan **health**. Hal ini menandakan bahwa semua artikel yang direkomendasikan dalam top-K rekomendasi adalah relevan.

-----

## **Kesimpulan**

**PERBANDINGAN HASIL CONTENT BASED FILTERING DAN HYBRID METHOD**
|index|Artikel ID|Authors|Title|Cites|Type|DOI|Method|Similarity|
|---|---|---|---|---|---|---|---|---|
|432|432|A\. Kishor|Artificial Intelligence and Internet of Things Based Healthcare 4\.0 Monitoring System|121|Article|10\.1007/s11277-021-08708-5|Content-Based|NaN|
|338|338|B\.D\. Deebak|Smart Mutual Authentication Protocol for Cloud Based Medical Healthcare Systems Using Internet of Medical Things|95|Article|10\.1109/JSAC\.2020\.3020599|Content-Based|NaN|
|338|338|B\.D\. Deebak|Smart Mutual Authentication Protocol for Cloud Based Medical Healthcare Systems Using Internet of Medical Things|95|Article|10\.1109/JSAC\.2020\.3020599|Hybrid-Based|-0\.6057570696334511|
|349|349|S\. Shukla|Identification and Authentication in Healthcare Internet-of-Things Using Integrated Fog Computing Based Blockchain Model|90|Article|10\.1016/j\.iot\.2021\.100422|Hybrid-Based|-0\.616200170529646|
|508|508|J\. Shahid|Data Protection and Privacy of the Internet of Healthcare Things \(IoHTs\)|70|Review|10\.3390/app12041927|Content-Based|NaN|
|508|508|J\. Shahid|Data Protection and Privacy of the Internet of Healthcare Things \(IoHTs\)|70|Review|10\.3390/app12041927|Hybrid-Based|-0\.5813165594459233|
|525|525|L\.K\. Ramasamy|Secure Smart Wearable Computing through Artificial Intelligence-Enabled Internet of Things and Cyber-Physical Systems for Health Monitoring|67|Article|10\.3390/s22031076|Content-Based|NaN|
|525|525|L\.K\. Ramasamy|Secure Smart Wearable Computing through Artificial Intelligence-Enabled Internet of Things and Cyber-Physical Systems for Health Monitoring|67|Article|10\.3390/s22031076|Hybrid-Based|-0\.11319916778405092|
|528|528|J\. Zhang|An Efficient Blockchain-Based Hierarchical Data Sharing for Healthcare Internet of Things|66|Article|10\.1109/TII\.2022\.3145851|Content-Based|NaN|
|528|528|J\. Zhang|An Efficient Blockchain-Based Hierarchical Data Sharing for Healthcare Internet of Things|66|Article|10\.1109/TII\.2022\.3145851|Hybrid-Based|-0\.10272237433010534|
|681|681|A\.A\. Khan|Data Security in Healthcare Industrial Internet of Things With Blockchain|49|Article|10\.1109/JSEN\.2023\.3273851|Content-Based|NaN|
|681|681|A\.A\. Khan|Data Security in Healthcare Industrial Internet of Things With Blockchain|49|Article|10\.1109/JSEN\.2023\.3273851|Hybrid-Based|0\.6034141277556289|
|694|694|M\. Osama|Internet of Medical Things and Healthcare 4\.0: Trends, Requirements, Challenges, and Research Directions|45|Review|10\.3390/s23177435|Content-Based|NaN|
|805|805|A\. Abbas|Blockchain-assisted secured data management framework for health information analysis based on Internet of Medical Things|44|Article|10\.1007/s00779-021-01583-8|Hybrid-Based|0\.7623200113283101|
|806|806|V\. Puri|Artificial intelligence-powered decentralized framework for Internet of Things in Healthcare 4\.0|43|Conference Paper|10\.1002/ett\.4245|Content-Based|NaN|
|743|743|N\. Savanović|Intrusion Detection in Healthcare 4\.0 Internet of Things Systems via Metaheuristics Optimized Machine Learning|36|Article|10\.3390/su151612563|Content-Based|NaN|
|744|744|H\.R\. Chi|Healthcare 5\.0: In the Perspective of Consumer Internet-of-Things-Based Fog/Cloud Computing|36|Article|10\.1109/TCE\.2023\.3293993|Hybrid-Based|1\.0|
|828|828|C\. Chakraborty|FC-SEEDA: fog computing-based secure and energy efficient data aggregation scheme for Internet of healthcare Things|20|Article|10\.1007/s00521-023-08270-0|Hybrid-Based|0\.421421198323368|
|873|873|J\.K\. Samriya|Adversarial ML-Based Secured Cloud Architecture for Consumer Internet of Things of Smart Healthcare|12|Article|10\.1109/TCE\.2023\.3341696|Content-Based|NaN|
|873|873|J\.K\. Samriya|Adversarial ML-Based Secured Cloud Architecture for Consumer Internet of Things of Smart Healthcare|12|Article|10\.1109/TCE\.2023\.3341696|Hybrid-Based|0\.27158636254570656|


## Keunggulan Metode Hybrid dalam Sistem Rekomendasi

Metode **hybrid** dalam sistem rekomendasi menggabungkan kekuatan dari dua pendekatan berbeda: **Content-Based Filtering** dan **Collaborative Filtering**. Keunggulan utama dari metode hybrid terletak pada kemampuannya untuk memberikan rekomendasi yang lebih akurat dan relevan dibandingkan dengan metode **Content-Based Filtering** yang hanya mengandalkan kesamaan dalam judul artikel. 

### Content-Based Filtering
Pada metode content-based, sistem hanya menilai kesamaan berdasarkan elemen-elemen konten yang ada, seperti kata-kata dalam judul artikel. Oleh karena itu, meskipun artikel yang memiliki kesamaan judul bisa direkomendasikan, pendekatan ini terbatas pada fitur konten yang sangat spesifik dan cenderung mengabaikan faktor lain yang bisa memengaruhi relevansi artikel bagi pengguna. Sistem ini tidak memperhitungkan faktor eksternal, seperti seberapa populer atau sering dikutipnya artikel tersebut, yang bisa menjadi indikator kualitas atau relevansi lebih lanjut.

### Hybrid Filtering
Di sisi lain, metode **hybrid** mengintegrasikan **Content-Based Filtering** dengan **Collaborative Filtering**. Content-Based Filtering memberikan rekomendasi berdasarkan kesamaan topik atau konten, seperti kesamaan judul artikel yang relevan dengan kata kunci yang dicari pengguna. Sementara itu, **Collaborative Filtering** menambahkan dimensi lain dengan mempertimbangkan faktor-faktor yang lebih luas, seperti popularitas artikel, yang diukur melalui jumlah sitasi atau bagaimana artikel tersebut diapresiasi oleh pengguna lain dalam sistem. Hal ini memungkinkan sistem untuk merekomendasikan artikel-artikel yang tidak hanya relevan dengan kata kunci, tetapi juga yang dianggap lebih penting atau berguna oleh komunitas atau komunitas ilmiah lebih luas.

### Keunggulan Sistem Hybrid
Dengan menggabungkan kedua pendekatan tersebut, sistem hybrid mampu menghasilkan rekomendasi yang lebih beragam dan lebih akurat. Artikel yang direkomendasikan tidak hanya didasarkan pada kesamaan isi, tetapi juga mempertimbangkan konteks yang lebih besar, seperti penerimaan dan dampak artikel dalam bidang yang relevan. Dengan demikian, pengguna dapat menerima rekomendasi yang lebih holistik dan bervariasi, meningkatkan kualitas rekomendasi yang diberikan sesuai dengan preferensi dan kebutuhan pengguna.

Secara keseluruhan, pendekatan hybrid memperbaiki keterbatasan dari masing-masing metode secara individual, menjadikannya pilihan yang lebih unggul dalam menciptakan sistem rekomendasi yang efektif dan relevan dalam skenario yang kompleks.


**------**
