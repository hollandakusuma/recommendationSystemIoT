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

## Business Understanding

Dalam era digital, volume informasi yang besar sering kali menyulitkan pengguna dalam menemukan artikel ilmiah yang relevan dan sesuai dengan kebutuhan mereka. Terutama di bidang Internet of Things (IoT), yang merupakan area penelitian yang berkembang pesat, kebutuhan akan sistem rekomendasi yang efektif menjadi semakin penting untuk mempermudah akses ke sumber daya yang relevan dan mendorong kemajuan penelitian.

### Problem Statements
**1. Kesulitan dalam Menemukan Artikel Ilmiah Relevan**

Banyaknya artikel ilmiah yang tersedia dapat membuat peneliti kewalahan dalam menemukan artikel yang paling sesuai dengan minat atau kebutuhan penelitian mereka.

**2. Kurangnya Personalisasi dalam Rekomendasi Artikel**

Sistem pencarian konvensional sering kali tidak mempertimbangkan preferensi atau pola interaksi pengguna dengan artikel, sehingga hasil yang ditampilkan kurang relevan.

### Goals
**1. Mengembangkan Sistem Rekomendasi Berbasis Konten**
Memanfaatkan atribut artikel seperti Title dan Type untuk merekomendasikan artikel yang serupa dengan preferensi pengguna.

**2. Meningkatkan Relevansi Rekomendasi Melalui Collaborative Filtering**
Membuat model yang memanfaatkan pola interaksi antara penulis atau pembaca dengan artikel untuk menyarankan konten yang paling sesuai.

### Solution Approach
**1. Content-Based Filtering**

Menggunakan fitur Title dan Type untuk menghitung kesamaan antara artikel menggunakan teknik TF-IDF Vectorization dan Cosine Similarity. Sistem ini memungkinkan rekomendasi artikel yang mirip dengan artikel yang diminati pengguna sebelumnya.

**2. Collaborative Filtering**
Membuat matriks interaksi antara pengguna (AuthorID) dan artikel (ArticleID) berdasarkan nilai InteractionValue. Matriks ini akan digunakan untuk model pembelajaran seperti Singular Value Decomposition (SVD) untuk merekomendasikan artikel berdasarkan pola interaksi.

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

1. Untuk Content-Based Filtering:

- **Title:** Judul artikel akan dianalisis menggunakan teknik TF-IDF Vectorization.
- **Type:** Jenis artikel untuk menyesuaikan preferensi pengguna terhadap tipe konten tertentu.

3. Untuk Collaborative Filtering:
- **Authors** dan **Title** digunakan untuk membentuk interaction_matrix, yang merepresentasikan hubungan antara penulis (pengguna) dan artikel yang mereka interaksikan.
- Kolom **Cites** dapat digunakan sebagai nilai InteractionValue, di mana jumlah kutipan menjadi metrik yang mencerminkan relevansi atau popularitas artikel.

### Exploratory Data Analysis (EDA)

**1.    Distribusi Kutipan:** Histogram jumlah kutipan (Cites) untuk melihat persebaran pengaruh artikel.

