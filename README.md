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

### Solution Approach
**1. Content-Based Filtering**

Pendekatan ini akan mengandalkan konten artikel itu sendiri, khususnya judul artikel, untuk menentukan seberapa relevan artikel tersebut dengan kata kunci pencarian yang dimasukkan oleh pengguna. Proses ini akan melibatkan:

*    Menyaring artikel yang judulnya mengandung kata kunci yang diberikan oleh pengguna.
*    Menghitung kesamaan antara kata kunci dan judul artikel menggunakan teknik TF-IDF (Term Frequency-Inverse Document Frequency) untuk menilai kepentingan setiap kata dalam judul.
*    Mengurutkan artikel berdasarkan cosine similarity untuk memberikan rekomendasi yang paling relevan.

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

### Exploratory Data Analysis (EDA)

**1.    Distribusi Kutipan:** Histogram jumlah kutipan (Cites) untuk melihat persebaran pengaruh artikel. Grafik distribusi jumlah sitasi menunjukkan pola yang sangat miring ke kanan, di mana mayoritas artikel memiliki jumlah sitasi rendah, berkisar antara 0 hingga 100. Hanya sedikit artikel yang mencapai lebih dari 500 sitasi, bahkan sangat jarang yang memiliki lebih dari 1000 sitasi. Pola ini mengindikasikan bahwa sebagian besar artikel dalam dataset memiliki dampak yang relatif kecil dalam komunitas akademik, sedangkan beberapa artikel unggulan menunjukkan pengaruh yang signifikan. Hal ini memberikan gambaran bahwa hanya artikel tertentu dengan kontribusi besar yang berhasil menarik perhatian luas. Fokus pada artikel dengan sitasi tinggi dapat membantu peneliti memahami karakteristik penelitian yang berhasil menciptakan dampak besar.

