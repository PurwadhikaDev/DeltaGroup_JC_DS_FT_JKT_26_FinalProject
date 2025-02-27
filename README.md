# DeltaGroup_JC_DS_FT_JKT_26_FinalProject

# E-Commerce Customer Churn Prediction 
---

**Delta Group JCDS2604 Purwadhika**
- [Nur Faaizah Faradhilah Ridwan](https://www.linkedin.com/in/nur-faaizah-faradhilah-ridwan/) JCDS-2604-007
- [Farhan Sandika Sumarna](https://www.linkedin.com/in/farhansandika/) JCDS-2604-015
- [Rina Adibah](https://www.linkedin.com/in/rina-adibah/) JCDS-2604-019

Batch: 2604 [Purwadhika Digital Technology School](https://www.purwadhika.com/)

---

## Overview
Customer churn merupakan tantangan besar dalam industri e-commerce. Dengan melakukan analisis mendalam dan membangun model Machine Learning, kita dapat mengidentifikasi penyebab utama churn, memprediksi pelanggan yang berisiko churn, serta mengambil tindakan strategis untuk meningkatkan retensi pelanggan. Proyek ini bertujuan untuk menganalisis data dan membangun model prediksi churn yang akurat menggunakan algoritma Machine Learning.

---

## Table of Contents

- [Business Understanding](#business-understanding)
- [Data Understanding](#data-understanding)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Preprocessing](#data-preprocessing)
- [Data Analysis](#data-analysis)
- [Feature Engineering](#feature-engineering)
- [Model Benchmarking & Optimization](#model-benchmarking--optimization)
- [Hyperparameter Tuning](#hyperparameter-tuning)
- [Final Model & Evaluation](#final-model--evaluation)
- [Model Interpretation](#model-interpretation)
- [Deployment](#deployment)
- [Conclusion & Recommendations](#conclusion--recommendations)
- [Limitations of the Project](#limitations-of-the-project)
- [Software Requirements](#software-requirements)
- [Dependencies & Libraries Used](#dependencies---libraries-sed)
- [Final Thoughts](#final-thoughts)
- [Tableau Dashboard](#tableau-dashboard)

---

## Business Understanding
### Context
Customer churn adalah fenomena di mana pelanggan berhenti menggunakan layanan. Studi menunjukkan bahwa **mengurangi churn sebesar 5% dapat meningkatkan profit hingga 95%**. Oleh karena itu, memahami faktor penyebab churn dan memprediksi pelanggan yang berisiko churn dapat membantu perusahaan mengalokasikan sumber daya dengan lebih efisien.

### Business Goals
- Mengidentifikasi faktor utama yang mempengaruhi churn.
- Membangun model prediksi churn berbasis Machine Learning.
- Mengembangkan strategi retensi pelanggan berbasis data.

### Stakeholders
- **Chief Marketing Officer (CMO):** Membutuhkan insight untuk strategi retensi pelanggan.

### Metric Evaluation
- **F2-Score:** Memprioritaskan recall agar pelanggan churn dapat terdeteksi.
- **PRC-AUC (Precision-Recall Curve AUC):** Mengukur keseimbangan antara precision dan recall.
- **ROC-AUC Score:** Menilai kemampuan model dalam membedakan pelanggan churn dan non-churn.

---

## Data Understanding
- **Dataset Source:** Kaggle - [E-Commerce Customer Churn Analysis](https://www.kaggle.com/datasets/ankitverma2010/ecommerce-customer-churn-analysis-and-prediction/data)
- **Jumlah pelanggan:** 5,630
- **Fitur utama:**
  - **Numerik:** `Tenure`, `OrderCount`, `CashbackAmount`, `SatisfactionScore`, dll.
  - **Kategorikal:** `PreferredLoginDevice`, `PreferredPaymentMode`, `MaritalStatus`, `PreferedOrderCat`, dll.

---

## Exploratory Data Analysis
- **Univariate Analysis:** Histogram, QQPlot, Boxplot.
- **Bivariate Analysis:** Spearman Correlation Matrix, Cramér’s V.
- **Distribusi Data:** Dataset tidak seimbang (**83.16% pelanggan tidak churn, 16.84% churn**).

---

## Data Preprocessing
- **Handling Missing Values:** Iterative Imputer untuk data numerik, Mode Imputation untuk kategorikal.
- **Handling Outliers:** RobustScaler untuk normalisasi data.
- **Encoding:** Label Encoding & One-Hot Encoding.
- **Balancing Data:** SMOTE, ADASYN, Random Oversampling.

---

## Data Analysis
- **Customer Segmentation Identification:** Berdasarkan `Tenure` dan `Churn`
- **Customer Demographic Analysis:** Berdasarkan `Gender`, `City Tier`, `Marital Status`, `Number of Address`, dan `Warehouse to Home`
- **Purchase Behaviour Analysis:**  Berdasarkan `Preferred Order Category`, `Preferred Payment Mode`, `Coupon Used`, `Cashback Amount`, dan kolom lainnya
- **Interaction with the Application:** Berdasarkan `Preferred Log In Device`, `Hour Spend on App`, dan `Number of Device Registered`
- **Customer Satisfaction:** Berdasarkan `Complain` dan `Satisfaction Score`

---

## Feature Engineering
- **Feature Selection:** Recursive Feature Elimination (RFE) & RFECV.
- **Feature Transformation:** Polynomial Features.
- **Interaction Features:** Kombinasi antar fitur untuk meningkatkan akurasi.

---

## Model Benchmarking & Optimization
- **Algoritma yang diuji:**
  - Logistic Regression
  - Decision Tree
  - Random Forest
  - XGBoost (Model Terbaik)
  - LightGBM
- **Model XGBoost menunjukkan performa terbaik dengan F2 Score = 0.9799**.

---

## Hyperparameter Tuning
- **Random Search vs Optuna:**
  - Optuna menghasilkan F2 Score tertinggi (0.8713).
  - Random Search lebih cepat (0.91 menit) dibandingkan Optuna (5.77 menit).

---

## Final Model & Evaluation
- **Threshold Optimization:** Threshold optimal = 0.7 untuk keseimbangan precision-recall.
- **Confusion Matrix:** False Negative sangat rendah (4 pelanggan churn tidak terdeteksi).
- **Final Metrics:**
  - **F2 Score (Test Set) = 0.9617**
  - **ROC-AUC Score = 0.9974**
  - **PRC-AUC = 0.9872**

---

## Model Interpretation
- SHAP & LIME digunakan untuk memahami faktor utama yang mempengaruhi churn.
- Faktor terpenting dalam prediksi churn:
  - `Tenure` (Lama pelanggan berlangganan)
  - `Complain` (Apakah pelanggan pernah mengajukan keluhan)
  - `Satisfaction Score` (Skor kepuasan pelanggan)

---

## Deployment
- **WebApp Streamlit:**
  - Memungkinkan perusahaan memasukkan data pelanggan untuk mendapatkan prediksi churn secara real-time.

---

## Conclusion & Recommendations
### Business Impact
- Preferensi Kategori Pembelian, Jumlah Cashback yang Diterima Pelanggan, Komplain, dan Nilai Kepuasan menjadi faktor yang mempengaruhi churn pelanggan.
- Tanpa Machine Learning, perusahaan mengalami kerugian ₹45.2 juta per bulan akibat churn.
- Dengan Machine Learning, total kerugian turun menjadi hanya ₹178.5 ribu per bulan.
- Penghematan biaya mencapai ₹45 juta per bulan.

### Recommendations
1. Targetkan pelanggan berisiko tinggi dengan promosi eksklusif.
2. Optimalkan metode pembayaran digital untuk meningkatkan loyalitas.
3. Terapkan strategi customer engagement berbasis Machine Learning.
4. Gunakan retargeting berbasis data untuk pelanggan yang memiliki kemungkinan churn tinggi.
5. Pantau performa model secara berkala dan lakukan retraining dengan data terbaru.

---
## Limitations of the Project
Meskipun proyek ini berhasil membangun model prediksi churn dengan performa tinggi, terdapat beberapa keterbatasan yang perlu diperhatikan:

1. Ketergantungan pada Data Historis
   - Model hanya dilatih berdasarkan data transaksi dan interaksi pelanggan di platform e-commerce.
   - Tidak menggunakan data eksternal, seperti sentimen pelanggan dari media sosial, ulasan produk, atau faktor ekonomi makro.

2. Tidak Menangani Churn dalam Jangka Waktu Tertentu
   - Model ini bersifat **binary classification (Churn vs. Not Churn)** dan tidak memprediksi dalam berapa lama pelanggan akan churn.
   - Untuk memahami waktu hingga pelanggan churn, diperlukan **Survival Analysis** yang tidak diterapkan dalam proyek ini.

4. Tidak Menangani Berbagai Jenis Churn
   - Model ini hanya membedakan pelanggan **churn vs. tidak churn** tanpa membedakan penyebabnya.
   - Dalam real-world business, churn bisa dibagi menjadi:
     - **Voluntary Churn** (Pelanggan berhenti karena preferensi atau alasan pribadi).
     - **Involuntary Churn** (Pelanggan churn akibat kegagalan pembayaran atau kendala teknis).
       
---

## Software Requirements

Sebelum menjalankan proyek ini, pastikan software berikut telah diinstal:

- **Operating System:** Windows 10 / 11, macOS, atau Linux.
- **Python:** Versi **3.8 atau lebih tinggi**.
- **Jupyter Notebook / JupyterLab:** Untuk eksplorasi dan pengolahan data.
- **Anaconda (Opsional):** Disarankan untuk mengelola lingkungan Python dan dependensi.

---

## Dependencies & Libraries Used

Proyek ini menggunakan berbagai library Python untuk manipulasi data, analisis statistik, visualisasi, rekayasa fitur, pemodelan machine learning, evaluasi model, serta deployment. Pastikan semua dependensi telah terinstal sebelum menjalankan proyek.

### **Data Manipulation & Statistical Analysis**
- `numpy` – Operasi vektor dan matriks numerik.
- `pandas` – Manipulasi dan analisis dataset.
- `scipy.stats` – Uji statistik seperti Chi-Square dan Spearman correlation.

### **Data Visualization**
- `matplotlib` – Visualisasi data dasar (histogram, scatter plot, dll.).
- `seaborn` – Visualisasi statistik yang lebih kompleks.
- `missingno` – Analisis missing values dalam dataset.

### **Feature Engineering & Preprocessing**
- `sklearn.pipeline.Pipeline` – Automasi preprocessing.
- `sklearn.impute` – Penanganan missing values IterativeImputer.
- `sklearn.preprocessing` – Encoding, scaling, dan transformasi fitur.
- `sklearn.feature_selection` – Pemilihan fitur menggunakan SelectKBest, RFE, RFECV.

### **Machine Learning Models**
- `sklearn.linear_model.LogisticRegression` – Model regresi logistik untuk baseline.
- `sklearn.tree.DecisionTreeClassifier` – Model decision tree sederhana.
- `xgboost.XGBClassifier` – Algoritma boosting berbasis gradient boosting.
- `lightgbm.LGBMClassifier` – Alternatif XGBoost dengan optimasi lebih cepat.
- `sklearn.neighbors.KNeighborsClassifier` – Model berbasis K-Nearest Neighbors.
- `sklearn.svm.SVC` – Support Vector Machine untuk klasifikasi.

### **Model Evaluation & Hyperparameter Tuning**
- `sklearn.model_selection` – Split dataset, cross-validation, dan hyperparameter tuning.
- `sklearn.metrics` – Evaluasi performa model menggunakan berbagai metrik (Accuracy, Precision, Recall, F2 Score, ROC-AUC).
- `optuna` – Framework hyperparameter tuning otomatis.
- `scipy.stats` – Distribusi probabilitas untuk tuning parameter.

### **Handling Imbalanced Data**
- `imblearn.over_sampling` – Teknik balancing data seperti SMOTE, ADASYN, Random Oversampling.
- `imblearn.under_sampling` – Teknik undersampling untuk mengurangi dominasi kelas mayoritas.

### **Explainable AI (XAI)**
- `shap` – Analisis feature importance berbasis SHAP values.
- `lime.lime_tabular` – Teknik Local Interpretable Model-Agnostic Explanations (LIME) untuk interpretasi model.

### **Model Saving & Deployment**
- `pickle` – Menyimpan dan memuat model dalam format `.pkl`.
- `streamlit` – Membangun antarmuka WebApp interaktif untuk prediksi customer churn.

### **Miscellaneous**
- `warnings` – Mengabaikan peringatan selama proses eksekusi.
- `time` – Mengukur durasi eksekusi model.
- `collections.Counter` – Menganalisis distribusi label pada dataset.

---

## Final Thoughts
Proyek ini membuktikan bahwa **Machine Learning dapat digunakan untuk memprediksi churn dengan akurasi tinggi dan memberikan dampak bisnis yang signifikan**. Dengan model yang telah dikembangkan, perusahaan dapat menghemat biaya promosi yang tidak efisien, meningkatkan loyalitas pelanggan, serta meningkatkan profitabilitas bisnis.

---

## Tableau Dashboard
[Customer Churn Dashboard](https://public.tableau.com/app/profile/farhan.s.sumarna/viz/CustomerChurnDashboard-Delta/CustomerBehaviorDashboard)

Tableau Dashboard ini menyediakan visualisasi komprehensif tentang pola churn pelanggan, membantu bisnis menganalisis faktor-faktor utama yang mempengaruhi churn, termasuk segmentasi pelanggan dan demografi, perilaku pelanggan, kepuasan pelanggan, serta interaksi perangkat lunak, yang mencakup perangkat apa yang paling sering digunakan pelanggan dalam e-commerce ini.