![image](https://github.com/user-attachments/assets/0de9e434-5223-4f43-a16c-48f00d032d6c)

**2.    Distribusi Tipe Artikel:** Melihat proporsi artikel berdasarkan Type (Article, Review, Book Chapter, Conference Paper, Short Survey, Retracted, Editorial).

![image](https://github.com/user-attachments/assets/6780663d-ff9b-4f99-a144-ba8c303b9962)

**3.    Penulis dengan Artikel Terbanyak:** Mengetahui beberapa **Author** yang memiliki artikel ilmiah terbanyak.

![image](https://github.com/user-attachments/assets/2b36cd31-d7de-4b31-8b3e-544ec14a61df)

## Data Preparation
Tahapan Data Preparation bertujuan untuk membersihkan dan mengorganisasi data agar siap digunakan dalam proses analisis dan pengembangan sistem rekomendasi. Dalam proyek ini, langkah-langkah berikut dilakukan untuk memastikan data relevan dan berkualitas tinggi:

**1. Penghapusan Kolom Tidak Relevan**

Pada dataset asli, terdapat beberapa kolom yang kosong atau tidak relevan dengan tujuan proyek. Kolom-kolom ini dihapus untuk mengurangi kompleksitas data dan meningkatkan efisiensi pemrosesan. Berikut adalah kolom yang dihapus:

-    Publisher: Kolom ini sepenuhnya kosong sehingga tidak memberikan informasi yang berguna.
-    ECC: Informasi ini tidak relevan dengan pengembangan sistem rekomendasi.
-    Abstract: Tidak memiliki data yang terisi dan tidak digunakan dalam analisis.
-    FullTextURL: Kolom ini tidak berkontribusi pada fitur rekomendasi.
-    RelatedURL: Kolom ini kosong dan tidak memiliki relevansi.
-    Volume, Issue, StartPage, dan EndPage: Detail teknis publikasi ini tidak memiliki kontribusi langsung terhadap model rekomendasi yang dirancang.

**Alasan Penghapusan**

-    **Efisiensi:** Mengurangi kolom yang tidak penting mempercepat proses analisis dan pengembangan model.
-    **Relevansi:** Memastikan dataset hanya berisi informasi yang mendukung algoritma content-based filtering dan collaborative filtering.

**2. Persiapan Fitur untuk Content-Based dan Collaborative Filtering**

Pada tahap ini, dataset yang telah dibersihkan disiapkan untuk digunakan dalam dua pendekatan utama sistem rekomendasi: Content-Based Filtering dan Collaborative Filtering. Langkah-langkah berikut dilakukan:
*1. Content-Based Filtering*

Untuk pendekatan ini, fitur yang digunakan berasal dari informasi yang mendeskripsikan artikel, yaitu:

-    Title: Judul artikel, yang mencerminkan topik utama dan relevansi artikel.
-    Type: Jenis artikel, seperti journal paper, conference paper, atau lainnya, yang membantu memberikan konteks tambahan dalam proses rekomendasi.

Kode berikut digunakan untuk menyiapkan fitur ini:
```
content_features = data_cleaned[['Title', 'Type']]
```
*2. Collaborative Filtering*

Untuk pendekatan ini, fitur yang digunakan berasal dari informasi interaksi antara penulis dan artikel. Fitur-fitur yang relevan meliputi:

-    Authors: Penulis artikel, yang berfungsi sebagai identitas utama dalam membangun matriks interaksi.
-    Cites: Jumlah sitasi, yang mencerminkan popularitas atau relevansi artikel.
-    CitesPerYear: Rata-rata sitasi per tahun, yang memberikan konteks temporal untuk sitasi.
-    CitesPerAuthor: Rata-rata sitasi per penulis, yang merepresentasikan pengaruh setiap penulis terhadap popularitas artikel.

Kode berikut digunakan untuk menyiapkan fitur ini:
```
collaborative_features = data_cleaned[['Authors', 'Cites', 'CitesPerYear', 'CitesPerAuthor']]
```

### Alasan Pemilihan Fitur
1.    Content-Based Filtering: Fitur yang dipilih mencakup informasi utama yang mendeskripsikan artikel dan dapat diolah menggunakan algoritma berbasis konten, seperti penghitungan kemiripan teks (text similarity).
2.    Collaborative Filtering: Fitur yang dipilih memungkinkan pembuatan matriks interaksi (interaction matrix) antara penulis dan artikel untuk mendukung metode berbasis kolaborasi, seperti matrix factorization atau neighborhood-based filtering.

    
## Modeling
Pengembangan model sistem rekomendasi dibagi menjadi dua pendekatan utama: Content-Based Filtering dan Collaborative Filtering. Berikut penjelasan dari masing-masing pendekatan yang diterapkan.

### Content-Based Filtering

Content-Based Filtering bertujuan merekomendasikan artikel berdasarkan kemiripan antar artikel. Pada pendekatan ini, digunakan fitur berikut:

-    Title: Judul artikel diproses menjadi representasi numerik menggunakan metode TF-IDF (Term Frequency-Inverse Document Frequency).
#### **Langkah-langkah Pengembangan**

1. **Preprocessing**:
   - Kolom *Title* dan *Type* digabungkan menjadi satu fitur baru bernama `Content` untuk memperkaya informasi.
   - Teks pada kolom `Content` diubah menjadi vektor numerik menggunakan **TF-IDF Vectorizer**.

2. **Menghitung Kesamaan**:
   - Kesamaan antar artikel dihitung menggunakan **Cosine Similarity** berdasarkan vektor hasil TF-IDF.

3. **Fungsi Rekomendasi**:
   - Fungsi dirancang untuk memberikan rekomendasi artikel berdasarkan kata kunci (*keyword*) yang dimasukkan pengguna.
   - Fungsi ini mencari artikel dengan skor kemiripan tertinggi terhadap *keyword* yang diberikan.

4. **Output**:
   - Artikel dengan skor kesamaan tertinggi direkomendasikan kepada pengguna berdasarkan Keyword yang dimasukkan oleh pengguna. Sistem akan mencocokkan dengan artikel-artikel dalam dataset berdasarkan kemiripan..

**Contoh Penggunaan:**

```
Masukkan keyword untuk mencari artikel: marine
Rekomendasi artikel berdasarkan keyword:
210    Internet of Underwater Things and Big Marine D...
307    Flexible Seaweed-Like Triboelectric Nanogenera...
999    SWARAM: Osprey Optimization Algorithm-Based En...
328    Smart Home Energy Management Systems in Intern...
340    Integrating the Internet of Things in the hala...
Name: Title, dtype: object
```
---

### **Collaborative Filtering**

Pendekatan Collaborative Filtering memanfaatkan data interaksi antara pengguna dan artikel, seperti citasi, tingkat popularitas, dan tipe artikel, untuk menghasilkan rekomendasi.

#### **Langkah-langkah Pengembangan**

1. **Membuat Matriks Interaksi**:
   - Dibuat matriks pengguna-artikel (*User-Item Interaction Matrix*) yang memuat metrik gabungan dari `Cites`, `CitesPerYear`, dan `Type` dalam bentuk numerik.

2. **Penerapan SVD (Singular Value Decomposition)**:
   - SVD digunakan untuk mendekomposisi matriks interaksi menjadi representasi faktor laten.
   - Matriks ini kemudian direkonstruksi untuk memprediksi interaksi yang belum ada.

3. **Rekomendasi Artikel**:
   - Fungsi dibuat untuk memberikan rekomendasi artikel kepada pengguna dengan prediksi nilai interaksi tertinggi.
   - Output berupa daftar artikel dengan relevansi tertinggi terhadap pengguna tertentu.

**Contoh Penggunaan:**

```
Rekomendasi untuk pengguna 1:
- The adoption of Internet of Things in a Circular Supply Chain framework for the recovery of WEEE: The case of Lithium-ion electric vehicle battery packs oleh C. Garrido-Hidalgo
- Energy-Efficient Industrial Internet of Things: Overview and Open Issues oleh W. Mao
- Intrusion Detection in Industrial Internet of Things Network-Based on Deep Learning Model with Rule-Based Feature Selection oleh J.B. Awotunde
- An AI‐Enabled Hybrid Lightweight Authentication Model for Digital Healthcare Using Industrial Internet of Things Cyber‐Physical Systems oleh M.A. Almaiah
- Utilizing Deep Learning and the Internet of Things to Monitor the Health of Aquatic Ecosystems to Conserve Biodiversity oleh B.A. Odilov
```
---

Pendekatan **Content-Based Filtering** berfokus pada karakteristik artikel itu sendiri, sedangkan **Collaborative Filtering** mempertimbangkan pola interaksi pengguna terhadap artikel. Dengan menggabungkan kedua pendekatan ini, diharapkan sistem rekomendasi dapat menghasilkan saran yang lebih akurat dan relevan.

## **Evaluation**

Pada bagian ini, evaluasi dilakukan untuk mengukur kinerja model yang telah dibangun, baik untuk pendekatan **Content-Based Filtering** maupun **Collaborative Filtering**. Berikut adalah penjelasan mengenai metrik evaluasi yang digunakan serta hasil yang diperoleh.

---

### **Content-Based Filtering**

#### **Metrik Evaluasi: Cosine Similarity**

Cosine Similarity digunakan untuk mengukur kemiripan antar artikel berdasarkan representasi numeriknya. Formula Cosine Similarity adalah sebagai berikut:
$${Cosine Similarity} = \frac{\mathbf{A} \cdot \mathbf{B}}{\|\mathbf{A}\| \|\mathbf{B}\|}
$$

Di mana:
-   $\|\mathbf{B}\|$ adalah vektor representasi artikel.

- $\|\mathbf{A}\|$ dan $\|\mathbf{B}\|$ adalah vektor representasi artikel. 
- $\mathbf{A} \cdot \mathbf{B}$ adalah hasil perkalian dot product dari dua vektor. 
- ${\|\mathbf{A}\| \|\mathbf{B}\|}$ adalah panjang (magnitude) dari masing-masing vektor.

**Cara Kerja**:
- Nilai Cosine Similarity berkisar antara 0 hingga 1.
- Semakin mendekati 1, semakin mirip dua artikel tersebut berdasarkan fitur yang digunakan.

**Hasil Evaluasi**:
- Nilai Cosine Similarity antara artikel pertama dan artikel kedua: **0.3741**.
  - Interpretasi: Artikel pertama dan kedua memiliki tingkat kemiripan yang sedang.

---

### **Collaborative Filtering**

#### **Metrik Evaluasi: Mean Squared Error (MSE)**

Mean Squared Error (MSE) digunakan untuk mengukur perbedaan rata-rata kuadrat antara nilai prediksi dan nilai aktual pada matriks interaksi pengguna-artikel. Formula MSE adalah sebagai berikut:

$$\text{MSE} = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2
$$

Di mana:
- $(n)$ adalah jumlah data.
- $(y_i)$ adalah nilai aktual.
- $(\hat{y}_i)$ adalah nilai prediksi.

**Cara Kerja**:
- Nilai MSE menunjukkan seberapa jauh prediksi dari nilai aktual.
- Semakin kecil nilai MSE, semakin baik model dalam memprediksi.

**Hasil Evaluasi**:
- Nilai MSE: **24.0759**.
  - Interpretasi: Model Collaborative Filtering menghasilkan error yang cukup besar, menunjukkan bahwa ada ruang untuk perbaikan dalam memprediksi interaksi pengguna-artikel.

---

### **Kesimpulan Evaluasi**

1. Pada **Content-Based Filtering**, Cosine Similarity berhasil mengidentifikasi tingkat kemiripan antar artikel dengan hasil yang cukup baik.
2. Pada **Collaborative Filtering**, nilai MSE menunjukkan model masih perlu ditingkatkan, misalnya dengan menyesuaikan parameter model, menambahkan data interaksi, atau menggunakan teknik pembobotan pada data yang jarang (*sparse data*).

Evaluasi ini memberikan wawasan tentang kinerja masing-masing pendekatan dan menjadi dasar untuk perbaikan model di iterasi selanjutnya.

**------**
