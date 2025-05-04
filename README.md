# Laporan Proyek Machine Learning - Idha Kurniawati

## 🔎 Project Overview

Buku adalah jendela dunia. Salah satu cara untuk mendapatkan informasi dan mempelajari sesuatu adalah dengan membaca buku. Buku bukan sekadar kumpulan data, melainkan jalan menuju perubahan. Setiap aspek kehidupan manusia dipengaruhi oleh kemajuan teknologi. Sekarang buku tidak lagi hanya dijual secara offline di toko fisik. Perkembangan teknologi telah memungkinkan buku dijual di banyak toko online melalui platform e-commerce, media sosial, dan situs web pribadi toko buku. Selain itu, buku juga tersedia dalam bentuk e-book. E-book adalah versi digital dari buku cetak dalam format tertentu (misalnya PDF, EPUB atau MOBI) yang memungkinkan pembaca untuk mengakses dan membaca konten buku menggunakan perangkat digital mereka. 

UNESCO menyatakan bahwa indeks minat baca masyarakat Indonesia hanya 0,001% atau dari seribu orang Indonesia.  Dalam laman resmi Kementerian Komunikasi dan Informatika Republik Indonesia (Kemenkominfo) juga mengumumkan hasil penelitian yang dilakukan oleh Central Connecticut State University pada Maret 2016. Hasilnya menunjukkan bahwa Indonesia menduduki peringkat ke-60 dari 61 negara dalam hal minat membaca, tepat di bawah Thailand (59) dan di atas Bostwana (61). Sementara itu, Programme for International Student Assessment (PISA), sebuah penelitian internasional yang menilai kualitas sistem pendidikan dengan mengukur hasil belajar yang penting untuk keberhasilan di abad ke-21, melaporkan bahwa hasil literasi membaca Indonesia meningkat 5 posisi dibandingkan tahun 2018. Akibatnya, peringkat tersebut menurun, dan Indonesia masih berada di peringkat ke-11 terbawah dari 81 negara yang disurvei.

Hal ini akan memengaruhi pemahaman teknologi dan sains. Lebih jauh lagi, minimnya kegiatan membaca terutama di kalangan anak muda dapat berdampak buruk bagi negara karena kehilangan sumber daya manusia yang produktif dan berkualitas. Oleh karena itu, untuk mencetak generasi yang cerdas dan produktif, perlu dilakukan upaya peningkatan minat baca di Indonesia. Menyediakan berbagai jenis bahan bacaan untuk mendukung pembelajaran dan mendorong masyarakat agar mencintai buku merupakan salah satu cara untuk meningkatkan minat baca masyarakat. Langkah lain yang dapat dilakukan untuk meningkatkan minat membaca di Indonesia, yaitu dengan menggunakan sistem rekomendasi. Sistem rekomendasi memungkinkan pembaca menemukan referensi baru untuk buku yang sesuai dengan kategori yang disukai oleh pembaca sebelumnya. Beberapa sistem rekomendasi terdiri dari  Content-Based Filtering dan Collaborative Filtering. Content-Based Filtering adalah metode yang memberikan saran kepada pengguna berdasarkan preferensi pengguna dan hubungan antara metadata suatu item. Collaborative Filtering adalah model yang memberikan rekomendasi berdasarkan kumpulan pendapat dan minat pengguna, biasanya diberikan oleh pengguna dalam bentuk penilaian pada suatu item. Dengan mengukur kemiripan dari setiap buku, sistem dapat membuat skor untuk membuat rekomendasi yang sesuai dengan metadata buku tersebut. Melalui sistem rekomendasi ini, pembaca diharapkan dapat menambahkan referensi baru berdasarkan buku yang diminati sebelumnya.

Tujuan proyek ini adalah untuk mengembangkan sistem rekomendasi buku yang efektif menggunakan Book Recommendation Dataset dari Kaggle. Dengan menerapkan Content-Based Filtering dan Collaborative Filtering, proyek ini bertujuan untuk memberikan rekomendasi buku yang relevan dengan preferensipengguna, meningkatkan pengalaman membaca, dan berpotensi meningkatkan penjualan dan keterlibatan pada platform buku digital.

**Sumber Referensi**:

- Ardiansyah, R., Ari Bianto, M., & Saputra, B. D. (2023). Sistem Rekomendasi Buku Perpustakaan Sekolah menggunakan Metode Content-Based Filtering. Jurnal CoSciTech (Computer Science and Information Technology), 4(2), 510–518. https://doi.org/10.37859/coscitech.v4i2.5131

- Rosita, A., Puspitasari, N., & Kamila, V. Z. (2022). Rekomendasi Buku Perpustakaan Kampus Dengan Metode Item-Based Collaborative Filtering. Sebatik, 26(1), 340–346. https://doi.org/10.46984/sebatik.v26i1.1551

- Zayyad, M. R. (2021). Sistem Rekomendasi Buku Menggunakan Metode Content-Based Filtering. 1–45.



## 📖 Business Understanding

### Problem Statements

Berdasarkan latar belakang di atas, berikut rumusan masalah yang akan diselesaikan dalam proyek ini:
- Bagaimana cara mengembangkan sistem rekomendasi buku yang dapat memberikan saran personal kepada pengguna berdasarkan preferensi?
- Bagaimana mengintegrasikan informasi pada buku untuk memberikan rekomendasi yang akurat?
- Langkah-langkah evaluasi seperti apa yang diperlukan untuk memahami seberapa efektif dua pendekatan sistem rekomendasi yang telah diimplementasikan, serta untuk mengidentifikasi kekuatan dan kelemahan masing-masing?

