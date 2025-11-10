## 🚀 Modul Sains Data

**Program Studi Sistem Informasi - Semester 7**

**Dosen:** Erfian Junianto, S.T., M.Kom., CDMP

**Institusi:** Universitas ARS

-----

## 1️⃣ Pertemuan 1 - Pengantar Sains Data

### Tujuan Pembelajaran

  * Memahami **pengertian dan ruang lingkup Sains Data**.
  * Menjelaskan tahapan **Data Science Lifecycle (CRISP-DM/KDD)**.
  * Mengetahui **peran data scientist** dalam organisasi dan industri.

### Konsep Dasar

Sains Data adalah disiplin yang menggabungkan **Statistik, Ilmu Komputer, dan Pengetahuan Domain/Bisnis**.

### Contoh Kasus (Python)

```python
import pandas as pd
# Membaca dataset Iris
data = pd.read_csv("https://raw.githubusercontent.com/mwaskom/seaborn-data/master/iris.csv")
print(data.head()) 
```

### Tugas

Cari contoh penerapan sains data di industri (Netflix, Tokopedia, BPJS) dan identifikasi **masalah bisnis** yang diselesaikan.

-----

## 2️⃣ Pertemuan 2 - Jenis dan Sumber Data

### Tujuan Pembelajaran

  * Mengenali **tipe data** (kategorikal, numerik) dan **sumbernya**.
  * Memahami **struktur data** (terstruktur, semi-terstruktur, tidak terstruktur).

### Jenis Data

  * **Terstruktur:** Tabel, SQL.
  * **Semi-Terstruktur:** JSON, XML.
  * **Tidak Terstruktur:** Teks, Gambar, Video.

### Tugas

Buat daftar **5 sumber data terbuka** yang kredibel untuk analisis.

-----

## 3️⃣ Pertemuan 3 - Data Cleaning dan Preprocessing

### Tujuan Pembelajaran

  * Mampu melakukan **pembersihan data** (menangani *missing values*, *outliers*) dengan Pandas.
  * Memahami teknik **penanganan data duplikat** dan validasi format.

### Contoh Data Cleaning (Python)

```python
import pandas as pd

data = pd.read_csv("data.csv")
data = data.dropna()          # Mengatasi Missing Values
data = data.drop_duplicates() # Menghapus Data Duplikat
print(data.info())            
```

-----

## 4️⃣ Pertemuan 4 - Exploratory Data Analysis (EDA)

### Tujuan Pembelajaran

  * Memahami konsep **EDA** dan pentingnya di awal proyek.
  * Dapat menggali **statistik deskriptif** dan **korelasi antar variabel**.

### Contoh EDA (Python)

```python
import pandas as pd

data = pd.read_csv("iris.csv")
print(data.describe())              # Ringkasan Statistik
print(data.groupby('species').mean()) # Analisis per kelompok
```

### Tugas

Tulis minimal **3 *insight* kunci** (temuan penting) dari hasil eksplorasi data.

-----

## 5️⃣ Pertemuan 5 - Visualisasi Data

### Tujuan Pembelajaran

  * Mampu membuat visualisasi statis menggunakan **Matplotlib & Seaborn**.
  * Memahami **pemilihan jenis grafik** berdasarkan tujuan analisis.

### Contoh Visualisasi (Python)

```python
import seaborn as sns
import matplotlib.pyplot as plt
data = sns.load_dataset("iris")

sns.scatterplot(x="sepal_length", y="petal_length", hue="species", data=data)
plt.title("Hubungan Panjang Sepal vs. Panjang Petal")
plt.show()
```

-----

## 6️⃣ Pertemuan 6 - Statistik Dasar untuk Sains Data

### Tujuan Pembelajaran

  * Memahami konsep **Statistik Deskriptif** (mean, median, mode, standar deviasi).
  * Mengenal konsep dasar **Statistik Inferensial**.

### Contoh Statistik Sederhana (Python)

```python
import numpy as np
from scipy import stats

data = [10, 15, 20, 25, 30, 30]
print(f"Rata-rata: {np.mean(data)}")
print(f"Median: {np.median(data)}")
```

