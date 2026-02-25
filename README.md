# 📊 Analisis Website Instansi Pemerintah Kota Banjarbaru

Dokumen ini merupakan **manual book akademik** dari proyek *Analisis Website Instansi Pemerintah Kota Banjarbaru*. Proyek ini dikembangkan menggunakan **bahasa pemrograman Python** dan dijalankan pada platform **Google Colaboratory**.  

Sistem ini digunakan untuk melakukan pengolahan dan analisis data laporan website instansi pemerintah Kota Banjarbaru berdasarkan periode bulanan (Januari dan Februari), dengan fokus pada **aktivitas pembaruan (update/berita)** serta **ketersediaan informasi penting** sebagai bagian dari evaluasi layanan informasi publik.


---

## 1. Tujuan Penelitian / Proyek

Tujuan dari pengembangan sistem ini adalah sebagai berikut:

1. Menganalisis tingkat keaktifan website instansi pemerintah melalui jumlah update atau berita.
2. Mengevaluasi kelengkapan informasi penting yang tersedia pada website instansi pemerintah.
3. Menggabungkan dan membandingkan data laporan website antar periode.
4. Menyajikan hasil analisis dalam bentuk tabel terstruktur yang mudah dipahami.

---

## 2. Ruang Lingkup Sistem

Ruang lingkup sistem analisis ini meliputi:
- Data website instansi pemerintah Kota Banjarbaru
- Analisis laporan website periode Bulan
- Evaluasi informasi website berupa:
  - Update Berita
  - Visi dan Misi
  - Struktur Organisasi
  - Alamat Kantor
  - Email Resmi
  - Nomor Telepon
- Penyajian hasil analisis secara deskriptif dalam bentuk tabel

---

## 3. Teknologi dan Perangkat Lunak
Sistem ini dibangun menggunakan teknologi berikut:
### 3.1 Perangkat Lunak
- **Google Colaboratory** sebagai lingkungan eksekusi program
- **Python 3** sebagai bahasa pemrograman utama

### 3.2 Library Python
- `pandas`  
  Digunakan untuk membaca, mengolah, dan menganalisis data berbentuk tabel.
- `numpy`  
  Digunakan untuk mendukung operasi numerik.
- `google.colab.files`  
  Digunakan untuk mengunggah file data ke lingkungan Google Colab.

Seluruh library tersebut telah tersedia secara default pada Google Colaboratory.

---
## 5. Diagram Alur Sistem

Diagram alur berikut menjelaskan tahapan kerja sistem analisis website secara keseluruhan, mulai dari input data hingga output hasil analisis.

![alt text](https://github.com/AripppMuhammad/Magang/blob/main/Flowchart.jpeg?raw=true)

---

## 6. Data Input

Sistem menggunakan dua buah dataset dalam format **CSV**, yaitu:

1. `laporan_januari.csv`
2. `laporan_februari.csv`

### 6.1 Struktur Kolom Dataset

Dataset yang digunakan harus memiliki kolom sebagai berikut:

| Nama Kolom | Deskripsi |
|----------|----------|
| Nama SKPD | Nama instansi pemerintah |
| Alamat Website | URL website instansi |
| Update/Berita | Jumlah update atau berita |
| Visi/Misi | Ketersediaan visi dan misi |
| Struktur Organisasi | Ketersediaan struktur organisasi |
| Alamat Kantor | Ketersediaan alamat kantor |
| Email | Ketersediaan email resmi |
| Telepon | Ketersediaan nomor telepon |
| Bulan | Periode data  |

---

## 7. Langkah-Langkah Penggunaan Sistem

### 7.1 Membuka Notebook
1. Akses https://colab.research.google.com
2. Unggah atau buka file `Analisis_Web_Neww.ipynb`

### 7.2 Mengunggah Dataset
Jalankan kode berikut untuk mengunggah dataset:

python
from google.colab import files
files.upload()

7.3 Membaca Data

Dataset dibaca menggunakan library pandas:
import pandas as pd

df_januari = pd.read_csv("laporan_januari.csv")
df_februari = pd.read_csv("laporan_februari.csv")

7.4 Validasi Data
Pada tahap ini sistem menampilkan:
- Beberapa baris awal data
- Nama kolom
- Jumlah data
Tahap ini bertujuan untuk memastikan kesesuaian struktur data.

7.5 Penggabungan Data
Data dari dua periode digabungkan menggunakan:
df_all = pd.concat([df_januari, df_februari], ignore_index=True)
8. Proses Analisis Data
    8.1 Analisis Update/Berita
Sistem menghitung total update atau berita per bulan untuk mengukur tingkat keaktifan website.
df_all.groupby("Bulan")["Update/Berita"].sum()

8.2 Analisis Ketersediaan Informasi
Evaluasi dilakukan terhadap ketersediaan:
- Berita
- Visi dan Misi
- Struktur Organisasi
- Alamat Kantor
- Email
- Telepon

8.3 Ringkasan Hasil
Hasil analisis dirangkum untuk menggambarkan kondisi umum website instansi pemerintah.

8.4 Pemisahan Data Periode
Data dipisahkan kembali per bulan untuk analisis komparatif antar periode.

9. Output Sistem
Output yang dihasilkan oleh sistem meliputi:
    1. Tabel gabungan data website
    2. Ringkasan jumlah update/berita per bulan
    3. Ringkasan ketersediaan informasi website
    4. Tabel data per periode
    5. Daftar URL website instansi pemerintah
Seluruh output ditampilkan dalam bentuk tabel (DataFrame) pada notebook Google Colab.
