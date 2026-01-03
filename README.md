# Tubes Praktikum Machine Learning: Prediksi Biaya Asuransi (Insurance Cost Prediction)

Project ini adalah tugas akhir kelompok SaranNamaKelompok yang bertujuan untuk membangun model Machine Learning yang dapat memprediksi biaya tagihan asuransi kesehatan (*charges*) berdasarkan profil demografi dan kesehatan nasabah.

## 👥 Anggota Kelompok
| Nama | NIM |
|------|-----|
| Ari Gamaliel Manohan Silitonga | 231402030 |
|Ikhsan Shah Pohan | 231402039 |
|Kenward Keene  Hermanto | 231402081 |
|Muhammad Niki Ramandika | 231402097 |



## 📄 Deskripsi Dataset
Dataset yang digunakan adalah `insurance.csv` yang berisi data demografis nasabah asuransi.

**Fitur (Input):**
- `age`: Usia nasabah.
- `sex`: Jenis kelamin (male/female).
- `bmi`: Indeks Massa Tubuh (Body Mass Index).
- `children`: Jumlah anak/tanggungan yang dicover asuransi.
- `smoker`: Status perokok (yes/no).
- `region`: Wilayah tempat tinggal (southwest, southeast, northwest, northeast).

**Target (Output):**
- `charges`: Biaya tagihan asuransi individu.

## 🛠️ Teknologi & Library yang Digunakan
Project ini dibuat menggunakan bahasa pemrograman **Python** dengan library berikut:
- **Pandas & NumPy**: Untuk manipulasi dan analisis data.
- **Matplotlib & Seaborn**: Untuk visualisasi data (EDA).
- **Scikit-Learn**: Untuk preprocessing, pemodelan Machine Learning, dan evaluasi.

## 📊 Alur Kerja (Workflow)

### 1. Data Loading & Cleaning
- Memuat data dari `insurance.csv`.
- Memeriksa dan menghapus data duplikat.
- Menangani *Outliers* pada kolom `charges` dan `bmi` menggunakan metode IQR (Interquartile Range) dengan multiplier 2.0.

### 2. Exploratory Data Analysis (EDA)
- Melakukan visualisasi distribusi data untuk melihat persebaran biaya asuransi, usia, dan BMI.
- Menganalisis korelasi antar fitur.

### 3. Preprocessing
- **Encoding Variabel Kategorikal**:
  - Mengubah `smoker` dan `sex` menjadi numerik (0 dan 1).
  - Melakukan *One-Hot Encoding* manual untuk kolom `region` (menciptakan kolom baru: southwest, southeast, northwest, northeast).
- **Scaling**: Menyamakan skala data agar model bekerja lebih optimal.

### 4. Modeling & Evaluasi
Kami membandingkan beberapa algoritma Machine Learning:
- Linear Regression, Ridge, Lasso
- Random Forest Regressor
- Gradient Boosting Regressor
- Support Vector Regressor (SVR)
- K-Neighbors Regressor (KNN)

Evaluasi dilakukan menggunakan metrik: **R2 Score**, **MSE** (Mean Squared Error), dan **RMSE** (Root Mean Squared Error).

### 5. Hyperparameter Tuning
Menggunakan `RandomizedSearchCV` untuk mencari parameter terbaik guna meningkatkan performa model.

## 📈 Hasil Analisis
Berdasarkan pengujian yang telah dilakukan:
1. **Model Terbaik (Baseline):** Sebelum tuning, algoritma **Gradient Boosting** memberikan hasil terbaik dengan R2 score tertinggi dan error terendah dibandingkan model lain.
2. **Efek Hyperparameter Tuning:**
   - **Random Forest** mengalami peningkatan performa yang drastis setelah dilakukan tuning parameter.
   - Hasil akhirnya, performa Random Forest menjadi sangat kompetitif dan mendekati performa Gradient Boosting.
   - Linear Regression tidak mengalami perubahan signifikan karena terbatasnya parameter yang dapat diubah.

## 🚀 Cara Menjalankan Project
1. Clone repository ini:
   ```bash
   git clone [https://github.com/username-anda/nama-repo.git](https://github.com/username-anda/nama-repo.git)
   ```
2. Pastikan library yang dibutuhkan sudah terinstall. Anda bisa menginstallnya via pip:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn
   ```
3. Jalankan file notebook:
   ```bash
   jupyter notebook Final_Project_Kelompok_SaranNamaKelompok.ipynb
   ```
