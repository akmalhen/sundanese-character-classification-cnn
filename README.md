# Aksara Sunda Classification (CNN)

Repositori ini berisi implementasi Deep Learning menggunakan **Convolutional Neural Network (CNN)** untuk mengklasifikasikan aksara Sunda. Model ini dibangun menggunakan TensorFlow/Keras dan dilatih menggunakan dataset gambar karakter Aksara Sunda.

## 🚀 Teknologi yang Digunakan
- **Bahasa Pemrograman:** Python (versi 3.x)
- **Machine Learning Framework:** TensorFlow / Keras
- **Computer Vision & Manipulasi Gambar:** OpenCV (`cv2`)
- **Data preprocessing & Metrik evaluasi:** Scikit-Learn
- **Visualisasi & Analitik Data:** Matplotlib, Seaborn, Numpy

## 📊 Dataset
Dataset yang digunakan berasal dari Kaggle: [Abdi Dwi Ramdani - Aksara Sunda](https://www.kaggle.com/datasets/abdidwiramdani/aksara-sunda).
- **Jumlah Gambar:** 1800 gambar
- **Dimensi Gambar (Input Shape):** 64x64 pixel dengan 3 channel (RGB)
- Data telah dinormalisasi dengan membagi nilai piksel dengan `255.0` agar nilainya berada di antara 0 dan 1.

## 📁 Struktur Notebook (`cnn-aksara-sunda.ipynb`)
Notebook ini berisikan tahap-tahap end-to-end pembuatan model:
1. **Import Library:** Menginisialisasi semua library yang diperlukan.
2. **Load Dataset:** Membaca dataset dari penyimpanan, me-resize gambar menjadi 64x64, dan menetapkan label untuk tiap karakter.
3. **Visualisasi Data:** Menampilkan cuplikan gambar dari masing-masing kelas aksara Sunda untuk memastikan data terbaca dengan baik.
4. **Data Preprocessing & Splitting:** Label Encoding dan membagi dataset menjadi data latih (*training*) dan data uji (*testing*).
5. **Konstruksi Arsitektur CNN:** Membangun lapisan konvolusi, *pooling*, dan *dense layer* menggunakan Keras `Sequential`.
6. **Training Model:** Proses pelatihan (*fit*) model beserta penggunaan *callbacks* (seperti `EarlyStopping` atau `ReduceLROnPlateau`).
7. **Evaluasi & Prediksi:** Menampilkan kurva akurasi/loss, *Confusion Matrix*, dan *Classification Report*.

## ⚙️ Cara Menjalankan (How to Run)
Jika Anda ingin menjalankan atau memodifikasi kode:
1. Pastikan Anda sudah menginstall library pendukung. Jika menggunakan komputer lokal/virtual environment:
   ```bash
   pip install numpy matplotlib opencv-python seaborn tensorflow scikit-learn
   ```
2. Sesuaikan *path* dataset pada cell notebook (`data_dir`) ke tempat di mana Anda mengesktrak dataset aksara Sunda.
3. Jalankan notebook dari atas ke bawah.

## 🤖 Pengembangan Lebih Lanjut (Rencana Integrasi Web)
Model prediksi yang nanti telah dilatih dapat disave (contohnya menjadi format `.h5` atau format `TensorFlow.js`) dan diletakkan pada repositori Web secara terpisah untuk dibangun menjadi sistem *Handwriting Recognition* interaktif pada *canvas*.