-----

## 7️⃣ Pertemuan 7 - Konsep Machine Learning

### Tujuan Pembelajaran

  * Mengenal **konsep dasar Machine Learning** (ML).
  * Mengetahui perbedaan **Supervised** (Klasifikasi, Regresi) dan **Unsupervised Learning** (Clustering).

### Jenis Machine Learning

  * **Supervised Learning:** Prediksi harga, Klasifikasi.
  * **Unsupervised Learning:** Clustering pelanggan.

-----

## 8️⃣ Pertemuan 8 - Ujian Tengah Semester (UTS)

### Ujian Tengah Semester

Evaluasi komprehensif teori dan praktik analisis data (meliputi Pertemuan 1–7).

-----

## 9️⃣ Pertemuan 9 - Regresi Linear

### Tujuan Pembelajaran

  * Memahami **konsep dan asumsi** regresi linear sederhana.
  * Menggunakan **Scikit-Learn** untuk membangun model regresi.

### Contoh Regresi Linear (Python)

```python
from sklearn.linear_model import LinearRegression
import numpy as np

x = np.array([[1], [2], [3], [4], [5]])
y = np.array([2, 4, 5, 4, 5])

model = LinearRegression().fit(x, y)
print(f"Prediksi untuk 6 jam belajar: {model.predict([[6]])[0]:.2f}")
```

-----

## 🔟 Pertemuan 10 - K-Means Clustering

### Tujuan Pembelajaran

  * Mengetahui **prinsip kerja K-Means**.
  * Mengelompokkan data ke dalam *cluster* menggunakan Scikit-Learn.

### Contoh Clustering (Python)

```python
from sklearn.cluster import KMeans
import numpy as np

data = np.array([[1,2],[2,3],[6,7],[7,8]])
kmeans = KMeans(n_clusters=2, random_state=0, n_init='auto') 
kmeans.fit(data)
print(f"Label Cluster: {kmeans.labels_}") 
```

-----

## 1️⃣1️⃣ Pertemuan 11 - Feature Engineering (Pengembangan Fitur)

### Tujuan Pembelajaran

  * Mengetahui teknik **penyiapan fitur** untuk meningkatkan performa model.
  * Melakukan **One-Hot Encoding** dan **Feature Scaling** (Normalisasi/Standardisasi).

-----

## 1️⃣2️⃣ Pertemuan 12 - Evaluasi Model dan Validasi

### Tujuan Pembelajaran

  * Mampu mengevaluasi performa model menggunakan **metrik yang tepat** (Akurasi, MSE, R2).
  * Memahami teknik **Validasi Silang (Cross-Validation)** untuk mengurangi *overfitting*.

-----

## 1️⃣3️⃣ Pertemuan 13 - Dasar Big Data dan Lingkungan Komputasi

### Tujuan Pembelajaran

  * Mengenal konsep **Big Data** (Volume, Velocity, Variety).
  * Memahami perbedaan komputasi lokal dan **komputasi awan (Cloud)**.

-----

## 1️⃣4️⃣ Pertemuan 14 - Dashboard, Visualisasi Interaktif, dan Storytelling

### Tujuan Pembelajaran

  * Membuat **visualisasi interaktif** menggunakan Plotly/Dash/Power BI.
  * Mengembangkan kemampuan **Data Storytelling**: menyajikan hasil analisis menjadi narasi bisnis yang mudah dipahami.

-----

## 1️⃣5️⃣ Pertemuan 15 - Etika, Privasi Data, dan *Deployment*

### Tujuan Pembelajaran

  * Memahami pentingnya **Etika** dan kepatuhan **Privasi Data**.
  * Mengenal tahapan **Model Deployment**: mengubah model ML menjadi aplikasi yang bisa digunakan.

-----

## 1️⃣6️⃣ Pertemuan 16 - Presentasi Proyek Akhir

### Ujian Akhir Semester

Evaluasi komprehensif teori dan praktik seluruh materi silabus.

-----
