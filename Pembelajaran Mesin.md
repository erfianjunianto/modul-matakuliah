
# 📘 MATA KULIAH: PEMBELAJARAN MESIN (MACHINE LEARNING)
## Program Studi: Sistem Informasi (S1)
### Dosen Pengampu: Erfian Junianto, S.T., M.Kom., CDMP
### Semester: 6 | SKS: 3
---

# 🧠 Deskripsi Umum
Mata kuliah ini membahas konsep, teori, dan praktik penerapan algoritma *Machine Learning* dalam menyelesaikan permasalahan berbasis data. Mahasiswa akan memahami pipeline pembelajaran mesin, mulai dari preprocessing data, pelatihan model, evaluasi, hingga penerapan model pada kasus nyata.

---

# 🎯 Capaian Pembelajaran
1. Mahasiswa mampu memahami konsep dasar pembelajaran mesin.
2. Mahasiswa mampu mengimplementasikan algoritma supervised dan unsupervised learning.
3. Mahasiswa mampu menggunakan pustaka Python (scikit-learn, pandas, numpy) untuk membangun model ML.
4. Mahasiswa mampu mengevaluasi performa model dengan metrik yang sesuai.
5. Mahasiswa mampu membuat proyek machine learning berbasis data nyata.

---

# 📅 RENCANA PEMBELAJARAN PER PERTEMUAN

---

## 🧩 **Pertemuan 1 — Pengantar Machine Learning**
### Tujuan Pembelajaran
Mahasiswa memahami konsep dasar pembelajaran mesin, perbedaannya dengan AI dan data mining, serta jenis-jenis pembelajaran mesin.

### Materi Pokok
- Definisi Machine Learning (Tom Mitchell, 1997)
- Hubungan antara AI, ML, dan Deep Learning
- Jenis pembelajaran mesin: Supervised, Unsupervised, Reinforcement
- Komponen utama ML: Data, Model, Algoritma, Evaluasi
- Contoh penerapan ML di Sistem Informasi

### Contoh Kasus
Prediksi kelulusan mahasiswa berdasarkan nilai ujian.

### Latihan
Tuliskan contoh penggunaan ML dalam kehidupan sehari-hari.

---

## 🧩 **Pertemuan 2 — Workflow dan Data Pipeline**
### Tujuan
Mahasiswa memahami alur kerja machine learning dari data mentah hingga model.

### Materi
- Tahapan ML pipeline: Data Collection → Cleaning → Feature Selection → Training → Evaluation → Deployment
- Dataset: bentuk, tipe data, dan label
- Train-test split
- Feature extraction dan feature scaling

### Praktik
```python
import pandas as pd
from sklearn.model_selection import train_test_split

data = pd.read_csv('student_scores.csv')
X = data[['Hours']]
y = data['Scores']
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)
```

---

## 🧩 **Pertemuan 3 — Supervised Learning: Regresi**

### Tujuan

Mahasiswa mampu menjelaskan dan menerapkan algoritma regresi linear dan logistik.

### Materi

* Konsep supervised learning
* Linear Regression (Continuous Target)
* Logistic Regression (Categorical Target)
* Konsep *Loss Function* dan *Gradient Descent*

### Praktik

```python
from sklearn.linear_model import LinearRegression
model = LinearRegression()
model.fit(X_train, y_train)
pred = model.predict(X_test)
```

### Evaluasi

Gunakan `mean_squared_error` untuk menilai akurasi model.

---

## 🧩 **Pertemuan 4 — Supervised Learning: Klasifikasi**

### Tujuan

Mahasiswa memahami klasifikasi dengan Decision Tree dan KNN.

### Materi

* Konsep klasifikasi
* Decision Tree Classifier
* K-Nearest Neighbors
* Train, predict, evaluate

### Praktik

```python
from sklearn.tree import DecisionTreeClassifier
clf = DecisionTreeClassifier()
clf.fit(X_train, y_train)
y_pred = clf.predict(X_test)
```

---

## 🧩 **Pertemuan 5 — Unsupervised Learning: Clustering**

### Tujuan

Mahasiswa memahami prinsip clustering tanpa label.

### Materi

* Konsep unsupervised learning
* K-Means clustering
* Hierarchical clustering
* Evaluasi menggunakan silhouette score

### Praktik

```python
from sklearn.cluster import KMeans
kmeans = KMeans(n_clusters=3)
kmeans.fit(X)
```

---

## 🧩 **Pertemuan 6 — Data Preprocessing**

### Tujuan

Mahasiswa mampu melakukan pembersihan dan transformasi data.

### Materi

* Handling missing values
* Encoding categorical data
* Normalization & Standardization
* Feature scaling

### Praktik

```python
from sklearn.preprocessing import StandardScaler
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)
```

---

