# 🧠 Mata Kuliah: Deep Learning  
### Program Studi: Sistem Informasi  
### Semester: 7  
### SKS: 3  
### Dosen Pengampu: Erfian Junianto, S.T., M.Kom., CDMP  

---

## 📘 Pertemuan 1 — Pengenalan Deep Learning
### Tujuan Pembelajaran
Mahasiswa memahami konsep dasar Artificial Intelligence (AI), Machine Learning (ML), dan Deep Learning (DL), serta perbedaan dan keterkaitannya.

### Materi
- Definisi AI, ML, dan DL
- Evolusi pembelajaran mesin menuju deep learning
- Peran DL dalam sistem informasi
- Aplikasi dunia nyata: rekomendasi, prediksi penjualan, analisis citra

### Contoh Kasus
Memprediksi kepuasan pelanggan berdasarkan data transaksi menggunakan model sederhana.

### Contoh Kode (Python)
```python
import tensorflow as tf
print("TensorFlow version:", tf.__version__)
````

### Latihan

Cari 3 contoh penerapan deep learning dalam bidang sistem informasi (e-commerce, kesehatan, pendidikan).

---

## 📘 Pertemuan 2 — Konsep Neural Network

### Tujuan

Mahasiswa memahami struktur dasar neural network: neuron, layer, aktivasi, dan proses forward propagation.

### Materi

* Struktur jaringan syaraf tiruan (perceptron)
* Fungsi aktivasi: sigmoid, relu, tanh
* Konsep bobot dan bias
* Arsitektur feed-forward network

### Contoh Kode

```python
import tensorflow as tf
from tensorflow.keras import layers

model = tf.keras.Sequential([
    layers.Dense(8, activation='relu', input_shape=(4,)),
    layers.Dense(1, activation='sigmoid')
])
model.summary()
```

### Studi Kasus

Klasifikasi pelanggan yang berpotensi churn berdasarkan 4 variabel perilaku.

---

## 📘 Pertemuan 3 — Training dan Evaluasi Model Neural Network

### Tujuan

Mahasiswa memahami proses pelatihan model (training), fungsi loss, dan optimasi.

### Materi

* Loss function (MSE, Cross-Entropy)
* Optimizer (SGD, Adam)
* Epoch dan batch
* Overfitting dan underfitting

### Contoh Kode

```python
model.compile(optimizer='adam',
              loss='binary_crossentropy',
              metrics=['accuracy'])

# Dummy training
import numpy as np
x = np.random.rand(100, 4)
y = np.random.randint(2, size=(100, 1))
model.fit(x, y, epochs=10, batch_size=8)
```

---

## 📘 Pertemuan 4 — Regularization dan Dropout

### Tujuan

Mahasiswa mampu mencegah overfitting melalui regularization dan dropout.

### Materi

* Regularization: L1, L2
* Dropout layer
* Data augmentation

### Contoh Kode

```python
from tensorflow.keras import regularizers

model = tf.keras.Sequential([
    layers.Dense(64, activation='relu', kernel_regularizer=regularizers.l2(0.01)),
    layers.Dropout(0.5),
    layers.Dense(1, activation='sigmoid')
])
```

---

## 📘 Pertemuan 5 — Convolutional Neural Network (CNN) Dasar

### Tujuan

Mahasiswa memahami struktur dan cara kerja CNN untuk pengenalan citra.

### Materi

* Konsep convolution dan pooling
* Arsitektur CNN (Conv2D, MaxPooling)
* Dataset citra (MNIST, CIFAR)

### Contoh Kode

```python
from tensorflow.keras.datasets import mnist
(x_train, y_train), (x_test, y_test) = mnist.load_data()
x_train = x_train.reshape(-1, 28, 28, 1) / 255.0

model = tf.keras.Sequential([
    layers.Conv2D(32, (3,3), activation='relu', input_shape=(28,28,1)),
    layers.MaxPooling2D((2,2)),
    layers.Flatten(),
    layers.Dense(10, activation='softmax')
])
model.compile(optimizer='adam', loss='sparse_categorical_crossentropy', metrics=['accuracy'])
model.fit(x_train, y_train, epochs=3)
```

---

## 📘 Pertemuan 6 — Arsitektur CNN Lanjutan

### Tujuan

Mahasiswa memahami konsep CNN modern (VGG, ResNet) dan transfer learning.

### Materi

* Arsitektur populer: VGG16, ResNet50
* Transfer learning
* Fine-tuning model

### Contoh Kode

```python
from tensorflow.keras.applications import VGG16

base_model = VGG16(weights='imagenet', include_top=False, input_shape=(224,224,3))
for layer in base_model.layers:
    layer.trainable = False
