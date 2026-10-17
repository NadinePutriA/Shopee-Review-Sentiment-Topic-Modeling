# Shopee-Review-Sentiment-Topic-Modeling
Analisis sentimen ulasan Shopee dari Google Play Store menggunakan Naive Bayes dan SMOTE, serta identifikasi topik dengan LDA untuk memahami persepsi pengguna.

# Analisis Aspek dan Sentimen Review Pengguna Shopee

## Deskripsi Proyek

Repository ini berisi proyek analisis sentimen dan identifikasi aspek atau topik utama pada ulasan pengguna aplikasi Shopee di Google Play Store. Proyek ini dikembangkan menggunakan pendekatan *text mining* dengan menggabungkan klasifikasi sentimen menggunakan **Multinomial Naive Bayes** dan *topic modeling* menggunakan **Latent Dirichlet Allocation (LDA)**.

Ulasan pengguna dikumpulkan melalui web scraping, kemudian diproses melalui tahapan pembersihan teks, normalisasi slangword, penghapusan stopword, stemming, dan tokenisasi. Klasifikasi sentimen dilakukan ke dalam tiga kategori, yaitu positif, netral, dan negatif. Untuk menangani ketidakseimbangan jumlah data antarkelas, penelitian ini menerapkan metode Synthetic Minority Over-sampling Technique (SMOTE) pada data latih.

Selain klasifikasi sentimen, LDA digunakan untuk mengidentifikasi topik yang dibahas pengguna pada masing-masing kategori sentimen. Hasil analisis disajikan melalui berbagai visualisasi untuk membantu memahami pengalaman, kepuasan, dan keluhan pengguna terhadap aplikasi Shopee.

## Tujuan Proyek

- Menganalisis sentimen ulasan pengguna Shopee ke dalam kategori positif, netral, dan negatif.
- Mengevaluasi performa algoritma Naive Bayes dalam klasifikasi sentimen.
- Menganalisis penerapan SMOTE untuk menangani ketidakseimbangan kelas.
- Mengidentifikasi topik utama pada setiap kategori sentimen menggunakan LDA.
- Menyajikan visualisasi untuk memahami aspek yang sering dibahas dalam ulasan pengguna.

## Dataset

Data penelitian berupa **1.000 ulasan pengguna aplikasi Shopee** yang dikumpulkan dari Google Play Store menggunakan web scraping.

Atribut utama yang digunakan meliputi:

| Atribut | Keterangan |
|---|---|
| `userName` | Nama pengguna yang tercatat pada ulasan |
| `review` | Teks ulasan pengguna |
| `score` | Rating yang diberikan pengguna |
| `at` | Waktu atau tanggal ulasan |

### Pelabelan Sentimen

Label sentimen ditentukan berdasarkan rating pengguna:

- **Positif:** rating 4–5.
- **Netral:** rating 3.
- **Negatif:** rating 1–2.

## Metodologi

### 1. Web Scraping
Mengumpulkan ulasan pengguna Shopee dari Google Play Store beserta rating dan informasi tanggal ulasan.

### 2. Text Preprocessing
Melakukan pembersihan dan normalisasi teks melalui tahapan:
- Lowercasing.
- Penghapusan angka, emoji, dan tanda baca.
- Normalisasi slangword.
- Stopword removal.
- Stemming.
- Tokenisasi.

### 3. Exploratory Data Analysis (EDA)
Mengeksplorasi karakteristik data melalui distribusi rating, panjang ulasan, distribusi sentimen, dan word cloud untuk mengetahui kata-kata yang sering muncul.

### 4. Feature Engineering
Dua pendekatan representasi teks digunakan sesuai kebutuhan analisis:

- **TF-IDF:** untuk merepresentasikan teks sebagai fitur numerik pada klasifikasi sentimen.
- **Bag of Words (CountVectorizer):** untuk membentuk representasi dokumen yang digunakan pada topic modeling LDA.

### 5. Klasifikasi Sentimen dengan Naive Bayes
Model Multinomial Naive Bayes digunakan untuk memprediksi sentimen ulasan ke dalam tiga kategori. Data dibagi menjadi data latih dan data uji sebelum model dilatih dan dievaluasi.

### 6. Penanganan Imbalanced Data dengan SMOTE
SMOTE diterapkan hanya pada data latih untuk meningkatkan representasi kelas minoritas. Data uji tidak mengalami oversampling agar evaluasi tetap dilakukan pada data yang tidak dimodifikasi.

### 7. Topic Modeling dengan LDA
Latent Dirichlet Allocation digunakan untuk menemukan topik utama secara terpisah pada ulasan dengan sentimen positif, netral, dan negatif. Jumlah topik dipilih berdasarkan evaluasi coherence score serta kemudahan interpretasi. Penelitian memilih lima topik untuk setiap kategori sentimen.

### 8. Visualisasi Hasil
Hasil penelitian disajikan melalui word cloud, barplot kata dominan per topik, heatmap distribusi, confusion matrix, dan visualisasi interaktif menggunakan pyLDAvis.

## Hasil dan Temuan

### Klasifikasi Sentimen

Berdasarkan laporan penelitian, model Naive Bayes setelah penerapan SMOTE memperoleh hasil berikut:

| Metrik | Hasil |
|---|---:|
| Accuracy | 80% |
| Weighted F1-score | 0,82 |
| F1-score sentimen positif | 0,91 |
| F1-score sentimen negatif | 0,67 |
| F1-score sentimen netral | 0,11 |

Penerapan SMOTE membantu meningkatkan keseimbangan performa klasifikasi, terutama pada kelas minoritas. Namun, sentimen netral masih sulit diklasifikasikan dengan benar sehingga menjadi salah satu keterbatasan model.

### Topic Modeling

Hasil LDA menunjukkan beberapa aspek yang dibahas pengguna, antara lain:

- **Sentimen positif:** ekspresi kepuasan, pengalaman belanja, kepercayaan terhadap produk dan toko, promo, serta pengalaman pengiriman.
- **Sentimen netral:** informasi status pesanan, waktu pengiriman, penilaian produk, dan instruksi kepada penjual.
- **Sentimen negatif:** keluhan dan pengalaman kurang memuaskan yang perlu dianalisis berdasarkan hasil topik pada notebook.

Jumlah topik yang digunakan adalah lima untuk setiap kategori sentimen, berdasarkan pertimbangan coherence score dan interpretabilitas.

## Kesimpulan

Proyek ini menggabungkan klasifikasi sentimen dan topic modeling untuk memperoleh gambaran yang lebih menyeluruh mengenai ulasan pengguna Shopee. Naive Bayes digunakan untuk mengklasifikasikan sentimen, sedangkan LDA membantu mengidentifikasi aspek atau tema utama dalam ulasan. SMOTE diterapkan untuk membantu menangani ketidakseimbangan kelas, meskipun peningkatan performa pada sentimen netral masih menjadi tantangan.

## Konteks Akademik

Program Studi S1 Sains Data  
Fakultas Matematika dan Ilmu Pengetahuan Alam  
Universitas Negeri Surabaya
Mata Kuliah: Pemrosesan Teks  
Kelas: 2024 C
