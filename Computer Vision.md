# 📘 Mata Kuliah: Computer Vision

**Program Studi:** Sistem Informasi (S1)
**Bobot:** 3 SKS
**Semester:** 6
**Dosen Pengampu:** Erfian Junianto, S.T., M.Kom., CDMP

---

## 🧩 Pertemuan 1 — Pengantar Computer Vision

### 🎯 Tujuan Pembelajaran

Mahasiswa memahami konsep dasar, sejarah, dan ruang lingkup *Computer Vision* serta penerapannya di dunia nyata.

### 🧠 Materi

* Pengertian *Computer Vision*
  → Ilmu yang mempelajari bagaimana komputer dapat “melihat” dan menafsirkan gambar atau video seperti manusia.
* Hubungan dengan bidang lain:

  * AI (Artificial Intelligence)
  * Image Processing
  * Machine Learning
* Penerapan:

  * Face recognition
  * Object detection
  * Autonomous car
  * Medical image analysis

### 💡 Contoh Implementasi

```python
# Instalasi
# pip install opencv-python

import cv2
print("OpenCV version:", cv2.__version__)
```

### 🧩 Latihan

Cari contoh aplikasi *computer vision* yang digunakan di industri sistem informasi (misalnya retail, e-commerce, atau kesehatan digital).

---

## 🧩 Pertemuan 2 — Representasi dan Dasar Citra Digital

### 🎯 Tujuan

Mahasiswa memahami bagaimana gambar direpresentasikan secara digital (pixel, resolusi, warna).

### 🧠 Materi

* Gambar digital: kumpulan pixel (nilai intensitas cahaya)
* Model warna: Grayscale, RGB, HSV
* Resolusi: ukuran gambar (width × height)
* Format gambar: JPEG, PNG, BMP

### 💡 Contoh Implementasi

```python
import cv2

# Membaca gambar
img = cv2.imread('sample.jpg')

# Menampilkan dimensi gambar
print("Ukuran:", img.shape)

# Menampilkan gambar
cv2.imshow("Gambar Asli", img)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

---

## 🧩 Pertemuan 3 — Teknik Dasar Pengolahan Citra

### 🎯 Tujuan

Mahasiswa mampu menerapkan teknik dasar manipulasi gambar.

### 🧠 Materi

* Operasi dasar: brightness, contrast, blur
* Filter: Gaussian, Median
* Transformasi warna

### 💡 Contoh Implementasi

```python
import cv2

img = cv2.imread('sample.jpg')

# Mengubah brightness dan contrast
bright = cv2.convertScaleAbs(img, alpha=1.2, beta=30)

# Filter Gaussian
blur = cv2.GaussianBlur(img, (5, 5), 0)

cv2.imshow("Asli", img)
cv2.imshow("Brightness", bright)
cv2.imshow("Gaussian Blur", blur)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

---

## 🧩 Pertemuan 4 — Operasi Morfologi

### 🎯 Tujuan

Mahasiswa memahami operasi morfologi untuk pengolahan bentuk.

### 🧠 Materi

* Erosi: menghapus tepi objek
* Dilasi: menambah tepi objek
* Opening & Closing

### 💡 Contoh Implementasi

```python
import cv2
import numpy as np

img = cv2.imread('shapes.png', 0)
_, mask = cv2.threshold(img, 200, 255, cv2.THRESH_BINARY)

kernel = np.ones((5,5), np.uint8)
dilasi = cv2.dilate(mask, kernel, iterations=1)
erosi = cv2.erode(mask, kernel, iterations=1)

cv2.imshow("Asli", img)
cv2.imshow("Erosi", erosi)
cv2.imshow("Dilasi", dilasi)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

---

## 🧩 Pertemuan 5 — Deteksi Tepi dan Segmentasi

### 🎯 Tujuan

Mahasiswa mampu melakukan deteksi tepi dan segmentasi citra.

### 🧠 Materi

* Edge Detection: Canny, Sobel
* Segmentasi: thresholding, watershed

### 💡 Contoh Implementasi

```python
import cv2

img = cv2.imread('sample.jpg', 0)
edges = cv2.Canny(img, 100, 200)

cv2.imshow("Canny Edge", edges)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

---

## 🧩 Pertemuan 6 — Deteksi Objek Sederhana

### 🎯 Tujuan

Mahasiswa mampu mendeteksi objek sederhana (wajah, bentuk).

### 🧠 Materi

* Haar Cascade Classifier
* Contour detection

### 💡 Contoh Implementasi (Face Detection)

```python
import cv2

face_cascade = cv2.CascadeClassifier(cv2.data.haarcascades + "haarcascade_frontalface_default.xml")
img = cv2.imread('people.jpg')
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

faces = face_cascade.detectMultiScale(gray, 1.1, 4)
for (x, y, w, h) in faces:
    cv2.rectangle(img, (x, y), (x+w, y+h), (255, 0, 0), 2)

cv2.imshow("Face Detection", img)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

---

## 🧩 Pertemuan 7 — Ekstraksi Fitur

### 🎯 Tujuan

Mahasiswa mampu mengekstraksi fitur penting dari citra.

### 🧠 Materi

* SIFT (Scale Invariant Feature Transform)
* ORB (Oriented FAST and Rotated BRIEF)
* Deteksi keypoint

### 💡 Contoh Implementasi

```python
import cv2

