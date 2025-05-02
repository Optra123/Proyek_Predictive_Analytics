# Laporan Proyek Machine Learning Terapan - Optra Dananjaya
# Proyek Machine Learning Predictive Analytic Clasification Water Potability

## Domain Proyek

Air merupakan sumber daya alam yang sangat vital bagi kehidupan manusia. Ketersediaan air yang bersih dan layak konsumsi menjadi salah satu indikator utama dalam menentukan kualitas kesehatan masyarakat. Namun, menurut data dari World Health Organization (WHO), lebih dari 2 miliar orang di dunia tidak memiliki akses terhadap air minum yang aman [1]. Konsumsi air yang tercemar dapat menyebabkan berbagai penyakit serius seperti diare, kolera, dan bahkan keracunan logam berat.

Dalam konteks inilah, penggunaan teknologi seperti machine learning dapat membantu dalam mendeteksi dan mengklasifikasikan kelayakan air secara otomatis berdasarkan parameter fisik dan kimia yang terukur. Proses ini tidak hanya mempercepat pengambilan keputusan dalam pengawasan kualitas air, tetapi juga mengurangi ketergantungan pada pengujian laboratorium yang mahal dan memakan waktu.

Proyek ini bertujuan untuk mengembangkan model prediktif menggunakan algoritma machine learning untuk menentukan apakah air layak untuk dikonsumsi atau tidak, berdasarkan parameter seperti pH, kekerasan (hardness), tingkat kekeruhan (turbidity), kadar kloramin, dan zat terlarut lainnya. Dengan demikian, pendekatan ini diharapkan mampu memberikan kontribusi terhadap pengawasan kualitas air secara efisien, terutama di daerah-daerah dengan keterbatasan infrastruktur laboratorium.

Penelitian sebelumnya telah menunjukkan bahwa model prediktif berbasis machine learning, seperti Random Forest dan Support Vector Machine (SVM), mampu memberikan akurasi yang tinggi dalam klasifikasi kualitas air [2][3]. Oleh karena itu, pendekatan ini dinilai relevan dan potensial untuk diimplementasikan secara luas dalam sistem pemantauan kualitas air berbasis data.

### 🌍 Dampak Global Kualitas Air Buruk

| Dampak Kesehatan                     | Jumlah Kasus/Tahun (WHO, 2022)      |
|--------------------------------------|-------------------------------------|
| Kematian akibat diare                | >485.000 jiwa                       |
| Anak-anak terkena diare kronis       | ~1,7 miliar kasus                   |
| Wabah kolera                         | Dilaporkan di 24 negara             |
| Kekurangan air minum aman            | >2 miliar orang                     |
| Biaya ekonomi tahunan                | >260 miliar USD [estimasi UNICEF]  |

**Referensi:**
[1] World Health Organization, “Drinking-water,” WHO, 2023. [Online]. Available: https://www.who.int/news-room/fact-sheets/detail/drinking-water

[2] M. Alim, S. M. Rahman, and M. S. Alam, “Water quality prediction using machine learning techniques: A case study on Buriganga River,” International Journal of Advanced Computer Science and Applications, vol. 12, no. 5, pp. 456–462, 2021.

[3] R. Patel and K. Tiwari, “Application of machine learning for water quality monitoring and management,” Environmental Monitoring and Assessment, vol. 192, no. 3, pp. 1–12, 2020.


## Business Understanding

Untuk memahami secara menyeluruh permasalahan yang ingin diselesaikan dalam proyek ini, perlu dilakukan klarifikasi terhadap latar belakang dan tujuan proyek. Klarifikasi ini akan dijabarkan dalam bentuk pernyataan masalah (*problem statements*), tujuan (*goals*), serta solusi yang dapat diterapkan (*solution statements*).

---

### Problem Statements

1. **Bagaimana cara menentukan apakah air layak dikonsumsi atau tidak berdasarkan parameter kualitas air yang tersedia?**  
   Banyak wilayah belum memiliki sistem otomatis untuk mendeteksi kelayakan air minum secara cepat, akurat, dan berbasis data. Ini menjadi masalah ketika keputusan harus segera diambil, terutama dalam kondisi darurat atau di daerah terpencil.

2. **Bagaimana meningkatkan efisiensi dan akurasi dalam proses klasifikasi kelayakan air dibandingkan metode manual atau konvensional?**  
   Metode laboratorium memerlukan waktu, biaya, dan tenaga ahli. Diperlukan solusi berbasis data yang dapat memberikan hasil prediktif secara cepat dengan tetap menjaga akurasi yang tinggi.

---

### Goals

1. **Membangun model prediktif machine learning** yang mampu mengklasifikasikan apakah air layak konsumsi atau tidak, berdasarkan data parameter kualitas air seperti pH, chloramines, turbidity, dan lainnya.

2. **Mengevaluasi dan membandingkan performa berbagai algoritma machine learning** dalam menyelesaikan permasalahan klasifikasi ini, sehingga dapat dipilih model yang paling akurat dan efisien.

---

### Solution Statements

1. **Menggunakan beberapa algoritma klasifikasi** seperti Logistic Regression, Random Forest, dan Support Vector Machine (SVM) untuk membangun model awal (baseline). Kemudian membandingkan kinerja masing-masing model berdasarkan metrik seperti akurasi, precision, recall, dan F1-score.

2. **Melakukan hyperparameter tuning dan cross-validation** pada model terbaik untuk meningkatkan performa dan mencegah overfitting. Teknik seperti GridSearchCV atau RandomizedSearchCV akan digunakan untuk mengoptimalkan parameter model.

---

## Data Understanding
Paragraf awal bagian ini menjelaskan informasi mengenai data yang Anda gunakan dalam proyek. Sertakan juga sumber atau tautan untuk mengunduh dataset. Contoh: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Restaurant+%26+consumer+data).

Selanjutnya uraikanlah seluruh variabel atau fitur pada data. Sebagai contoh:  

### Variabel-variabel pada Restaurant UCI dataset adalah sebagai berikut:
- accepts : merupakan jenis pembayaran yang diterima pada restoran tertentu.
- cuisine : merupakan jenis masakan yang disajikan pada restoran.
- dst

**Rubrik/Kriteria Tambahan (Opsional)**:
- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data atau exploratory data analysis.

## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan. Anda perlu menjelaskan tahapan dan parameter yang digunakan pada proses pemodelan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan kelebihan dan kekurangan dari setiap algoritma yang digunakan.
- Jika menggunakan satu algoritma pada solution statement, lakukan proses improvement terhadap model dengan hyperparameter tuning. **Jelaskan proses improvement yang dilakukan**.
- Jika menggunakan dua atau lebih algoritma pada solution statement, maka pilih model terbaik sebagai solusi. **Jelaskan mengapa memilih model tersebut sebagai model terbaik**.

## Evaluation
Pada bagian ini anda perlu menyebutkan metrik evaluasi yang digunakan. Lalu anda perlu menjelaskan hasil proyek berdasarkan metrik evaluasi yang digunakan.

Sebagai contoh, Anda memiih kasus klasifikasi dan menggunakan metrik **akurasi, precision, recall, dan F1 score**. Jelaskan mengenai beberapa hal berikut:
- Penjelasan mengenai metrik yang digunakan
- Menjelaskan hasil proyek berdasarkan metrik evaluasi

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.
