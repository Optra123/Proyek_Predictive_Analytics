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
Dataset yang digunakan dalam proyek ini adalah dataset **Water Potability** yang tersedia di platform Kaggle. Dataset ini berisi sampel data kualitas air dan indikator kelayakan air untuk dikonsumsi. Dataset ini dapat diakses melalui tautan berikut:

🔗 [Water Potability Dataset - Kaggle](https://www.kaggle.com/datasets/adityakadiwal/water-potability)

Dataset ini terdiri dari 3276 entri dan 10 kolom, yang mencakup variabel-variabel kimia dan fisika air serta label `Potability` sebagai indikator kelayakan konsumsi.

---

### Variabel-variabel pada Water Potability Dataset adalah sebagai berikut:

- **ph**: Mengukur tingkat keasaman atau kebasaan air. Nilai ideal untuk air minum berkisar antara 6.5 - 8.5.
- **Hardness**: Mengukur jumlah kalsium dan magnesium yang terlarut dalam air. Hardness tinggi dapat mempengaruhi rasa dan menimbulkan kerak.
- **Solids**: Jumlah total zat padat terlarut dalam air (Total Dissolved Solids atau TDS). Nilai tinggi dapat mengindikasikan pencemaran.
- **Chloramines**: Kandungan kloramin dalam air, yang digunakan sebagai disinfektan. Kandungan terlalu tinggi dapat berdampak buruk bagi kesehatan.
- **Sulfate**: Ion sulfat yang jika berlebih dapat menyebabkan masalah kesehatan, seperti gangguan pencernaan.
- **Conductivity**: Kemampuan air dalam menghantarkan listrik, yang menunjukkan jumlah ion terlarut (berkorelasi dengan TDS).
- **Organic_carbon**: Kandungan karbon organik dalam air. Nilai tinggi dapat mengindikasikan adanya kontaminasi bahan organik.
- **Trihalomethanes**: Senyawa kimia hasil reaksi klorin dengan bahan organik; bersifat karsinogenik bila dikonsumsi dalam jangka panjang.
- **Turbidity**: Tingkat kekeruhan air. Air keruh sering kali mengandung partikel yang bisa mengandung mikroorganisme patogen.
- **Potability**: Label target. Nilai `1` berarti air layak minum, sedangkan `0` berarti tidak layak.

---

### Ringkasan Statistik Deskriptif

| Fitur              | Count     | Mean     | Std Dev   | Min       | 25%       | 50%       | 75%       | Max         |
|--------------------|-----------|----------|-----------|-----------|-----------|-----------|-----------|-------------|
| ph                 | 2785.00   | 7.08     | 1.59      | 0.00      | 6.09      | 7.04      | 8.06      | 14.00       |
| Hardness           | 3276.00   | 196.37   | 32.88     | 47.43     | 176.85    | 196.97    | 216.67    | 323.12      |
| Solids             | 3276.00   | 22014.09 | 8768.57   | 320.94    | 15666.69  | 20927.83  | 27332.76  | 61227.20    |
| Chloramines        | 3276.00   | 7.12     | 1.58      | 0.35      | 6.13      | 7.13      | 8.11      | 13.13       |
| Sulfate            | 2495.00   | 333.78   | 41.42     | 129.00    | 307.70    | 333.07    | 359.95    | 481.03      |
| Conductivity       | 3276.00   | 426.21   | 80.82     | 181.48    | 365.73    | 421.88    | 481.79    | 753.34      |
| Organic_carbon     | 3276.00   | 14.28    | 3.31      | 2.20      | 12.07     | 14.22     | 16.56     | 28.30       |
| Trihalomethanes    | 3114.00   | 66.40    | 16.18     | 0.74      | 55.84     | 66.62     | 77.34     | 124.00      |
| Turbidity          | 3276.00   | 3.97     | 0.78      | 1.45      | 3.44      | 3.96      | 4.50      | 6.74        |
| Potability         | 3276.00   | 0.39     | 0.49      | 0.00      | 0.00      | 0.00      | 1.00      | 1.00        |

---

### Data yang Hilang

Tabel berikut menunjukkan jumlah nilai hilang (missing values) pada setiap fitur:

| Fitur             | Missing Values |
|-------------------|----------------|
| ph                | 491            |
| Sulfate           | 781            |
| Trihalomethanes   | 162            |
| (Fitur lainnya)   | 0              |

> Terdapat tiga fitur dengan missing values cukup signifikan: `ph`, `Sulfate`, dan `Trihalomethanes`. Penanganan data hilang akan dilakukan pada tahap Data Preparation, baik dengan teknik imputasi seperti median/mean imputation atau dengan pendekatan prediktif.

---


## Data Preparation

Tahap data preparation bertujuan untuk membersihkan dan menyiapkan data agar dapat digunakan secara optimal dalam proses pelatihan model machine learning. Persiapan ini melibatkan dua langkah utama, yaitu penanganan data yang hilang dan standardisasi fitur numerik.

---

### 1. Penanganan Nilai yang Hilang

Berdasarkan hasil eksplorasi pada tahap sebelumnya, ditemukan bahwa beberapa fitur dalam dataset memiliki nilai yang hilang (*missing values*). Rincian jumlah nilai yang hilang adalah sebagai berikut:

| Fitur              | Jumlah Nilai Hilang |
|--------------------|---------------------|
| ph                 | 491                 |
| Sulfate            | 781                 |
| Trihalomethanes    | 162                 |

Untuk mengatasi masalah ini, digunakan teknik **imputasi dengan nilai rata-rata (mean imputation)** menggunakan `SimpleImputer` dari pustaka `scikit-learn`. Teknik ini menggantikan nilai yang hilang dengan rata-rata dari kolom masing-masing, menjaga distribusi data tetap stabil.

```python
from sklearn.impute import SimpleImputer

imputer = SimpleImputer(strategy='mean')
data[['ph', 'Sulfate', 'Trihalomethanes']] = imputer.fit_transform(data[['ph', 'Sulfate', 'Trihalomethanes']])
```

**Alasan**:  
Jika nilai hilang tidak ditangani, maka proses pelatihan model tidak dapat dilakukan secara menyeluruh karena beberapa algoritma tidak dapat menangani nilai kosong. Imputasi mean merupakan pendekatan sederhana dan efektif ketika distribusi data tidak terlalu miring (skewed).

---

### 2. Standardisasi Fitur Numerik

Langkah berikutnya adalah melakukan **standardisasi (scaling)** terhadap seluruh fitur numerik, kecuali fitur target `Potability`. Standardisasi dilakukan menggunakan `StandardScaler`, yang mengubah skala setiap fitur agar memiliki **rata-rata 0** dan **standar deviasi 1**. Ini dilakukan karena fitur dalam dataset memiliki rentang nilai yang berbeda-beda, yang dapat mempengaruhi performa algoritma pembelajaran mesin, terutama yang berbasis jarak atau gradien.

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()
numeric_cols = data.select_dtypes(include='number').columns.tolist()
numeric_cols.remove('Potability')
data[numeric_cols] = scaler.fit_transform(data[numeric_cols])
```

**Alasan**:  
Model seperti KNN, SVM, dan Logistic Regression sensitif terhadap perbedaan skala fitur. Jika tidak distandarisasi, fitur dengan nilai besar akan mendominasi proses pembelajaran. Oleh karena itu, standardisasi sangat penting untuk membuat setiap fitur berkontribusi secara seimbang.

**Statistik Deskriptif Setelah Standardisasi**:  
Setelah dilakukan standardisasi, fitur-fitur numerik memiliki nilai rata-rata mendekati 0 dan standar deviasi mendekati 1, yang merupakan indikasi bahwa proses ini berhasil dilakukan dengan baik.

---

Dengan dua tahapan penting ini — imputasi nilai hilang dan standarisasi fitur — dataset kini telah bersih, konsisten, dan siap digunakan pada tahap selanjutnya yaitu **modeling**.



## Modeling

Pada tahap modeling, beberapa algoritma machine learning digunakan untuk memprediksi apakah air layak dikonsumsi atau tidak (Potability). Tujuan utama dari proses ini adalah untuk membandingkan performa berbagai model dan memilih model terbaik berdasarkan akurasi pada data uji. Setiap model diuji dengan pendekatan evaluasi yang konsisten, termasuk pembagian data training dan testing, serta penerapan hyperparameter tuning untuk peningkatan performa model tertentu.

---

### 1. Logistic Regression (Baseline)

Logistic Regression dipilih sebagai baseline model karena kesederhanaannya dan kemampuannya dalam menangani klasifikasi biner. Model ini bekerja dengan mengasumsikan hubungan linear antara fitur input dan probabilitas output kelas. Pada proyek ini, digunakan regularisasi L2 dengan `C=0.001` dan solver `'liblinear'`.

**Kelebihan:**
- Cepat dalam pelatihan dan prediksi.
- Mudah diinterpretasikan dan dijadikan baseline.
- Tidak memerlukan banyak tuning parameter.

**Kekurangan:**
- Tidak mampu menangkap hubungan non-linear dalam data.
- Kinerjanya menurun pada dataset yang kompleks dan tidak terpisah secara linear.

```python
logreg = LogisticRegression(C=0.001, class_weight=None, n_jobs=-1, penalty='l2', solver='liblinear')
logreg.fit(X_train, y_train)
y_pred_logreg = logreg.predict(X_test)
```

---

### 2. Support Vector Machine (SVM) + Hyperparameter Tuning

Support Vector Machine digunakan untuk meningkatkan performa klasifikasi dibandingkan baseline. SVM bekerja dengan mencari hyperplane optimal yang memisahkan kelas secara maksimal. Untuk mendapatkan performa terbaik, dilakukan proses tuning parameter menggunakan **GridSearchCV**.

Parameter yang disesuaikan:
- `C`: 0.1, 1, 10
- `kernel`: 'linear', 'rbf'
- `gamma`: 'scale', 'auto'

Proses tuning dilakukan menggunakan validasi silang (cross-validation) sebanyak 5 fold untuk menghindari overfitting.

**Kelebihan:**
- Efektif pada data berdimensi tinggi.
- Dapat digunakan pada data non-linear dengan kernel yang tepat.
- Tahan terhadap overfitting, terutama dengan margin besar.

**Kekurangan:**
- Membutuhkan waktu komputasi yang lebih tinggi.
- Sensitif terhadap pilihan kernel dan parameter.

```python
param_grid_svm = {
    'C': [0.1, 1, 10],
    'kernel': ['linear', 'rbf'],
    'gamma': ['scale', 'auto']
}
grid_search_svm = GridSearchCV(SVC(), param_grid_svm, cv=5, scoring='accuracy')
grid_search_svm.fit(X_train, y_train)
best_svm = grid_search_svm.best_estimator_
y_pred_svm = best_svm.predict(X_test)
```

---

### 3. Random Forest Classifier

Random Forest adalah algoritma ensemble yang menggabungkan banyak decision tree untuk menghasilkan prediksi yang lebih stabil dan akurat. Pada proyek ini, Random Forest dipilih karena mampu menangani data non-linear dan bekerja baik meskipun terdapat fitur yang tidak relevan.

Model dilatih dengan parameter default, dan hasilnya menunjukkan performa yang kompetitif. Random Forest juga memberikan kemampuan interpretasi terhadap pentingnya fitur (feature importance).

**Kelebihan:**
- Dapat menangani data numerik dan kategorikal.
- Tidak sensitif terhadap outlier dan missing value (dalam jumlah kecil).
- Memberikan informasi pentingnya fitur (feature importance).

**Kekurangan:**
- Cenderung overfitting jika tidak dikontrol (misalnya terlalu banyak tree).
- Kurang efisien secara waktu dan memori dibanding model sederhana.

```python
rf_model = RandomForestClassifier(random_state=42)
rf_model.fit(X_train, y_train)
y_pred_rf = rf_model.predict(X_test)
```

---

### 4. Artificial Neural Network (ANN)

Model deep learning yang digunakan adalah Artificial Neural Network (ANN) yang dibangun menggunakan arsitektur sederhana. Model terdiri dari beberapa lapisan Dense (fully connected) dengan fungsi aktivasi ReLU dan sigmoid di output layer.

Untuk melatih model ANN, digunakan parameter berikut:
- Loss function: `binary_crossentropy`
- Optimizer: `adam`
- Epochs: 100
- Batch size: 32
- Validation split: 0.2

Model ini menunjukkan kemampuan yang baik dalam menangkap hubungan kompleks antar fitur, namun juga memerlukan waktu pelatihan lebih lama dan tuning yang lebih hati-hati.

**Kelebihan:**
- Mampu menangkap hubungan kompleks dan non-linear.
- Fleksibel dalam struktur dan dapat dikembangkan lebih lanjut.

**Kekurangan:**
- Membutuhkan banyak data dan waktu pelatihan lebih lama.
- Berisiko overfitting tanpa teknik regularisasi dan validasi yang baik.

```python
model = Sequential()
model.add(Dense(64, input_dim=X_train.shape[1], activation='relu'))
model.add(Dense(32, activation='relu'))
model.add(Dense(1, activation='sigmoid'))

model.compile(loss='binary_crossentropy', optimizer='adam', metrics=['accuracy'])
model.fit(X_train, y_train, epochs=100, batch_size=32, validation_split=0.2, verbose=0)
y_pred_nn = model.predict(X_test)
y_pred_nn_classes = np.round(y_pred_nn)
```

---

### Pemilihan Model Terbaik

Empat model telah dibangun dan diuji untuk menyelesaikan masalah klasifikasi potabilitas air, yaitu:

- Logistic Regression
- Support Vector Machine (SVM)
- Random Forest
- Artificial Neural Network (Deep Learning)

Berdasarkan hasil evaluasi pada data uji, berikut adalah skor akurasi dari masing-masing model:

| Model                   | Akurasi   |
|-------------------------|-----------|
| Logistic Regression     | 0.628     |
| Support Vector Machine  | 0.695     |
| Random Forest           | 0.681     |
| Deep Learning           | 0.681     |

Dari tabel tersebut, dapat dilihat bahwa **Support Vector Machine (SVM)** memberikan hasil akurasi tertinggi sebesar **0.695**. Oleh karena itu, SVM dipilih sebagai **model terbaik** dalam proyek ini.

**Alasan Pemilihan SVM:**
- Memiliki akurasi tertinggi di antara semua model yang diuji.
- Mampu menangani data berdimensi tinggi dan kompleksitas non-linear melalui pemilihan kernel yang sesuai.
- Memberikan margin pemisah yang optimal antara dua kelas (air layak dan tidak layak konsumsi).

Meskipun model seperti Random Forest dan Deep Learning juga memberikan hasil yang cukup baik, SVM unggul dari segi performa tanpa memerlukan arsitektur kompleks maupun pelatihan berulang kali seperti pada ANN.


## Evaluation

Dalam proyek klasifikasi potabilitas air ini, metrik evaluasi utama yang digunakan adalah **akurasi (accuracy)**. Metrik ini dipilih karena memberikan gambaran umum seberapa sering model membuat prediksi yang benar terhadap data uji, yang terdiri dari dua kelas: air yang layak dikonsumsi dan air yang tidak layak dikonsumsi.

### Apa itu Akurasi?

Akurasi merupakan proporsi dari jumlah prediksi yang benar dibandingkan dengan seluruh jumlah prediksi yang dilakukan. Rumus akurasi adalah sebagai berikut:

**Accuracy = (TP + TN) / (TP + TN + FP + FN)**

Dimana:
- **TP (True Positive)**: Model memprediksi air layak konsumsi dan memang layak
- **TN (True Negative)**: Model memprediksi air tidak layak konsumsi dan memang tidak layak
- **FP (False Positive)**: Model memprediksi air layak konsumsi padahal tidak
- **FN (False Negative)**: Model memprediksi air tidak layak konsumsi padahal layak

### Hasil Evaluasi

Dari hasil pemodelan terhadap empat algoritma yang berbeda, diperoleh akurasi sebagai berikut:

| Model                   | Akurasi   |
|-------------------------|-----------|
| Logistic Regression     | 0.628     |
| Support Vector Machine  | **0.695** |
| Random Forest           | 0.681     |
| Deep Learning           | 0.681     |

Model **Support Vector Machine (SVM)** memberikan akurasi tertinggi yaitu sebesar **69,5%**, menjadikannya model terbaik dalam proyek ini.

### Interpretasi Hasil

Akurasi sebesar 69,5% mengindikasikan bahwa model SVM mampu memprediksi dengan benar hampir 7 dari 10 sampel data uji. Dalam konteks potabilitas air, meskipun akurasi ini belum mencapai tingkat yang sangat tinggi, hal ini tetap menunjukkan potensi penggunaan model untuk membantu proses awal klasifikasi kualitas air secara otomatis. Namun, untuk penggunaan di dunia nyata seperti penilaian kualitas air publik, model ini masih memerlukan peningkatan lebih lanjut — baik dari sisi kualitas data, fitur yang digunakan, hingga kemungkinan penggabungan dengan sensor atau pengukuran fisik lainnya.

Selain itu, akurasi saja tidak selalu cukup untuk menilai model secara komprehensif, terutama jika terdapat ketidakseimbangan kelas. Oleh karena itu, pada pengembangan lanjutan, akan sangat disarankan untuk mempertimbangkan metrik lain seperti precision, recall, dan F1 score untuk mendapatkan pemahaman yang lebih menyeluruh mengenai performa model.


