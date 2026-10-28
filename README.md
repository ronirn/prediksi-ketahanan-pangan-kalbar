
<div align="center">

# Prediksi Indeks Ketahanan Pangan
### Kabupaten/Kota di Provinsi Kalimantan Barat

**Implementasi Multilayer Perceptron Berbasis Data BAPANAS dan BPS**

Aplikasi web berbasis machine learning untuk estimasi, eksplorasi,
dan visualisasi Indeks Ketahanan Pangan (IKP).

**Python · Flask · Scikit-learn · Tailwind CSS · Chart.js · Leaflet**

</div>

---

## Overview

Ketahanan pangan merupakan salah satu aspek penting dalam
pembangunan daerah dan kesejahteraan masyarakat. Pemantauan
Indeks Ketahanan Pangan (IKP) dapat memberikan gambaran
mengenai kondisi ketahanan pangan pada tingkat kabupaten/kota.

Proyek ini mengimplementasikan algoritma **Multilayer Perceptron
(MLP)** untuk mengestimasi nilai IKP menggunakan enam indikator
sosial ekonomi dan pangan.

Aplikasi dikembangkan menggunakan **Flask** dengan antarmuka
responsif, visualisasi interaktif, dan integrasi model machine
learning untuk mendukung eksplorasi hasil penelitian.

### Research Information

| Informasi | Keterangan |
|---|---|
| Bidang | Machine Learning / Food Security |
| Wilayah Penelitian | Provinsi Kalimantan Barat |
| Unit Analisis | 14 Kabupaten/Kota |
| Periode Data | 2021–2025 |
| Jumlah Observasi | 70 |
| Variabel Masukan | 6 Indikator |
| Variabel Target | Indeks Ketahanan Pangan (IKP) |
| Algoritma Utama | Multilayer Perceptron |
| Model Terpilih | MLP Ensemble Log |
| Sumber Data | BPS dan BAPANAS |

---

## Application Features

Aplikasi menyediakan lima halaman utama yang saling terintegrasi.

| Halaman | Fungsionalitas |
|---|---|
| **Dashboard** | Ringkasan statistik IKP, tren tahunan, dan peta persebaran geografis. |
| **Dataset** | Eksplorasi data historis, pencarian, filter, pengurutan, serta ekspor data. |
| **Prediksi IKP** | Estimasi nilai IKP berdasarkan enam indikator menggunakan model MLP. |
| **Visualisasi** | Grafik perkembangan IKP, perbandingan wilayah, komposisi skor, dan peta interaktif. |
| **Evaluasi Model** | Perbandingan kinerja MLP, Naïve, dan Linear Regression menggunakan MAE, RMSE, dan R². |

---

## Application Preview

Dokumentasi berikut menampilkan antarmuka aplikasi yang
telah dikembangkan.

### 01. Dashboard

Halaman utama menyediakan ringkasan statistik ketahanan pangan,
grafik perkembangan IKP, dan peta interaktif wilayah
Kalimantan Barat.

<p align="center">
  <img
    src="Dokumentasi/dashboard.png"
    alt="Dashboard Indeks Ketahanan Pangan"
    width="850"
  >
</p>

---

### 02. Dataset

Halaman Dataset menampilkan data historis indikator sosial
ekonomi dan pangan pada 14 kabupaten/kota selama
periode 2021–2025.

Tersedia fasilitas pencarian, filter, pengurutan,
pagination, dan pengunduhan data.

<p align="center">
  <img
    src="Dokumentasi/dataset.png"
    alt="Halaman Dataset Ketahanan Pangan"
    width="850"
  >
</p>

---

### 03. Prediksi IKP

Halaman Prediksi digunakan untuk mengestimasi nilai IKP
berdasarkan enam indikator menggunakan model
**MLP Ensemble Log**.

Sistem menyediakan validasi input, hasil estimasi,
interpretasi indikatif, dan riwayat prediksi sementara.