### Goals

Tujuan dari proyek ini adalah sebagai berikut.:
- Mengembangkan sistem rekomendasi buku yang dapat menyarankan buku-buku relevan sesuai dengan preferensi pengguna secara personal.
- Membangun model yang dapat mengidentifikasi kemiripan antar buku berdasarkan metadata buku.
- Mengevaluasi dan membandingkan performa dua pendekatan sistem rekomendasi yang telah diimplementasikan untuk mengidentifikasi efektivitas, kekuatan, dan kelemahan masing-masing.

### Solution statements
- Pendekatan Content Based Filtering adalah mempelajari profil minat pengguna baru berdasarkan data penilaian objek sebelumnya untuk merekomendasikan item serupa yang disukai di masa lalu atau saat ini dilihat, di mana akurasi rekomendasi meningkat seiring dengan bertambahnya informasi pengguna. Berikut implementasi Content Based Filtering.
    - Mengekstrak fitur dari data buku menggunakan TF-IDF Vectorizer.
    - Menghitung similarity matrix menggunakan cosine similarity.
    - Membuat fungsi rekomendasi yang dapat menyarankan buku serupa berdasarkan judul buku yang diinput.
- Pendekatan Collaborative Filtering adalah merekomendasikan sesuatu berdasarkan perilaku pengguna lain yang memiliki preferensi serupa.  Berikut implementasi Collaborative Filtering.
    - Menggunakan algoritma Singular Value Decomposition (SVD) dari library Surprise.
    - Melatih model untuk memprediksi rating yang mungkin diberikan pengguna terhadap buku yang belum mereka baca. 
    - Membuat fungsi rekomendasi yang dapat menyarankan buku-buku dengan prediksi rating tertinggi untuk pengguna tertentu.

Kedua pendekatan ini akan diimplementasikan secara paralel dan dievaluasi untuk menentukan kelebihan dan kekurangan masing-masing dalam konteks rekomendasi buku.

## 🧩 Data Understanding

