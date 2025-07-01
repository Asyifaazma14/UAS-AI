# UAS Kecerdasan Buatan  
## Prediksi Kelulusan Mahasiswa Menggunakan Algoritma Gaussian Naive Bayes

###  Deskripsi Proyek
Proyek ini bertujuan untuk membangun model klasifikasi guna memprediksi tingkat kelulusan atau performa akademik mahasiswa berdasarkan data aktivitas pembelajaran daring.  
Model yang digunakan adalah **Gaussian Naive Bayes** karena sederhana, cepat, dan cukup efektif untuk klasifikasi multiclass dengan fitur numerik dan kategorikal.


###  Tahapan Proyek

#### 1. Business Understanding
Mengidentifikasi kebutuhan akademik untuk memprediksi performa mahasiswa guna membantu pengambilan keputusan seperti intervensi belajar dan pemetaan risiko kegagalan studi.

#### 2. Data Understanding
- **Dataset**: *Students' Academic Performance Dataset* dari Kaggle  
- **Jumlah data**: 480 baris dan 17 kolom  
- **Fitur** mencakup atribut demografis (gender, nationality), perilaku belajar (raised hands, visited resources), dan absensi

#### 3. Data Preparation
- **Pemeriksaan data**: Tidak ditemukan missing values  
- **Duplikasi**: 2 baris duplikat dihapus  
- **Target**: Kolom `Class` dijadikan label  
- **Encoding**:
  - Fitur kategorikal → *OneHotEncoder*
  - Fitur numerik → *StandardScaler*
- **Splitting data**: 80% data latih, 20% data uji (*stratified split*)  
- **Validasi NaN setelah preprocessing**: Tidak ditemukan  

#### 4. Exploratory Data Analysis (EDA)
- Visualisasi distribusi kelas target *(Low, Medium, High)*  
- Histogram fitur numerik: `raisedhands`, `VisITedResources`, dll  
- Countplot fitur kategorikal: `gender`, `satisfaction`, `absensi`  
- Heatmap korelasi antar fitur numerik  
- Ditemukan ketidakseimbangan kelas, terutama pada kelas `M`  

#### 5. Modeling
- **Model**: Gaussian Naive Bayes dari `sklearn.naive_bayes`  
- **Training data**: `X_train_processed`, `y_train`  
- **Parameter model**:
  - `class_prior_`: probabilitas awal tiap kelas  
  - `theta_`, `sigma_`: mean dan variansi tiap fitur per kelas  

#### 6. Evaluation
- **Confusion Matrix**: digunakan untuk memvisualisasikan prediksi terhadap data uji  
- **Metrik evaluasi**:
  - **Accuracy**: 57.29%  
  - **Precision (weighted)**: 68.51%  
  - **Recall (weighted)**: 57.29%  
  - **F1-score (weighted)**: 49.19%

####  Analisis
- Kelas `L` memiliki tingkat akurasi prediksi tertinggi  
- Kelas `M` paling sering salah diklasifikasikan, terutama ke kelas `H`  
- Visualisasi menggunakan heatmap membantu mengidentifikasi distribusi kesalahan model

####  Kesimpulan & Rekomendasi
- Model cukup efektif untuk memetakan performa mahasiswa  
- Perlu perbaikan pada prediksi kelas `M`, misalnya dengan:
  - Teknik balancing seperti **SMOTE**
  - Menggunakan algoritma lain seperti **Random Forest**
- Pipeline sudah mengikuti standar tahapan machine learning
