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
    ├── Chapter05_Linear_Models_and_Regularization.ipynb
    ├── Chapter06_Advanced_Logistic_Regression_and_Extensions.ipynb
    ├── Chapter07_Support_Vector_Machines_and_Kernel_Methods.ipynb
    ├── Chapter08_Tree-Based_Algorithms_and_Ensemble_Methods.ipynb
    ├── Chapter09_Text_Processing_and_Multiclass_Classification.ipynb
    ├── Chapter10_Clustering_Techniques.ipynb
    ├── Chapter11_Outlier_and_Novelty_Detection.ipynb
    ├── Chapter12_Cross-Validation_and_Model_Evaluation_Techniques.ipynb
    └── Chapter13_Deploying_scikit-learn_Models_in_Production.ipynb
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
| 06 | Advanced Logistic Regression and Extensions | ✅ |
| 07 | Support Vector Machines and Kernel Methods | ✅ |
| 08 | Tree-Based Algorithms and Ensemble Methods | ✅ |
| 09 | Text Processing and Multiclass Classification | ✅ |
| 10 | Clustering Techniques | ✅ |
| 11 | Outlier and Novelty Detection | ✅ |
| 12 | Cross-Validation and Model Evaluation Techniques | ✅ |
| 13 | Deploying scikit-learn Models in Production | ✅ |

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

### [Chapter 6 — Advanced Logistic Regression and Extensions](notebooks/Chapter06_Advanced_Logistic_Regression_and_Extensions.ipynb)
Klasifikasi dengan **Logistic Regression**: fungsi sigmoid, log-odds, dan *log-loss*. Dibahas **klasifikasi multiclass** (One-vs-Rest vs multinomial/softmax), **regularisasi** (parameter `C`, penalti L2/Ridge dan L1/Lasso yang menghasilkan koefisien nol), **klasifikasi multilabel** (`MultiOutputClassifier`), serta **metrik evaluasi** (confusion matrix, precision, recall, F1, ROC-AUC). Latihannya meliputi L1 untuk seleksi fitur, evaluasi model multinomial, dan visualisasi *decision boundary*.

### [Chapter 7 — Support Vector Machines and Kernel Methods](notebooks/Chapter07_Support_Vector_Machines_and_Kernel_Methods.ipynb)
**Support Vector Machine** mencari *hyperplane* dengan **margin maksimum**; *support vector* adalah titik yang menentukan batas tersebut. Dibahas soft margin (parameter `C`), **kernel trick** (linear, polynomial, RBF, sigmoid) untuk data yang tidak terpisah secara linear, **tuning `C` dan `gamma`** dengan `GridSearchCV`, SVM pada **data berdimensi tinggi**, dan evaluasi model SVM. Latihannya: SVM pada Iris, grid search pada Breast Cancer, dan visualisasi decision boundary 2D.

### [Chapter 8 — Tree-Based Algorithms and Ensemble Methods](notebooks/Chapter08_Tree-Based_Algorithms_and_Ensemble_Methods.ipynb)
**Decision Tree** (impurity Gini/entropy, kedalaman pohon, pruning), lalu metode ensemble: **Bagging dan Random Forest** yang mengurangi *variance* dengan merata-ratakan banyak pohon, **Gradient Boosting** yang mengurangi *bias* dengan menambah pohon secara bertahap untuk memperbaiki residual, **hyperparameter tuning** untuk pohon dan ensemble, serta **perbandingan bagging, boosting, dan stacking**.

### [Chapter 9 — Text Processing and Multiclass Classification](notebooks/Chapter09_Text_Processing_and_Multiclass_Classification.ipynb)
Mengubah **teks menjadi fitur numerik** agar bisa dipakai model: tokenisasi, stop words, *stemming*/lemmatization, **Bag-of-Words** (`CountVectorizer`) dan **TF-IDF** (`TfidfVectorizer`), serta n-gram. Fitur teks tersebut dipakai untuk **klasifikasi multiclass** dengan Naive Bayes, SVM, dan Logistic Regression, termasuk strategi **One-vs-Rest** dan **One-vs-One**, lalu dievaluasi dengan `classification_report` per kelas. Dataset utamanya adalah korpus **Brown** dari NLTK.

### [Chapter 10 — Clustering Techniques](notebooks/Chapter10_Clustering_Techniques.ipynb)
Mengelompokkan data **tanpa label**. Dimulai dari persiapan data (scaling), lalu **K-Means** (inisialisasi k-means++, *elbow method*), **Hierarchical Clustering** (dendrogram dan linkage), **DBSCAN** (cluster berbasis kepadatan yang bisa mendeteksi noise dan bentuk tidak beraturan), dan **metrik evaluasi** (silhouette score, Davies–Bouldin, Calinski–Harabasz, ARI). Dibahas juga cara memilih algoritma yang tepat, serta teknik lanjutan **Spectral Clustering** dan **Gaussian Mixture Models**.

### [Chapter 11 — Outlier and Novelty Detection](notebooks/Chapter11_Outlier_and_Novelty_Detection.ipynb)
Membedakan **outlier detection** (data latih sudah tercemar anomali) dan **novelty detection** (data latih bersih, lalu mendeteksi data baru yang menyimpang). Algoritma yang dibahas: **Isolation Forest** (anomali lebih cepat terisolasi oleh pemisahan acak), **One-Class SVM** (batas di sekitar data normal), dan **Local Outlier Factor** (membandingkan kepadatan lokal). Dibahas juga evaluasi detektor (precision/recall saat label tersedia), cara menangani outlier yang terdeteksi (hapus, *cap*/winsorize, transformasi), dan pemilihan teknik yang tepat.

### [Chapter 12 — Cross-Validation and Model Evaluation Techniques](notebooks/Chapter12_Cross-Validation_and_Model_Evaluation_Techniques.ipynb)
Mengestimasi performa model pada data baru dengan **validasi silang**. Materinya mencakup **K-Fold** dan **Stratified K-Fold** (menjaga proporsi kelas tiap fold), **LOOCV**, dan **nested CV** yang memisahkan tuning hyperparameter dari evaluasi agar skor tidak bias optimistis. Diperkenalkan juga API `cross_val_score`, `cross_validate`, serta **`GridSearchCV` vs `RandomizedSearchCV`**. Bagian terakhir memakai **learning curve** dan **validation curve** untuk mendiagnosis underfitting dan overfitting.

### [Chapter 13 — Deploying scikit-learn Models in Production](notebooks/Chapter13_Deploying_scikit-learn_Models_in_Production.ipynb)
Membawa model dari notebook ke **produksi**: menyajikan model sebagai **REST API** (Flask/FastAPI, disimulasikan di dalam notebook) dan mengemasnya dengan Docker, **serialisasi** (`joblib`/`pickle`, format aman `skops`, dan ONNX), **scaling** model untuk produksi, **monitoring** (mendeteksi *data drift* dan penurunan akurasi), **siklus hidup model** (versioning dan retraining), serta **deployment pipeline** dengan *validation gate* sebelum model baru dirilis.

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
