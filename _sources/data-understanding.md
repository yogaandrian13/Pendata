# Data Understanding

## Ekplorasi data iris

<h2>korelasi antara sepal_width dan sepal_length</h2>
<br>
<img src="_static/gambar1.png"/>
<p>Dari gambar di atas menunjukkan korelasi antara sepal_widh dan sepal_length sangat lemah atau tidak ada korelasi, dikarenakan Titik-titik data tersebar tanpa membentuk pola yang jelas, menunjukkan bahwa tidak ada hubungan yang kuat antara sepal length dan sepal width. artinya Kedua variabel ini dapat dianggap sebagai fitur yang berdiri sendiri dan tidak saling mempengaruhi secara linear.</p>
<br>
<h2>korelasi antara petal_width dan petal_length</h2>
<br>
<img src="_static/gambar2.png"/>
<p>dari gambar di atas menunjukkan korelasi antara petal_width dan petal_length sangat kuat, dikarenakan Titik-titik data membentuk pola yang jelas dari kiri bawah ke kanan atas, menunjukkan bahwa semakin besar nilai petal_length, semakin besar pula nilai petal_width. artinya kedua variabel sangat rapat membentuk pola linear yang jelas. namun terdapat Dua cluster yang terpisah kemungkinan besar merepresentasikan iris yang berbeda, tetapi tidak menyebabkan ambigu.</p>
<br>
<h2>korelasi antara sepal_length dan petal_length</h2>
<br>
<img src="_static/gambar3.png"/>
<p>Dari gambar di atas menunjukkan korelasi antara sepal_length dan petal_length sangat kuat, dikarenakan titik-titik data membentuk pola yang jelas dari kiri bawah ke kanan atas, menunjukkan bahwa semakin besar nilai sepal_length, semakin besar pula nilai petal_length. Artinya kedua variabel sangat rapat membentuk pola linear yang jelas. Namun terdapat dua cluster yang terpisah kemungkinan besar merepresentasikan iris yang berbeda, tetapi tidak menyebabkan ambigu.</p>
<br>
<h2>korelasi antara sepal_length dan petal_width</h2><br>

<img src="_static/gambar4.png"/>
<p>Dari gambar di atas menunjukkan korelasi antara sepal_length dan petal_width sangat kuat, dikarenakan titik-titik data membentuk pola yang jelas dari kiri bawah ke kanan atas, menunjukkan bahwa semakin besar nilai sepal_length, semakin besar pula nilai petal_width. Artinya kedua variabel sangat rapat membentuk pola linear yang jelas. Namun terdapat dua cluster yang terpisah kemungkinan besar merepresentasikan iris yang berbeda, tetapi tidak menyebabkan ambigu.</p>
<br>
<h2>korelasi antara sepal_width dan petal_length</h2><br>

<img src="_static/gambar5.png"/>
<p>Dari gambar di atas menunjukkan korelasi antara sepal_width dan petal_length cenderung lemah, dikarenakan titik-titik data tidak membentuk pola linear yang konsisten dari kiri bawah ke kanan atas. Terlihat adanya dua cluster yang sangat terpisah secara vertikal, di mana cluster bawah memiliki petal_length rendah dan cluster atas memiliki petal_length tinggi, namun dalam masing-masing cluster tidak ada hubungan yang jelas dengan sepal_width. Artinya kedua variabel tidak menunjukkan pola yang rapat dan penyebaran data relatif acak. Dua cluster yang terpisah ini kemungkinan besar merepresentasikan spesies iris yang berbeda dengan karakteristik yang sangat berbeda, dan pemisahan yang sangat jelas ini tidak menyebabkan ambigu.</p>
<br>
<h2>korelasi antara sepal_width dan petal_width</h2><br>

<img src="_static/gambar6.png"/>
<p>Dari gambar di atas menunjukkan korelasi antara sepal_width dan petal_width lemah atau tidak konsisten, dikarenakan titik-titik data tidak membentuk pola linear yang jelas dari kiri bawah ke kanan atas. Terlihat adanya dua cluster yang sangat terpisah secara vertikal, di mana cluster bawah memiliki petal_width sangat rendah dan cluster atas memiliki petal_width lebih tinggi, namun dalam masing-masing cluster penyebaran data relatif acak tanpa menunjukkan hubungan yang kuat dengan sepal_width. Artinya kedua variabel tidak membentuk pola linear yang rapat dan peningkatan sepal_width tidak diikuti oleh peningkatan petal_width secara konsisten. Dua cluster yang terpisah ini kemungkinan besar merepresentasikan spesies iris yang berbeda, dan pemisahan yang sangat jelas ini tidak menyebabkan ambigu.</p>
<br>
<h2>statistik dikriptif</h2><br>

<img src="_static/statistik.jpg"/>
<p>Berdasarkan tabel statistik deskriptif di atas, dataset Iris menunjukkan karakteristik yang menarik untuk setiap variabel pengukuran. Pada sepal_length, nilai rata-rata sebesar 5.84 cm sangat dekat dengan median 5.8 cm, mengindikasikan distribusi data yang relatif simetris dan terkonsentrasi di kisaran 5-6 cm dengan variasi yang kecil. Sementara itu, sepal_width memiliki mean 3.05 cm dengan median dan mode sama-sama bernilai 3 cm, menunjukkan bahwa lebar sepal cenderung homogen antar spesies dengan penyebaran data yang rapat.
Berbeda dengan pengukuran sepal, variabel petal_length dan petal_width menunjukkan pola yang lebih kompleks. Nilai mode pada petal_length (1.5 cm) dan petal_width (0.2 cm) sangat berbeda dengan median masing-masing (4.35 cm dan 1.3 cm), yang mengindikasikan adanya distribusi bimodal atau dua kelompok data yang terpisah jelas. Hal ini diperkuat oleh nilai dispersi yang lebih tinggi pada petal_width (0.63) dibandingkan variabel lainnya, menunjukkan bahwa pengukuran petal memiliki variabilitas yang lebih besar dan lebih efektif untuk membedakan antar spesies.</p>

<h2>python (google colab)</h2><br>
<h2>bukti screenshot</h2><br>

<img src="_static/ch1.png"/>
<br>
<img src="_static/ch2.png"/>

<h2>link program</h2><br>

https://colab.research.google.com/drive/1GSy-86MX61px6TsFmbnX_iAG0U7MrHCT?usp=sharing
<br>
<h2>kode lengkap</h2><br>
<p>

```python
import pandas as pd
from scipy import stats

df = pd.read_csv("IRIS.csv")

print("Daftar Kolom:", df.columns.tolist())
print("-" * 60)

kolom_numerik = ['sepal_length', 'sepal_width', 'petal_length', 'petal_width']

for kolom in kolom_numerik:
    print(f"\n Statistik untuk kolom: {kolom.upper()}")
    print("-" * 40)
    print("Jumlah data     :", df[kolom].count())
    print("Rata-rata       :", "{0:.2f}".format(df[kolom].mean()))
    print("Nilai minimal   :", df[kolom].min())
    print("Q1              :", "{0:.2f}".format(df[kolom].quantile(0.25)))
    print("Q2 (Median)     :", "{0:.2f}".format(df[kolom].quantile(0.5)))
    print("Q3              :", "{0:.2f}".format(df[kolom].quantile(0.75)))
    print("Nilai Max       :", df[kolom].max())
    print("Kemencengan 1   :", "{0:.2f}".format(round(df[kolom].skew(), 2)))
    print("Kemencengan 2   :", "{0:.6f}".format(round(df[kolom].skew(), 6)))
    print("Standar Deviasi :", "{0:.2f}".format(round(df[kolom].std(), 2)))
    print("Variansi        :", "{0:.2f}".format(round(df[kolom].var(), 2)))

    mode_result = stats.mode(df[kolom].dropna(), keepdims=True)
    if len(mode_result.mode) > 0 and not pd.isna(mode_result.mode[0]):
        print("Nilai modus     : {} dengan frekuensi {}".format(
            mode_result.mode[0], mode_result.count[0]))
    else:
        print("Nilai modus     : Tidak ada modus tunggal")

print(f"\n🌸 Statistik untuk kolom: SPECIES")
print("-" * 40)
print("Jumlah data     :", df['species'].count())
print("Jumlah class     :", df['species'].nunique())
print("nama class     :", df['species'].unique().tolist())
print("\nJumlah data per class:")
print(df['species'].value_counts())
print("\nModus (kategori paling sering):", df['species'].mode().values[0])
```
</p>
<br>
<h2>output </h2><br>

<p>

```text
Daftar Kolom: ['sepal_length', 'sepal_width', 'petal_length', 'petal_width', 'species']
------------------------------------------------------------

 Statistik untuk kolom: SEPAL_LENGTH
----------------------------------------
Jumlah data     : 150
Rata-rata       : 5.84
Nilai minimal   : 4.3
Q1              : 5.10
Q2 (Median)     : 5.80
Q3              : 6.40
Nilai Max       : 7.9
Kemencengan 1   : 0.31
Kemencengan 2   : 0.314911
Standar Deviasi : 0.83
Variansi        : 0.69
Nilai modus     : 5.0 dengan frekuensi 10

 Statistik untuk kolom: SEPAL_WIDTH
----------------------------------------
Jumlah data     : 150
Rata-rata       : 3.05
Nilai minimal   : 2.0
Q1              : 2.80
Q2 (Median)     : 3.00
Q3              : 3.30
Nilai Max       : 4.4
Kemencengan 1   : 0.33
Kemencengan 2   : 0.334053
Standar Deviasi : 0.43
Variansi        : 0.19
Nilai modus     : 3.0 dengan frekuensi 26

 Statistik untuk kolom: PETAL_LENGTH
----------------------------------------
Jumlah data     : 150
Rata-rata       : 3.76
Nilai minimal   : 1.0
Q1              : 1.60
Q2 (Median)     : 4.35
Q3              : 5.10
Nilai Max       : 6.9
Kemencengan 1   : -0.27
Kemencengan 2   : -0.274464
Standar Deviasi : 1.76
Variansi        : 3.11
Nilai modus     : 1.5 dengan frekuensi 14

 Statistik untuk kolom: PETAL_WIDTH
----------------------------------------
Jumlah data     : 150
Rata-rata       : 1.20
Nilai minimal   : 0.1
Q1              : 0.30
Q2 (Median)     : 1.30
Q3              : 1.80
Nilai Max       : 2.5
Kemencengan 1   : -0.10
Kemencengan 2   : -0.104997
Standar Deviasi : 0.76
Variansi        : 0.58
Nilai modus     : 0.2 dengan frekuensi 28

🌸 Statistik untuk kolom: SPECIES
----------------------------------------
Jumlah data     : 150
Jumlah class     : 3
nama class     : ['Iris-setosa', 'Iris-versicolor', 'Iris-virginica']

Jumlah data per class:
species
Iris-setosa        50
Iris-versicolor    50
Iris-virginica     50
Name: count, dtype: int64

Modus (kategori paling sering): Iris-setosa
```
</p>

