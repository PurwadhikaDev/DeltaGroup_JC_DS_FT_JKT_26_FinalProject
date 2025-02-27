# DeltaGroup_JC_DS_FT_JKT_26_FinalProject

# Customer Churn Prediction - E-Commerce Analysis

## Deskripsi Proyek
Proyek ini bertujuan untuk menganalisis perilaku pelanggan pada platform e-commerce dan membangun model machine learning untuk memprediksi kemungkinan pelanggan melakukan churn (berhenti menggunakan layanan). Dengan pemahaman yang lebih baik tentang pola churn, perusahaan dapat mengoptimalkan strategi retensi pelanggan dan mengalokasikan anggaran pemasaran dengan lebih efisien.

## Tujuan Proyek
1. Mengidentifikasi faktor utama yang mempengaruhi churn pelanggan.
2. Mengembangkan model machine learning yang dapat memprediksi pelanggan berisiko churn.
3. Mengoptimalkan strategi pemasaran berbasis data untuk meningkatkan retensi pelanggan dan efisiensi anggaran promosi.
4. Mengintegrasikan model ke dalam sistem bisnis melalui WebApp Streamlit untuk memberikan prediksi secara real-time.

## Impact Finansial dari Penerapan Machine Learning
Penerapan machine learning dalam prediksi churn memungkinkan perusahaan untuk secara signifikan mengurangi **biaya operasional dan kehilangan pendapatan akibat churn**, dengan hasil berikut:
- Sebelum penerapan machine learning, perusahaan mengalami kerugian lebih dari **₹45 juta per bulan** akibat promosi yang tidak efektif dan kehilangan pelanggan yang tidak terdeteksi.
- Dengan model prediksi churn, total kerugian berkurang menjadi hanya **₹178 ribu per bulan**, menghasilkan penghematan lebih dari **₹45 juta per bulan**.
- Efisiensi biaya meningkat sebesar **99.6%**, memungkinkan perusahaan mengalokasikan sumber daya pemasaran dengan lebih strategis dan akurat.

## Struktur Notebook
### **Chapter 1: Business Problem Understanding**
- **Context**: Pentingnya retensi pelanggan dalam e-commerce.
- **Problem Statement**: Tantangan utama dalam menurunkan churn dan mengoptimalkan strategi pemasaran.
- **Business Goals**: Mengurangi churn dan meningkatkan retensi pelanggan dengan pendekatan machine learning.
- **Stakeholders**: Chief Marketing Officer (CMO) sebagai pengguna utama model prediksi churn.
- **Metric Evaluation**: F2-score, PRC-AUC, dan Recall dipilih sebagai metrik utama karena lebih sesuai untuk data imbalanced.

### **Chapter 2: Data Understanding**
- Eksplorasi dataset dan distribusi fitur.
- Identifikasi missing values dan outliers.
- Analisis hubungan antara variabel menggunakan korelasi Spearman dan Cramér’s V.

### **Chapter 3: Exploratory Data Analysis (EDA)**
- Analisis distribusi fitur numerik dan kategorikal.
- Pemeriksaan pola churn berdasarkan variabel utama seperti cashback, jumlah transaksi, dan jumlah keluhan pelanggan.

### **Chapter 4: Data Cleaning**
- Penanganan missing values dengan iterative imputation.
- Encoding fitur kategorikal dan normalisasi data numerik.
- Identifikasi dan penanganan outliers menggunakan robust scaling.

### **Chapter 5: Pipeline Otomatis untuk Preprocessing Data**
- Membuat pipeline preprocessing menggunakan `ColumnTransformer` dan `Pipeline`.
- Automasi transformasi fitur untuk memastikan hasil yang konsisten pada data training dan testing.

### **Chapter 6: Model Benchmarking & Optimization**
- Pengujian beberapa algoritma machine learning: Logistic Regression, Decision Tree, Random Forest, XGBoost, dan LightGBM.
- Penerapan balancing data menggunakan SMOTE dan ADASYN.
- Feature selection menggunakan Recursive Feature Elimination (RFE) dan RFECV.