## 🧩 **Pertemuan 7 — Evaluasi Model**

### Tujuan

Mahasiswa mampu menilai kinerja model ML dengan metrik yang tepat.

### Materi

* Confusion Matrix
* Accuracy, Precision, Recall, F1-score
* ROC Curve dan AUC
* Cross-validation

### Praktik

```python
from sklearn.metrics import confusion_matrix, classification_report
print(confusion_matrix(y_test, y_pred))
print(classification_report(y_test, y_pred))
```

---

## 🧩 **Pertemuan 8 — Ujian Tengah Semester (UTS)**

### Bentuk Ujian

* Teori konsep ML
* Implementasi sederhana supervised dan unsupervised learning

---

## 🧩 **Pertemuan 9 — Ensemble Learning**

### Tujuan

Mahasiswa memahami konsep kombinasi beberapa model untuk hasil lebih baik.

### Materi

* Ensemble: Bagging, Boosting, Stacking
* Random Forest, AdaBoost, Gradient Boosting
* Voting Classifier

### Praktik

```python
from sklearn.ensemble import RandomForestClassifier
rf = RandomForestClassifier()
rf.fit(X_train, y_train)
```

---

## 🧩 **Pertemuan 10 — Feature Engineering**

### Tujuan

Mahasiswa mampu meningkatkan performa model dengan fitur baru.

### Materi

* Feature selection
* Feature extraction
* Encoding dan polynomial feature

### Praktik

```python
from sklearn.preprocessing import PolynomialFeatures
poly = PolynomialFeatures(degree=2)
X_poly = poly.fit_transform(X)
```

---

## 🧩 **Pertemuan 11 — Overfitting dan Regularisasi**

### Tujuan

Mahasiswa mampu mengenali dan mengatasi overfitting.

### Materi

* Bias vs Variance
* Overfitting vs Underfitting
* Regularization (L1, L2)
* Cross-validation

### Praktik

```python
from sklearn.linear_model import Ridge
ridge = Ridge(alpha=1.0)
ridge.fit(X_train, y_train)
```

---

## 🧩 **Pertemuan 12 — Pengenalan Deep Learning**

### Tujuan

Mahasiswa mengenal konsep Neural Network dan arsitektur dasar Deep Learning.

### Materi

* Perceptron
* Multi-Layer Perceptron (MLP)
* Aktivasi: Sigmoid, ReLU
* Framework: TensorFlow & PyTorch

### Praktik

```python
from sklearn.neural_network import MLPClassifier
mlp = MLPClassifier(hidden_layer_sizes=(10,10), max_iter=1000)
mlp.fit(X_train, y_train)
```

---

## 🧩 **Pertemuan 13 — Studi Kasus ML pada Sistem Informasi**

### Tujuan

Mahasiswa mampu menerapkan ML pada kasus nyata bidang SI.

### Studi Kasus

* Prediksi churn pelanggan
* Analisis sentimen ulasan produk
* Prediksi penjualan

### Praktik

Gunakan dataset publik seperti:

* [Kaggle: Customer Churn Dataset](https://www.kaggle.com/)
* [UCI Machine Learning Repository](https://archive.ics.uci.edu/)

---

## 🧩 **Pertemuan 14 — Presentasi Proyek Akhir**

### Tujuan

Mahasiswa mempresentasikan hasil proyek ML berbasis dataset nyata.

### Kriteria Penilaian

* Pemahaman konsep
* Implementasi algoritma
* Analisis hasil
* Visualisasi dan presentasi

---

## 🧩 **Pertemuan 15 — Ujian Akhir Semester (UAS)**

### Bentuk

* Teori (30%)
* Praktik kode Python (70%)

---

## 🧩 **Pertemuan 16 — Refleksi & Feedback**

### Tujuan

Evaluasi hasil belajar dan diskusi capaian proyek.

### Kegiatan

* Review model terbaik mahasiswa
* Diskusi kesulitan dan solusi
* Evaluasi pembelajaran dan saran perbaikan

---

# 📚 Referensi Utama

1. Aurélien Géron, *Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow*, O'Reilly, 2023.
2. Andreas Müller & Sarah Guido, *Introduction to Machine Learning with Python*, O'Reilly, 2016.
3. Tom M. Mitchell, *Machine Learning*, McGraw-Hill, 1997.
4. Ethem Alpaydin, *Introduction to Machine Learning*, MIT Press, 2020.
5. Dokumentasi resmi: [https://scikit-learn.org/stable/](https://scikit-learn.org/stable/)

---

# 🧩 Tools yang Digunakan

* Python 3.x
* Jupyter Notebook / Google Colab
* Libraries: `numpy`, `pandas`, `matplotlib`, `seaborn`, `scikit-learn`, `tensorflow`, `pytorch`

---

