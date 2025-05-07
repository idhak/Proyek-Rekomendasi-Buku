# Laporan Proyek Machine Learning - Idha Kurniawati

## 🔎 Project Overview

Buku adalah jendela dunia. Salah satu cara untuk mendapatkan informasi dan mempelajari sesuatu adalah dengan membaca buku. Buku bukan sekadar kumpulan data, melainkan jalan menuju perubahan. Setiap aspek kehidupan manusia dipengaruhi oleh kemajuan teknologi. Sekarang buku tidak lagi hanya dijual secara *offline* di toko fisik. Perkembangan teknologi telah memungkinkan buku dijual di banyak toko *online* melalui platform *e-commerce*, media sosial, dan situs web pribadi toko buku. Selain itu, buku juga tersedia dalam bentuk *e-book*. *E-book* adalah versi digital dari buku cetak dalam format tertentu (misalnya PDF, EPUB atau MOBI) yang memungkinkan pembaca untuk mengakses dan membaca konten buku menggunakan perangkat digital mereka. 

UNESCO menyatakan bahwa indeks minat baca masyarakat Indonesia hanya 0,001% atau dari seribu orang Indonesia.  Dalam laman resmi Kementerian Komunikasi dan Informatika Republik Indonesia (Kemenkominfo) juga mengumumkan hasil penelitian yang dilakukan oleh Central Connecticut State University pada Maret 2016. Hasilnya menunjukkan bahwa Indonesia menduduki peringkat ke-60 dari 61 negara dalam hal minat membaca, tepat di bawah Thailand (59) dan di atas Bostwana (61). Sementara itu, Programme for International Student Assessment (PISA), sebuah penelitian internasional yang menilai kualitas sistem pendidikan dengan mengukur hasil belajar yang penting untuk keberhasilan di abad ke-21, melaporkan bahwa hasil literasi membaca Indonesia meningkat 5 posisi dibandingkan tahun 2018. Akibatnya, peringkat tersebut menurun, dan Indonesia masih berada di peringkat ke-11 terbawah dari 81 negara yang disurvei.

Hal ini akan memengaruhi pemahaman teknologi dan sains. Lebih jauh lagi, minimnya kegiatan membaca terutama di kalangan anak muda dapat berdampak buruk bagi negara karena kehilangan sumber daya manusia yang produktif dan berkualitas. Oleh karena itu, untuk mencetak generasi yang cerdas dan produktif, perlu dilakukan upaya peningkatan minat baca di Indonesia. Menyediakan berbagai jenis bahan bacaan untuk mendukung pembelajaran dan mendorong masyarakat agar mencintai buku merupakan salah satu cara untuk meningkatkan minat baca masyarakat. Langkah lain yang dapat dilakukan untuk meningkatkan minat membaca di Indonesia, yaitu dengan menggunakan sistem rekomendasi. Sistem rekomendasi memungkinkan pembaca menemukan referensi baru untuk buku yang sesuai dengan kategori yang disukai oleh pembaca sebelumnya. Beberapa sistem rekomendasi terdiri dari  *content-based filtering* dan *collaborative filtering*. *Content-based filtering* adalah metode yang memberikan saran kepada pengguna berdasarkan preferensi pengguna dan hubungan antara metadata suatu item. *Collaborative filtering* adalah model yang memberikan rekomendasi berdasarkan kumpulan pendapat dan minat pengguna, biasanya diberikan oleh pengguna dalam bentuk penilaian pada suatu item. Dengan mengukur kemiripan dari setiap buku, sistem dapat membuat skor untuk membuat rekomendasi yang sesuai dengan metadata buku tersebut. Melalui sistem rekomendasi ini, pembaca diharapkan dapat menambahkan referensi baru berdasarkan buku yang diminati sebelumnya.

Tujuan proyek ini adalah untuk mengembangkan sistem rekomendasi buku yang efektif menggunakan Book Recommendation Dataset dari Kaggle. Dengan menerapkan *content-based filtering* dan *collaborative filtering*, proyek ini bertujuan untuk memberikan rekomendasi buku yang relevan dengan preferensi pengguna, meningkatkan pengalaman membaca, dan berpotensi meningkatkan penjualan dan keterlibatan pada platform buku digital.

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
- Pendekatan *Content Based Filtering* adalah mempelajari profil minat pengguna baru berdasarkan data penilaian objek sebelumnya untuk merekomendasikan item serupa yang disukai di masa lalu atau saat ini dilihat, di mana akurasi rekomendasi meningkat seiring dengan bertambahnya informasi pengguna. Berikut implementasi *Content Based Filtering*.
    - Mengekstrak fitur dari data buku menggunakan *TF-IDF vectorizer*.
    - Menghitung *similarity matrix* menggunakan *cosine similarity*.
    - Membuat fungsi rekomendasi yang dapat menyarankan buku serupa berdasarkan judul buku yang diinput.