```

---

## 📘 Pertemuan 7 — Evaluasi dan Interpretasi Model CNN

### Tujuan

Mahasiswa mampu mengevaluasi performa model CNN.

### Materi

* Confusion matrix
* Precision, recall, f1-score
* Visualisasi hasil prediksi

### Contoh Kode

```python
from sklearn.metrics import classification_report
import numpy as np

y_pred = np.random.randint(10, size=100)
y_true = np.random.randint(10, size=100)
print(classification_report(y_true, y_pred))
```

---

## 📘 Pertemuan 8 — Ujian Tengah Semester (UTS)

**Evaluasi teori dan praktik materi pertemuan 1–7.**

---

## 📘 Pertemuan 9 — Recurrent Neural Network (RNN)

### Tujuan

Mahasiswa memahami prinsip RNN dan aplikasinya pada data berurutan.

### Materi

* Konsep time-series dan sequence
* Arsitektur RNN dan LSTM
* Vanishing gradient problem

### Contoh Kode

```python
model = tf.keras.Sequential([
    layers.SimpleRNN(64, activation='tanh', input_shape=(10, 8)),
    layers.Dense(1)
])
model.summary()
```

---

## 📘 Pertemuan 10 — Long Short-Term Memory (LSTM)

### Tujuan

Mahasiswa mampu mengimplementasikan LSTM untuk prediksi data urutan.

### Contoh Kasus

Prediksi harga saham berdasarkan 10 hari terakhir.

### Contoh Kode

```python
model = tf.keras.Sequential([
    layers.LSTM(64, return_sequences=True, input_shape=(10,1)),
    layers.LSTM(32),
    layers.Dense(1)
])
```

---

## 📘 Pertemuan 11 — Natural Language Processing (NLP)

### Tujuan

Mahasiswa memahami penerapan deep learning untuk teks.

### Materi

* Tokenisasi dan embedding
* Word2Vec, GloVe
* Text classification

### Contoh Kode

```python
from tensorflow.keras.preprocessing.text import Tokenizer
from tensorflow.keras.preprocessing.sequence import pad_sequences

sentences = ["Deep learning is powerful", "Neural networks learn patterns"]
tokenizer = Tokenizer(num_words=100)
tokenizer.fit_on_texts(sentences)
print(tokenizer.word_index)
```

---

## 📘 Pertemuan 12 — Transformer dan Attention Mechanism

### Tujuan

Mahasiswa mengenal konsep attention dan transformer.

### Materi

* Attention mechanism
* Transformer architecture
* Model BERT dan GPT secara konsep

### Contoh Kode

```python
from transformers import pipeline
generator = pipeline("text-generation", model="gpt2")
print(generator("Deep learning is", max_length=20))
```

---

## 📘 Pertemuan 13 — Hyperparameter Tuning dan Model Optimization

### Tujuan

Mahasiswa mampu mengoptimasi performa model.

### Materi

* Grid search dan random search
* Learning rate scheduler
* Early stopping

### Contoh Kode

```python
callback = tf.keras.callbacks.EarlyStopping(monitor='val_loss', patience=3)
model.fit(x_train, y_train, validation_split=0.2, callbacks=[callback])
```

---

## 📘 Pertemuan 14 — Etika dan Dampak Sosial Deep Learning

### Tujuan

Mahasiswa memahami implikasi sosial, etika, dan bias dalam model AI.

### Materi

* Bias data dan diskriminasi algoritmik
* Privasi dan keamanan data
* AI ethics framework

### Aktivitas

Diskusi: “Apakah AI menggantikan manusia dalam pengambilan keputusan?”

---

## 📘 Pertemuan 15 — Proyek Akhir Deep Learning

### Tujuan

Mahasiswa merancang proyek end-to-end deep learning.

### Kegiatan

* Pemilihan dataset (gambar, teks, atau angka)
* Preprocessing data
* Pembangunan dan pelatihan model
* Evaluasi performa

---

## 📘 Pertemuan 16 — Presentasi dan Evaluasi Proyek

### Tujuan

Mahasiswa mempresentasikan hasil proyek dan refleksi pembelajaran.

### Kriteria Penilaian

* Kompleksitas model (30%)
* Akurasi & performa (30%)
* Dokumentasi & presentasi (25%)
* Etika penggunaan data (15%)

---

# 📚 Referensi

1. Ian Goodfellow, Yoshua Bengio, Aaron Courville. *Deep Learning*, MIT Press (2016).
2. François Chollet. *Deep Learning with Python*, Manning (2021).
3. Aurélien Géron. *Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow*, O’Reilly (2022).
4. TensorFlow Official Docs: [https://www.tensorflow.org](https://www.tensorflow.org)
5. PyTorch Docs: [https://pytorch.org/docs/](https://pytorch.org/docs/)

---