### **Chapter 7: Hyperparameter Tuning**
- Implementasi **Randomized Search** dan **Optuna** untuk menemukan kombinasi hyperparameter optimal pada XGBoost.
- Evaluasi model dengan cross-validation.

### **Chapter 8: Final Model**
- Training ulang model terbaik dengan hyperparameter optimal.
- Evaluasi performa model berdasarkan metrik utama: F2-score, PRC-AUC, dan Recall.

### **Chapter 9: Interpretasi Model dengan Explainable AI**
- Analisis **feature importance** menggunakan SHAP untuk memahami faktor yang paling berpengaruh terhadap churn.
- Penerapan **LIME** untuk melihat bagaimana model mengambil keputusan pada level individual.

### **Chapter 10: Model Deployment**
- Model diintegrasikan ke dalam WebApp Streamlit untuk memungkinkan tim pemasaran mengakses prediksi churn secara real-time.

### **Chapter 11: Conclusion**
- Evaluasi dampak model terhadap efisiensi biaya pemasaran dan retensi pelanggan.
- Analisis dampak finansial dari pengurangan churn.

### **Chapter 12: Recommendations**
- **Untuk bisnis**: Optimalisasi program loyalitas, peningkatan layanan pelanggan berbasis AI, dan strategi retargeting pelanggan churn.
- **Untuk model**: Pengembangan lebih lanjut dengan model deep learning untuk meningkatkan akurasi.
- **Untuk data**: Pengumpulan lebih banyak variabel yang mungkin memiliki korelasi tinggi dengan churn.

## Hasil dan Insight
- Pelanggan dengan **tenure pendek, cashback lebih sedikit, dan sering mengajukan keluhan** lebih cenderung churn.
- Pelanggan dengan jarak gudang lebih jauh dan jumlah pesanan lebih sedikit memiliki kemungkinan churn lebih tinggi.
- Model **XGBoost dengan hyperparameter tuning mencapai F2-score sebesar 0.82 dan PRC-AUC sebesar 0.79**, menunjukkan performa yang baik dalam mendeteksi pelanggan churn.


## Rekomendasi Bisnis
1. **Segmentasi pelanggan berdasarkan tingkat risiko churn**:
   - Pelanggan dengan risiko tinggi diberikan insentif loyalitas dan layanan prioritas.
   - Pelanggan dengan risiko sedang diberikan promo berbasis histori pembelian.
   - Pelanggan dengan risiko rendah ditargetkan untuk upselling dan cross-selling.

2. **Optimasi anggaran promosi**:
   - Model prediksi churn membantu perusahaan mengalokasikan promosi hanya kepada pelanggan dengan risiko tinggi dan sedang, menghemat lebih dari **₹45 juta per bulan**.

3. **Peningkatan pengalaman pelanggan**:
   - Menyediakan **pengiriman prioritas** bagi pelanggan dengan churn probability tinggi.
   - Menggunakan **chatbot AI** untuk menangani keluhan pelanggan dengan lebih cepat.

4. **Retargeting pelanggan dengan pola transaksi tidak stabil**:
   - Menggunakan automated email dan push notification untuk mengingatkan pelanggan kembali bertransaksi.

5. **Deployment dan automasi**:
   - WebApp Streamlit memungkinkan tim pemasaran memasukkan data pelanggan dan mendapatkan prediksi churn secara real-time.
   - Model terintegrasi dengan sistem CRM untuk otomatisasi keputusan pemasaran.

## Limitasi Proyek
Meskipun model ini memberikan prediksi churn yang cukup akurat, terdapat beberapa keterbatasan yang perlu diperhatikan:
1. **Keterbatasan data fitur pelanggan**  
   - Dataset tidak mencakup beberapa faktor eksternal yang mungkin mempengaruhi churn, seperti tren pasar, strategi kompetitor, dan kebijakan promosi dari pesaing.

2. **Imbalanced Dataset**  
   - Meskipun telah dilakukan balancing dengan teknik SMOTE dan ADASYN, kelas pelanggan churn tetap lebih sedikit dibanding pelanggan yang bertahan.

3. **Prediksi churn berbasis pola historis**  
   - Model hanya memprediksi churn berdasarkan pola data historis. Jika terjadi perubahan tren drastis, model mungkin perlu retraining lebih sering.

