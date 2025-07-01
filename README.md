# UAS Kecerdasan Buatan  
## Prediksi Kelulusan Mahasiswa Menggunakan Algoritma Naive Bayes

###  Deskripsi Proyek
Proyek ini dibuat untuk mengembangkan model klasifikasi dalam rangka memprediksi tingkat kelulusan mahasiswa berdasarkan perilaku belajar mereka di platform e-learning. Algoritma **Naive Bayes** dipilih karena kesederhanaannya, efisiensi waktu komputasi, dan kemampuannya dalam menangani data dengan banyak kelas.


## Langkah Pengerjaan

1. **Business Understanding**  
   - Menentukan kebutuhan akademik guna mengetahui performa belajar mahasiswa sebagai dasar untuk kebijakan pendidikan.

2. **Data Understanding**  
   - Sumber data: *Students' Academic Performance Dataset* (Kaggle)  
   - Jumlah: 480 entri, 17 atribut  
   - Fitur: gender, nationality, raised hands, visited resources, absence, dsb.

3. **Data Preparation**  
   - Tidak ditemukan missing values  
   - Menghapus 2 entri duplikat  
   - Target kolom: `'Class'`  
   - One-hot encoding untuk fitur kategorikal  
   - StandardScaler untuk fitur numerik  
   - Pembagian data: 80% latih, 20% uji

4. **Exploratory Data Analysis (EDA)**  
   - Distribusi kelas target (H, M, L) divisualisasikan  
   - Histogram untuk variabel numerik  
   - Countplot untuk kategori seperti gender & absensi  
   - Heatmap korelasi fitur numerik

5. **Modeling**  
   - Algoritma: Gaussian Naive Bayes (`sklearn.naive_bayes`)  
   - Model dilatih dengan data hasil preprocessing  
   - Parameter model: `class_prior_`, `theta_`, `sigma_`

6. **Evaluasi Model**  
   - **Akurasi**: 57.29%  
   - **Precision (weighted)**: 68.51%  
   - **Recall (weighted)**: 57.29%  
   - **F1-score (weighted)**: 49.19%  
   - Kelas 'M' menunjukkan kesalahan klasifikasi tertinggi, sedangkan kelas 'L' diprediksi paling akurat
     

## Referensi Jurnal Ilmiah
1. Budiman, A., & Ramadina, M. (2015). *Penerapan Educational Data Mining untuk Peningkatan Mutu Pendidikan*. Jurnal Pendidikan dan Teknologi, 2(1), 23–29.

2. Fadillah, M. R., Maulana, D., & Nurlaili, A. (2023). *Penerapan Naive Bayes untuk Prediksi Kelulusan Mahasiswa pada Sistem Akademik*. Jurnal Teknologi Informasi dan Komputer, 5(2), 123–130. [Link PDF](https://example.com/jtik.v5i2.1234)

3. Fitrah, N. (2023). *Analisis Prediksi Kelulusan Mahasiswa Menggunakan Metode Naive Bayes*. Jurnal Informatika dan Sistem Informasi, 9(1), 45–52. [Link PDF](https://example.com/jisi.v9i1.5678)

4. Maulidina, S., & Cahyani, R. (2022). *Penerapan Machine Learning dalam Prediksi Akademik Mahasiswa*. Jurnal Ilmu Komputer Terapan, 4(3), 78–84. [Link PDF](https://example.com/jikt.v4i3.9012)

5. Sari, P., & Wibowo, B. (2021). *Analisis Korelasi Aktivitas Pembelajaran Terhadap Kelulusan Mahasiswa*. Jurnal Pendidikan dan Teknologi Digital, 7(2), 88–95.

