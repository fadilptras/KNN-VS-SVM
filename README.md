# Analisis Stroke Predict Dataset dengan EDA, KNN, dan SVM
Eksplorasi Data, Visualisasi, dan Perbandingan Model Machine Learning untuk Prediksi Stroke


# Deskripsi Proyek
Proyek ini bertujuan untuk menganalisis Healthcare Dataset Stroke Prediction dari Kaggle dengan melakukan:
1. Exploratory Data Analysis (EDA) → Membersihkan data, mencari pola, dan memvisualisasikan distribusi variabel.
2. Preprocessing Data → Menangani missing values, menghapus duplikasi, dan normalisasi data.
3. Implementasi Model Machine Learning → Menggunakan K-Nearest Neighbors (KNN) dan Support Vector Machine (SVM).
4. Evaluasi Model → Membandingkan performa kedua model berdasarkan akurasi, precision, recall, F1-score, dan AUC-ROC.

Dataset yang dipilih yaitu "Healthcare Dataset Stroke Prediction" by Poulami Bakshi
https://www.kaggle.com/code/poulamibakshi/healthcare-dataset-stroke-prediction?scriptVersionId=57462578&cellId=1

# Exploratory Data Analysis (EDA) - analisis_eda.ipynb
Tujuan: Memahami karakteristik dataset sebelum pemodelan.
Langkah-langkah dalam EDA
- Pembersihan Data
- Mengisi nilai kosong (bmi) dengan median.
- Menghapus data duplikat.
- Visualisasi Data
- Distribusi variabel menggunakan histogram & bar chart.
- Scatter Plot: Hubungan antara umur (age) dan rata-rata kadar glukosa (avg_glucose_level).
- Histogram berdasarkan kategori stroke.
- Analisis Korelasi Antar Variabel
- Heatmap korelasi untuk melihat hubungan antar variabel.
- Korelasi age vs stroke (0.25) menunjukkan bahwa semakin tua seseorang, semakin besar kemungkinan mengalami stroke.
- BMI vs stroke (0.04) menunjukkan hubungan yang sangat lemah.

Kesimpulan: Usia adalah faktor signifikan dalam risiko stroke. Kadar glukosa darah memiliki sedikit hubungan dengan usia dan BMI. BMI tidak terlalu berpengaruh terhadap stroke dalam dataset ini.

# Implementasi KNN & SVM - analisis_knn_svm.ipynb
Tujuan: Membandingkan performa K-Nearest Neighbors (KNN) dan Support Vector Machine (SVM) dalam memprediksi penyakit jantung berdasarkan fitur age dan stroke.

Langkah-langkah dalam Pemodelan
- Preprocessing Data
- Normalisasi data menggunakan StandardScaler() agar skala fitur seragam.
- Split dataset: 80% data untuk training, 20% untuk testing.
- Implementasi Model KNN
  Hasil Evaluasi KNN
  - Akurasi	94%
  - Precision (Kelas 1)	33%
  - Recall (Kelas 1) 2%
  - AUC	0.63
     
- Implementasi Model SVM
  Hasil Evaluasi SVM
  - Akurasi 94%
  - Precision (Kelas 1) 0%
  - Recall (Kelas 1) 0%
  - AUC 0.50
 
# Perbandingan Model KNN vs SVM
Model	Akurasi	Precision	Recall AUC

<img width="277" alt="knn" src="https://github.com/user-attachments/assets/f9459c20-f385-4a0a-83ca-b6ae12e12839" />
<img width="275" alt="svm" src="https://github.com/user-attachments/assets/1d0081d6-c49f-4187-bbb9-b4b49ddccfe0" />


Kesimpulan : KNN lebih baik dalam dataset kecil, tetapi memiliki akurasi tinggi dengan recall rendah, menunjukkan kesulitan dalam mendeteksi kelas minoritas.
SVM memberikan margin yang lebih baik, terutama jika data lebih kompleks.