## penjelasan mengukur Jarak dengan tipe data campuran
<h2>Latar Belakang</h2><br>
<p>Dalam praktik nyata, database yang digunakan untuk analisis data sering kali tidak hanya mengandung satu jenis tipe data saja, melainkan berbagai tipe data yang tercampur menjadi satu kesatuan. Sebagai contoh, sebuah dataset dapat memuat atribut nominal seperti warna atau jenis produk, atribut binary simetris seperti jenis kelamin, atribut binary asimetris seperti hasil tes medis yang bernilai Y/N, atribut numerik berupa data interval atau rasio seperti suhu atau pendapatan, serta atribut ordinal yang memiliki tingkatan atau peringkat seperti level kepuasan atau tingkat pendidikan. Karena setiap tipe data tersebut memiliki karakteristik dan cara pengukuran yang berbeda-beda, kita tidak dapat menerapkan satu rumus jarak secara langsung untuk menghitung kemiripan atau perbedaan antar objek. Sebagai solusi, pendekatan yang dapat digunakan adalah metode pembobotan, yaitu dengan menghitung jarak untuk setiap atribut secara terpisah sesuai dengan tipe datanya, kemudian menggabungkan seluruh hasil perhitungan tersebut menggunakan rumus jarak campuran yang memperhitungkan indikator validitas setiap atribut. Dengan pendekatan ini, seluruh jenis atribut dapat berkontribusi secara proporsional dalam perhitungan jarak akhir, sehingga hasil analisis menjadi lebih akurat dan mencerminkan karakteristik data yang sebenarnya.
</p>
<br>
<h2>Rumus mengukur jarak data campuran</h2><br>
<img src="_static/image.png"/>
<p>Keterangan:</p>
<table>
<tr>
<td>simbol</td>
<td>penjelasan</td>
</tr>
<tr>
<td>d(i,j)</td>
<td>Jarak antara objek i dan j</td>
</tr>
<tr>
<td>p</td>
<td>umlah total atribut</td>
</tr>
<tr>
<td>δ 
ij
(f)
​
</td>
<td>Indikator: 1 jika atribut ke-f valid untuk dibandingkan, 0 jika tidak (misal: data missing)</td>
</tr>
<tr>
<td>d 
ij
(f)
​
</td>
<td>	
Jarak untuk atribut ke-f saja</td>
</tr>
</table>

<h2> Cara Menghitung d(f)ij per Tipe Atribut</h2><bf>
<h3>1. Atribut Nominal atau Binary</h3><br>
<p>ij(f) = 0, jika xif = xjf  (nilai sama)</p><br>
<p>dij(f) = 1, jika xif ≠ xjf  (nilai berbeda)</p><br>
<p>cara penghitungannya Menggunakan metode simple matching.</p><br>
<h3>2. Atribut Numerik</h3><br>
<p>Lakukan normalisasi terlebih dahulu agar skala seragam, misalnya dengan:</p><br>
<img src="_static/image-1.png"/>
<p>Mean Absolute Deviation: lebih robust terhadap outlier</p><br>
<p>Setelah dinormalisasi, hitung jarak dengan metode numerik (Euclidean, Manhattan, dll).</p><br>
<h3>Atribut Ordinal</h3><br>
<p>Langkah-langkah:</p><br>
<p>Ganti nilai dengan ranking 
r
i
f
​ (misal: rendah=1, sedang=2, tinggi=3)</p><br>
<img src="_static/image-2.png"/>
<p>Hitung jarak menggunakan metode numerik pada nilai 
z
i
f
​</p><br>

## analisi mengunakan orange data mining untuk data yang campuran
<img src="_static/data.png"/>
<p>contoh data dengan tipe data campuran dimana ada 891 baris dan ada 9 fitur dalam data tersebut</p><br>
<img src="_static/image-10.png"/>
<p>Gambar tersebut adalah proses Preprocessing data pada software Orange Data Mining sebelum menghitung jarak atau melakukan analisis pada dataset Titanic Dataset.
Preprocessing diperlukan karena data Titanic memiliki data campuran (numerik dan kategorikal), sehingga harus diolah terlebih dahulu agar bisa digunakan dalam algoritma data mining.</p><br>
<h3>Continuize Discrete Variables</h3><br>
<p>Pengaturan ini digunakan untuk mengubah data kategorikal menjadi numerik. Pada dataset Titanic terdapat data kategorikal seperti Sex (male / female), Embarked (S, C, Q), Pclass (kelas 1,2,3). Karena algoritma pengukuran jarak hanya bisa menghitung angka, maka data tersebut diubah menjadi numerik</p><br>
<h3>Impute Missing Values</h3><br>
<p>Fitur ini digunakan untuk mengisi data yang kosong (missing value).
Dalam dataset Titanic terdapat data kosong pada age dan cabin</p>

<img src="_static/image-3.png"/>
<p>Widget Distances digunakan untuk menghitung matriks dissimilarity (jarak) antar objek dalam dataset. arameter Compare diset ke Rows yang berarti perhitungan jarak dilakukan antar objek/data point (baris dalam dataset), bukan antar atribut. Hal ini sesuai dengan konsep matriks dissimilarity, dimana matriks segitiga dihasilkan dari perhitungan jarak antar n titik data. Metric jarak yang dipilih adalah Manhattan (normalized) karena data yang saya pakai memiliki data campuran</p>
<img src="_static/image-11.png"/>
<p>gambar di atas merupakan hasil dari pengkuran jarak dari tipe data campuran.</p>
<br>
<img src="_static/image-12.png"/>
<p>Berdasarkan dendrogram, hierarchical 
clustering dilakukan dengan metode linkage Ward dan 
menghasilkan 4 cluster optimal. Pemotongan dendrogram 
dilakukan pada ketinggian tertentu sehingga diperoleh:

Cluster 1: sejumlah X customer,
Cluster 2: sejumlah X customer,
Cluster 3: sejumlah X customer,
Cluster 4: sejumlah X customer,

Metode Ward linkage dipilih karena mampu menghasilkan 
cluster yang lebih kompak dengan meminimalkan varians 
dalam setiap cluster.</p>

## implementasikan data iris untuk mengukur jara di orange
<img src="_static/image-7.png"/>

<p>gambar diatas merupakan sebagian data mentah dari iris untuk diimplementasikan dalam menghitung jarak</p><br>
<img src="_static/image-8.png"/>
<p>gambar di atas merupakan hasil dari menghitung jarak pada data iris dimana prosesnya sama dengan yang tadi </p><br>
<img src="_static/image-9.png"/>
<p>gambar di atas merupakan visualiasi pengukuran jarak pada orange, tetapi sementara saya menggunakan widget csv file impor untuk mengimpor data iris bukan menggunakan sql table karena widget tersebut masih ada erornya atau tidak bisa di pakai dan belum menemukan solusinya</p>

## menyelesaikan Missing values dengan WKNN (manual)  dan code menghitung WKNN
<h3>Tabel Data Asli untuk mencari missing values</h3>