![image](https://github.com/user-attachments/assets/0b2f1962-15ef-4e0a-9c7a-52d5e70871ae)


**2.    Distribusi Tipe Artikel:** Melihat proporsi artikel berdasarkan Type (Article, Review, Book Chapter, Conference Paper, Short Survey, Retracted, Editorial). Grafik frekuensi tipe artikel memperlihatkan bahwa mayoritas artikel dalam dataset bertipe "Article", diikuti oleh tipe "Review". Jenis lainnya, seperti "Conference Paper", "Book Chapter", dan "Editorial", memiliki frekuensi yang jauh lebih rendah. Dominasi tipe "Article" menunjukkan bahwa dataset ini terutama berisi penelitian primer yang dipublikasikan dalam bentuk artikel jurnal. Jenis "Review" yang menempati posisi kedua menunjukkan adanya ulasan literatur yang signifikan. Dengan demikian, rekomendasi artikel dapat lebih fokus pada tipe artikel "Article" karena lebih relevan bagi kebutuhan kebanyakan pengguna yang mencari penelitian primer.

![image](https://github.com/user-attachments/assets/6780663d-ff9b-4f99-a144-ba8c303b9962)


**3.    Frekuensi Sumber Artikel:** Mengetahui beberapa sebaran **tempat** Artikel Ilmiah dipublikasikan. Grafik frekuensi sumber artikel menunjukkan bahwa jurnal "IEEE Internet of Things Journal" dan "IEEE Access" merupakan sumber dominan dalam dataset, dengan jumlah artikel yang jauh lebih tinggi dibandingkan sumber lainnya. Selain itu, jurnal seperti "Sensors", "IEEE Transactions on Industrial Informatics", dan "Internet of Things (Netherlands)" juga menjadi kontributor signifikan. Hal ini mencerminkan bahwa dataset ini sangat berfokus pada topik-topik terkait teknologi IoT, jaringan komunikasi, dan perangkat sensor. Dominasi sumber-sumber ini menunjukkan relevansi yang tinggi dengan tren penelitian terkini di bidang teknik elektro dan teknologi informasi. Peneliti dapat memanfaatkan informasi ini untuk mengidentifikasi jurnal-jurnal yang relevan dan memiliki reputasi baik dalam topik yang diminati.

![image](https://github.com/user-attachments/assets/3bd90eb0-8281-4d86-8c0d-b5d8be069f04)

**4.    Penulis dengan Artikel Terbanyak:** Mengetahui beberapa **Author** yang memiliki artikel ilmiah terbanyak. Penulis dengan jumlah artikel terbanyak adalah Y. Liu, A. Rejeb, dan X. Wang, masing-masing menulis 7 artikel. Ini menunjukkan bahwa mereka adalah kontributor utama dalam penelitian atau publikasi yang terkait. Ada perbedaan signifikan antara penulis dengan jumlah artikel tertinggi (7 artikel) dan penulis lainnya yang berada di kisaran 4 hingga 5 artikel. Hal ini mencerminkan ketimpangan kontribusi di antara penulis dalam publikasi. Nama seperti Wang dan Liu tampak cukup sering muncul dalam komunitas akademik, mengindikasikan mereka mungkin bekerja dalam jaringan atau kolaborasi yang produktif.

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


**2. Pembersihan Teks (*Text Cleaning*)**

Proses yang dilakukan adalah pembersihan teks pada kolom **'Title'** dari dataset. Pembersihan ini dilakukan dengan mengubah teks menjadi huruf kecil, menghapus tanda baca, dan menghapus kata-kata yang tidak memiliki makna penting (*stopwords*). Pembersihan ini sangat penting karena teks yang bersih akan meningkatkan kualitas pemodelan dan mengurangi kebisingan yang bisa mengganggu proses ekstraksi fitur dan perhitungan kemiripan artikel. Misalnya, kata seperti "the," "and," atau "in" tidak memberikan informasi yang signifikan dalam analisis konten, sehingga harus dihapus untuk memperbaiki hasil pemrosesan.

**Alasan Pembersihan**

-    Menghapus tanda baca dan stopwords membantu mengurangi kebisingan dalam data, meningkatkan kualitas analisis, dan menghindari kesalahan dalam ekstraksi fitur.

**3. Ekstraksi Fitur Menggunakan TF-IDF (*Term Frequency-Inverse Document Frequency*)**

Setelah teks dibersihkan, langkah berikutnya adalah mengonversi teks yang telah dibersihkan menjadi representasi numerik dengan menggunakan TF-IDF Vectorizer. TF-IDF adalah teknik yang sangat berguna dalam pemrosesan teks untuk mengukur seberapa penting kata dalam dokumen relatif terhadap keseluruhan koleksi dokumen. TF-IDF memberikan bobot lebih tinggi pada kata yang sering muncul dalam satu artikel tetapi jarang muncul di artikel lain, yang membantu sistem memahami kata-kata kunci yang paling relevan dalam artikel tersebut.

Dengan mengonversi judul artikel ke dalam bentuk vektor numerik, kita dapat lebih mudah melakukan analisis berbasis matematika, seperti penghitungan kemiripan antar artikel. Tanpa representasi numerik ini, perhitungan kemiripan menggunakan algoritma seperti cosine similarity tidak dapat dilakukan.

**Alasan Ekstraksi Fitur**

-    Mengonversi teks menjadi representasi numerik memungkinkan kita untuk melakukan perhitungan matematis yang dibutuhkan untuk rekomendasi berbasis konten. Tanpa ekstraksi fitur, artikel tidak dapat dianalisis dengan metode statistik seperti cosine similarity.
    
## Modeling and Result
Pengembangan model sistem rekomendasi dibagi menjadi dua pendekatan utama: Content-Based Filtering dan Hybrid Method. Berikut penjelasan dari masing-masing pendekatan yang diterapkan.

### Content-Based Filtering

**Content-Based Filtering** memberikan rekomendasi berdasarkan kesamaan isi konten, terutama pada **Title** artikel. Sistem ini mengandalkan representasi teks dari artikel yang telah dibersihkan dan diproses untuk mengidentifikasi kesamaan antara artikel berdasarkan kata-kata yang terkandung dalam judul.

#### **Proses Content-Based Filtering:**

-    **Cosine Similarity:** Menghitung cosine similarity antar artikel berdasarkan representasi numerik untuk menemukan artikel yang paling relevan dengan artikel yang dicari pengguna. Nilai similarity yang tinggi menunjukkan bahwa dua artikel memiliki kesamaan konten. Proses ini penting dalam membangun sistem rekomendasi karena memungkinkan kita untuk menemukan artikel yang paling relevan dengan artikel yang sedang dianalisis.

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
Pada metode **content-based filtering**, sistem hanya menilai kesamaan berdasarkan elemen-elemen konten yang ada, seperti kata-kata dalam judul artikel. Oleh karena itu, meskipun artikel yang memiliki kesamaan judul bisa direkomendasikan, pendekatan ini terbatas pada fitur konten yang sangat spesifik dan cenderung mengabaikan faktor lain yang bisa memengaruhi relevansi artikel bagi pengguna. Sistem ini tidak memperhitungkan faktor eksternal, seperti seberapa populer atau sering dikutipnya artikel tersebut, yang bisa menjadi indikator kualitas atau relevansi lebih lanjut.

**------**