- Pendekatan *collaborative filtering* adalah merekomendasikan sesuatu berdasarkan perilaku pengguna lain yang memiliki preferensi serupa.  Berikut implementasi *collaborative filtering*.
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
Berdasarkan pengecekan, dataset books menunjukkan adanya *missing values* pada kolom `Book-Author`, `Publisher`, dan `Image-URL-L`.

##### Pengecekan Duplikat.
Berdasarkan pengecekan, dataset books tidak memiliki duplikat data.

##### Visualisasi
Berikut beberapa visualisasi pada dataset books:

![10 Penulis Buku Terbanyak](https://github.com/user-attachments/assets/8389042d-1f62-4c94-9bd6-11f6709ff02d)


Berdasarkan visualisasi di atas, dapat disimpulkan bahwa:

- Agatha Christie adalah penulis dengan jumlah buku terbanyak di antara 10 penulis yang ditampilkan, yaitu sebesar 632 buku. Jumlah ini secara signifikan lebih banyak dibandingkan penulis lainnya dalam daftar.
- Charles Dickens memiliki jumlah buku paling sedikit di antara 10 penulis ini, yaitu sebesar 302 buku.

![Visualisasi 10 Penerbit Terbanyak](https://github.com/user-attachments/assets/bf857766-25a5-45ee-8bd3-532f2d06dfc4)

    
Berdasarkan visualisasi di atas, dapat disimpulkan bahwa:

- Harlequin adalah penerbit dengan jumlah buku terbanyak di antara 10 penerbit yang ditampilkan, yaitu sebesar 7535 buku. Jumlah ini jauh lebih banyak dibandingkan penerbit lainnya dalam daftar.
- Penerbit Warner Books memiliki jumlah buku paling sedikit di antara 10 penerbit ini, yaitu sebesar 2727 buku.

![Visualisasi Panjang Judul Buku](https://github.com/user-attachments/assets/b2ee7d4f-f623-4192-83e6-d457887d1f47)

    
Berdasarkan visualisasi di atas, dapat disimpulkan bahwa:

- Sebagian besar judul buku memiliki panjang yang relatif pendek. Puncak kurva KDE dan batang-batang tertinggi berada di sekitar panjang judul antara 10 hingga 30 karakter.
- Distribusi panjang judul buku miring ke kanan (*positively skewed*). Hal ini berarti sebagian besar data terkumpul di sisi kiri (judul pendek), dan ada "ekor" yang memanjang ke kanan yang menunjukkan adanya sejumlah kecil judul buku yang sangat panjang.
- Frekuensi buku yang panjang judulnya di atas 100 karakter sangat rendah dan mengalami penurunan seiring bertambahnya panjang.
    
    
#### Analisis Univariat pada Dataset Ratings

##### Pengecekan Missing Values.
Berdasarkan pengecekan, dataset ratings menunjukkan tidak ada *missing values*.

##### Pengecekan Duplikat.
Berdasarkan pengecekan, dataset ratings tidak memiliki duplikat data.

##### Visualisasi
Berikut beberapa visualisasi pada dataset ratings:

![Distribusi Rating Buku](https://github.com/user-attachments/assets/5feea789-41e1-48e0-88eb-d3c59cb1d8ae)


Berdasarkan visualisasi di atas, dapat disimpulkan bahwa:

- Rating 0 memiliki jumlah yang sangat dominan dibandingkan dengan rating lainnya. Terdapat 716.109 rating dengan nilai 0.
- Rating 1 memiliki jumlah yang paling sedikit, yaitu sebesar 1770 rating.
- Distribusi rating tidak merata. Ada konsentrasi besar pada rating 0, diikuti oleh peningkatan jumlah rating hingga nilai 8, dan kemudian sedikit penurunan pada nilai 9 dan 10.

![10 User Paling Aktif Memberi Rating](https://github.com/user-attachments/assets/0bfae675-907a-43ac-9497-a2715a04f277)


Berdasarkan visualisasi di atas, dapat disimpulkan bahwa:

- User dengan ID 11676 adalah user yang paling aktif dalam memberikan rating, dengan jumlah rating mencapai 13602. Jumlah ini jauh lebih tinggi dibandingkan user aktif lainnya dalam grafik.
- Aktivitas rating menurun secara signifikan setelah user pertama. 
- User dengan ID 235105 adalah user yang memberikan rating paling sedikit pada grafik di atas, yaitu sebesar 3067.

![Top 10 Buku dengan Rating Terbanyak](https://github.com/user-attachments/assets/17b4322b-8856-41db-a396-e63c062910ce)


Berdasarkan visualisasi di atas, dapat disimpulkan bahwa:

- Buku dengan ISBN 0971880107 adalah buku yang paling banyak dirating, dengan jumlah rating mencapai 2502. Jumlah ini jauh lebih tinggi dibandingkan buku-buku lain dalam grafik.
- Buku dengan ISBN 0671027360 adalah buku kesepuluh yang paling banyak dirating, dengan jumlah rating 586.

#### Analisis Univariat pada Dataset Users

##### Pengecekan Missing Values.
Berdasarkan pengecekan, dataset users menunjukkan adanya *missing values* pada kolom Age sebesar 110762.

##### Pengecekan Duplikat.
Berdasarkan pengecekan, dataset users tidak memiliki duplikat data.

##### Visualisasi
Berikut beberapa visualisasi pada dataset users:

![Distribusi Umur Pengguna](https://github.com/user-attachments/assets/25752ce7-8553-4ed1-85c5-974eec2fa626)


Berdasarkan visualisasi di atas, dapat disimpulkan bahwa:

- Distribusi umur pengguna miring ke kanan (*positively skewed*). Ini berarti sebagian besar data terkumpul di sisi kiri (umur muda), dan ada "ekor" yang memanjang ke kanan yang menunjukkan adanya sejumlah kecil pengguna dengan umur yang lebih tua.
- Sebagian besar pengguna berada dalam rentang umur dewasa muda hingga dewasa. Puncak kurva KDE dan batang-batang tertinggi berada di sekitar umur 20 hingga 40 tahun.
- Jumlah pengguna menurun seiring bertambahnya umur setelah rentang 40 tahun. Frekuensi pengguna dengan umur di atas 60 tahun semakin rendah.
- Terdapat beberapa lonjakan kecil pada umur yang tidak lazim (sekitar 100 sampai dengan 150 tahun). Lonjakan ini kemungkinan merupakan kesalahan input data atau nilai ekstrem yang perlu diselidiki lebih lanjut.

![10 Lokasi dengan Jumlah Pengguna Terbanyak](https://github.com/user-attachments/assets/d2de2c75-ee47-4db4-bbce-6b72317f682e)


Berdasarkan visualisasi di atas, dapat disimpulkan bahwa:

- London, England, United Kingdom adalah lokasi dengan jumlah pengguna terbanyak, yaitu sebesar 2506 pengguna. Jumlah ini secara signifikan lebih tinggi dibandingkan lokasi lainnya dalam grafik.
- Vancouver, British Columbia, Canada memiliki jumlah pengguna paling sedikit di antara 10 lokasi teratas, yaitu sebesar 1359 pengguna.

![10 Negara dengan Jumlah Pengguna Terbanyak](https://github.com/user-attachments/assets/f05cc563-07ad-4405-9aaa-9d5e9d32f13e)


Berdasarkan visualisasi di atas, dapat disimpulkan bahwa:

- USA (Amerika Serikat) adalah negara dengan jumlah pengguna terbanyak, yaitu sebesar 139711 pengguna. Jumlah ini jauh lebih tinggi dibandingkan negara-negara lain dalam daftar.
-  Portugal memiliki jumlah pengguna yang paling sedikit di antara 10 negara teratas, yaitu sebesar 3325 pengguna serta penurunan yang cukup tajam dibandingkan negara-negara sebelumnya.

## 🧮 Data Preprocessing

Pada tahap ini, menggabungkan dataset `books` dan `ratings` lalu menyimpannya ke dalam dataset baru yang bernama `books_ratings`. Berikut kode perintah dari merger dataset `books` dan `ratings`.

```python
books_ratings=books.merge(ratings,on="ISBN")
books_ratings.head()
```

## ⚙️ Data Preparation

Terdapat beberapa teknik data preparation yang dilakukan pada bagian ini yaitu sebagai berikut.

### Copy Dataset

Pada tahap ini, membuat salinan (*copy*) dari **dataframe** `books_ratings` dan menyimpannya ke variabel baru bernama `df` terlebih dahulu agar perubahan yang dilakukan pada `df` tidak akan memengaruhi **dataframe** asli `books_ratings`. Berikut kode perintahnya.

```python
df = books_ratings.copy()
```

### Clean Book-Title

```python
df["Book-Title"] = df["Book-Title"].apply(lambda x: re.sub("[\W_]+", " ", x).strip())
```

Pembersihan judul buku dengan menghapus karakter non-alfanumerik dan spasi berlebih dilakukan untuk standarisasi data teks. Hal ini akan meningkatkan akurasi dalam perbandingan judul buku dan mencegah duplikasi akibat perbedaan format penulisan.

### Drop Irrelevant Columns

```python
df.drop(columns=["ISBN", "Image-URL-S", "Image-URL-M", "Image-URL-L"], inplace=True)
```

Kolom `ISBN` dan URL gambar dihapus karena tidak relevan dalam pembuatan model rekomendasi berbasis konten atau kolaboratif. `ISBN` merupakan identifier yang tidak membawa informasi konten buku, sementara URL gambar tidak diperlukan untuk analisis preferensi.

### Drop Ratings == 0 and Missing Values

```python
df.drop(index=df[df["Book-Rating"]==0].index, inplace=True)
df.dropna(inplace=True)
```

Baris dengan nilai kosong dan rating = 0 dihapus karena tidak memberikan informasi preferensi pengguna.

### Reset Index

```python
df.reset_index(drop=True,inplace=True)
```

Reset index dilakukan setelah penghapusan baris untuk memastikan indeks tetap berurutan dan tidak ada gap. Hal ini dilakukan untuk konsistensi dan memudahkan dalam mengakses data berdasarkan indeks.

### Remove DuplicateS/Handling Duplicate untuk Content-Based Filtering

```python
cbf_df = df.drop_duplicates('Book-Title')
```

Data duplikat pada kolom judul buku dihapus untuk menghindari bias dan pengulangan.

### Sampling Data untuk Content-Based Filtering

```python
cbf_df = cbf_df.sample(10000, random_state=42)
```

Membatasi jumlah maksimum buku sebesar 10.000 agar menghindari *Out of Memory* saat proses *similarity*.

### Ekstraksi Fitur dengan TF-IDF untuk Content-Based Filtering

```python
cbf_df['content'] = cbf_df['Book-Title'] + ' ' + cbf_df['Book-Author'] + ' ' + cbf_df['Publisher']
tfidf = TfidfVectorizer(stop_words='english', max_features=5000)
tfidf_matrix = tfidf.fit_transform(cbf_df['content'])
```

Fitur teks digabung dari kolom `Book-Title`, `Book-Author`, dan `Publisher`. Kemudian ditransformasikan ke bentuk vektor numerik menggunakan TF-IDF.

### Filtering Data untuk Collaborative Filtering

```python
book_counts = df['Book-Title'].value_counts()
user_counts = df['User-ID'].value_counts()
filtered_books = book_counts[book_counts >= 15].index
filtered_users = user_counts[user_counts >= 15].index
cf_df = df[(df['Book-Title'].isin(filtered_books)) & (df['User-ID'].isin(filtered_users))]
```

Melakukan filtering user dan buku dengan minimal 15 rating, sehingga data yang dihasilkan `cf_df` lebih cocok untuk dianalisis menggunakan teknik *collaborative filtering*.

### Mapping Data untuk Collaborative Filtering

```python
user_ids = cf_df['User-ID'].unique().tolist()
book_ids = cf_df['Book-Title'].unique().tolist()
user_to_index = {user: i for i, user in enumerate(user_ids)}
book_to_index = {book: i for i, book in enumerate(book_ids)}
cf_df['user_index'] = cf_df['User-ID'].map(user_to_index)
cf_df['book_index'] = cf_df['Book-Title'].map(book_to_index)
```

Melakukan mapping data yang bertujuan untuk mengubah ID pengguna dan judul buku (yang berupa string atau angka asli) menjadi angka berurutan. Hal ini sering dilakukan untuk memudahkan pemrosesan oleh model *machine learning* terutama model yang bekerja dengan matriks atau *array* numerik dan membuat representasi data yang lebih ringkas dalam beberapa algoritma.

### Split Train/Test untuk Collaborative Filtering

```python
train_data, test_data = train_test_split(cf_df, test_size=0.2,  random_state=42)
```

Dataset *collaborative filtering* dibagi menjadi *data training* dan *testing* dengan rasio 80:20.



## 🤖 Modeling
Dalam proyek ini, dua pendekatan pemodelan sistem rekomendasi telah diimplementasikan yaitu *content-based filtering* dan *collaborative filtering*.

### Content-Based Filtering

*Content-based filtering* diimplementasikan dengan menggunakan *TF-IDF vectorizer* dan *cosine similarity* untuk mengidentifikasi kemiripan antara buku berdasarkan atribut tekstual. Alasan menggunakan model ini karena tidak membutuhkan data pengguna lain dan cocok untuk *cold-start* pengguna.

Cara kerjanya model ini, yaitu pertama memeriksa apakah judul buku ada dalam *database* (*dictionary indices*); jika tidak ditemukan, fungsi mengembalikan pesan *error*. Jika buku ditemukan, fungsi mengambil indeks buku tersebut, kemudian mengakses nilai kesamaan buku ini dengan semua buku lain dari matriks `cosine_sim`. Hasil kesamaan dikonversi menjadi list dan diurutkan dari tertinggi ke terendah, mengabaikan kesamaan dengan dirinya sendiri (indeks ke-0), dan hanya mengambil `top_n` buku teratas. Fungsi kemudian mengekstrak indeks buku-buku yang direkomendasikan, mengambil informasi buku (`Book-Title`, `Book-Author`, `Publisher`, `Year-Of-Publication`) dari **dataframe** `cbf_df`, menambahkan kolom skor kesamaan, dan mengembalikan hasil rekomendasi final.

#### Example of Using Content-Based Filtering Recommendations

Sistem rekomendasi *content-based filtering* pada proyek ini dijalankan menggunakan fungsi berbasis input pengguna. Berikut adalah implementasi kode dan penjelasannya:

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

Fungsi `interactive_content_based_recommendation` adalah antarmuka interaktif untuk sistem rekomendasi *content-based filtering*. Cara kerjanya, yaitu fungsi meminta pengguna memasukkan judul buku, lalu memeriksa apakah judul tersebut ada dalam `indices`. Jika ditemukan, fungsi memanggil fungsi rekomendasi yang diberikan (recommendation_func) dengan judul buku tersebut dan menampilkan hasilnya. Jika buku tidak ditemukan dan parameter `fallback` diaktifkan (default: True), fungsi akan mengambil judul buku pertama dari `indices` sebagai alternatif, memberitahu pengguna bahwa buku yang dicari tidak ditemukan, dan menampilkan rekomendasi untuk buku alternatif tersebut. Jika fallback dinonaktifkan, fungsi hanya memberitahu pengguna bahwa buku tidak ditemukan tanpa memberikan rekomendasi alternatif. Fungsi ini dipanggil dengan `indices` (*dictionary* judul buku dan indeksnya) dan `content_based_recommendations` (fungsi yang menghitung rekomendasi) sebagai parameter.

##### Contoh Output

Ketika pengguna mengetik:

```
Masukkan judul buku: Death Notes
```

Dan buku tersebut ditemukan, maka sistem akan menampilkan:

```
Rekomendasi untuk buku 'Death Notes':
                                             Book-Title      Book-Author  \
1992                                     The Veiled One     Ruth Rendell   
3376  Sins of the Fathers Formerly Titled a New Leas...     Ruth Rendell   
8996                                     Phantom in Rot     Ruth Rendell   
6286                          Death of a Travelling Man     M. C. Beaton   
7529                                   One Dollar Death    Richard Barth   
7957              Heartstones Harper Short Novel Series     Ruth Rendell   
4627                         Das geheime Haus des Todes     Ruth Rendell   
8289                              It s My Birthday Suit        Bil Keane   
8093                 Blood Lines Long and Short Stories     Ruth Rendell   
2183                                     A Book of Ruth  Syrell R. Leahy   

             Publisher Year-Of-Publication  Similarity Score  
1992     Fawcett Books                1993          0.797992  
3376  Ballantine Books                1990          0.529843  
8996          Goldmann                2000          0.489507  
6286     Fawcett Books                1996          0.470414  
7529     Fawcett Books                1991          0.468697  
7957     Harpercollins                1987          0.454255  
4627          Goldmann                1995          0.421677  
8289     Fawcett Books                1984          0.415223  
8093  Random House Inc                1996          0.374384  
2183      Bantam Books                1982          0.372153   
```


### Collaborative Filtering

Model *collaborative filtering* ini menggunakan *neural network*. Pertama, model dibuat dengan dua input (user dan buku) yang diubah menjadi vektor *embedding* 32-dimensi, kemudian di-*flatten* dan digabungkan. Vektor gabungan diproses melalui dua hidden layer (64 dan 32 neuron) dengan aktivasi ReLU, BatchNormalization, dan Dropout (0.3), berakhir pada output layer dengan 1 neuron untuk prediksi rating. Model dikompilasi dengan optimizer AdamW, fungsi loss MSE, dan metrik MAE, lalu dilatih dengan data rating yang dinormalisasi menggunakan *early stopping*. Fungsi `get_collaborative_recommendations` menggunakan model ini untuk memprediksi preferensi pengguna terhadap semua buku dengan mengambil indeks pengguna, menciptakan *array* berisi semua indeks buku, memprediksikan rating untuk setiap kombinasi pengguna-buku, mengurutkan hasilnya, dan mengembalikan top-n buku dengan prediksi rating tertinggi.

#### Plot Loss

Membuat visualisasi plot loss untuk membantu memantau dan menganalisis performa model selama pelatihan dengan melihat tren loss dan RMSE pada data training dan validasi. Visualisasi ini sangat penting untuk memastikan model yang dibangun efektif dan tidak terlalu fit terhadap data training saja.

#### Example of Using Collaborative Filtering Recommendations 

Setelah memastikan tidak *underfitting* dan *overfitting*, langkah selanjutnya yaitu implementasi fungsi rekomendasi berbasis *collaborative filtering*. Fungsi ini memudahkan mendapatkan rekomendasi yang relevan berdasarkan preferensi yang dipelajari model dari data historis interaksi pengguna dan buku. Berikut cuplikan kode dan penjelasannya:

```python
example_user = cf_df['User-ID'].iloc[200]  # ambil salah satu user dari data
recommendations = get_collaborative_recommendations(example_user, top_n=5)
print(f"Rekomendasi buku untuk User {example_user}:")
for i, book in enumerate(recommendations, 1):
    print(f"{i}. {book}")
```

##### Penjelasan Kode

Kode tersebut memilih satu pengguna acak dari dataset (dengan indeks 200), lalu menggunakan fungsi `get_collaborative_recommendations` untuk mendapatkan 5 rekomendasi buku teratas untuk pengguna tersebut berdasarkan teknik *collaborative filtering*. 

##### Contoh Output

```
Rekomendasi buku untuk User 132492:
1. The Giving Tree
2. The Diamond Age
3. Dragonsong Harper Hall Trilogy
4. The Color Purple
5. The Far Side Gallery 4  
```

## 🖇️ Evaluation

Dalam proyek ini, beberapa metrik evaluasi digunakan untuk menilai performa kedua model rekomendasi:

### Content-Based Filtering

#### 1. Precision@k

Precision@k mengukur proporsi item yang relevan dari k rekomendasi teratas yang diberikan kepada pengguna.

**Formula:**
```
Precision@k = (Jumlah item relevan dalam k rekomendasi) / k
```

**Cara Kerja**:

- Mengambil k rekomendasi teratas untuk setiap pengguna
- Menghitung berapa banyak dari rekomendasi tersebut yang relevan (disukai pengguna)
- Membagi jumlah rekomendasi yang relevan dengan k

#### 2. Coverage

Coverage mengukur proporsi item dalam katalog yang dapat direkomendasikan oleh sistem.

**Formula:**
```
Coverage = (Jumlah unique item yang direkomendasikan) / (Total jumlah item)
```

**Cara kerja:**

- Mengambil sampel item dari katalog
- Menghasilkan rekomendasi untuk setiap item sampel
- Menghitung berapa banyak item unik yang muncul dalam rekomendasi
- Membagi jumlah item unik dengan total jumlah item dalam katalog

#### 3. Diversity

Diversity mengukur keragaman item dalam rekomendasi yang diberikan.

**Formula:**
```
Diversity = 1 - (Rata-rata similarity antar item yang direkomendasikan)
```

**Cara kerja:**

- Mengambil sampel item dari katalog
- Menghasilkan rekomendasi untuk setiap item sampel
- Menghitung similaritas antar item dalam setiap set rekomendasi
- Menghitung rata-rata similaritas dan mengkonversi menjadi diversity (1 - similaritas)

#### Hasil Evaluasi

Berikut perintah untuk menghasilkan hasil evaluasi model *content-based filtering*:

```python
# Evaluasi model Content-Based Filtering
def evaluate_content_based_model(test_data, cbf_df, indices, cosine_sim):
    precision_at_k = evaluate_content_based_precision_at_k(test_data, indices)
    coverage = evaluate_content_based_coverage(cbf_df, indices)
    diversity = evaluate_content_based_diversity(cbf_df, indices, cosine_sim)

    print("\nEvaluasi Model Content-Based Filtering:")
    print(f"Precision@10: {precision_at_k:.4f}")
    print(f"Coverage: {coverage:.4f}")
    print(f"Diversity: {diversity:.4f}")

    return precision_at_k, coverage, diversity

precision_at_k, coverage, diversity_cbf = evaluate_content_based_model(test_data, cbf_df, indices, cosine_sim)
```

Output dari perintah di atas adalah sebagai berikut:

```
Evaluasi Model Content-Based Filtering:
Precision@10: 0.0143
Coverage: 0.0198
Diversity: 0.7468
```

Berikut penjelsan singkat mengenai hasil output di atas:

1. Precision@10 : Dari 10 rekomendasi yang diberikan ke pengguna, rata-rata hanya 1.43% (0.0143) yang benar-benar relevan atau disukai pengguna karena sistem rekomendasi memberikan banyak rekomendasi yang tidak sesuai preferensi pengguna.

2. Coverage : Sistem hanya merekomendasikan 1.98% (0.0198)dari seluruh item yang tersedia. Hal ini menunjukkan bahwa ruang rekomendasi sangat sempit.

3. Diversity : Berdasarkan output 0.7468 (74.68%), hal ini menunjukkan bahwa rekomendasi cukup beragam  satu sama lain, artinya model merekomendasikan item yang relatif tidak terlalu mirip satu sama lain (dari segi konten).

### Collaborative Filtering

#### 1. RMSE (Root Mean Squared Error)

RMSE mengukur akurasi prediksi rating dalam sistem rekomendasi.

**Formula:**
```
RMSE = √(1/n ∑(y_true - y_pred)²)
```

Di mana:
- y_true adalah rating sebenarnya
- y_pred adalah rating yang diprediksi
- n adalah jumlah prediksi

**Cara kerja:**

- Menghitung selisih antara rating sebenarnya dan rating prediksi
- Mengkuadratkan selisih tersebut
- Menghitung rata-rata dari nilai kuadrat selisih
- Mengambil akar kuadrat dari rata-rata tersebut

#### 2. MAE (Mean Absolute Error)

MAE mengukur rata-rata kesalahan absolut antara rating prediksi dan aktual.

**Formula:**
```
MAE = 1/n ∑|y_true - y_pred|
```

**Cara kerja:**

- Menghitung selisih absolut antara rating sebenarnya dan rating prediksi
- Menghitung rata-rata dari nilai absolut selisih tersebut

#### 3. Recall@k

Recall@k mengukur proporsi item relevan yang berhasil direkomendasikan dari total item relevan.

**Formula:**
```
Recall@k = (Jumlah item relevan dalam k rekomendasi) / (Total jumlah item relevan)
```

**Cara kerja:**

- Mengambil k rekomendasi teratas untuk setiap pengguna
- Menghitung berapa banyak item relevan yang berhasil direkomendasikan
- Membagi dengan total jumlah item relevan untuk pengguna tersebut

#### 4. Hit Rate

Hit Rate mengukur proporsi pengguna yang mendapatkan setidaknya satu rekomendasi yang relevan.

**Formula:**
```
Hit Rate = (Jumlah pengguna dengan ≥1 rekomendasi relevan) / (Total jumlah pengguna)
```

**Cara kerja:**

- Menghasilkan rekomendasi untuk setiap pengguna dalam set pengujian
- Menghitung berapa banyak pengguna yang mendapatkan setidaknya satu rekomendasi yang relevan
- Membagi dengan total jumlah pengguna dalam set pengujian

#### Hasil Evaluasi

Berikut perintah untuk menghasilkan hasil evaluasi model *collaborative filtering*:

```python
def visualize_cf_metrics(rmse_actual, mae_actual, recall_at_10, hit_rate):
    metrics_cf = ['RMSE/10', 'MAE/10', 'Recall@10', 'Hit Rate']
    values_cf = [rmse_actual/10, mae_actual/10, recall_at_10, hit_rate]

    plt.figure(figsize=(10, 6))
    bars = plt.bar(metrics_cf, values_cf, color=['red', 'blue', 'green', 'purple'])

    for bar in bars:
        height = bar.get_height()
        plt.text(bar.get_x() + bar.get_width()/2, height + 0.01,
                f'{height:.4f}', ha='center', va='bottom', fontsize=10)

    plt.title('Metrik Evaluasi untuk Collaborative Filtering')
    plt.ylim(0, 1)
    plt.ylabel('Skor')
    plt.grid(axis='y', linestyle='--', alpha=0.7)
    plt.show()

rmse, mae, rmse_actual, mae_actual, recall_at_10, hit_rate = evaluate_collaborative_filtering(
        model, test_data, user_ids, book_ids, user_to_index, book_to_index)
```

Output dari perintah di atas adalah sebagai berikut:

```
Evaluasi Model Collaborative Filtering:
RMSE (skala 0-1): 0.1598
MAE (skala 0-1): 0.1250
RMSE (skala asli 1-10): 1.5983
MAE (skala asli 1-10): 1.2503
Recall@10: 0.0044
Hit Rate: 0.0200
```

Berikut penjelsan singkat mengenai hasil output di atas:

- RMSE mengukur seberapa besar kesalahan rata-rata antara prediksi rating dan rating sebenarnya, dengan memberi penalti lebih besar untuk kesalahan besar. Nilai 1.5983 berarti, rata-rata prediksi rating meleset sekitar 1.6 poin dari rating sebenarnya.

- MAE mengukur rata-rata kesalahan absolut antara rating yang diprediksi dan rating aktual tanpa penalti berlebih untuk outlier, berbeda dengan RMSE. Nilai 1.25 berarti rata-rata prediksi meleset sekitar 1.25 poin dari rating asli.

- Recall@10 menunjukkan seberapa banyak item relevan (yang benar-benar disukai pengguna) berhasil muncul di 10 rekomendasi teratas. Nilai 0.0044 berarti hanya 0.44% dari item relevan yang berhasil direkomendasikan.

- Hit Rate menunjukkan seberapa sering setidaknya satu item yang direkomendasikan muncul di daftar item yang benar-benar relevan bagi pengguna. Nilai 0.02 berarti hanya 2% dari pengguna yang mendapat rekomendasi yang sesuai (hit), sisanya yaitu 98% dari pengguna tidak mendapatkan rekomendasi yang cocok sama sekali dari sistem.

### Kesimpulan

**Perbandingan Model Sistem Rekomendasi**:
1. *Content-Based Filtering*

  - Kelebihan:
    1.  Memberikan rekomendasi yang bervariasi, tidak terjebak pada item-item populer saja.
    2. Bisa memberi rekomendasi meski hanya berdasarkan fitur item + histori pengguna (*cold-start user* sedikit lebih mudah diatasi).
    3. Lebih bisa dikontrol.

  - Kekurangan:
    1.  Hanya 1.4% dari top 10 rekomendasi yang benar-benar relevan.
    2. Model hanya menggunakan 1.98% dari seluruh item dalam rekomendasi, artinya item yang direkomendasikan itu-itu saja, dan kurang menjangkau seluruh inventori.
    3. Tergantung kualitas fitur item.

1. *Collaborative Filtering*

  - Kelebihan:
    1.  Mengandalkan kemiripan antar pengguna/item sehingga hasil lebih spesifik untuk individu.
    2. Tidak butuh fitur item karena cukup berdasarkan *user-item interaction matrix*.
    3. Dapat menangkap pola selera kompleks yang tidak terlihat dari fitur item saja.

  - Kekurangan:
    1.   Hanya 0.44% dari item relevan muncul dalam top 10, artinya rekomendasi banyak yang tidak sesuai.
    2. Hanya 2% pengguna yang menerima rekomendasi relevan sama sekali.
    3. RMSE 1.59 dan MAE 1.25 menunjukkan prediksi rating belum akurat.
    4. Sulit bekerja jika pengguna atau item baru belum memiliki cukup interaksi.

Berdasarkan kelemahan dan kelebihan model di atas, rekomendasi model terbaik *Content-based filtering* karena menghasilkan rekomendasi yang lebih relevan, bervariasi, dan stabil, terutama jika data interaksi pengguna masih terbatas. *Collaborative filtering* masih perlu peningkatan signifikan dalam kualitas prediksi dan recall.