<table border="1" style="border-collapse: collapse; width: 100%; font-family: Arial, sans-serif; font-size: 14px;">
  <thead>
    <tr style="background-color: #2c3e50; color: white;">
      <th style="padding: 10px; border: 1px solid #444;">No</th>
      <th style="padding: 10px; border: 1px solid #444;">Nama</th>
      <th style="padding: 10px; border: 1px solid #444;">IPK</th>
      <th style="padding: 10px; border: 1px solid #444;">Penghasilan_OT</th>
      <th style="padding: 10px; border: 1px solid #444;">Nilai_Tugas</th>
      <th style="width: 20px; background-color: #1e1e1e;"></th>
      <th style="padding: 10px; border: 1px solid #444;">No</th>
      <th style="padding: 10px; border: 1px solid #444;">Nama</th>
      <th style="padding: 10px; border: 1px solid #444;">IPK'</th>
      <th style="padding: 10px; border: 1px solid #444;">Penghasilan'</th>
      <th style="padding: 10px; border: 1px solid #444;">Nilai_Tugas</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">1</td>
      <td style="padding: 8px; border: 1px solid #444;">Andi</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">3.50</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">5000</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">80</td>
      <td style="background-color: #1e1e1e;"></td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">1</td>
      <td style="padding: 8px; border: 1px solid #444;">Andi</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">0.7586</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">0.5385</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">80</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">2</td>
      <td style="padding: 8px; border: 1px solid #444;">Budi</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">2.75</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">2000</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">65</td>
      <td style="background-color: #1e1e1e;"></td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">2</td>
      <td style="padding: 8px; border: 1px solid #444;">Budi</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">0.2414</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">0.0769</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">65</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">3</td>
      <td style="padding: 8px; border: 1px solid #444;"><strong>Citra</strong></td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">3.85</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">8000</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">92</td>
      <td style="background-color: #1e1e1e;"></td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">3</td>
      <td style="padding: 8px; border: 1px solid #444;"><strong>Citra</strong></td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">1.0000</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">1.0000</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">92</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">4</td>
      <td style="padding: 8px; border: 1px solid #444;">Deni</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">2.40</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">1500</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">55</td>
      <td style="background-color: #1e1e1e;"></td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">4</td>
      <td style="padding: 8px; border: 1px solid #444;">Deni</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">0.0000</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">0.0000</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">55</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">5</td>
      <td style="padding: 8px; border: 1px solid #444;">Eva</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">3.10</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">3500</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">75</td>
      <td style="background-color: #1e1e1e;"></td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">5</td>
      <td style="padding: 8px; border: 1px solid #444;">Eva</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">0.4828</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">0.3077</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">75</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">6</td>
      <td style="padding: 8px; border: 1px solid #444;">Fajar</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">3.60</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">6000</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">85</td>
      <td style="background-color: #1e1e1e;"></td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">6</td>
      <td style="padding: 8px; border: 1px solid #444;">Fajar</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">0.8276</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">0.6923</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">85</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">7</td>
      <td style="padding: 8px; border: 1px solid #444;">Gina</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">2.90</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">2500</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">?</td>
      <td style="background-color: #1e1e1e;"></td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">7</td>
      <td style="padding: 8px; border: 1px solid #444;">Gina</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">0.3448</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">0.1538</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">?</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">8</td>
      <td style="padding: 8px; border: 1px solid #444;">Hadi</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">3.20</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">4000</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">78</td>
      <td style="background-color: #1e1e1e;"></td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">8</td>
      <td style="padding: 8px; border: 1px solid #444;">Hadi</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">0.5517</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">0.3846</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">78</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">9</td>
      <td style="padding: 8px; border: 1px solid #444;">Indah</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">3.75</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">7500</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">88</td>
      <td style="background-color: #1e1e1e;"></td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">9</td>
      <td style="padding: 8px; border: 1px solid #444;">Indah</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">0.9310</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">0.9231</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">88</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">10</td>
      <td style="padding: 8px; border: 1px solid #444;">Joko</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">2.55</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">1800</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">60</td>
      <td style="background-color: #1e1e1e;"></td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">10</td>
      <td style="padding: 8px; border: 1px solid #444;">Joko</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">0.1034</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">0.0462</td>
      <td style="padding: 8px; border: 1px solid #444; text-align: center;">60</td>
    </tr>
  </tbody>
</table>

<br>

**Keterangan:**
- **Data Asli (Kiri)**: Data sebelum normalisasi
- **Data Normalisasi (Kanan)**: Data setelah dinormalisasi menggunakan Min-Max Normalization (skala 0-1)

### penyelesaian missing values menggunakan WKNN (manual)
<h3>Langkah 1: Hitung Jarak dan Kemiripan (s<sub>i</sub>)</h3>

<p>Gunakan rumus jarak Euclidean untuk data multi-dimensi:</p>
<p>d² = Σ(x<sub>i</sub> - x<sub>j</sub>)²<br>
s<sub>i</sub> = 1/d²</p>
<h3>Perhitungan Jarak ke Semua Baris:</h3>

<p><strong>1. Ke Andi (0.7586, 0.5385):</strong><br>
d = √(0.3448 - 0.7586)² + (0.1538 - 0.5385)²<br>
d = √(-0.4138)² + (-0.3847)² = √0.1712 + 0.1480<br>
d = √0.3192 ≈ <strong>0.5650</strong><br>
Nilai_Tugas = 80</p>

<p><strong>2. Ke Budi (0.2414, 0.0769):</strong><br>
d = √(0.3448 - 0.2414)² + (0.1538 - 0.0769)²<br>
d = √(0.1034)² + (0.0769)² = √0.0107 + 0.0059<br>
d = √0.0166 ≈ <strong>0.1288</strong><br>
Nilai_Tugas = 65</p>

<p><strong>3. Ke Citra (1.0000, 1.0000):</strong><br>
d = √(0.3448 - 1.0)² + (0.1538 - 1.0)²<br>
d = √(-0.6552)² + (-0.8462)² = √0.4293 + 0.7161<br>
d = √1.1454 ≈ <strong>1.0703</strong><br>
Nilai_Tugas = 92</p>

<p><strong>4. Ke Deni (0.0000, 0.0000):</strong><br>
d = √(0.3448 - 0.0)² + (0.1538 - 0.0)²<br>
d = √(0.3448)² + (0.1538)² = √0.1189 + 0.0237<br>
d = √0.1426 ≈ <strong>0.3777</strong><br>
Nilai_Tugas = 55</p>

<p><strong>5. Ke Eva (0.4828, 0.3077):</strong><br>
d = √(0.3448 - 0.4828)² + (0.1538 - 0.3077)²<br>
d = √(-0.1380)² + (-0.1539)² = √0.0190 + 0.0237<br>
d = √0.0427 ≈ <strong>0.2067</strong><br>
Nilai_Tugas = 75</p>

<p><strong>6. Ke Fajar (0.8276, 0.6923):</strong><br>
d = √(0.3448 - 0.8276)² + (0.1538 - 0.6923)²<br>
d = √(-0.4828)² + (-0.5385)² = √0.2331 + 0.2900<br>
d = √0.5231 ≈ <strong>0.7233</strong><br>
Nilai_Tugas = 85</p>

<p><strong>7. Ke Hadi (0.5517, 0.3846):</strong><br>
d = √(0.3448 - 0.5517)² + (0.1538 - 0.3846)²<br>
d = √(-0.2069)² + (-0.2308)² = √0.0428 + 0.0533<br>
d = √0.0961 ≈ <strong>0.2802</strong><br>
Nilai_Tugas = 78</p>

<p><strong>8. Ke Indah (0.9310, 0.9231):</strong><br>
d = √(0.3448 - 0.9310)² + (0.1538 - 0.9231)²<br>
d = √(-0.5862)² + (-0.7693)² = √0.3436 + 0.5918<br>
d = √0.9354 ≈ <strong>0.9672</strong><br>
Nilai_Tugas = 88</p>

<p><strong>9. Ke Joko (0.1034, 0.0462):</strong><br>
d = √(0.3448 - 0.1034)² + (0.1538 - 0.0462)²<br>
d = √(0.2414)² + (0.1076)² = √0.0583 + 0.0116<br>
d = √0.0699 ≈ <strong>0.2644</strong><br>
Nilai_Tugas = 60</p>

<p>Kita hitung untuk 5 tetangga terdekat Gina:</p>

<table border="1" style="border-collapse: collapse; width: 100%;">
  <thead>
    <tr style="background-color: #2c3e50; color: white;">
      <th style="padding: 10px; border: 1px solid #ddd;">Tetangga</th>
      <th style="padding: 10px; border: 1px solid #ddd;">Selisih IPK (x<sub>i</sub> - x<sub>j</sub>)</th>
      <th style="padding: 10px; border: 1px solid #ddd;">Selisih Penghasilan (x<sub>i</sub> - x<sub>j</sub>)</th>
      <th style="padding: 10px; border: 1px solid #ddd;">Kuadrat (d²)</th>
      <th style="padding: 10px; border: 1px solid #ddd;">Kemiripan (s<sub>i</sub>)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="padding: 8px; border: 1px solid #ddd;"><strong>Budi</strong></td>
      <td style="padding: 8px; border: 1px solid #ddd;">0.3448 - 0.2414 = 0.1034</td>
      <td style="padding: 8px; border: 1px solid #ddd;">0.1538 - 0.0769 = 0.0769</td>
      <td style="padding: 8px; border: 1px solid #ddd;">0.0107 + 0.0059 = <strong>0.0166</strong></td>
      <td style="padding: 8px; border: 1px solid #ddd;"><strong>60.2410</strong></td>
    </tr>
    <tr >
      <td style="padding: 8px; border: 1px solid #ddd;"><strong>Eva</strong></td>
      <td style="padding: 8px; border: 1px solid #ddd;">0.3448 - 0.4828 = -0.1380</td>
      <td style="padding: 8px; border: 1px solid #ddd;">0.1538 - 0.3077 = -0.1539</td>
      <td style="padding: 8px; border: 1px solid #ddd;">0.0190 + 0.0237 = <strong>0.0427</strong></td>
      <td style="padding: 8px; border: 1px solid #ddd;"><strong>23.4192</strong></td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #ddd;"><strong>Joko</strong></td>
      <td style="padding: 8px; border: 1px solid #ddd;">0.3448 - 0.1034 = 0.2414</td>
      <td style="padding: 8px; border: 1px solid #ddd;">0.1538 - 0.0462 = 0.1076</td>
      <td style="padding: 8px; border: 1px solid #ddd;">0.0583 + 0.0116 = <strong>0.0699</strong></td>
      <td style="padding: 8px; border: 1px solid #ddd;"><strong>14.3062</strong></td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #ddd;"><strong>Hadi</strong></td>
      <td style="padding: 8px; border: 1px solid #ddd;">0.3448 - 0.5517 = -0.2069</td>
      <td style="padding: 8px; border: 1px solid #ddd;">0.1538 - 0.3846 = -0.2308</td>
      <td style="padding: 8px; border: 1px solid #ddd;">0.0428 + 0.0533 = <strong>0.0961</strong></td>
      <td style="padding: 8px; border: 1px solid #ddd;"><strong>10.4058</strong></td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #ddd;"><strong>Deni</strong></td>
      <td style="padding: 8px; border: 1px solid #ddd;">0.3448 - 0.0000 = 0.3448</td>
      <td style="padding: 8px; border: 1px solid #ddd;">0.1538 - 0.0000 = 0.1538</td>
      <td style="padding: 8px; border: 1px solid #ddd;">0.1189 + 0.0237 = <strong>0.1426</strong></td>
      <td style="padding: 8px; border: 1px solid #ddd;"><strong>7.0126</strong></td>
    </tr>
  </tbody>
</table>

<h3>Langkah 2: Hitung Estimasi Menggunakan Weighted Average</h3>