### Sumber Data
Dataset yang digunakan dalam proyek ini adalah "Book Recommendation Dataset" yang tersedia di platform Kaggle. Dataset ini dapat diakses melalui link berikut: [Book Recommendation Dataset](https://www.kaggle.com/datasets/arashnic/book-recommendation-dataset/data).

Dataset ini terdiri dari tiga file CSV utama:
1. Books.csv - Informasi tentang buku
2. Ratings.csv - Rating yang diberikan oleh pengguna
3. Users.csv - Informasi tentang pengguna

### Informasi Dataset
Berikut ringkasan informasi mengenai tiga dataset yang dipakai:

**Books Dataset:**
- Jumlah baris: 271360 baris
- Jumlah kolom: 8 kolom

**Ratings Dataset:**
- Jumlah data: 1149780 baris
- Jumlah kolom: 3 kolom

**Users Dataset:**
- Jumlah baris: 278858 baris
- Jumlah kolom: 3 kolom

### Variabel pada Dataset

**1. Books.csv:**
- **ISBN**: International Standard Book Number, kode unik identifikasi buku
- **Book-Title**: Judul buku
- **Book-Author**: Nama penulis buku
- **Year-Of-Publication**: Tahun publikasi buku
- **Publisher**: Nama penerbit buku
- **Image-URL-S**: URL untuk gambar sampul buku ukuran kecil
- **Image-URL-M**: URL untuk gambar sampul buku ukuran medium
- **Image-URL-L**: URL untuk gambar sampul buku ukuran besar

**2. Ratings.csv:**
- **User-ID**: ID unik pengguna
- **ISBN**: ISBN buku yang diberi rating
- **Book-Rating**: Rating yang diberikan oleh pengguna (skala 1-10)

**3. Users.csv:**
- **User-ID**: ID unik pengguna
- **Location**: Lokasi pengguna
- **Age**: Usia pengguna

### 📊 Exploratory Data Analysis (EDA)

#### Analisis Univariat pada Dataset Books

##### Pengecekan Missing Values.
Berdasarkan pengecekan, dataset books menunjukkan adanya missing values pada kolom Book-Author, Publisher, dan Image-URL-L.

##### Pengecekan Duplikat.
Berdasarkan pengecekan, dataset books tidak memiliki duplikat data.

##### Visualisasi
Berikut beberapa visualisasi pada dataset books:

![10 Penulis Buku Terbanyak](https://drive.google.com/uc?id=12NfhfFloPn2M_KyYZ08U0-ydmNf0XjFF)

Berdasarkan visualisasi di atas, dapat disimpulkan bahwa:

- Agatha Christie adalah penulis dengan jumlah buku terbanyak di antara 10 penulis yang ditampilkan, yaitu sebesar 632 buku. Jumlah ini secara signifikan lebih banyak dibandingkan penulis lainnya dalam daftar.
- Charles Dickens memiliki jumlah buku paling sedikit di antara 10 penulis ini, yaitu sebesar 302 buku.

![Visualisasi 10 Penerbit Terbanyak](https://drive.google.com/uc?id=1YtcE9SqWXv4UnBcEOP-IZkZs2TXNA9KY)
    
Berdasarkan visualisasi di atas, dapat disimpulkan bahwa:

- Harlequin adalah penerbit dengan jumlah buku terbanyak di antara 10 penerbit yang ditampilkan, yaitu sebesar 7535 buku. Jumlah ini jauh lebih banyak dibandingkan penerbit lainnya dalam daftar.
- Penerbit Warner Books memiliki jumlah buku paling sedikit di antara 10 penerbit ini, yaitu sebesar 2727 buku.

![Visualisasi Panjang Judul Buku](https://drive.google.com/uc?id=1ZVYwfUWhHqBeCT_swyPPrEgijFFbyx10)
    
Berdasarkan visualisasi di atas, dapat disimpulkan bahwa:

- Sebagian besar judul buku memiliki panjang yang relatif pendek. Puncak kurva KDE dan batang-batang tertinggi berada di sekitar panjang judul antara 10 hingga 30 karakter.
- Distribusi panjang judul buku miring ke kanan (positively skewed). Hal ini berarti sebagian besar data terkumpul di sisi kiri (judul pendek), dan ada "ekor" yang memanjang ke kanan yang menunjukkan adanya sejumlah kecil judul buku yang sangat panjang.
- Frekuensi buku yang panjang judulnya di atas 100 karakter sangat rendah dan mengalami penurunan seiring bertambahnya panjang.
    
    
#### Analisis Univariat pada Dataset Ratings

##### Pengecekan Missing Values.
Berdasarkan pengecekan, dataset ratings menunjukkan tidak ada missing values.

##### Pengecekan Duplikat.
Berdasarkan pengecekan, dataset ratings tidak memiliki duplikat data.

##### Visualisasi
Berikut beberapa visualisasi pada dataset ratings:

![Distribusi Rating Buku](https://drive.google.com/uc?id=17HkuHbUDdiPLeQ7fa2DkSYnmzWOeevx0)

Berdasarkan visualisasi di atas, dapat disimpulkan bahwa:

- Rating 0 memiliki jumlah yang sangat dominan dibandingkan dengan rating lainnya. Terdapat 716.109 rating dengan nilai 0.
- Rating 1 memiliki jumlah yang paling sedikit, yaitu sebesar 1770 rating.
- Distribusi rating tidak merata. Ada konsentrasi besar pada rating 0, diikuti oleh peningkatan jumlah rating hingga nilai 8, dan kemudian sedikit penurunan pada nilai 9 dan 10.

![10 User Paling Aktif Memberi Rating](https://drive.google.com/uc?id=1G1N_f6LQ3K4Hl6sSyMRY7WhZZrcJyrz0)

Berdasarkan visualisasi di atas, dapat disimpulkan bahwa:

- User dengan ID 11676 adalah user yang paling aktif dalam memberikan rating, dengan jumlah rating mencapai 13602. Jumlah ini jauh lebih tinggi dibandingkan user aktif lainnya dalam grafik.
- Aktivitas rating menurun secara signifikan setelah user pertama. 
- User dengan ID 235105 adalah user yang memberikan rating paling sedikit pada grafik di atas, yaitu sebesar 3067.

![Top 10 Buku dengan Rating Terbanyak](https://drive.google.com/uc?id=1Fml_0Mt9RsBLDX8J26jK2KqDhjJMjxx-)

Berdasarkan visualisasi di atas, dapat disimpulkan bahwa:

- Buku dengan ISBN 0971880107 adalah buku yang paling banyak dirating, dengan jumlah rating mencapai 2502. Jumlah ini jauh lebih tinggi dibandingkan buku-buku lain dalam grafik.
- Buku dengan ISBN 0671027360 adalah buku kesepuluh yang paling banyak dirating, dengan jumlah rating 586.

#### Analisis Univariat pada Dataset Users

##### Pengecekan Missing Values.
Berdasarkan pengecekan, dataset users menunjukkan adanya missing values pada kolom Age sebesar 110762.

##### Pengecekan Duplikat.
Berdasarkan pengecekan, dataset users tidak memiliki duplikat data.

##### Visualisasi
Berikut beberapa visualisasi pada dataset users:

![Distribusi Umur Pengguna](https://drive.google.com/uc?id=1ba8WOKnYrtjeAHcsvq6nclzUW58jrqqs)

Berdasarkan visualisasi di atas, dapat disimpulkan bahwa:

- Distribusi umur pengguna miring ke kanan (positively skewed). Ini berarti sebagian besar data terkumpul di sisi kiri (umur muda), dan ada "ekor" yang memanjang ke kanan yang menunjukkan adanya sejumlah kecil pengguna dengan umur yang lebih tua.
- Sebagian besar pengguna berada dalam rentang umur dewasa muda hingga dewasa. Puncak kurva KDE dan batang-batang tertinggi berada di sekitar umur 20 hingga 40 tahun.
- Jumlah pengguna menurun seiring bertambahnya umur setelah rentang 40 tahun. Frekuensi pengguna dengan umur di atas 60 tahun semakin rendah.
- Terdapat beberapa lonjakan kecil pada umur yang tidak lazim (sekitar 100 sampai dengan 150 tahun). Lonjakan ini kemungkinan merupakan kesalahan input data atau nilai ekstrem yang perlu diselidiki lebih lanjut.

![10 Lokasi dengan Jumlah Pengguna Terbanyak](https://drive.google.com/uc?id=16nrcfADOfMumBSGpZX60g_2HOes8AQ74)

Berdasarkan visualisasi di atas, dapat disimpulkan bahwa:

- London, England, United Kingdom adalah lokasi dengan jumlah pengguna terbanyak, yaitu sebesar 2506 pengguna. Jumlah ini secara signifikan lebih tinggi dibandingkan lokasi lainnya dalam grafik.
- Vancouver, British Columbia, Canada memiliki jumlah pengguna paling sedikit di antara 10 lokasi teratas, yaitu sebesar 1359 pengguna.

![10 Negara dengan Jumlah Pengguna Terbanyak](https://drive.google.com/uc?id=1Bxxg8WFJSacEPYyhW87-Y-xTRbtOvRfc)

Berdasarkan visualisasi di atas, dapat disimpulkan bahwa:

- USA (Amerika Serikat) adalah negara dengan jumlah pengguna terbanyak, yaitu sebesar 139711 pengguna. Jumlah ini jauh lebih tinggi dibandingkan negara-negara lain dalam daftar.
-  Portugal memiliki jumlah pengguna yang paling sedikit di antara 10 negara teratas, yaitu sebesar 3325 pengguna serta penurunan yang cukup tajam dibandingkan negara-negara sebelumnya.

## 🧮 Data Preprocessing

Pada tahap ini, menggabungkan dataset books dan ratings lalu menyimpannya ke dalam dataset baru yang bernama books_ratings. Berikut kode perintah dari merger dataset books dan ratings.

```python
books_ratings=books.merge(ratings,on="ISBN")
books_ratings.head()
```

## ⚙️ Data Preparation

Terdapat beberapa teknik data preparation yang dilakukan pada bagian ini yaitu sebagai berikut.

### Copy Dataset

Pada tahap ini, membuat salinan (copy) dari DataFrame books_ratings dan menyimpannya ke variabel baru bernama df terlebih dahulu agar perubahan yang dilakukan pada df tidak akan memengaruhi DataFrame asli books_ratings. Berikut kode perintahnya.

```python
df = books_ratings.copy()
```

### Clearing Book-Title

```python
df["Book-Title"] = df["Book-Title"].apply(lambda x: re.sub("[\W_]+", " ", x).strip())
```

**Alasan:** Pembersihan judul buku dengan menghapus karakter non-alfanumerik dan spasi berlebih dilakukan untuk standarisasi data teks. Hal ini akan meningkatkan akurasi dalam perbandingan judul buku dan mencegah duplikasi akibat perbedaan format penulisan.

### Drop Unnecessary Column

```python
df.drop(columns=["ISBN","Image-URL-S","Image-URL-M", "Image-URL-L"],axis=1,inplace=True)
```

**Alasan:** Kolom ISBN dan URL gambar dihapus karena tidak relevan dalam pembuatan model rekomendasi berbasis konten atau kolaboratif. ISBN merupakan identifier yang tidak membawa informasi konten buku, sementara URL gambar tidak diperlukan untuk analisis preferensi.

### Change Data Type

```python
try:
    df['Year-Of-Publication'] = df['Year-Of-Publication'].astype(int)
    print("Berhasil mengubah tipe data 'Year-Of-Publication' pada dataset df menjadi int.")
except Exception as e:
    print(f"Gagal mengubah tipe data 'Year-Of-Publication' pada dataset df: {e}")
```

**Alasan:** Konversi tipe data dilakukan untuk memastikan konsistensi dan efisiensi dalam pemrosesan data. 'Year-Of-Publication' diubah menjadi integer untuk memudahkan operasi numerik.

### Resolve Missing Value

```python
df.drop(index=df[df["Book-Rating"]==0].index,inplace=True)

df = df.dropna()
missing_values = df.isnull().sum()
if missing_values.sum() == 0:
    print("Berhasil mengatasi missing values. Tidak ada missing values lagi.")
else:
    print("Masih terdapat missing values pada beberapa kolom.")

print(missing_values)
```

**Alasan:** Rating dengan nilai 0 dihapus karena bisa jadi merepresentasikan ketidakhadiran rating daripada rating terendah. Baris dengan missing values juga dihapus untuk memastikan kualitas data dan mencegah error dalam pembuatan model.

### Reset Index

```python
df.reset_index(drop=True,inplace=True)
```

**Alasan:** Reset index dilakukan setelah penghapusan baris untuk memastikan indeks tetap berurutan dan tidak ada gap. Hal ini dilakukan untuk konsistensi dan memudahkan dalam mengakses data berdasarkan indeks.

## 🤖 Modeling
Dalam proyek ini, dua pendekatan pemodelan sistem rekomendasi telah diimplementasikan: Content-Based Filtering dan Collaborative Filtering.

### Content-Based Filtering

Content-Based Filtering diimplementasikan dengan menggunakan TF-IDF Vectorizer dan Cosine Similarity untuk mengidentifikasi kemiripan antara buku berdasarkan atribut tekstual. Selain itu, membatasi jumlah data buku untuk menghindari out of memory error yang mana mengakibatkan Google Colab dan Kaggle auto restart. Berikut langkah-langkah dalam pembuatan model ini:

#### Copy Dataset

Sebelum melakukan modelling, pertama-tama membuat salinan (copy) baru dari DataFrame df dan menyimpannya dalam variabel cbf_df. Secara default, metode .copy() membuat deep copy, artinya seluruh data dan indeks DataFrame disalin secara independen. Perubahan pada cbf_df tidak akan memengaruhi df, begitu juga sebaliknya. Hal ini berguna ketika ingin memanipulasi data tanpa mengubah DataFrame asli. Berikut kode perintahnya.

```python
cbf_df = df.copy()
```

#### Check for Duplicates

Melakukan pengecekan duplikat pada pada kolom 'Book-Title' di DataFrame cbf_df. Berdasarkan outputnya, terdapat data duplikat sebanyak 249288. Untuk menghindari kerancuan, bias, dan kesalahan analisis, data duplikat tersebut akan dihapus.

#### Limiting the Amount of Data

Selanjutnya, melakukan pembatasan  jumlah data buku yang digunakan dalam DataFrame cbf_df hingga maksimal 10.000 baris, serta mengatur ulang indeks DataFrame setelah proses sampling. Hal ini dilakukan untuk mengontrol ukuran dataset agar tidak terlalu besar (maksimal 10.000 buku), yang berguna untuk mengurangi waktu komputasi dan penggunaan memori saat membangun model rekomendasi.

#### Implementation of TF-IDF Vectorizer

Langkah berikutnya melakukan implementasi TF-IDF Vectorizer menggunakan library scikit-learn untuk mengubah data teks menjadi representasi numerik yang dapat digunakan dalam model machine learning, khususnya dalam konteks Content-Based Filtering pada sistem rekomendasi buku.

#### Implementation of Cosine Similarity

Langkah selanjutnya menggunakan cosine similarity untuk merekomendasikan buku berdasarkan kemiripan konten (judul, penulis, penerbit) yang sudah diubah menjadi representasi TF-IDF.

#### Example of Using Content-Based Filtering Recommendations

Sistem rekomendasi Content-Based Filtering pada proyek ini dijalankan menggunakan fungsi berbasis input pengguna. Berikut adalah implementasi kode dan penjelasannya:

```python
# Contoh rekomendasi content-based filtering
def interactive_content_based_recommendation(indices, recommendation_func, fallback=True):
    book_title = input("Masukkan judul buku: ").strip()

    if book_title in indices:
        print(f"\nRekomendasi untuk buku '{book_title}':")
        print(recommendation_func(book_title))
    elif fallback:
        sample_title = indices.index[0]
        print(f"\nBuku '{book_title}' tidak ditemukan dalam database.")
        print(f"Berikut adalah rekomendasi untuk buku '{sample_title}':")
        print(recommendation_func(sample_title))
    else:
        print(f"\nBuku '{book_title}' tidak ditemukan dalam database dan fallback dinonaktifkan.")

# Pemanggilan fungsi:        
interactive_content_based_recommendation(indices, content_based_recommendations)
```

##### Penjelasan Kode

- **Input Pengguna**: Program meminta pengguna memasukkan judul buku melalui `input("Masukkan judul buku: ")`.
- **Pengecekan Judul**: Jika judul yang dimasukkan ada dalam `indices` (yang berisi pemetaan antara judul buku dan indeks baris dalam dataset), maka sistem akan menampilkan rekomendasi buku berdasarkan judul tersebut.
- **Fallback**: Jika judul tidak ditemukan dan fallback diaktifkan (`fallback=True`), sistem akan menampilkan rekomendasi berdasarkan judul buku pertama dalam database sebagai pengganti.
- **Output**: Rekomendasi akan ditampilkan dalam format DataFrame hasil dari fungsi `recommendation_func`, yaitu `content_based_recommendations`.

##### Contoh Output

Ketika pengguna mengetik:

```
Masukkan judul buku: Death Notes
```

Dan buku tersebut ditemukan, maka sistem akan menampilkan:

```
Rekomendasi untuk buku 'Death Notes':
                                             Book-Title         Book-Author  \
7032                                     The Veiled One        Ruth Rendell   
9888                                         Live Flesh        RUTH RENDELL   
9597              Heartstones Harper Short Novel Series        Ruth Rendell   
8722                                           Gangster  Lorenzo Carcaterra   
8582  The Babes in the Wood A Chief Inspector Wexfor...        Ruth Rendell   
8562                         King Henry IV Part 1 Notes    James K.  Lowers   
1752                              Overcoming Overeating  Jane R. Hirschmann   
2410                                  Call in the Night             Howatch   
6126                                       World Before     Ruth Montgomery   
4725                             Mythology Cliffs Notes       James  Weigel   

             Publisher  Year-Of-Publication  Similarity Score  
7032     Fawcett Books                 1993          0.808624  
9888           Fawcett                 1987          0.601159  
9597     Harpercollins                 1987          0.464678  
8722     Fawcett Books                 2002          0.410844  
8582  Crown Publishers                 2003          0.373697  
8562      Cliffs Notes                 1960          0.336894  
1752     Fawcett Books                 1998          0.303785  
2410     Fawcett Books                 1980          0.298184  
6126  Ballantine Books                 1977          0.281394  
4725      Cliffs Notes                 1973          0.272417  
```

##### Catatan
- Nilai **Similarity Score** menunjukkan tingkat kemiripan antara buku yang dimasukkan dan buku-buku lain berdasarkan representasi TF-IDF judul buku.
- Output ini memberikan konteks genre atau penulis yang serupa dengan buku yang dicari, sehingga pengguna dapat menemukan bacaan serupa sesuai preferensi.

### Collaborative Filtering

Collaborative Filtering diimplementasikan menggunakan deep learning dengan TensorFlow dan Keras. Berikut langkah-langkah pemyususan model ini:

#### Filter Dataset

Langkah pertama yaitu memfilter dataset rating buku berdasarkan jumlah minimum rating yang diberikan oleh pengguna dan jumlah minimum rating yang diterima oleh buku, dengan tujuan membersihkan data dan mengurangi sparsity sebelum digunakan dalam model Collaborative Filtering. Selain itu juga dapat meningkatkan performa model.

#### Create Mapping

Langkah berikutnya yaitu  membuat mapping (pemetaan) antara ID asli pengguna dan buku ke indeks numerik yang berurutan, serta melakukan konversi ID asli ke indeks tersebut dalam DataFrame cf_df. Hal ini adalah langkah penting dalam persiapan data untuk model rekomendasi, terutama Collaborative Filtering yang biasanya membutuhkan indeks numerik untuk pengguna dan item.

#### Split Dataset

Selanjutnya,  membagi dataset cf_df menjadi dua bagian: data training dan data testing dengan proporsi tertentu, menggunakan fungsi train_test_split dari library scikit-learn. Pembagian ini penting dalam machine learning untuk melatih model pada data training dan menguji performanya pada data testing yang belum pernah dilihat model sebelumnya.

#### Build Model

Membangun arsitektur model dengan menggunakan layer embedding untuk merepresentasikan pengguna dan buku sebagai vektor berdimensi embedding_size. Kemudian, model menghitung dot product antara embedding pengguna dan buku sebagai fitur utama, lalu memprosesnya melalui beberapa lapisan dense dengan aktivasi ReLU dan dropout untuk mengurangi overfitting. Output model berupa prediksi rating dalam bentuk nilai kontinu dengan aktivasi linear. Model dikompilasi menggunakan fungsi loss Mean Squared Error (MSE) dan dievaluasi dengan metrik Root Mean Squared Error (RMSE) serta Mean Absolute Error (MAE).

#### Model Initiation

Langkah selanjutnya melakukan inisiasi model untuk mendapatkan jumlah total pengguna dan buku dari dataset serta membangun model dengan parameter tersebut.

#### Normalization

Pada tahap ini, melakukan normalisasi rating ke skala 0-1 agar model lebih stabil saat pelatihan.

#### Prepare Data Training and Testing

Langkah berikutnya mengambil input user dan buku dalam bentuk indeks numerik dan target rating untuk training dan testing.

#### Training Model

Selanjutnya melakukan training model selama 10 epoch dengan batch size 256, dimana pada setiap epoch performa model divalidasi menggunakan data testing untuk memantau kemajuan pelatihan. Selama proses ini, objek history menyimpan riwayat pelatihan yang dapat digunakan untuk analisis dan evaluasi performa model secara mendalam setelah pelatihan selesai. 

#### Plot Loss

Membuat visualisasi plot loss untuk membantu memantau dan menganalisis performa model selama pelatihan dengan melihat tren loss dan RMSE pada data training dan validasi. Visualisasi ini sangat penting untuk memastikan model yang dibangun efektif dan tidak terlalu fit terhadap data training saja.

#### Example of Using Collaborative Filtering Recommendations 

Setelah memastikan tidak underfitting da overfitting, langkah selanjutnya yaitu implementasi fungsi rekomendasi berbasis Collaborative Filtering yang menggunakan model prediksi rating untuk semua buku yang ada, kemudian memilih buku dengan prediksi rating tertinggi sebagai rekomendasi personal untuk pengguna tertentu. Fungsi ini memudahkan mendapatkan rekomendasi yang relevan berdasarkan preferensi yang dipelajari model dari data historis interaksi pengguna dan buku. Berikut cuplikan kode dan penjelasannya:

```python
sample_user = user_ids[0]
print(f"\nRekomendasi buku untuk pengguna {sample_user}:")
collab_recommendations = get_collaborative_recommendations(sample_user, model)
print(collab_recommendations)
```

##### Penjelasan Kode

- Kode `sample_user = user_ids[0]:` berfungsi untuk memilih salah satu pengguna dari dataset untuk dijadikan sampel (dalam hal ini pengguna pertama dalam daftar user_ids).

- Kode `print(f"\nRekomendasi buku untuk pengguna {sample_user}:"):` berfungsi untuk menampilkan ID pengguna yang sedang direkomendasikan buku.

- Fungsi `get_collaborative_recommendations()` digunakan untuk menghasilkan rekomendasi buku berdasarkan model Collaborative Filtering yang telah dilatih sebelumnya.

- Kode `print(collab_recommendations)` berfungsi untuk menampilkan daftar buku rekomendasi yang telah disortir berdasarkan skor prediksi.

##### Contoh Output

```
Rekomendasi buku untuk pengguna 11676:
                                          Book-Title        Book-Author  \
0                                    Purity in Death          J.D. Robb   
1   This Year It Will Be Different And Other Stories       Maeve Binchy   
2  Left Behind A Novel of the Earth s Last Days L...         Tim Lahaye   
3                                  The Street Lawyer       JOHN GRISHAM   
4                                      LONESOME DOVE     Larry McMurtry   
5                                  Breathing Lessons         Anne Tyler   
6                                  The Joy Luck Club            Amy Tan   
7                                    The Tao of Pooh      Benjamin Hoff   
8                                         Seabiscuit  LAURA HILLENBRAND   
9  Life s Little Instruction Book Life s Little I...   H. Jackson Brown   

   Predicted Rating  
0           7.90945  
1           7.90945  
2           7.90945  
3           7.90945  
4           7.90945  
5           7.90945  
6           7.90945  
7           7.90945  
8           7.90945  
9           7.90945  
```

##### Catatan

- Predicted Rating merupakan hasil prediksi model terhadap seberapa besar kemungkinan pengguna akan menyukai buku tersebut. Skala awal rating dinormalisasi antara 0–1 saat training dan kemudian dikembalikan ke skala 0–10 saat evaluasi atau interpretasi hasil.
- Rating bernilai sama karena struktur model yang sederhana (menggunakan dot product dan dense layers terbatas), prediksi untuk banyak buku bisa bernilai sama. Hal ini menunjukkan bahwa model bisa dikembangkan lebih lanjut dengan memperkaya fitur atau menambah kompleksitas model.

## 🖇️ Evaluation

Dalam proyek ini, beberapa metrik evaluasi digunakan untuk menilai performa kedua model rekomendasi:

### Content-Based Filtering

#### 1. Precision@k

Precision@k mengukur proporsi item yang relevan dari k rekomendasi teratas yang diberikan kepada pengguna.

**Cara Kerja**:

- Sistem merekomendasikan k item teratas untuk pengguna
- Dihitung berapa banyak item dari rekomendasi tersebut yang benar-benar relevan
- Relevansi ditentukan berdasarkan buku yang disukai pengguna (rating ≥ 8)
- Nilai berkisar antara 0 (tidak ada yang relevan) hingga 1 (semua relevan)

#### 2. Coverage

Coverage mengukur proporsi item dalam katalog yang dapat direkomendasikan oleh sistem.

**Cara Kerja**:

- Sistem merekomendasikan item untuk sampel buku
- Semua rekomendasi dikumpulkan dalam satu set
- Dihitung berapa persen dari total katalog yang tercakup dalam rekomendasi
- Nilai tinggi menunjukkan sistem mampu merekomendasikan berbagai macam item

#### 3. Diversity

Diversity mengukur keragaman item dalam rekomendasi yang diberikan.

**Cara Kerja**:

- Dihitung similaritas kosinus antar semua pasangan item dalam rekomendasi
- Diambil rata-rata dari semua nilai similaritas
- Diversity = 1 - rata-rata similaritas
- Nilai tinggi menunjukkan rekomendasi beragam (item tidak terlalu mirip)

#### Hasil Evaluasi

Berikut perintah untuk menhasilkan hasil evaluasi model Content-Based Filtering:

```python
# Evaluasi model Content-Based Filtering
precision_at_k = evaluate_content_based_precision_at_k(test_data)
coverage = evaluate_content_based_coverage(test_data)
diversity = evaluate_content_based_diversity(test_data)

print("\nEvaluasi Model Content-Based Filtering:")
print(f"Precision@10: {precision_at_k:.4f}")
print(f"Coverage: {coverage:.4f}")
print(f"Diversity: {diversity:.4f}")
```

Output dari perintah di atas adalah sebagai berikut:

```
Evaluasi Model Content-Based Filtering:
Precision@10: 0.0018
Coverage: 0.0198
Diversity: 0.7925
```

Berikut penjelsan singkat mengenai hasil output di atas:

##### **Precision**

Nilai 0.0018 (atau 0.18%) berarti bahwa rata-ratanya hanya sekitar 0.18% dari 10 rekomendasi teratas yang diberikan oleh model Content-Based Filtering yang dianggap relevan oleh pengguna. 

##### **Coverage**

Nilai 0.0198 (atau 1.98%) mengindikasikan bahwa model Content-Based Filtering hanya mampu merekomendasikan kurang dari 2% dari total buku yang tersedia dalam katalog.

##### **Diversity**

Nilai 0.7925 adalah nilai yang relatif tinggi (mendekati 1). Hal ini menunjukkan bahwa meskipun model kesulitan memberikan rekomendasi yang relevan (seperti terlihat dari Precision@10 yang rendah), buku-buku yang direkomendasikan dalam daftar 10 teratas cenderung cukup berbeda satu sama lain atau tidak terlalu mirip dalam hal konten (judul, penulis, penerbit) berdasarkan representasi TF-IDF.

### Collaborative Filtering

#### 1. RMSE (Root Mean Squared Error)

RMSE mengukur akurasi prediksi rating dengan menghitung akar kuadrat dari rata-rata error kuadrat.

**Cara Kerja**:

- Menghitung selisih antara rating aktual dan prediksi untuk setiap pasangan user-item
- Setiap selisih dikuadratkan untuk menghilangkan nilai negatif
- Diambil rata-rata dari semua nilai kuadrat selisih
- Dihitung akar kuadrat dari hasil tersebut
- Nilai rendah menunjukkan prediksi yang akurat

#### 2. MAE (Mean Absolute Error)

MAE mengukur rata-rata kesalahan absolut antara rating prediksi dan aktual.

**Cara Kerja**:

- Menghitung selisih absolut antara rating aktual dan prediksi
- Diambil rata-rata dari semua nilai selisih absolut
- Nilai rendah menunjukkan prediksi yang akurat

#### 3. Recall@k

Recall@k mengukur proporsi item relevan yang berhasil direkomendasikan dari total item relevan.

**Cara Kerja**:

- Sistem merekomendasikan k item teratas untuk pengguna
- Dihitung berapa banyak item dari rekomendasi tersebut yang benar-benar relevan
- Relevansi ditentukan berdasarkan threshold rating (normalized_rating ≥ 0.6)
- Nilai dibagi dengan total item relevan yang diketahui untuk pengguna
- Nilai tinggi menunjukkan sistem mampu merekomendasikan sebagian besar item yang relevan

#### 4. Hit Rate

Hit Rate mengukur proporsi pengguna yang mendapatkan setidaknya satu rekomendasi yang relevan.

**Cara Kerja**:

- Untuk setiap pengguna, sistem memberikan k rekomendasi teratas
- Dihitung berapa pengguna yang setidaknya satu rekomendasinya relevan
- Nilai dibagi dengan total jumlah pengguna
- Nilai tinggi menunjukkan sistem mampu memberikan rekomendasi yang relevan kepada banyak pengguna

#### Hasil Evaluasi

Berikut perintah untuk menhasilkan hasil evaluasi model Collaborative Filtering:

```python
# Evaluasi model Collaborative Filtering
recall_at_10 = evaluate_recall_at_k(model, test_data, k=10)
hit_rate = evaluate_hit_rate(model, test_data, k=10)
rmse_actual, mae_actual = calculate_rating_prediction_accuracy(model, test_data)

print("\nEvaluasi Model Collaborative Filtering:")
print(f"RMSE (skala 0-1): {rmse:.4f}")
print(f"MAE (skala 0-1): {mae:.4f}")
print(f"RMSE (skala asli 1-10): {rmse_actual:.4f}")
print(f"MAE (skala asli 1-10): {mae_actual:.4f}")
print(f"Recall@10: {recall_at_10:.4f}")
print(f"Hit Rate: {hit_rate:.4f}")

```

Output dari perintah di atas adalah sebagai berikut:

```
Evaluasi Model Collaborative Filtering:
RMSE (skala 0-1): 0.1783
MAE (skala 0-1): 0.1402
RMSE (skala asli 1-10): 1.7730
MAE (skala asli 1-10): 1.4195
Recall@10: 0.0000
Hit Rate: 0.0100
```

Berikut penjelsan singkat mengenai hasil output di atas:

##### 1. **RMSE (Root Mean Squared Error)**

- Skala 0-1 (0.1783) merupakan RMSE yang dihitung pada skala rating yang sudah dinormalisasi (antara 0 dan 1). Nilai 0.1783 menunjukkan rata-rata besarnya error (kesalahan) prediksi pada skala ini. Semakin mendekati 0, semakin baik.
- Skala Asli 1-10 (1.7730) merupakan RMSE pada skala rating asli (1 sampai 10) yang rata-rata prediksi rating yang diberikan model berbeda sekitar 1.77 poin dari rating asli yang diberikan pengguna. RMSE memberikan bobot lebih besar pada kesalahan yang besar. Nilai ini menunjukkan ada selisih yang cukup terasa antara prediksi dan rating sebenarnya.

##### 2. **MAE (Mean Absolute Error)**

- Skala 0-1 (0.1402) merupakan MAE pada skala rating yang dinormalisasi. Nilai ini menunjukkan rata-rata selisih absolut (tanpa memandang positif atau negatif) antara prediksi dan rating asli pada skala 0-1.
- Skala Asli 1-10 (1.4195) merupakan MAE pada skala rating asli. Secara rata-rata, prediksi model meleset sekitar 1.42 poin dari rating asli pengguna. Kesalahan rata-rata 1.42 poin pada skala 10 poin cukup signifikan.

##### 3. **Recall@10 (0.0000)**

Hasil Recall@10: 0.0000 menunjukkan bahwa model Collaborative Filtering Anda, meskipun mungkin bisa memprediksi rating dengan akurasi tertentu (seperti yang ditunjukkan oleh RMSE/MAE), sangat buruk dalam menempatkan buku-buku yang benar-benar relevan bagi pengguna ke dalam 10 rekomendasi teratasnya. Pengguna kemungkinan besar tidak akan menemukan buku yang mereka sukai dalam 10 saran pertama yang diberikan oleh model ini.

##### 4. **Hit Rate (0.0100)**

Hit Rate mengukur persentase pengguna yang mendapatkan setidaknya satu rekomendasi yang relevan dalam daftar top-k (dalam hal ini, top 10). Nilai 0.0100 (atau 1%) berarti hanya 1% dari pengguna yang diuji coba menerima setidaknya satu buku yang relevan dalam 10 rekomendasi teratas mereka. Ini merupakan nilai yang sangat rendah, yang mana mengindikasikan bahwa sebagian besar pengguna (99%) tidak mendapatkan satu pun rekomendasi yang relevan dari model ini dalam 10 saran teratas.

### Kesimpulan

**Perbandingan Model Sistem Rekomendasi**:
- **Content-Based Filtering**:
  - Kelebihan:

    1. Dapat memberikan rekomendasi yang spesifik berdasarkan karakteristik item
    2. Tidak memerlukan data pengguna lain (cold-start untuk pengguna baru tidak menjadi masalah)
    3. Dapat memberikan rekomendasi untuk item yang belum pernah dirating
    4. Dapat memberikan penjelasan mengapa suatu item direkomendasikan

  - Kekurangan:

    1. Cenderung over-specialized (rekomendasi terlalu mirip dan kurang beragam)
    2. Tidak dapat merekomendasikan berdasarkan preferensi orang lain yang serupa
    3. Keterbatasan fitur mempengaruhi kualitas rekomendasi
    4. Sulit merekomendasikan item baru yang belum memiliki fitur yang cukup

- **Collaborative Filtering**:
  - Kelebihan:
    1. Dapat menemukan pola yang tidak terlihat dalam fitur item
    2. Mampu merekomendasikan item yang tidak mirip dengan yang pernah dikonsumsi (serendipity)
    3. Kualitas rekomendasi meningkat seiring bertambahnya data
    4. Tidak memerlukan informasi konten dari item

  - Kekurangan:
    1. Masalah cold-start untuk pengguna baru atau item baru
    2. Memerlukan data rating yang cukup untuk membuat prediksi akurat
    3. Skalabilitas menjadi masalah saat dataset sangat besar
    4. Sulit menjelaskan alasan di balik rekomendasi

Berdasarkan evaluasi, dapat disimpulkan bahwa kedua model rekomendasi, baik Content-Based Filtering maupun Collaborative Filtering, menunjukkan kegagalan dalam memberikan rekomendasi yang akurat dan relevan sebagaimana tercermin dari nilai "Precision@k / Recall@k" yang sangat rendah. Meskipun demikian, kedua model ini cukup berhasil dalam menyajikan rekomendasi yang beragam, dengan model Content-Based Filtering menunjukkan sedikit keunggulan dibandingkan Collaborative Filtering dalam aspek diversitas ini.
