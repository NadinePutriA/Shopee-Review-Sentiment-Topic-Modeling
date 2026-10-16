# Shopee-Review-Sentiment-Topic-Modeling
Analisis sentimen ulasan Shopee dari Google Play Store menggunakan Naive Bayes dan SMOTE, serta identifikasi topik dengan LDA untuk memahami persepsi pengguna.

**Analisis Sentimen dan Pemodelan Topik Ulasan Pengguna Shopee**

Proyek mata kuliah Pemrosesan Teks yang menganalisis sentimen dan aspek utama dalam ulasan pengguna aplikasi Shopee di Google Play Store menggunakan algoritma Naive Bayes dan metode Latent Dirichlet Allocation (LDA).

**Deskripsi Proyek**

Ulasan pengguna pada aplikasi digital mengandung informasi mengenai pengalaman, kepuasan, dan keluhan terhadap layanan yang diberikan. Namun, ulasan berbentuk teks tidak terstruktur sehingga membutuhkan proses pengolahan sebelum dapat dianalisis secara sistematis.

Pada proyek ini, dilakukan analisis terhadap ulasan pengguna aplikasi Shopee untuk mengelompokkan sentimen ke dalam kategori positif, netral, dan negatif. Selain itu, dilakukan pemodelan topik untuk mengidentifikasi aspek-aspek yang sering dibahas pengguna berdasarkan masing-masing kategori sentimen.

Algoritma Multinomial Naive Bayes digunakan untuk klasifikasi sentimen, sedangkan SMOTE diterapkan untuk membantu menangani ketidakseimbangan kelas. Selanjutnya, LDA digunakan untuk menemukan topik utama dalam ulasan pengguna.

**Tujuan**

1. Mengidentifikasi sentimen pengguna Shopee berdasarkan ulasan di Google Play Store.
2. Melakukan preprocessing teks berbahasa Indonesia.
3. Membandingkan hasil klasifikasi Naive Bayes sebelum dan sesudah penerapan SMOTE.
4. Mengidentifikasi topik utama pada sentimen positif, netral, dan negatif menggunakan LDA.
5. Menyajikan visualisasi untuk membantu memahami persepsi pengguna terhadap aplikasi Shopee.

**Dataset**

Data diperoleh melalui proses web scraping ulasan aplikasi Shopee di Google Play Store menggunakan Python.

Informasi dataset:
- Jumlah data: 1.000 ulasan.
- Atribut utama: userName, review, score, dan at.
- Sumber: ulasan pengguna aplikasi Shopee di Google Play Store.

Pelabelan sentimen dilakukan berdasarkan rating pengguna:
- Rating 4–5: Positif.
- Rating 3: Netral.
- Rating 1–2: Negatif.

**Konteks Akademik**

Mata Kuliah: Pemrosesan Teks
Program Studi: S-1 Sains Data
Fakultas: Matematika dan Ilmu Pengetahuan Alam
Universitas: Universitas Negeri Surabaya

**Catatan**

Proyek ini disusun untuk keperluan akademik dalam penerapan text mining, analisis sentimen, dan topic modeling. Hasil analisis menggambarkan pola pada dataset yang digunakan dan tidak selalu mewakili seluruh pengguna Shopee.