<p>Kita gunakan rumus (2): kali setiap <strong>Nilai Tugas (y<sub>j</sub>)</strong> dengan <strong>Kemiripan (s<sub>i</sub>)</strong>, lalu bagi dengan total Kemiripan.</p>

<h4>A. Pembilang (Σ s<sub>i</sub> · y<sub>jh</sub>):</h4>
<ul>
  <li><strong>Budi</strong>: 60.2410 × 65 = 3915.665</li>
  <li><strong>Eva</strong>: 23.4192 × 75 = 1756.440</li>
  <li><strong>Joko</strong>: 14.3062 × 60 = 858.372</li>
  <li><strong>Hadi</strong>: 10.4058 × 78 = 811.652</li>
  <li><strong>Deni</strong>: 7.0126 × 55 = 385.693</li>
</ul>

<p><strong>Total Pembilang:</strong><br>
3915.665 + 1756.440 + 858.372 + 811.652 + 385.693 = <strong>7727.822</strong></p>

<h4>B. Penyebut (Σ s<sub>i</sub>):</h4>
<p>60.2410 + 23.4192 + 14.3062 + 10.4058 + 7.0126 = <strong>115.3848</strong></p>

<h3>Hasil Akhir</h3>

<p>ŷ = 7727.822 / 115.3848 ≈ <strong>66.97</strong></p>

<p><strong>Kesimpulan:</strong> Nilai Tugas Gina yang hilang diisi dengan <strong>66.97</strong> (dibulatkan menjadi <strong>67</strong>).</p>

<p><strong>Logikanya:</strong> Budi yang paling dekat mendapat bobot terbesar (60.24) dan paling mempengaruhi hasil, sedangkan Deni yang paling jauh mendapat bobot terkecil (7.01).</p>

### penyelesaian missing values menggunakan WKNN (code)
```python
import math

# 1. Data latih (ternormalisasi Min-Max) — Baris 1-6 dan 8-10
train_data = [
    {"nama": "Andi",  "ipk": 0.7586, "po": 0.5385, "nilai": 80},
    {"nama": "Budi",  "ipk": 0.2414, "po": 0.0769, "nilai": 65},
    {"nama": "Citra", "ipk": 1.0000, "po": 1.0000, "nilai": 92},
    {"nama": "Deni",  "ipk": 0.0000, "po": 0.0000, "nilai": 55},
    {"nama": "Eva",   "ipk": 0.4828, "po": 0.3077, "nilai": 75},
    {"nama": "Fajar", "ipk": 0.8276, "po": 0.6923, "nilai": 85},
    {"nama": "Hadi",  "ipk": 0.5517, "po": 0.3846, "nilai": 78},
    {"nama": "Indah", "ipk": 0.9310, "po": 0.9231, "nilai": 88},
    {"nama": "Joko",  "ipk": 0.1034, "po": 0.0462, "nilai": 60},
]

# 2. Data target: Gina (yang dicari)
target_ipk = 0.3448
target_po  = 0.1538

print("=== PERHITUNGAN JARAK (EUCLIDEAN DISTANCE) ===")
hasil_jarak = []
for d in train_data:
    jarak = math.sqrt((d["ipk"] - target_ipk)**2 + (d["po"] - target_po)**2)
    hasil_jarak.append({"nama": d["nama"], "jarak": jarak, "nilai": d["nilai"]})

hasil_jarak.sort(key=lambda x: x["jarak"])
for h in hasil_jarak:
    print(f"Ke {h['nama']:6} -> Jarak = {h['jarak']:.4f} | Nilai_Tugas = {h['nilai']}")

print("\n=== PERHITUNGAN BOBOT WKNN (K=5) ===")
K      = 5
top5   = hasil_jarak[:K]
sum_w  = 0.0
sum_wv = 0.0
for t in top5:
    w = 1 / t["jarak"]
    sum_w  += w
    sum_wv += w * t["nilai"]
    print(f"{t['nama']:6} (nilai={t['nilai']}) | d={t['jarak']:.4f} | w={w:.4f} | w×v={w*t['nilai']:.2f}")

print(f"\n=== HASIL AKHIR ===")
print(f"Nilai_Tugas Gina = {sum_wv:.2f} / {sum_w:.4f} = {sum_wv/sum_w:.2f}")
```
```text
=== PERHITUNGAN JARAK (EUCLIDEAN DISTANCE) ===
Ke Budi   -> Jarak = 0.1289 | Nilai_Tugas = 65
Ke Eva    -> Jarak = 0.2067 | Nilai_Tugas = 75
Ke Joko   -> Jarak = 0.2643 | Nilai_Tugas = 60
Ke Hadi   -> Jarak = 0.3100 | Nilai_Tugas = 78
Ke Deni   -> Jarak = 0.3775 | Nilai_Tugas = 55
Ke Andi   -> Jarak = 0.5650 | Nilai_Tugas = 80
Ke Fajar  -> Jarak = 0.7232 | Nilai_Tugas = 85
Ke Indah  -> Jarak = 0.9672 | Nilai_Tugas = 88
Ke Citra  -> Jarak = 1.0702 | Nilai_Tugas = 92

=== PERHITUNGAN BOBOT WKNN (K=5) ===
Budi   (nilai=65) | d=0.1289 | w=7.7603 | w×v=504.42
Eva    (nilai=75) | d=0.2067 | w=4.8377 | w×v=362.83
Joko   (nilai=60) | d=0.2643 | w=3.7837 | w×v=227.02
Hadi   (nilai=78) | d=0.3100 | w=3.2262 | w×v=251.64
Deni   (nilai=55) | d=0.3775 | w=2.6487 | w×v=145.68

=== HASIL AKHIR ===
Nilai_Tugas Gina = 1491.59 / 22.2565 = 67.02
```



## Normalisasi data

<p>Normalisasi data adalah teknik pra-pemrosesan yang sangat penting dalam <em>data mining</em> dan <em>machine learning</em>. Tujuannya adalah menyamakan skala seluruh variabel/fitur agar tidak ada satu atribut pun yang mendominasi atribut lain hanya karena memiliki rentang angka yang lebih besar (misalnya, membandingkan atribut <strong>Penghasilan Orang Tua</strong> dalam ribuan dengan <strong>IPK</strong> dalam satuan kecil 2–4).</p>

<p><strong>Misal kita punya data mahasiswa: X = [IPK, Penghasilan_OT, Nilai_UAS, Jarak_Kampus]</strong></p>
<p>Berikut adalah tiga teknik normalisasi data yang paling sering digunakan:</p>
<h2>Dataset Sebelum Normalisasi</h2>

<table border="1" style="border-collapse: collapse; width: 100%;">
  <thead>
    <tr style="background-color: #2c3e50; color: white;">
      <th style="padding: 10px; border: 1px solid #444;">No</th>
      <th style="padding: 10px; border: 1px solid #444;">Nama</th>
      <th style="padding: 10px; border: 1px solid #444;">IPK</th>
      <th style="padding: 10px; border: 1px solid #444;">Penghasilan_OT (rb)</th>
      <th style="padding: 10px; border: 1px solid #444;">Nilai_UAS</th>
      <th style="padding: 10px; border: 1px solid #444;">Jarak_Kampus (km)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">1</td>
      <td style="padding: 8px; border: 1px solid #444;">Andi</td>
      <td style="padding: 8px; border: 1px solid #444;">3.50</td>
      <td style="padding: 8px; border: 1px solid #444;">5000</td>
      <td style="padding: 8px; border: 1px solid #444;">85</td>
      <td style="padding: 8px; border: 1px solid #444;">10</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">2</td>
      <td style="padding: 8px; border: 1px solid #444;">Budi</td>
      <td style="padding: 8px; border: 1px solid #444;">2.75</td>
      <td style="padding: 8px; border: 1px solid #444;">2000</td>
      <td style="padding: 8px; border: 1px solid #444;">65</td>
      <td style="padding: 8px; border: 1px solid #444;">25</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">3</td>
      <td style="padding: 8px; border: 1px solid #444;">Citra</td>
      <td style="padding: 8px; border: 1px solid #444;">3.85</td>
      <td style="padding: 8px; border: 1px solid #444;">8000</td>
      <td style="padding: 8px; border: 1px solid #444;">92</td>
      <td style="padding: 8px; border: 1px solid #444;">5</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">4</td>
      <td style="padding: 8px; border: 1px solid #444;">Deni</td>
      <td style="padding: 8px; border: 1px solid #444;">2.40</td>
      <td style="padding: 8px; border: 1px solid #444;">1500</td>
      <td style="padding: 8px; border: 1px solid #444;">55</td>
      <td style="padding: 8px; border: 1px solid #444;">40</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">5</td>
      <td style="padding: 8px; border: 1px solid #444;">Eva</td>
      <td style="padding: 8px; border: 1px solid #444;">3.10</td>
      <td style="padding: 8px; border: 1px solid #444;">3500</td>
      <td style="padding: 8px; border: 1px solid #444;">78</td>
      <td style="padding: 8px; border: 1px solid #444;">15</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">6</td>
      <td style="padding: 8px; border: 1px solid #444;">Fajar</td>
      <td style="padding: 8px; border: 1px solid #444;">3.60</td>
      <td style="padding: 8px; border: 1px solid #444;">6000</td>
      <td style="padding: 8px; border: 1px solid #444;">88</td>
      <td style="padding: 8px; border: 1px solid #444;">8</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">7</td>
      <td style="padding: 8px; border: 1px solid #444;">Gina</td>
      <td style="padding: 8px; border: 1px solid #444;">2.90</td>
      <td style="padding: 8px; border: 1px solid #444;">2500</td>
      <td style="padding: 8px; border: 1px solid #444;">70</td>
      <td style="padding: 8px; border: 1px solid #444;">30</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">8</td>
      <td style="padding: 8px; border: 1px solid #444;">Hadi</td>
      <td style="padding: 8px; border: 1px solid #444;">3.20</td>
      <td style="padding: 8px; border: 1px solid #444;">4000</td>
      <td style="padding: 8px; border: 1px solid #444;">80</td>
      <td style="padding: 8px; border: 1px solid #444;">12</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">9</td>
      <td style="padding: 8px; border: 1px solid #444;">Indah</td>
      <td style="padding: 8px; border: 1px solid #444;">3.75</td>
      <td style="padding: 8px; border: 1px solid #444;">7500</td>
      <td style="padding: 8px; border: 1px solid #444;">90</td>
      <td style="padding: 8px; border: 1px solid #444;">6</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">10</td>
      <td style="padding: 8px; border: 1px solid #444;">Joko</td>
      <td style="padding: 8px; border: 1px solid #444;">2.55</td>
      <td style="padding: 8px; border: 1px solid #444;">1800</td>
      <td style="padding: 8px; border: 1px solid #444;">60</td>
      <td style="padding: 8px; border: 1px solid #444;">35</td>
    </tr>
  </tbody>
