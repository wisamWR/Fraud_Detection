# 🕵️‍♂️ Fraud Detection Prediction App

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=Streamlit&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)

Aplikasi berbasis web untuk mendeteksi potensi **transaksi penipuan keuangan (Fraud)** secara real-time menggunakan Machine Learning. Proyek ini dibangun dengan **Streamlit** sebagai antarmuka pengguna dan menggunakan model **Logistic Regression** yang telah dioptimasi untuk data yang tidak seimbang.

## 📋 Daftar Isi
- [Tentang Proyek](#-tentang-proyek)
- [Fitur Utama](#-fitur-utama)
- [Teknologi](#%EF%B8%8F-teknologi)
- [Struktur File](#-struktur-file)
- [Instalasi dan Penggunaan](#-instalasi-dan-penggunaan)
- [Performa Model](#-performa-model)
- [Disclaimer](#%EF%B8%8F-disclaimer)

---

## 📖 Tentang Proyek

Penipuan transaksi digital adalah masalah kritis. Aplikasi ini bertujuan membantu mengidentifikasi transaksi mencurigakan berdasarkan pola historis. Model dilatih menggunakan dataset transaksi keuangan (misal: `AIML Dataset.csv`) dan mampu memprediksi apakah transaksi baru berpotensi **Fraud** atau **Aman**.

Fokus utama model ini adalah **Recall** yang tinggi untuk kelas Fraud, meminimalkan risiko lolosnya transaksi penipuan.

## 🚀 Fitur Utama

* **Analisis Data Otomatis:** Pipeline preprocessing yang menangani *scaling* data numerik dan *encoding* data kategorikal (One-Hot Encoding).
* **Penanganan Imbalance Data:** Menggunakan parameter `class_weight='balanced'` untuk menangani ketimpangan jumlah data antara transaksi normal dan fraud.
* **Antarmuka Web Interaktif:** Pengguna dapat memasukkan detail transaksi (Tipe, Jumlah, Saldo) dan mendapatkan hasil prediksi instan melalui Streamlit.
* **Serialisasi Model:** Model disimpan dalam format `.pkl` menggunakan Joblib untuk efisiensi deployment.

## 🛠️ Teknologi

| Kategori | Tools / Library |
| :--- | :--- |
| **Bahasa** | Python |
| **Data Processing** | Pandas, NumPy |
| **Visualisasi** | Matplotlib, Seaborn |
| **Machine Learning** | Scikit-Learn (LogisticRegression, Pipeline, ColumnTransformer) |
| **Deployment UI** | Streamlit |
| **Model Saving** | Joblib |

## 📂 Struktur File

```text
├── AIML Dataset.csv              # Dataset sumber (Wajib ada untuk training)
├── analysis_model.ipynb          # Notebook untuk EDA, Preprocessing, & Training Model
├── app.py                        # Kode utama aplikasi Streamlit
├── fraud_detection_pipeline.pkl  # File model yang sudah dilatih (Output dari notebook)
├── requirements.txt              # Daftar library yang dibutuhkan
└── README.md                     # Dokumentasi proyek

```
---

## ⚙️ Instalasi dan Penggunaan
Ikuti langkah berikut untuk menjalankan aplikasi di komputer lokal Anda:

1. Clone Repository & Siapkan Environment
Bash

# Clone repository
git clone [https://github.com/username-anda/fraud-detection-app.git](https://github.com/username-anda/fraud-detection-app.git)
cd fraud-detection-app

# (Opsional) Buat Virtual Environment
python -m venv venv
# Windows:
venv\Scripts\activate
# Mac/Linux:
source venv/bin/activate
2. Install Dependencies
Buat file requirements.txt dengan isi di bawah ini, atau install manual:

Plaintext

streamlit
pandas
numpy
scikit-learn
matplotlib
seaborn
joblib
Jalankan perintah install:

Bash

pip install -r requirements.txt
3. Latih Model (Jika file .pkl belum ada)
Jalankan Jupyter Notebook analysis_model.ipynb untuk memproses data, melatih model, dan menghasilkan file fraud_detection_pipeline.pkl. Pastikan file AIML Dataset.csv berada di folder yang sama.

4. Jalankan Aplikasi
Gunakan perintah berikut di terminal:

Bash

streamlit run app.py
Aplikasi akan terbuka otomatis di browser pada alamat http://localhost:8501.
