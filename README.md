# scikit-learn Cookbook

Repository ini berisi **reproduksi kode Python**, **ringkasan setiap chapter**, dan **penjelasan teori** dari buku
*scikit-learn Cookbook: Over 80 recipes for machine learning in Python with scikit-learn* (3rd Edition)
karya **John Sukup** (Packt, 2025 — tersedia di O'Reilly Learning).

Dibuat untuk memenuhi **Tugas 2 — Enrichment for Machine Learning Class (Individual Task)**:
*"Code Reproduction + Theoretical Deep-Dive from scikit-learn Cookbook"*.

| | |
|---|---|
| **Nama** | Ahmad Ghazali El Faruqi Hsb |
| **NIM** | 101032330080 |
| **Mata Kuliah** | Machine Learning |

---

## 📁 Struktur Repository

```
scikit-learn-Cookbook/
├── README.md
├── requirements.txt
└── notebooks/
    ├── Chapter01_Common_Conventions_and_API_Elements.ipynb
    ├── Chapter02_Pre-Model_Workflow_and_Data_Preprocessing.ipynb
    ├── Chapter03_Dimensionality_Reduction_Techniques.ipynb
    ├── Chapter04_Distance_Metrics_and_Nearest_Neighbors.ipynb
    └── Chapter05_Linear_Models_and_Regularization.ipynb
```

Setiap notebook disusun dengan pola: **teori → kode → interpretasi output** untuk setiap recipe, lalu ditutup dengan **ringkasan chapter**.
Semua dataset yang dipakai adalah dataset bawaan scikit-learn (`load_*`, `fetch_*`, `make_*`), jadi tidak perlu mengunduh file data terpisah (khusus `fetch_california_housing` membutuhkan koneksi internet saat pertama kali dijalankan).

---

## 📚 Ringkasan Isi Setiap Chapter

| # | Chapter | Status |
|---|---|---|
| 01 | Common Conventions and API Elements of scikit-learn | ✅ |
| 02 | Pre-Model Workflow and Data Preprocessing | ✅ |
| 03 | Dimensionality Reduction Techniques | ✅ |
| 04 | Building Models with Distance Metrics and Nearest Neighbors | ✅ |
| 05 | Linear Models and Regularization | ✅ |
| 06 | Advanced Logistic Regression and Extensions | ⏳ (deadline 17 Okt 2026) |
| 07 | Support Vector Machines and Kernel Methods | ⏳ (deadline 17 Okt 2026) |
| 08 | Tree-Based Algorithms and Ensemble Methods | ⏳ (deadline 17 Okt 2026) |

### [Chapter 1 — Common Conventions and API Elements of scikit-learn](notebooks/Chapter01_Common_Conventions_and_API_Elements.ipynb)
Fondasi untuk seluruh buku: **cara kerja API scikit-learn**. Membahas prinsip desain library (konsistensi, inspeksi, komposisi, default yang masuk akal), representasi data sebagai **feature matrix `X`** berukuran `(n_samples, n_features)` dan **target `y`**, serta dataset bawaan (`load_*`, `make_*`). Inti chapter ini adalah tiga jenis objek: **Estimator** (`fit`, hyperparameter vs atribut hasil belajar berakhiran `_`), **Predictor** (`predict`, `predict_proba`, `score`), dan **Transformer** (`fit`, `transform`, `fit_transform`). Dibahas juga `train_test_split`, **Pipeline** dan `ColumnTransformer` untuk menggabungkan langkah-langkah, serta penyimpanan model dengan **joblib**.

### [Chapter 2 — Pre-Model Workflow and Data Preprocessing](notebooks/Chapter02_Pre-Model_Workflow_and_Data_Preprocessing.ipynb)
Menyiapkan data sebelum masuk ke model, karena kualitas model sangat bergantung pada kualitas data. Topiknya meliputi **penanganan missing data** (`SimpleImputer`, `KNNImputer`, `IterativeImputer`), **teknik scaling** (`StandardScaler`, `MinMaxScaler`, `Normalizer`), **encoding variabel kategorikal** (`OneHotEncoder`, `LabelEncoder`, `ColumnTransformer`), **Pipeline** beserta visualisasinya, dan **feature engineering** (`PolynomialFeatures`, `KBinsDiscretizer`, serta seleksi fitur dengan `RFE` dan `SelectFromModel`). Chapter ditutup dengan latihan membangun pipeline preprocessing lengkap + Random Forest pada dataset **California Housing**.

### [Chapter 3 — Dimensionality Reduction Techniques](notebooks/Chapter03_Dimensionality_Reduction_Techniques.ipynb)
Mengurangi jumlah fitur sambil mempertahankan informasi penting, untuk melawan **curse of dimensionality**, mempercepat training, dan memudahkan visualisasi. Dibahas **PCA** (proyeksi ke arah variansi maksimum, *explained variance ratio*), **LDA** (proyeksi *supervised* yang memaksimalkan separasi antar kelas), dan **t-SNE** (embedding non-linear untuk visualisasi struktur lokal). Latihannya menggabungkan PCA dengan Logistic Regression dan memakai t-SNE untuk memvisualisasikan cluster.

### [Chapter 4 — Building Models with Distance Metrics and Nearest Neighbors](notebooks/Chapter04_Distance_Metrics_and_Nearest_Neighbors.ipynb)
Model berbasis jarak: **k-Nearest Neighbors (KNN)** memprediksi berdasarkan tetangga terdekat di ruang fitur. Topiknya meliputi cara kerja KNN, **metrik jarak** (Euclidean, Manhattan, Minkowski, dsb.) dan pengaruhnya, pentingnya scaling, **hyperparameter tuning** (`n_neighbors`, `weights`, `metric`) dengan `GridSearchCV`, serta **evaluasi performa** (accuracy, confusion matrix, classification report).

### [Chapter 5 — Linear Models and Regularization](notebooks/Chapter05_Linear_Models_and_Regularization.ipynb)
Model linear sebagai *baseline* yang kuat dan mudah diinterpretasi. Dibahas **Linear Regression** (Ordinary Least Squares), lalu **regularization** untuk mencegah overfitting: **Ridge** (penalti L2, mengecilkan koefisien), **Lasso** (penalti L1, menghasilkan koefisien nol / seleksi fitur), dan **ElasticNet** (gabungan L1 dan L2). Chapter ini juga membahas **Polynomial Regression** dan **spline** untuk menangkap hubungan non-linear, serta *bias–variance trade-off*.

### Chapter 6 — Advanced Logistic Regression and Extensions *(menyusul)*
Klasifikasi dengan **Logistic Regression**: fungsi sigmoid dan log-loss, **klasifikasi multiclass** (One-vs-Rest, multinomial/softmax), **regularization** pada logistic regression (parameter `C`, L1/L2), **klasifikasi multilabel**, serta **metrik evaluasi** (precision, recall, F1, ROC-AUC).

### Chapter 7 — Support Vector Machines and Kernel Methods *(menyusul)*
**Support Vector Machine**: mencari *hyperplane* dengan margin maksimum, soft margin (parameter `C`), dan **kernel trick** (linear, polynomial, RBF) untuk data non-linear. Dibahas juga tuning `C` dan `gamma`, SVM pada data berdimensi tinggi, dan evaluasi model SVM.

### Chapter 8 — Tree-Based Algorithms and Ensemble Methods *(menyusul)*
**Decision Tree** (impurity Gini/entropy, pruning), lalu metode ensemble: **Random Forest dan Bagging** (mengurangi variance), **Gradient Boosting** (mengurangi bias secara bertahap), **hyperparameter tuning** untuk tree/ensemble, dan **perbandingan metode ensemble**.

---

## ⚙️ Cara Menjalankan

```bash
git clone https://github.com/<username>/scikit-learn-Cookbook.git
cd scikit-learn-Cookbook
pip install -r requirements.txt
jupyter notebook
```
Buka notebook di folder `notebooks/`, lalu jalankan **Run All**. Notebook diuji dengan Python 3.12 dan scikit-learn 1.9.

---

## 📖 Referensi
- Sukup, J. (2025). *scikit-learn Cookbook* (3rd ed.). Packt Publishing.
- Kode resmi buku: https://github.com/PacktPublishing/scikit-learn-Cookbook-Third-Edition
- Dokumentasi scikit-learn: https://scikit-learn.org/stable/