</table>

<h2>1. Min-Max Normalization</h2>

<p>Metode ini digunakan untuk menyesuaikan nilai data agar berada dalam rentang tertentu, biasanya <strong>0 sampai 1</strong>. Teknik ini sering dipakai pada algoritma yang menghitung jarak antar data, misalnya pada <em>K-Means Clustering</em> dan <em>K-Nearest Neighbor</em>.</p>

<ul>
  <li><strong>Kelebihan:</strong> Hubungan antar nilai data tetap terjaga. Output selalu dalam rentang [0, 1].</li>
  <li><strong>Kelemahan:</strong> Mudah terpengaruh oleh <em>outlier</em> — jika ada satu data yang nilainya jauh melebihi lainnya, semua data lain akan terkompresi mendekati 0.</li>
  <li><strong>Rumus:</strong></li>
</ul>

<div style="text-align: center; margin: 20px 0; font-size: 18px;">
  x' = (x - x<sub>min</sub>) / (x<sub>max</sub> - x<sub>min</sub>)
</div>

<h3>Contoh</h3>

<p>Mengubah nilai data agar berada pada rentang <strong>0 sampai 1</strong>. Kolom <strong>IPK</strong>, mahasiswa <strong>Andi (IPK = 3.50)</strong>:</p>

<ul>
  <li>Nilai minimum IPK: <strong>x<sub>min</sub> = 2.40</strong> (Deni)</li>
  <li>Nilai maksimum IPK: <strong>x<sub>max</sub> = 3.85</strong> (Citra)</li>
  <li>Contoh hitung (IPK Andi = 3.50):</li>
</ul>

<div style="text-align: center; margin: 20px 0; font-size: 18px;">
  IPK'<sub>Andi</sub> = (3.50 - 2.40) / (3.85 - 2.40) = 1.10 / 1.45 ≈ <strong>0.7586</strong>
</div>

<p>Artinya, IPK Andi berada di posisi <strong>75.86%</strong> dari rentang nilai terendah ke tertinggi. Nilai <strong>0</strong> dimiliki Deni (terendah) dan nilai <strong>1</strong> dimiliki Citra (tertinggi).</p>

<h3>Tabel Sebelum (kiri) dan Sesudah Min-Max Normalization (kanan):</h3>

<table border="1" style="border-collapse: collapse; width: 100%;">
  <thead>
    <tr style="background-color: #2c3e50; color: white;">
      <th style="padding: 10px; border: 1px solid #444;">Nama</th>
      <th style="padding: 10px; border: 1px solid #444;">IPK</th>
      <th style="padding: 10px; border: 1px solid #444;">Penghasilan_OT</th>
      <th style="padding: 10px; border: 1px solid #444;">Nilai_UAS</th>
      <th style="padding: 10px; border: 1px solid #444;">Jarak_Km</th>
      <th style="padding: 10px; border: 1px solid #444;">IPK'</th>
      <th style="padding: 10px; border: 1px solid #444;">Penghasilan'</th>
      <th style="padding: 10px; border: 1px solid #444;">UAS'</th>
      <th style="padding: 10px; border: 1px solid #444;">Jarak'</th>
    </tr>
  </thead>
  <tbody>
    <tr style="font-weight: bold;">
      <td style="padding: 8px; border: 1px solid #444;">Andi</td>
      <td style="padding: 8px; border: 1px solid #444;">3.50</td>
      <td style="padding: 8px; border: 1px solid #444;">5000</td>
      <td style="padding: 8px; border: 1px solid #444;">85</td>
      <td style="padding: 8px; border: 1px solid #444;">10</td>
      <td style="padding: 8px; border: 1px solid #444;">0.7586</td>
      <td style="padding: 8px; border: 1px solid #444;">0.5385</td>
      <td style="padding: 8px; border: 1px solid #444;">0.8108</td>
      <td style="padding: 8px; border: 1px solid #444;">0.1429</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">Budi</td>
      <td style="padding: 8px; border: 1px solid #444;">2.75</td>
      <td style="padding: 8px; border: 1px solid #444;">2000</td>
      <td style="padding: 8px; border: 1px solid #444;">65</td>
      <td style="padding: 8px; border: 1px solid #444;">25</td>
      <td style="padding: 8px; border: 1px solid #444;">0.2414</td>
      <td style="padding: 8px; border: 1px solid #444;">0.0769</td>
      <td style="padding: 8px; border: 1px solid #444;">0.2703</td>
      <td style="padding: 8px; border: 1px solid #444;">0.5714</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">Citra</td>
      <td style="padding: 8px; border: 1px solid #444;">3.85</td>
      <td style="padding: 8px; border: 1px solid #444;">8000</td>
      <td style="padding: 8px; border: 1px solid #444;">92</td>
      <td style="padding: 8px; border: 1px solid #444;">5</td>
      <td style="padding: 8px; border: 1px solid #444;">1.0000</td>
      <td style="padding: 8px; border: 1px solid #444;">1.0000</td>
      <td style="padding: 8px; border: 1px solid #444;">1.0000</td>
      <td style="padding: 8px; border: 1px solid #444;">0.0000</td>
    </tr>
    <tr >
      <td style="padding: 8px; border: 1px solid #444;">Deni</td>
      <td style="padding: 8px; border: 1px solid #444;">2.40</td>
      <td style="padding: 8px; border: 1px solid #444;">1500</td>
      <td style="padding: 8px; border: 1px solid #444;">55</td>
      <td style="padding: 8px; border: 1px solid #444;">40</td>
      <td style="padding: 8px; border: 1px solid #444;">0.0000</td>
      <td style="padding: 8px; border: 1px solid #444;">0.0000</td>
      <td style="padding: 8px; border: 1px solid #444;">0.0000</td>
      <td style="padding: 8px; border: 1px solid #444;">1.0000</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">Eva</td>
      <td style="padding: 8px; border: 1px solid #444;">3.10</td>
      <td style="padding: 8px; border: 1px solid #444;">3500</td>
      <td style="padding: 8px; border: 1px solid #444;">78</td>
      <td style="padding: 8px; border: 1px solid #444;">15</td>
      <td style="padding: 8px; border: 1px solid #444;">0.4828</td>
      <td style="padding: 8px; border: 1px solid #444;">0.3077</td>
      <td style="padding: 8px; border: 1px solid #444;">0.6216</td>
      <td style="padding: 8px; border: 1px solid #444;">0.2857</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">Fajar</td>
      <td style="padding: 8px; border: 1px solid #444;">3.60</td>
      <td style="padding: 8px; border: 1px solid #444;">6000</td>
      <td style="padding: 8px; border: 1px solid #444;">88</td>
      <td style="padding: 8px; border: 1px solid #444;">8</td>
      <td style="padding: 8px; border: 1px solid #444;">0.8276</td>
      <td style="padding: 8px; border: 1px solid #444;">0.6923</td>
      <td style="padding: 8px; border: 1px solid #444;">0.8919</td>
      <td style="padding: 8px; border: 1px solid #444;">0.0857</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">Gina</td>
      <td style="padding: 8px; border: 1px solid #444;">2.90</td>
      <td style="padding: 8px; border: 1px solid #444;">2500</td>
      <td style="padding: 8px; border: 1px solid #444;">70</td>
      <td style="padding: 8px; border: 1px solid #444;">30</td>
      <td style="padding: 8px; border: 1px solid #444;">0.3448</td>
      <td style="padding: 8px; border: 1px solid #444;">0.1538</td>
      <td style="padding: 8px; border: 1px solid #444;">0.4054</td>
      <td style="padding: 8px; border: 1px solid #444;">0.7143</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">Hadi</td>
      <td style="padding: 8px; border: 1px solid #444;">3.20</td>
      <td style="padding: 8px; border: 1px solid #444;">4000</td>
      <td style="padding: 8px; border: 1px solid #444;">80</td>
      <td style="padding: 8px; border: 1px solid #444;">12</td>
      <td style="padding: 8px; border: 1px solid #444;">0.5517</td>
      <td style="padding: 8px; border: 1px solid #444;">0.3846</td>
      <td style="padding: 8px; border: 1px solid #444;">0.6757</td>
      <td style="padding: 8px; border: 1px solid #444;">0.2000</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">Indah</td>
      <td style="padding: 8px; border: 1px solid #444;">3.75</td>
      <td style="padding: 8px; border: 1px solid #444;">7500</td>
      <td style="padding: 8px; border: 1px solid #444;">90</td>
      <td style="padding: 8px; border: 1px solid #444;">6</td>
      <td style="padding: 8px; border: 1px solid #444;">0.9310</td>
      <td style="padding: 8px; border: 1px solid #444;">0.9231</td>
      <td style="padding: 8px; border: 1px solid #444;">0.9459</td>
      <td style="padding: 8px; border: 1px solid #444;">0.0286</td>
    </tr>
    <tr >
      <td style="padding: 8px; border: 1px solid #444;">Joko</td>
      <td style="padding: 8px; border: 1px solid #444;">2.55</td>
      <td style="padding: 8px; border: 1px solid #444;">1800</td>
      <td style="padding: 8px; border: 1px solid #444;">60</td>
      <td style="padding: 8px; border: 1px solid #444;">35</td>
      <td style="padding: 8px; border: 1px solid #444;">0.1034</td>
      <td style="padding: 8px; border: 1px solid #444;">0.0462</td>
      <td style="padding: 8px; border: 1px solid #444;">0.1351</td>
      <td style="padding: 8px; border: 1px solid #444;">0.8571</td>
    </tr>
  </tbody>
