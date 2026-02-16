# Data Preparation

Data Preparation adalah tahap mempersiapkan data agar siap digunakan untuk pemodelan. Tahap ini seringkali memakan waktu paling lama dalam proyek data mining (60-80% dari total waktu proyek).

## 3.1 Pembersihan Data

Handling missing values: Menghapus record yang memiliki missing values Mengisi dengan nilai mean/median/mode Imputasi menggunakan algoritma machine learning Outlier detection dan treatment: Mengidentifikasi nilai ekstrem Menggunakan metode IQR (Interquartile Range) atau Z-score Keputusan: menghapus atau mengganti dengan nilai yang lebih wajar.

## 3.2 Transformasi Data

Normalisasi: Mengubah skala data ke range tertentu (misalnya 0-1) Standarisasi: Mengubah distribusi data menjadi normal Encoding variabel kategorikal: One-hot encoding Label encoding Feature scaling: Memastikan semua variabel memiliki skala yang sebanding.

## 3.3 Feature Engineering

Membuat variabel baru dari variabel yang sudah ada: Contoh: dari tanggal transaksi, dibuat variabel hari dalam minggu, bulan, atau apakah hari libur Agregasi data: Menggabungkan data dari berbagai tabel atau sumber Seleksi fitur: Memilih variabel yang paling relevan untuk pemodelan Menghapus variabel yang redundan atau tidak informatif.

## 3.4 Pembagian Dataset

Train-test split: Membagi data menjadi data latih (70-80%) dan data uji (20-30%) Stratified sampling: Memastikan distribusi kelas tetap proporsional Cross-validation: Membagi data menjadi beberapa fold untuk validasi yang lebih robust.