<p align="center">
  <img
    src="Dokumentasi/prediksi.png"
    alt="Halaman Prediksi IKP"
    width="850"
  >
</p>

---

### 04. Visualisasi

Halaman Visualisasi menyediakan eksplorasi data menggunakan
grafik interaktif dan peta geografis.

Visualisasi mencakup perkembangan IKP per tahun,
perbandingan antarwilayah, distribusi kelompok skor,
serta persebaran IKP kabupaten/kota.

<p align="center">
  <img
    src="Dokumentasi/visual.png"
    alt="Visualisasi Indeks Ketahanan Pangan"
    width="850"
  >
</p>

---

### 05. Evaluasi Model

Halaman Evaluasi menampilkan hasil pengukuran kinerja
model menggunakan MAE, RMSE, dan R².

Pengguna dapat membandingkan hasil model MLP,
Naïve, dan Linear Regression pada periode
validasi historis 2022–2023.

<p align="center">
  <img
    src="Dokumentasi/evaluasi.png"
    alt="Evaluasi Kinerja Model"
    width="850"
  >
</p>

---

## Research Methodology

Tahapan penelitian meliputi:

1. Pengumpulan dan integrasi data BPS serta BAPANAS.
2. Pemeriksaan kualitas dan prapemrosesan dataset.
3. Pembagian data berdasarkan urutan waktu.
4. Pengembangan beberapa konfigurasi Multilayer Perceptron.
5. Penerapan Naïve dan Linear Regression sebagai pembanding.
6. Evaluasi menggunakan MAE, RMSE, dan R².
7. Implementasi model dan hasil penelitian pada aplikasi Flask.

Model utama menggunakan pendekatan **ensemble** yang
menggabungkan lima jaringan MLP. Transformasi logaritmik
diterapkan pada sejumlah fitur untuk menangani perbedaan
skala dan distribusi data.

---

## Model Evaluation

Evaluasi dilakukan menggunakan pendekatan
**rolling-origin validation** pada periode historis
2022–2023.

| Model | MAE ↓ | RMSE ↓ | R² ↑ |
|---|---:|---:|---:|
| MLP Ensemble Log | 3.229 | 3.714 | 0.609 |
| Naïve | **2.101** | **2.866** | **0.755** |
| Linear Regression (6 Features) | 4.648 | 5.579 | 0.123 |

**MLP Ensemble Log** memperoleh kinerja terbaik
di antara konfigurasi MLP yang diuji.

Sementara itu, metode Naïve menghasilkan kesalahan
lebih rendah pada validasi historis, tetapi menggunakan
informasi masukan yang berbeda dari MLP.

### Research Limitations

Data IKP periode 2021–2023 menggunakan seri historis,
sedangkan tahun 2024–2025 menggunakan metodologi
penghitungan 12 indikator.

Perbedaan metodologi tersebut menjadi keterbatasan
dalam menilai kemampuan generalisasi model pada
periode berikutnya.

Hasil prediksi aplikasi merupakan estimasi penelitian,
bukan nilai IKP resmi yang diterbitkan BAPANAS.

---

## Technology Stack

| Komponen | Teknologi |
|---|---|
| Backend | Python, Flask |
| Machine Learning | Scikit-learn, Multilayer Perceptron |
| Data Processing | Pandas, NumPy |
| Frontend | HTML, Tailwind CSS, JavaScript |
| Data Visualization | Chart.js |
| Geographic Visualization | Leaflet, GeoJSON |
| Model Serialization | Joblib |

---

## Source Code Availability

This repository is intended for **public documentation
and academic project presentation**.

The Flask application source code, trained machine
learning models, and research datasets are not included
in this public repository.

The repository contains application screenshots,
research information, and a summary of model evaluation.

---

## Author

**Roni, S.Kom.**

Machine Learning and Web Application Development

West Kalimantan, Indonesia

---

<div align="center">

**Prediksi Indeks Ketahanan Pangan Kalimantan Barat**

Academic Research Project · 2026

</div>