</table>
<div style="background-color: #34495e; color: white; padding: 15px; border-radius: 5px; margin: 20px 0;">
  <p style="margin: 0;"><strong>Baris Andi (tebal)</strong> = contoh yang dihitung manual di atas. Citra mendapat <strong>1.0000</strong> karena nilai tertinggi, Deni mendapat <strong>0.0000</strong> karena nilai terendah.</p>
</div>

<h3>Min-Max New (Custom Range)</h3>

<p>Min-Max juga bisa digunakan untuk mengubah data ke <strong>rentang baru yang kita tentukan sendiri</strong>, misalnya 0–10, −1 sampai 1, atau rentang lainnya.</p>

<ul>
  <li><strong>Rumus:</strong></li>
</ul>

<div style="text-align: center; margin: 20px 0; font-size: 18px;">
  x' = (x - x<sub>min</sub>) / (x<sub>max</sub> - x<sub>min</sub>) × (New<sub>max</sub> - New<sub>min</sub>) + New<sub>min</sub>
</div>

<h4>Contoh</h4>

<p>Misalnya IPK Andi ingin diubah ke rentang <strong>0 sampai 10</strong>:</p>

<div style="text-align: center; margin: 20px 0; font-size: 18px;">
  IPK'<sub>Andi</sub> = (3.50 - 2.40) / (3.85 - 2.40) × (10 - 0) + 0 = 1.10 / 1.45 × 10 ≈ <strong>7.586</strong>
</div>

<hr>

<h2>2. Z-Score Normalization</h2>

<p>Teknik ini mengubah data sehingga nilai rata-rata (<em>mean</em>) menjadi <strong>0</strong> dan standar deviasi menjadi <strong>1</strong>. Metode ini sering digunakan ketika data memiliki skala yang berbeda atau terdapat <em>outlier</em>.</p>

<ul>
  <li><strong>Kelebihan:</strong> Lebih tahan terhadap <em>outlier</em> dibanding Min-Max karena mempertimbangkan penyebaran data.</li>
  <li><strong>Kelemahan:</strong> Hasil normalisasi tidak memiliki batas rentang tetap seperti 0 sampai 1.</li>
  <li><strong>Rumus:</strong></li>
</ul>

<div style="text-align: center; margin: 20px 0; font-size: 18px;">
  x' = (x - μ) / σ
</div>

<p><em>(Keterangan: μ adalah rata-rata dan σ adalah standar deviasi)</em></p>

<h3>Contoh</h3>

<p>Tujuan: mengubah data sehingga <strong>mean = 0</strong> dan <strong>standar deviasi = 1</strong>. Kolom <strong>IPK</strong>, mahasiswa <strong>Andi (IPK = 3.50)</strong>:</p>

<h4>Langkah 1 — Hitung rata-rata (μ):</h4>

<div style="text-align: center; margin: 20px 0; font-size: 18px;">
  μ = (3.50 + 2.75 + 3.85 + 2.40 + 3.10 + 3.60 + 2.90 + 3.20 + 3.75 + 2.55) / 10 = <strong>3.16</strong>
</div>

<h4>Langkah 2 — Hitung standar deviasi (σ):</h4>

<div style="text-align: center; margin: 20px 0; font-size: 18px;">
  σ = √[Σ(x - μ)² / (n - 1)] = <strong>0.5082</strong>
</div>

<h4>Langkah 3 — Masukkan ke rumus Z-Score:</h4>

<div style="text-align: center; margin: 20px 0; font-size: 18px;">
  IPK'<sub>Andi</sub> = (3.50 - 3.16) / 0.5082 = 0.34 / 0.5082 ≈ <strong>0.6691</strong>
</div>

<p>Nilai positif berarti IPK Andi berada <strong>0.6691 standar deviasi di atas rata-rata</strong>. Jika hasilnya negatif seperti Budi (−0.8068), berarti IPK Budi berada di bawah rata-rata kelompok.</p>

<h3>Tabel Sebelum (kiri) dan Sesudah Z-Score Normalization (kanan):</h3>

<table border="1" style="border-collapse: collapse; width: 100%;">
  <thead>
    <tr style="background-color: #2c3e50; color: white;">
      <th style="padding: 10px; border: 1px solid #444;">Nama</th>
      <th style="padding: 10px; border: 1px solid #444;">IPK</th>
      <th style="padding: 10px; border: 1px solid #444;">Penghasilan_OT</th>
      <th style="padding: 10px; border: 1px solid #444;">Nilai_UAS</th>
      <th style="padding: 10px; border: 1px solid #444;">Jarak_Km</th>
      <th style="padding: 10px; border: 1px solid #444;">IPK'</th>
      <th style="padding: 10px; border: 1px solid #444;">Penghasilan'</th>
      <th style="padding: 10px; border: 1px solid #444;">UAS'</th>
      <th style="padding: 10px; border: 1px solid #444;">Jarak'</th>
    </tr>
  </thead>
  <tbody>
    <tr style="font-weight: bold;">
      <td style="padding: 8px; border: 1px solid #444;">Andi</td>
      <td style="padding: 8px; border: 1px solid #444;">3.50</td>
      <td style="padding: 8px; border: 1px solid #444;">5000</td>
      <td style="padding: 8px; border: 1px solid #444;">85</td>
      <td style="padding: 8px; border: 1px solid #444;">10</td>
      <td style="padding: 8px; border: 1px solid #444;">0.6691</td>
      <td style="padding: 8px; border: 1px solid #444;">0.3461</td>
      <td style="padding: 8px; border: 1px solid #444;">0.6629</td>
      <td style="padding: 8px; border: 1px solid #444;">−0.6696</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">Budi</td>
      <td style="padding: 8px; border: 1px solid #444;">2.75</td>
      <td style="padding: 8px; border: 1px solid #444;">2000</td>
      <td style="padding: 8px; border: 1px solid #444;">65</td>
      <td style="padding: 8px; border: 1px solid #444;">25</td>
      <td style="padding: 8px; border: 1px solid #444;">−0.8068</td>
      <td style="padding: 8px; border: 1px solid #444;">−0.9202</td>
      <td style="padding: 8px; border: 1px solid #444;">−0.8610</td>
      <td style="padding: 8px; border: 1px solid #444;">0.4983</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">Citra</td>
      <td style="padding: 8px; border: 1px solid #444;">3.85</td>
      <td style="padding: 8px; border: 1px solid #444;">8000</td>
      <td style="padding: 8px; border: 1px solid #444;">92</td>
      <td style="padding: 8px; border: 1px solid #444;">5</td>
      <td style="padding: 8px; border: 1px solid #444;">1.3579</td>
      <td style="padding: 8px; border: 1px solid #444;">1.6124</td>
      <td style="padding: 8px; border: 1px solid #444;">1.1963</td>
      <td style="padding: 8px; border: 1px solid #444;">−1.0590</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">Deni</td>
      <td style="padding: 8px; border: 1px solid #444;">2.40</td>
      <td style="padding: 8px; border: 1px solid #444;">1500</td>
      <td style="padding: 8px; border: 1px solid #444;">55</td>
      <td style="padding: 8px; border: 1px solid #444;">40</td>
      <td style="padding: 8px; border: 1px solid #444;">−1.4956</td>
      <td style="padding: 8px; border: 1px solid #444;">−1.1312</td>
      <td style="padding: 8px; border: 1px solid #444;">−1.6230</td>
      <td style="padding: 8px; border: 1px solid #444;">1.6663</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">Eva</td>
      <td style="padding: 8px; border: 1px solid #444;">3.10</td>
      <td style="padding: 8px; border: 1px solid #444;">3500</td>
      <td style="padding: 8px; border: 1px solid #444;">78</td>
      <td style="padding: 8px; border: 1px solid #444;">15</td>
      <td style="padding: 8px; border: 1px solid #444;">−0.1181</td>
      <td style="padding: 8px; border: 1px solid #444;">−0.2870</td>
      <td style="padding: 8px; border: 1px solid #444;">0.1295</td>
      <td style="padding: 8px; border: 1px solid #444;">−0.2803</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">Fajar</td>
      <td style="padding: 8px; border: 1px solid #444;">3.60</td>
      <td style="padding: 8px; border: 1px solid #444;">6000</td>
      <td style="padding: 8px; border: 1px solid #444;">88</td>
      <td style="padding: 8px; border: 1px solid #444;">8</td>
      <td style="padding: 8px; border: 1px solid #444;">0.8659</td>
      <td style="padding: 8px; border: 1px solid #444;">0.7682</td>
      <td style="padding: 8px; border: 1px solid #444;">0.8915</td>
      <td style="padding: 8px; border: 1px solid #444;">−0.8254</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">Gina</td>
      <td style="padding: 8px; border: 1px solid #444;">2.90</td>
      <td style="padding: 8px; border: 1px solid #444;">2500</td>
      <td style="padding: 8px; border: 1px solid #444;">70</td>
      <td style="padding: 8px; border: 1px solid #444;">30</td>
      <td style="padding: 8px; border: 1px solid #444;">−0.5117</td>
      <td style="padding: 8px; border: 1px solid #444;">−0.7091</td>
      <td style="padding: 8px; border: 1px solid #444;">−0.4800</td>
      <td style="padding: 8px; border: 1px solid #444;">0.8877</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">Hadi</td>
      <td style="padding: 8px; border: 1px solid #444;">3.20</td>
      <td style="padding: 8px; border: 1px solid #444;">4000</td>
      <td style="padding: 8px; border: 1px solid #444;">80</td>
      <td style="padding: 8px; border: 1px solid #444;">12</td>
      <td style="padding: 8px; border: 1px solid #444;">0.0787</td>
      <td style="padding: 8px; border: 1px solid #444;">−0.0760</td>
      <td style="padding: 8px; border: 1px solid #444;">0.2819</td>
      <td style="padding: 8px; border: 1px solid #444;">−0.5139</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">Indah</td>
      <td style="padding: 8px; border: 1px solid #444;">3.75</td>
      <td style="padding: 8px; border: 1px solid #444;">7500</td>
      <td style="padding: 8px; border: 1px solid #444;">90</td>
      <td style="padding: 8px; border: 1px solid #444;">6</td>
      <td style="padding: 8px; border: 1px solid #444;">1.1611</td>
      <td style="padding: 8px; border: 1px solid #444;">1.4013</td>
      <td style="padding: 8px; border: 1px solid #444;">1.0439</td>
      <td style="padding: 8px; border: 1px solid #444;">−0.9811</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">Joko</td>
      <td style="padding: 8px; border: 1px solid #444;">2.55</td>
      <td style="padding: 8px; border: 1px solid #444;">1800</td>
      <td style="padding: 8px; border: 1px solid #444;">60</td>
      <td style="padding: 8px; border: 1px solid #444;">35</td>
      <td style="padding: 8px; border: 1px solid #444;">−1.2004</td>
      <td style="padding: 8px; border: 1px solid #444;">−1.0046</td>
      <td style="padding: 8px; border: 1px solid #444;">−1.2420</td>
      <td style="padding: 8px; border: 1px solid #444;">1.2770</td>
    </tr>
  </tbody>