img = cv2.imread('building.jpg', 0)
orb = cv2.ORB_create()
keypoints, descriptors = orb.detectAndCompute(img, None)
img_kp = cv2.drawKeypoints(img, keypoints, None, color=(0,255,0))

cv2.imshow("Keypoints", img_kp)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

---

## 🧩 Pertemuan 8 — UTS

Evaluasi teori dan praktik pengolahan citra dasar.

---

## 🧩 Pertemuan 9 — Machine Learning untuk Computer Vision

### 🎯 Tujuan

Mahasiswa memahami konsep supervised learning untuk visi komputer.

### 🧠 Materi

* Klasifikasi gambar dengan KNN dan SVM
* Dataset & feature extraction
* Pipeline ML sederhana

### 💡 Contoh Implementasi

```python
from sklearn import datasets, svm, metrics
from sklearn.model_selection import train_test_split

digits = datasets.load_digits()
X_train, X_test, y_train, y_test = train_test_split(digits.data, digits.target)

clf = svm.SVC()
clf.fit(X_train, y_train)

predicted = clf.predict(X_test)
print("Akurasi:", metrics.accuracy_score(y_test, predicted))
```

---

## 🧩 Pertemuan 10 — CNN untuk Klasifikasi Gambar

### 🎯 Tujuan

Mahasiswa memahami konsep dasar Convolutional Neural Network (CNN).

### 🧠 Materi

* Layer: Convolution, Pooling, Flatten, Dense
* Dataset: MNIST atau CIFAR-10

### 💡 Contoh Implementasi

```python
import tensorflow as tf
from tensorflow.keras import layers, models

model = models.Sequential([
    layers.Conv2D(32, (3,3), activation='relu', input_shape=(28,28,1)),
    layers.MaxPooling2D((2,2)),
    layers.Flatten(),
    layers.Dense(64, activation='relu'),
    layers.Dense(10, activation='softmax')
])

model.compile(optimizer='adam',
              loss='sparse_categorical_crossentropy',
              metrics=['accuracy'])

# Dataset MNIST
(x_train, y_train), (x_test, y_test) = tf.keras.datasets.mnist.load_data()
x_train = x_train.reshape((-1,28,28,1)) / 255.0
x_test = x_test.reshape((-1,28,28,1)) / 255.0

model.fit(x_train, y_train, epochs=3, validation_data=(x_test, y_test))
```

---

## 🧩 Pertemuan 11 — Evaluasi Model dan Metrik

### 🎯 Tujuan

Mahasiswa memahami cara mengevaluasi performa model visi komputer.

### 🧠 Materi

* Confusion Matrix
* Precision, Recall, F1-score

### 💡 Contoh Implementasi

```python
from sklearn.metrics import confusion_matrix, classification_report

print(confusion_matrix(y_test, predicted))
print(classification_report(y_test, predicted))
```

---

## 🧩 Pertemuan 12 — Deteksi Objek Lanjutan (YOLO, SSD)

### 🎯 Tujuan

Mahasiswa mengenal model deteksi objek modern.

### 🧠 Materi

* YOLO (You Only Look Once)
* SSD (Single Shot Detector)
* Bounding Box

### 💡 Contoh Implementasi (Konsep)

```python
# pip install ultralytics
from ultralytics import YOLO

model = YOLO('yolov8n.pt')
results = model('people.jpg', show=True)
```

---

## 🧩 Pertemuan 13 — Integrasi CV ke Sistem Informasi

### 🎯 Tujuan

Mahasiswa memahami integrasi hasil CV dengan sistem informasi.

### 🧠 Materi

* Integrasi hasil deteksi ke dashboard web
* Mengirim hasil deteksi via API (Flask)

### 💡 Contoh Implementasi

```python
from flask import Flask, jsonify
app = Flask(__name__)

@app.route("/detection")
def detect():
    return jsonify({"object": "person", "confidence": 0.92})

if __name__ == "__main__":
    app.run()
```

---

## 🧩 Pertemuan 14 — Laporan dan Presentasi Proyek

### 🎯 Tujuan

Mahasiswa mampu menyusun laporan proyek dan presentasi hasil aplikasi CV.

### 🧠 Materi

* Struktur laporan proyek
* Teknik presentasi ilmiah
* Pengujian dan dokumentasi hasil

---

## 🧩 Pertemuan 15 — Proyek Akhir (UAS)

### 🎯 Tujuan

Mahasiswa mengembangkan aplikasi visi komputer berbasis kasus nyata.

### 💡 Contoh Tema Proyek

* Deteksi masker wajah
* Penghitung jumlah kendaraan
* Deteksi jenis buah berdasarkan citra

Output:

* Aplikasi Python + OpenCV
* Laporan dan presentasi proyek akhir

---

## 🧩 Pertemuan 16 — Refleksi dan Evaluasi

### 🎯 Tujuan

Mahasiswa melakukan refleksi pembelajaran dan evaluasi capaian.

### 🧠 Materi

* Diskusi hasil proyek
* Evaluasi capaian CPMK
* Feedback dan rekomendasi pengembangan diri