</table>
<div style="background-color: #34495e; color: white; padding: 15px; border-radius: 5px; margin: 20px 0;">
  <p style="margin: 0;">Nilai <strong>positif</strong> = di atas rata-rata. Nilai <strong>negatif</strong> = di bawah rata-rata. Baris <strong>Andi</strong> (tebal) = contoh perhitungan manual di atas.</p>
</div>

<h2>3. Decimal Scaling</h2>

<p>Teknik ini bekerja dengan menggeser titik desimal dari nilai data. Jumlah pergeseran desimal bergantung pada nilai absolut maksimum di dalam atribut tersebut. Ini adalah metode normalisasi yang <strong>paling mudah dihitung secara manual</strong>.</p>

<ul>
  <li><strong>Kelebihan:</strong> Sederhana dan mudah dihitung, tidak perlu menghitung mean atau std.</li>
  <li><strong>Kelemahan:</strong> Tidak mempertimbangkan distribusi data secara keseluruhan.</li>
  <li><strong>Rumus:</strong></li>
</ul>

<div style="text-align: center; margin: 20px 0; font-size: 18px;">
  x' = x / 10<sup>j</sup>
</div>

<p><em>(Keterangan: j adalah bilangan bulat terkecil sehingga nilai mutlak maksimum dari x' kurang dari 1)</em></p>

<h3>Contoh</h3>

<p>Menggeser koma desimal. Pembaginya ditentukan oleh jumlah digit nilai terbesar di setiap kolom supaya nilai akhirnya kurang dari 1:</p>

<p><strong>Kolom IPK</strong> — nilai terbesar = 3.85, bagian bulat = 3 → <strong>1 digit</strong> → j = 1 → dibagi 10<sup>1</sup> = 10:</p>

<div style="text-align: center; margin: 20px 0; font-size: 18px;">
  IPK'<sub>Andi</sub> = 3.50 / 10 = <strong>0.350</strong>
</div>

<p><strong>Kolom Penghasilan_OT</strong> — nilai terbesar = 8000 → <strong>4 digit</strong> → j = 4 → dibagi 10<sup>4</sup> = 10.000:</p>

<div style="text-align: center; margin: 20px 0; font-size: 18px;">
  Penghasilan'<sub>Andi</sub> = 5000 / 10000 = <strong>0.5000</strong>
</div>

<p>Nilai <em>j</em> yang digunakan per kolom:</p>
<ul>
  <li><strong>IPK:</strong> maks = 3.85 → j = 1 → dibagi <strong>10</strong></li>
  <li><strong>Penghasilan_OT:</strong> maks = 8000 → j = 4 → dibagi <strong>10.000</strong></li>
  <li><strong>Nilai_UAS:</strong> maks = 92 → j = 2 → dibagi <strong>100</strong></li>
  <li><strong>Jarak_Kampus:</strong> maks = 40 → j = 2 → dibagi <strong>100</strong></li>
</ul>

<h3>Tabel Sebelum (kiri) dan Sesudah Decimal Scaling (kanan):</h3>

<table border="1" style="border-collapse: collapse; width: 100%;">
  <thead>
    <tr style="background-color: #2c3e50; color: white;">
      <th style="padding: 10px; border: 1px solid #444;">Nama</th>
      <th style="padding: 10px; border: 1px solid #444;">IPK</th>
      <th style="padding: 10px; border: 1px solid #444;">Penghasilan_OT</th>
      <th style="padding: 10px; border: 1px solid #444;">Nilai_UAS</th>
      <th style="padding: 10px; border: 1px solid #444;">Jarak_Km</th>
      <th style="padding: 10px; border: 1px solid #444;">IPK'</th>
      <th style="padding: 10px; border: 1px solid #444;">Penghasilan'</th>
      <th style="padding: 10px; border: 1px solid #444;">UAS'</th>
      <th style="padding: 10px; border: 1px solid #444;">Jarak'</th>
    </tr>
  </thead>
  <tbody>
    <tr style="font-weight: bold;">
      <td style="padding: 8px; border: 1px solid #444;">Andi</td>
      <td style="padding: 8px; border: 1px solid #444;">3.50</td>
      <td style="padding: 8px; border: 1px solid #444;">5000</td>
      <td style="padding: 8px; border: 1px solid #444;">85</td>
      <td style="padding: 8px; border: 1px solid #444;">10</td>
      <td style="padding: 8px; border: 1px solid #444;">0.3500</td>
      <td style="padding: 8px; border: 1px solid #444;">0.5000</td>
      <td style="padding: 8px; border: 1px solid #444;">0.85</td>
      <td style="padding: 8px; border: 1px solid #444;">0.10</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">Budi</td>
      <td style="padding: 8px; border: 1px solid #444;">2.75</td>
      <td style="padding: 8px; border: 1px solid #444;">2000</td>
      <td style="padding: 8px; border: 1px solid #444;">65</td>
      <td style="padding: 8px; border: 1px solid #444;">25</td>
      <td style="padding: 8px; border: 1px solid #444;">0.2750</td>
      <td style="padding: 8px; border: 1px solid #444;">0.2000</td>
      <td style="padding: 8px; border: 1px solid #444;">0.65</td>
      <td style="padding: 8px; border: 1px solid #444;">0.25</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">Citra</td>
      <td style="padding: 8px; border: 1px solid #444;">3.85</td>
      <td style="padding: 8px; border: 1px solid #444;">8000</td>
      <td style="padding: 8px; border: 1px solid #444;">92</td>
      <td style="padding: 8px; border: 1px solid #444;">5</td>
      <td style="padding: 8px; border: 1px solid #444;">0.3850</td>
      <td style="padding: 8px; border: 1px solid #444;">0.8000</td>
      <td style="padding: 8px; border: 1px solid #444;">0.92</td>
      <td style="padding: 8px; border: 1px solid #444;">0.05</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">Deni</td>
      <td style="padding: 8px; border: 1px solid #444;">2.40</td>
      <td style="padding: 8px; border: 1px solid #444;">1500</td>
      <td style="padding: 8px; border: 1px solid #444;">55</td>
      <td style="padding: 8px; border: 1px solid #444;">40</td>
      <td style="padding: 8px; border: 1px solid #444;">0.2400</td>
      <td style="padding: 8px; border: 1px solid #444;">0.1500</td>
      <td style="padding: 8px; border: 1px solid #444;">0.55</td>
      <td style="padding: 8px; border: 1px solid #444;">0.40</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">Eva</td>
      <td style="padding: 8px; border: 1px solid #444;">3.10</td>
      <td style="padding: 8px; border: 1px solid #444;">3500</td>
      <td style="padding: 8px; border: 1px solid #444;">78</td>
      <td style="padding: 8px; border: 1px solid #444;">15</td>
      <td style="padding: 8px; border: 1px solid #444;">0.3100</td>
      <td style="padding: 8px; border: 1px solid #444;">0.3500</td>
      <td style="padding: 8px; border: 1px solid #444;">0.78</td>
      <td style="padding: 8px; border: 1px solid #444;">0.15</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">Fajar</td>
      <td style="padding: 8px; border: 1px solid #444;">3.60</td>
      <td style="padding: 8px; border: 1px solid #444;">6000</td>
      <td style="padding: 8px; border: 1px solid #444;">88</td>
      <td style="padding: 8px; border: 1px solid #444;">8</td>
      <td style="padding: 8px; border: 1px solid #444;">0.3600</td>
      <td style="padding: 8px; border: 1px solid #444;">0.6000</td>
      <td style="padding: 8px; border: 1px solid #444;">0.88</td>
      <td style="padding: 8px; border: 1px solid #444;">0.08</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">Gina</td>
      <td style="padding: 8px; border: 1px solid #444;">2.90</td>
      <td style="padding: 8px; border: 1px solid #444;">2500</td>
      <td style="padding: 8px; border: 1px solid #444;">70</td>
      <td style="padding: 8px; border: 1px solid #444;">30</td>
      <td style="padding: 8px; border: 1px solid #444;">0.2900</td>
      <td style="padding: 8px; border: 1px solid #444;">0.2500</td>
      <td style="padding: 8px; border: 1px solid #444;">0.70</td>
      <td style="padding: 8px; border: 1px solid #444;">0.30</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">Hadi</td>
      <td style="padding: 8px; border: 1px solid #444;">3.20</td>
      <td style="padding: 8px; border: 1px solid #444;">4000</td>
      <td style="padding: 8px; border: 1px solid #444;">80</td>
      <td style="padding: 8px; border: 1px solid #444;">12</td>
      <td style="padding: 8px; border: 1px solid #444;">0.3200</td>
      <td style="padding: 8px; border: 1px solid #444;">0.4000</td>
      <td style="padding: 8px; border: 1px solid #444;">0.80</td>
      <td style="padding: 8px; border: 1px solid #444;">0.12</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">Indah</td>
      <td style="padding: 8px; border: 1px solid #444;">3.75</td>
      <td style="padding: 8px; border: 1px solid #444;">7500</td>
      <td style="padding: 8px; border: 1px solid #444;">90</td>
      <td style="padding: 8px; border: 1px solid #444;">6</td>
      <td style="padding: 8px; border: 1px solid #444;">0.3750</td>
      <td style="padding: 8px; border: 1px solid #444;">0.7500</td>
      <td style="padding: 8px; border: 1px solid #444;">0.90</td>
      <td style="padding: 8px; border: 1px solid #444;">0.06</td>
    </tr>
    <tr>
      <td style="padding: 8px; border: 1px solid #444;">Joko</td>
      <td style="padding: 8px; border: 1px solid #444;">2.55</td>
      <td style="padding: 8px; border: 1px solid #444;">1800</td>
      <td style="padding: 8px; border: 1px solid #444;">60</td>
      <td style="padding: 8px; border: 1px solid #444;">35</td>
      <td style="padding: 8px; border: 1px solid #444;">0.2550</td>
      <td style="padding: 8px; border: 1px solid #444;">0.1800</td>
      <td style="padding: 8px; border: 1px solid #444;">0.60</td>
      <td style="padding: 8px; border: 1px solid #444;">0.35</td>
    </tr>
  </tbody>
</table>

<div style="background-color: #34495e; color: white; padding: 15px; border-radius: 5px; margin: 20px 0;">
  <p style="margin: 0;"><strong>Baris Andi (tebal)</strong> = contoh yang dihitung manual di atas.</p>
</div>

<h2>Implementasi dengan Sklearn dan Fungsi Kustom</h2>

<p>Berikut adalah script Python menggunakan <code>scikit-learn</code> untuk Min-Max dan Z-Score, serta fungsi manual untuk Decimal Scaling.</p>

```python
import pandas as pd
import numpy as np
from sklearn.preprocessing import MinMaxScaler, StandardScaler

# Data asli mahasiswa
data = {
    'Nama':           ['Andi','Budi','Citra','Deni','Eva','Fajar','Gina','Hadi','Indah','Joko'],
    'IPK':            [3.50, 2.75, 3.85, 2.40, 3.10, 3.60, 2.90, 3.20, 3.75, 2.55],
    'Penghasilan_OT': [5000, 2000, 8000, 1500, 3500, 6000, 2500, 4000, 7500, 1800],
    'Nilai_UAS':      [85, 65, 92, 55, 78, 88, 70, 80, 90, 60],
    'Jarak_Kampus':   [10, 25, 5, 40, 15, 8, 30, 12, 6, 35]
}
df    = pd.DataFrame(data)
fitur = ['IPK', 'Penghasilan_OT', 'Nilai_UAS', 'Jarak_Kampus']

print("Data Asli:")
print(df.to_string(index=False))

# 1. Min-Max Scaling (Sklearn)
minmax_scaler = MinMaxScaler()
X_minmax = minmax_scaler.fit_transform(df[fitur])
print("\n1. Hasil Min-Max Scaling:")
print(X_minmax.round(4))

# 2. Z-Score / Standardization (Sklearn)
standard_scaler = StandardScaler()
X_standard = standard_scaler.fit_transform(df[fitur])
print("\n2. Hasil Z-Score (Standardization):")
print(X_standard.round(4))

# 3. Decimal Scaling (Custom Function)
def decimal_scaling(df_input, cols):
    """
    Melakukan decimal scaling pada setiap kolom numerik.
    Nilai dibagi dengan 10^j, di mana j adalah jumlah digit
    dari nilai absolut terbesar pada kolom tersebut.
    """
    result = df_input.copy()
    for col in cols:
        max_abs = result[col].abs().max()
        j = len(str(int(max_abs)))          # Jumlah digit nilai maks
        result[col] = (result[col] / (10 ** j)).round(4)
        print(f"  Kolom '{col}': nilai maks = {max_abs}, j = {j}, dibagi {10**j}")
    return result

print("\n3. Decimal Scaling (Fungsi Manual):")
df_decimal = decimal_scaling(df, fitur)
print(df_decimal.to_string(index=False))
```
```text
Data Asli:
 Nama  IPK  Penghasilan_OT  Nilai_UAS  Jarak_Kampus
 Andi 3.50            5000         85            10
 Budi 2.75            2000         65            25
Citra 3.85            8000         92             5
 Deni 2.40            1500         55            40
  Eva 3.10            3500         78            15
Fajar 3.60            6000         88             8
 Gina 2.90            2500         70            30
 Hadi 3.20            4000         80            12
Indah 3.75            7500         90             6
 Joko 2.55            1800         60            35

1. Hasil Min-Max Scaling:
[[0.7586 0.5385 0.8108 0.1429]
 [0.2414 0.0769 0.2703 0.5714]
 [1.     1.     1.     0.    ]
 [0.     0.     0.     1.    ]
 [0.4828 0.3077 0.6216 0.2857]
 [0.8276 0.6923 0.8919 0.0857]
 [0.3448 0.1538 0.4054 0.7143]
 [0.5517 0.3846 0.6757 0.2   ]
 [0.931  0.9231 0.9459 0.0286]
 [0.1034 0.0462 0.1351 0.8571]]

2. Hasil Z-Score (Standardization):
[[ 0.7053  0.3648  0.6988 -0.7059]
 [-0.8505 -0.9699 -0.9076  0.5253]
 [ 1.4313  1.6996  1.261  -1.1163]
 [-1.5765 -1.1924 -1.7108  1.7565]
 [-0.1245 -0.3025  0.1365 -0.2955]
 [ 0.9127  0.8098  0.9397 -0.87  ]
 [-0.5393 -0.7475 -0.506   0.9357]
 [ 0.083  -0.0801  0.2972 -0.5417]
 [ 1.2239  1.4771  1.1004 -1.0342]
 [-1.2654 -1.0589 -1.3092  1.3461]]

3. Decimal Scaling (Fungsi Manual):
  Kolom 'IPK': nilai maks = 3.85, j = 1, dibagi 10
  Kolom 'Penghasilan_OT': nilai maks = 8000, j = 4, dibagi 10000
  Kolom 'Nilai_UAS': nilai maks = 92, j = 2, dibagi 100
  Kolom 'Jarak_Kampus': nilai maks = 40, j = 2, dibagi 100
 Nama   IPK  Penghasilan_OT  Nilai_UAS  Jarak_Kampus
 Andi 0.350            0.50       0.85          0.10
 Budi 0.275            0.20       0.65          0.25
Citra 0.385            0.80       0.92          0.05
 Deni 0.240            0.15       0.55          0.40
  Eva 0.310            0.35       0.78          0.15
Fajar 0.360            0.60       0.88          0.08
 Gina 0.290            0.25       0.70          0.30
 Hadi 0.320            0.40       0.80          0.12
Indah 0.375            0.75       0.90          0.06
 Joko 0.255            0.18       0.60          0.35
```

# UTS
## Analisa Data Kesuburan Tanah (KNN)
![alt text](image-13.png)
## 1 METODE
metode yang saya gunakan  adalah  K-Nearest Neighbors (KNN) untuk klasifikasi tanah menjadi dua kelas: Subur dan Tidak Subur.
![alt text](image-14.png)
KNN bekerja dengan cara menghitung jarak antar data kemudian k tetangga terdekat (5) setelah itu menentukan kelas berdasarkan mayoritas tetangganya

## missing value
![alt text](image-15.png)
Node Missing Value digunakan untuk mengisi data yang kosong. Nilai numerik diisi dengan rata-rata (mean), sedangkan data teks diisi dengan nilai yang paling sering muncul. Tujuannya agar data lengkap dan siap digunakan untuk analisis.
## one to many
Node One to Many digunakan untuk mengubah data kategorikal (teks) menjadi bentuk numerik biner (one-hot encoding). Misalnya, kolom Tekstur Tanah diubah menjadi beberapa kolom seperti Debu, Pasir, dll, dengan nilai 0 dan 1. Tujuannya agar data bisa diproses oleh algoritma seperti KNN yang hanya menerima data numerik.

## colum filter
![alt text](image-16.png)
Node Column Filter di KNIME Analytics Platform digunakan untuk memilih kolom yang akan dipakai atau dihapus. kolom Tekstur Tanah (teks) dihapus setelah proses encoding, sementara kolom lain termasuk Label tetap digunakan. Tujuannya agar hanya fitur yang relevan dan numerik yang masuk ke model.

## normalizer
![alt text](image-17.png)
Node Normalizer di KNIME Analytics Platform digunakan untuk menyamakan skala nilai data, biasanya ke rentang 0–1 (Min-Max scaling). Hal ini penting agar semua fitur memiliki bobot yang seimbang saat dihitung jaraknya oleh algoritma seperti KNN

## table partition
![alt text](image-18.png)
Node Table Partitioning di KNIME Analytics Platform digunakan untuk membagi data menjadi data training dan testing. Biasanya menggunakan rasio 80% untuk training dan 20% untuk testing, agar model dapat dilatih terlebih dahulu lalu diuji performanya.

## evaluasi matrik
![alt text](image-19.png)
Precision = 1 (100%) → semua prediksi positif benar <br>
Recall / Sensitivity = 1 (100%) → semua data positif terdeteksi <br>
Specificity = 1 (100%) → semua data negatif terdeteksi <br>
F-measure = 1 → keseimbangan precision & recall sempurna <br>
Accuracy = 1 (100%) → seluruh prediksi benar <br>
 ## distribusi kelas
![alt text](image-20.png)
subur= 200 <br>
tidak subur 200 <br>