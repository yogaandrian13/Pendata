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


# NAIVE BAYES
![alt text](image-21.png)
## file raider
Fungsi: Membaca dan mengimpor data dari berbagai format file (CSV, Excel, TXT, dll)<br>
Tujuan: Memuat dataset ke dalam workflow untuk diproses lebih lanjut
## Missing Value
Fungsi: Menangani data yang hilang atau kosong (null/NaN) dalam dataset<br>
Tujuan:Membersihkan data sebelum analisis. Mengisi nilai yang hilang dengan berbagai. metode (mean, median, modus, atau nilai konstan). Memastikan kualitas data lebih baik untuk pemrosesan selanjutnya
## Python Script (legacy)
Fungsi: Menjalankan skrip Python kustom dalam workflow<br>
Tujuan: Melakukan pemrosesan data yang kompleks. Implementasi algoritma machine learning. Analisis data khusus yang tidak tersedia di node standar KNIME. Transformasi data sesuai kebutuhan
```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.naive_bayes import GaussianNB
from sklearn.metrics import accuracy_score, classification_report

df = input_table_1.copy()

df = df[['Survived', 'Sex', 'Pclass']]

df['Sex'] = df['Sex'].map({'male': 0, 'female': 1})

df = df.dropna()

X = df[['Sex', 'Pclass']]
y = df['Survived'].astype(int)

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

model = GaussianNB()
model.fit(X_train, y_train)

y_pred = model.predict(X_test)

print("Akurasi:", accuracy_score(y_test, y_pred))
print(classification_report(y_test, y_pred))

df['prediction'] = model.predict(X)

output_table_1 = df
```
Analisis Naive Bayes - Penjelasan Langkah demi Langkah<br>

| Baris Kode | Fungsi & Penjelasan |
|------------|---------------------|
| `import pandas as pd` | Mengimpor library yang dibutuhkan: **pandas** (manipulasi data), **scikit-learn** (pemodelan & evaluasi) |
| `df = input_table_1.copy()` | Mengambil data dari port input KNIME. `.copy()` digunakan agar tidak mengubah data asli di memori KNIME |
| `df = df[['Survived', 'Sex', 'Pclass']]` | **Seleksi kolom**: Hanya mempertahankan 3 kolom. Kolom lain (seperti Age, Fare, Embarked) diabaikan |
| `df['Sex'] = df['Sex'].map({'male': 0, 'female': 1})` | **Encoding kategorikal**: Mengubah teks 'male'/'female' menjadi angka 0/1 karena algoritma machine learning hanya menerima input numerik |
| `df = df.dropna()` | **Handling missing value**: Menghapus baris yang mengandung nilai kosong (NaN) pada kolom yang dipilih agar tidak menyebabkan error saat training |
| `X = df[['Sex', 'Pclass']]` | **Pemisahan fitur & target**: X adalah data fitur (input), y adalah label/target |
| `y = df['Survived']` | Memisahkan variabel target (Survived) untuk supervised learning |
| `from sklearn.naive_bayes import GaussianNB` | Mengimpor algoritma **Gaussian Naive Bayes** dari scikit-learn |
| `model = GaussianNB()` | Membuat instance/model Naive Bayes yang siap digunakan |
| `model.fit(X, y)` | **Training model**: Melatih model dengan data X (fitur) dan y (target) |
| `predictions = model.predict(X)` | **Prediksi**: Menggunakan model yang sudah dilatih untuk memprediksi data yang sama |
| `from sklearn.metrics import accuracy_score` | Mengimpor fungsi untuk menghitung akurasi model |
| `accuracy = accuracy_score(y, predictions)` | Menghitung akurasi dengan membandingkan prediksi dengan nilai sebenarnya |
| `print(f"Akurasi: {accuracy:.2%}")` | Menampilkan hasil akurasi dalam bentuk persentase |
```text
Akurasi: 0.7821229050279329
              precision    recall  f1-score   support
           0       0.80      0.84      0.82       105
           1       0.75      0.70      0.73        74
    accuracy                           0.78       179
   macro avg       0.78      0.77      0.77       179
weighted avg       0.78      0.78      0.78       179

```
![alt text](image-22.png)
![alt text](image-23.png)
## Scorer
Fungsi: Mengevaluasi kinerja model machine learning<br>
Tujuan: Mengukur akurasi model. Menghitung metrik evaluasi (precision, recall, F1-score, accuracy). Membandingkan prediksi dengan nilai aktual. Memberikan insight tentang kualitas model
![alt text](image-24.png)

# DECISION TREE
![alt text](image-25.png)
## Excel Reader
Node Excel Reader digunakan untuk membaca atau mengimpor dataset dari file Excel ke dalam KNIME. Dataset yang telah dibaca akan menjadi sumber data utama yang digunakan dalam proses analisis dan pembuatan model klasifikasi.
## Table Partitioner
Node Table Partitioner digunakan untuk membagi dataset menjadi dua bagian, yaitu:
data training → data untuk melatih model,
data testing → data untuk menguji performa model.
pembagian data punya saya yaitu 70% training dan 30% testing,

## Color Manager
Node Color Manager digunakan untuk memberikan warna pada kelas target atau label data. Pewarnaan ini bertujuan untuk mempermudah visualisasi dan membedakan setiap kelas pada proses analisis.

## Decision Tree Learner
Node Decision Tree Learner merupakan inti proses klasifikasi yang digunakan untuk membangun model pohon keputusan berdasarkan data training.<br>
Node ini bekerja dengan:<br>
menganalisis seluruh atribut pada dataset,<br>
menghitung atribut terbaik menggunakan metode Gain Ratio,<br>
membentuk cabang-cabang keputusan,<br>
hingga menghasilkan struktur pohon keputusan.<br>
Hasil dari node ini adalah model klasifikasi Decision Tree yang siap digunakan untuk prediksi.

## Decision Tree Predictor
Node Decision Tree Predictor digunakan untuk melakukan prediksi terhadap data testing menggunakan model yang telah dibuat pada node Decision Tree Learner.<br>
Cara kerjanya:<br>
model pohon keputusan dari data training diterapkan pada data testing,<br>
setiap data diuji mengikuti aturan pada pohon keputusan,<br>
kemudian sistem menghasilkan kelas prediksi.<br>

## Scorer
Node Scorer digunakan untuk mengevaluasi performa model klasifikasi dengan membandingkan hasil prediksi dan data asli.
Evaluasi dilakukan menggunakan:
### Confusion Matrix
Tabel yang menunjukkan jumlah:<br>

prediksi benar,<br>
prediksi salah,<br>
data positif dan negatif.<br>
### Accuracy
Mengukur tingkat ketepatan model dalam melakukan prediksi.

## Kesimpulan
Workflow ini digunakan untuk melakukan proses klasifikasi menggunakan metode Decision Tree di KNIME, dimulai dari membaca data, membagi data training dan testing, membangun model menggunakan Gain Ratio, melakukan prediksi, hingga mengevaluasi performa model menggunakan confusion matrix dan accuracy.

# Random Forest
![alt text](image-26.png)
data yang digunankan menggunakan data iris
## table partitioner
data training sebesar 70% <br>
data testing sebesar 30%
## pyhton script (legacy)
``` python
import pandas as pd
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score, classification_report
train_df = input_table_1.copy()
test_df = input_table_2.copy()
X_train = train_df[
    [
        'sepal_length',
        'sepal_width',
        'petal_length',
        'petal_width'
    ]
]
y_train = train_df['species']
X_test = test_df[
    [
        'sepal_length',
        'sepal_width',
        'petal_length',
        'petal_width'
    ]
]
y_test = test_df['species']
model = RandomForestClassifier(
    n_estimators=10,
    random_state=42
)
model.fit(X_train, y_train)
y_pred = model.predict(X_test)
print("Akurasi:", accuracy_score(y_test, y_pred))
print(classification_report(y_test, y_pred))
test_df['prediction'] = y_pred
output_table_1 = test_df
```
Penjelasan Kode Python Random Forest (Legacy)

### Import Library

```python
import pandas as pd
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score, classification_report
```

* `pandas` digunakan untuk mengolah data dalam bentuk tabel/dataframe.
* `RandomForestClassifier` digunakan untuk membuat model Random Forest.
* `accuracy_score` digunakan untuk menghitung nilai accuracy model.
* `classification_report` digunakan untuk menampilkan laporan hasil klasifikasi seperti precision, recall, dan f1-score.

---

### Membaca Data Training dan Testing

```python
train_df = input_table_1.copy()
test_df = input_table_2.copy()
```
Penjelasan:

* `input_table_1` merupakan data training dari output atas Table Partitioner.
* `input_table_2` merupakan data testing dari output bawah Table Partitioner.
* `.copy()` digunakan untuk menyalin data agar data asli tidak berubah.

---

### Menentukan Fitur Training

```python
X_train = train_df[
    [
        'sepal_length',
        'sepal_width',
        'petal_length',
        'petal_width'
    ]
]
```

Penjelasan:

Kode tersebut digunakan untuk memilih atribut atau fitur yang digunakan dalam proses training model Random Forest.

Fitur yang digunakan:

* sepal_length
* sepal_width
* petal_length
* petal_width

---

### Menentukan Target Training

```python
y_train = train_df['species']
```

Penjelasan:

Kode ini digunakan untuk menentukan kolom target atau kelas yang akan diprediksi, yaitu `species`.

---

### Menentukan Fitur Testing

```python
X_test = test_df[
    [
        'sepal_length',
        'sepal_width',
        'petal_length',
        'petal_width'
    ]
]
```

Penjelasan:

Kode ini digunakan untuk mengambil fitur pada data testing yang akan digunakan dalam proses prediksi.

---

### Menentukan Target Testing

```python
y_test = test_df['species']
```

Penjelasan:

Kode ini digunakan untuk mengambil nilai target asli pada data testing sebagai pembanding hasil prediksi model.

---

### Membuat Model Random Forest

```python
model = RandomForestClassifier(
    n_estimators=10,
    random_state=42
)
```
Penjelasan:

Kode ini digunakan untuk membuat model Random Forest.

Parameter:

* `n_estimators=10`
  → jumlah pohon keputusan (decision tree) yang digunakan sebanyak 10 pohon.
* `random_state=42`
  → digunakan agar hasil random tetap sama setiap dijalankan.

Random Forest bekerja dengan menggabungkan banyak pohon keputusan untuk meningkatkan akurasi dan mengurangi overfitting.

---

### Melatih Model

```python
model.fit(X_train, y_train)
```

Penjelasan:

Kode ini digunakan untuk melatih model Random Forest menggunakan data training.

* `X_train` berisi fitur training
* `y_train` berisi target training

---

### Melakukan Prediksi

```python
y_pred = model.predict(X_test)
```

Penjelasan:

Kode ini digunakan untuk melakukan prediksi terhadap data testing menggunakan model yang telah dilatih sebelumnya.

Hasil prediksi disimpan pada variabel `y_pred`.

---

### Menghitung Accuracy

```python
print("Akurasi:", accuracy_score(y_test, y_pred))
```

Penjelasan:

Kode ini digunakan untuk menghitung tingkat accuracy model berdasarkan hasil prediksi dan data asli testing.

Rumus accuracy:

```math
Accuracy = \frac{Jumlah\ Prediksi\ Benar}{Total\ Data} \times 100\%
```

---

### Menampilkan Classification Report

```python
print(classification_report(y_test, y_pred))
```

Penjelasan:

Kode ini digunakan untuk menampilkan laporan hasil klasifikasi yang terdiri dari:

* precision
* recall
* f1-score
* support

Laporan ini digunakan untuk mengetahui performa model secara lebih detail.

---

### Menambahkan Hasil Prediksi

```python
test_df['prediction'] = y_pred
```

Penjelasan:

Kode ini digunakan untuk menambahkan kolom hasil prediksi ke dalam dataframe testing.

Kolom baru bernama:

```text
prediction
```

---

### Mengirim Output ke KNIME

```python
output_table_1 = test_df
```
Penjelasan:

Kode ini digunakan untuk mengirim hasil dataframe testing beserta hasil prediksi ke output node KNIME agar dapat digunakan pada node berikutnya seperti Scorer.

---
## score
### desicion tree
![alt text](image-27.png)
Penjelasan:<br>
Sebanyak 18 data Iris-setosa berhasil diprediksi dengan benar.<br>
Sebanyak 10 data Iris-versicolor berhasil diprediksi dengan benar.<br>
Sebanyak 15 data Iris-virginica berhasil diprediksi dengan benar.<br>
2 data Iris-virginica diprediksi sebagai Iris-versicolor.

### Random forest
![alt text](image-28.png)
Penjelasan:<br>
Sebanyak 18 data Iris-setosa berhasil diprediksi dengan benar.<br>
Sebanyak 10 data Iris-versicolor berhasil diprediksi dengan benar. <br>
Sebanyak 14 data Iris-virginica berhasil diprediksi dengan benar.<br>
2 data Iris-virginica diprediksi sebagai Iris-versicolor.<br>
1 data Iris-versicolor diprediksi sebagai Iris-virginica.<br>

## kesimpulan 
dari dua metode antara desicion tree dan random forest, pada dataset Iris metode Decision Tree justru memberikan hasil yang sedikit lebih tinggi dibandingkan dengan random forest

# Linear regresi

---

## 1. DATASET PROYEK

### A. Data Awal (Training Data)

Data di bawah ini adalah data historis yang digunakan untuk melatih model dan mencari garis tren regresi linear terbaik.

| No (Data Awal) | Variabel Independen (X) | Variabel Dependen (Y) |
|---|---|---|
| 1 | 2 | 2 |
| 2 | 4 | 3 |
| 3 | 3 | 5 |
| 4 | 3 | 4 |
| 5 | 3 | 3 |
| 6 | 4 | 5 |
| 7 | 5 | 6 |

### B. Data Prediksi (Test Data)

Data di bawah ini merupakan nilai X baru yang ingin dicari prediksi nilai Y-nya berdasarkan model yang terbentuk.

| Prediksi Ke- | Variabel Independen (X) | Variabel Dependen (Y) |
|---|---|---|
| 8 | 0 | *?* |
| 9 | 1 | *?* |

---

## 2. PERHITUNGAN SECARA ANALITIK (MATRIKS)

Perhitungan koefisien regresi menggunakan metode **Ordinary Least Squares (OLS)** dengan rumus berbasis manipulasi matriks:

$$
\hat{\beta} = (X^T X)^{-1} X^T Y
$$

Vektor koefisien $\hat{\beta}$ terdiri atas intersep ($\beta_0$) dan kemiringan/slope ($\beta_1$):

$$
\hat{\beta} =
\begin{bmatrix}
\beta_0 \\
\beta_1
\end{bmatrix}
$$

### Langkah 1: Menyusun Matriks X dan Vektor Y

Kolom pertama pada matriks $X$ diisi dengan angka 1 sebagai komponen pengali untuk intersep ($\beta_0$).

$$
X =
\begin{bmatrix}
1 & 2 \\
1 & 4 \\
1 & 3 \\
1 & 3 \\
1 & 3 \\
1 & 4 \\
1 & 5
\end{bmatrix},
\quad
Y =
\begin{bmatrix}
2 \\
3 \\
5 \\
4 \\
3 \\
5 \\
6
\end{bmatrix}
$$

### Langkah 2: Menghitung Transpose Matriks X ($X^T$)

$$
X^T =
\begin{bmatrix}
1 & 1 & 1 & 1 & 1 & 1 & 1 \\
2 & 4 & 3 & 3 & 3 & 4 & 5
\end{bmatrix}
$$

### Langkah 3: Menghitung Perkalian Matriks $X^T X$

$$
X^T X =
\begin{bmatrix}
1 & 1 & 1 & 1 & 1 & 1 & 1 \\
2 & 4 & 3 & 3 & 3 & 4 & 5
\end{bmatrix}
\begin{bmatrix}
1 & 2 \\
1 & 4 \\
1 & 3 \\
1 & 3 \\
1 & 3 \\
1 & 4 \\
1 & 5
\end{bmatrix}
=
\begin{bmatrix}
7 & 24 \\
24 & 88
\end{bmatrix}
$$

### Langkah 4: Menghitung Invers Matriks $(X^T X)^{-1}$

- **Determinan ($ad - bc$):**

$$
(7 \times 88) - (24 \times 24)
= 616 - 576
= 40
$$

$$
(X^T X)^{-1}
=
\frac{1}{40}
\begin{bmatrix}
88 & -24 \\
-24 & 7
\end{bmatrix}
=
\begin{bmatrix}
2.2 & -0.6 \\
-0.6 & 0.175
\end{bmatrix}
$$

### Langkah 5: Menghitung Perkalian Matriks $X^T Y$

$$
X^T Y =
\begin{bmatrix}
1 & 1 & 1 & 1 & 1 & 1 & 1 \\
2 & 4 & 3 & 3 & 3 & 4 & 5
\end{bmatrix}
\begin{bmatrix}
2 \\
3 \\
5 \\
4 \\
3 \\
5 \\
6
\end{bmatrix}
=
\begin{bmatrix}
28 \\
102
\end{bmatrix}
$$

### Langkah 6: Menghitung Nilai Koefisien Regresi ($\hat{\beta}$)

$$
\hat{\beta}
=
\begin{bmatrix}
2.2 & -0.6 \\
-0.6 & 0.175
\end{bmatrix}
\begin{bmatrix}
28 \\
102
\end{bmatrix}
$$

#### Menghitung Intersep ($\beta_0$)

$$
\beta_0
=
(2.2 \times 28) + (-0.6 \times 102)
$$

$$
= 61.6 - 61.2
$$

$$
= 0.4
$$

#### Menghitung Slope/Kemiringan ($\beta_1$)

$$
\beta_1
=
(-0.6 \times 28) + (0.175 \times 102)
$$

$$
= -16.8 + 17.85
$$

$$
= 1.05
$$

## 3. PANDUAN IMPLEMENTASI GAMBAR (GEOGEBRA)
![alt text](image-29.png)

---


## 4. PERHITUNGAN MENGGUNAKAN PROGRAM (PYTHON)

Berikut adalah kode pemrograman Python menggunakan pustaka `scikit-learn` untuk mengotomatisasi perhitungan koefisien regresi serta memprediksi data:

```python
import numpy as np
from sklearn.linear_model import LinearRegression

# 1. Menyiapkan Data Training (Awal)
X_train = np.array([[2], [4], [3], [3], [3], [4], [5]])
Y_train = np.array([2, 3, 5, 4, 3, 5, 6])

# 2. Inisialisasi dan Pelatihan Model Regresi Linear
model = LinearRegression()
model.fit(X_train, Y_train)

# 3. Mengambil Nilai Koefisien Hasil Program
intersep_b0 = model.intercept_
slope_b1 = model.coef_[0]

print("=== KOEFISIEN REGRESI (OUTPUT PROGRAM) ===")
print(f"Intersep (Beta 0) : {intersep_b0:.4f}")
print(f"Slope (Beta 1)    : {slope_b1:.4f}")
print(f"Persamaan Garis   : Y = {intersep_b0:.4f} + {slope_b1:.4f}X\n")

# 4. Prediksi Nilai Baru dari Tabel Prediksi
X_pred = np.array([[0], [1]])
Y_pred = model.predict(X_pred)

print("=== HASIL PREDIKSI DATA ===")
for i, x_val in enumerate(X_pred.flatten()):
    print(f"Data Prediksi ke-{i+8} (X = {x_val}) -> Hasil Nilai Y = {Y_pred[i]:.4f}")
```

---

didapatkan hasil prediksi nilai $Y$ sebagai berikut:

| No (Prediksi) | Input Nilai X | Operasi Rumus Model ($Y = 0.4 + 1.05X$) | Hasil Akhir Nilai Y |
|---|---|---|---|
| 8 | 0 | $0.4 + (1.05 \times 0)$ | **0.4000** |
| 9 | 1 | $0.4 + (1.05 \times 1)$ | **1.4500** |





## 5. KESIMPULAN

Berdasarkan hasil perhitungan regresi linear sederhana menggunakan metode analitik berbasis matriks *Ordinary Least Squares (OLS)* dan metode komputasi menggunakan bahasa pemrograman Python (`scikit-learn`), diperoleh hasil koefisien regresi yang sama, yaitu:

$$
\beta_0 = 0.4
$$

dan

$$
\beta_1 = 1.05
$$

Sehingga terbentuk persamaan regresi linear:

$$
Y = 0.4 + 1.05X
$$

Persamaan tersebut menunjukkan bahwa ketika nilai variabel independen ($X$) bernilai 0, maka model memprediksi nilai awal variabel dependen ($Y$) sebesar 0.4. Selain itu, setiap kenaikan 1 satuan pada variabel $X$ akan menyebabkan peningkatan nilai $Y$ sebesar 1.05 satuan.

Hasil prediksi menggunakan model regresi menunjukkan bahwa:

- Untuk $X = 0$, diperoleh prediksi $Y = 0.4$
- Untuk $X = 1$, diperoleh prediksi $Y = 1.45$

Visualisasi menggunakan GeoGebra juga membuktikan bahwa garis regresi yang terbentuk mampu merepresentasikan pola hubungan antar data dengan baik, serta titik hasil prediksi berada tepat pada lintasan garis regresi linear.

Dengan demikian, dapat disimpulkan bahwa metode regresi linear sederhana efektif digunakan untuk memodelkan hubungan antara variabel independen dan variabel dependen, baik melalui perhitungan manual berbasis matriks maupun melalui implementasi program Python.

# Peramalan kadar NO2 di daerah Pamekasan Madura
## 1. Pengumpulan Data
Kita install terlebih dahulu openoneo:
``` text
pip install openeo
```
Lalu tuliskan code dibawah:
``` text
import openeo
```
``` text
connection = openeo.connect("openeo.dataspace.copernicus.eu").authenticate_oidc()
```
``` python
aoi = {
    "type": "Polygon",
    "coordinates": [
        [
            [113.09, -6.89],
            [112.68, -6.89],
            [112.68, -7.20],
            [113.09, -7.20],
            [113.09, -6.89],
        ]
    ]
}

s5post = connection.load_collection(
    "SENTINEL_5P_L2",
    temporal_extent=["2023-10-01", "2025-10-01"],
    spatial_extent={
        "west": 112.68,
        "south": -7.20,
        "east": 113.09,
        "north": -6.89
    },
    bands=["NO2"],
)

# Now aggregate by day to avoid having multiple data per day
s5p_no2_daily = s5post.aggregate_temporal_period(reducer="mean", period="day")

# Now create a spatial aggregation to generate mean timeseries data
s5p_no2_aoi = s5p_no2_daily.aggregate_spatial(reducer="mean", geometries=aoi)
```
Code diatas memerlukan titik koordinasi area yang akan diambil data 
-nya, untuk mengambil titik koordinasi kaian kunjungi webiste https://geojson.io/?map=8.61/-7/113.43 . Didalam website tersebut kalian akan memilih daerah dengan cara memberi shape kotak didaerah yang ingin kalian ambil datanya.
![alt text](image-30.png)
Di panel sebelah kanan terdapat data JSON yang berupa koordinat daerah yang kalian pilih, kalian salin terus sesuaikan dengan code diatas di bagian variabel “aoi” dan spatial_extent.<br>
Lalu kalian tambahkan baris code dibawah untuk memulai pengambilan data:
``` python
job = s5post.execute_batch(title="NO2 in Pamekasan", outputfile="NO2Pamekasan.nc")
```
Tunggu proses pengambilan data, output proses seperti berikut:
``` text
0:00:00 Job 'j-2606030345014573816874721c7f0710': send 'start'
0:00:12 Job 'j-2606030345014573816874721c7f0710': queued (progress 0%)
0:00:17 Job 'j-2606030345014573816874721c7f0710': queued (progress 0%)
0:00:24 Job 'j-2606030345014573816874721c7f0710': queued (progress 0%)
0:00:32 Job 'j-2606030345014573816874721c7f0710': queued (progress 0%)
0:00:42 Job 'j-2606030345014573816874721c7f0710': queued (progress 0%)
0:00:54 Job 'j-2606030345014573816874721c7f0710': queued (progress 0%)
0:01:10 Job 'j-2606030345014573816874721c7f0710': running (progress N/A)
0:01:29 Job 'j-2606030345014573816874721c7f0710': running (progress N/A)
0:01:53 Job 'j-2606030345014573816874721c7f0710': running (progress N/A)
0:02:24 Job 'j-2606030345014573816874721c7f0710': finished (progress 100%)
```
Ketika proses pengambilan data, aktivitas kalian akan terekam di halaman https://editor.openeo.org/?server=https%3A%2F%2Fopeneo.dataspace.copernicus.eu%2Fopeneo%2F1.2 . Disitu terdapat nama dataset dan status pengambilan data.
![alt text](image-31.png)

## 2. Preproccessing Data
Setelah kita mengambil data, data bisa diunduh di halaman https://editor.openeo.org/?server=https%3A%2F%2Fopeneo.dataspace.copernicus.eu%2Fopeneo%2F1.2 . File akan berbentuk .nc. Kita cuman perlu kolom date dan NO2 menggunakan code dibawah:
``` python
import netCDF4

file_path = "openEO.nc"
ds = netCDF4.Dataset(file_path)

# Lihat seluruh variabel yang tersedia
print("📦 Variabel dalam file:")
print(ds.variables.keys())
# dict_keys(['t', 'x', 'y', 'crs', 'NO2'])

# Ambil NO2
no2 = ds.variables["NO2"][:]

# Ambil Time
time = ds.variables["t"][:]

# Konversi waktu ke format tanggal jika punya atribut 'units'
try:
    time_units = ds.variables["t"].units
    dates = netCDF4.num2date(time, units=time_units)
except Exception:
    dates = time  # fallback kalau tidak ada units

# Tampilkan struktur data NO2
print(type(no2))
# type <class 'numpy.ma.core.MaskedArray'>

print(len(no2))
# banyaknya data record NO2 725

print(len(no2[0]))
# panjang data perbaris 9

print(len(no2[0][0]))
# panjang perdata 8

print(no2[0][0][0])
# 3.7701793e-05
```
``` text
📦 Variabel dalam file:
dict_keys(['t', 'x', 'y', 'crs', 'NO2'])
<class 'numpy.ma.MaskedArray'>
61
9
5
--
```
Untuk melihat 10 data pertama adalah:
``` python
print("Contoh data pertama:")
for i in range(0, 10):
    print(no2[i])
```
``` text
Contoh data pertama:
[[-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- 9.61525415732467e-07 --]
 [-- 2.1458754417835735e-05 2.1458754417835735e-05 9.61525415732467e-07
  2.504570147721097e-05]
 [9.978138223232236e-06 2.1458754417835735e-05 1.4053041013539769e-05
  2.504570147721097e-05 -1.490594627284736e-06]
 [9.893085007206537e-06 1.4053041013539769e-05 1.4053041013539769e-05
  -1.490594627284736e-06 -1.490594627284736e-06]
 [9.893085007206537e-06 1.3830820535076782e-05 1.3830820535076782e-05
  -1.490594627284736e-06 7.528892183472635e-06]
 [1.2178630640846677e-05 1.3830820535076782e-05 1.5055943549668882e-05
  7.528892183472635e-06 7.528892183472635e-06]
 [2.115600000252016e-05 1.5055943549668882e-05 1.5055943549668882e-05
  7.246691438922426e-06 7.246691438922426e-06]]
[[-- 1.4124046174401883e-05 1.4124046174401883e-05 2.482243326085154e-05
  1.225495452672476e-05]
 [-- -- -- 2.9153743525967002e-05 1.204462387249805e-05]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- 9.588666216586716e-06]]
[[6.847168151580263e-06 2.2603488105232827e-05 1.372965743939858e-05 --
  --]
 [2.0322269847383723e-05 2.2603488105232827e-05 1.372965743939858e-05
  1.3469954865286127e-05 --]
 [-- -- -- 1.3469954865286127e-05 --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [9.062567869477789e-07 -- -- -- --]
 [1.4294840184447821e-05 1.1820839063148014e-05 2.168526862078579e-06
  2.168526862078579e-06 -6.095970547903562e-06]
 [1.4294840184447821e-05 1.1820839063148014e-05 8.895062819647137e-06
  1.3951847904536407e-05 1.2480927580327261e-05]
 [1.1549172086233739e-05 1.1549172086233739e-05 8.895062819647137e-06
  1.3951847904536407e-05 1.2480927580327261e-05]]
[[-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- -1.112526547331072e-06]
 [-- -- -- 1.9345276086824015e-05 -1.112526547331072e-06]
 [-- -- -- -- 1.5339172023232095e-05]
 [-- -- -- -- 4.047525180794764e-06]
 [-- -- 1.6738479189370992e-06 9.896171832224354e-06
  4.047525180794764e-06]]
[[2.8803173336200416e-05 -- 1.7342907085549086e-05 1.3539247447624803e-05
  --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- 3.062319819946424e-07 1.2125381545047276e-05 -- --]
 [-- -- 2.403447615506593e-05 2.063418094166991e-07
  3.5624730116978753e-06]
 [-- 4.8862380026548635e-06 2.403447615506593e-05 2.401791607553605e-05
  2.157118979084771e-05]
 [-- 2.7470101485960186e-05 1.9922199498978443e-05 2.401791607553605e-05
  2.157118979084771e-05]
 [-9.710182894195896e-06 2.7470101485960186e-05 2.2575102775590494e-05
  1.8144188288715668e-05 1.1031198482669424e-05]
 [2.937010140158236e-05 2.563972884672694e-05 2.2575102775590494e-05
  1.253730488315341e-06 1.65877668223402e-06]]
[[-- 1.4587973055313341e-05 3.7762252759421244e-05 -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]]
[[-- 1.5697201888542622e-05 1.5697201888542622e-05 --
  4.590063326759264e-06]
 [-- -- -- -- 7.966914381540846e-06]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]]
[[4.033688128401991e-06 1.7370048226439394e-05 1.3981777556182351e-05
  1.2897712622361723e-05 1.2897712622361723e-05]
 [1.3522299923351966e-05 1.7370048226439394e-05 1.3981777556182351e-05
  1.3981777556182351e-05 1.0595568710414227e-05]
 [-- -- -- -- 1.0595568710414227e-05]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]]
[[-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]]
[[-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]
 [-- -- -- -- --]]
```
### a. Mengatasi Missing Value menggunakan metode Interpolasi Linear
Sekarang kita akan mengatasi permasalahan missing value pada data NO2.
``` python
import numpy as np
import pandas as pd

# Interpolasi Linear
no2_filled = np.zeros_like(no2)
# Untuk jaga-jaga jika terdapat '--' tidak berubah menjadi 0
no2_filled = no2_filled.filled(0)

# loop tiap grid (y,x)
for i in range(no2.shape[1]):     # 9 baris
    for j in range(no2.shape[2]): # 8 kolom
        series = pd.Series(no2[:, i, j])
        no2_filled[:, i, j] = series.interpolate(method='linear', limit_direction='both').to_numpy()
```
Dengan code diatas, missing value yang terdapat pada data NO2 akan diisi secara otomatis menggunakan metode Interpolasi Linear.
### b. Rata-rata kan Data dan ubah Datetime
``` python
new_dates = []
new_no2 = []
for i in range(len(dates)):
    # ubah format datetime
    new_date = dates[i].strftime('%Y-%m-%d')
    new_dates.append(new_date)
    new_no2.append(np.mean(no2_filled[i]))
```
### Simpan data dalam bentuk CSV
Setelah itu kita akan membentuk data menjadi DataFrame Pandas untuk disimpan menjadi CSV.
``` python
df = pd.DataFrame({
    "date": dates,
    "NO2": new_no2
})

# Simpan ke CSV
df.to_csv("NO2_Pamekasan_timeseries.csv", index=False)
```
Untuk mengatasi missing value dan menyimpan data ke CSV sudah berhasil.
### d. Pengecekan Missing Value data harian pada CSV
Sekarang setelah data berbentuk CSV, kita cek apakah data Time Series harian lengkap. Cara men-cek apakah data Time Series Harian lengkap gunakan code dibawah:
``` python
import pandas as pd
import numpy as np

df = pd.read_csv("NO2_Pamekasan_timeseries.csv")

# Pastikan kolom 'date' bertipe datetime
df['date'] = pd.to_datetime(df['date'])

# Buat rentang tanggal lengkap
start_date = "2026-04-01"
end_date = "2026-06-01"
full_range = pd.date_range(start=start_date, end=end_date, freq='D')

# Cek tanggal yang hilang
missing_dates = full_range.difference(df['date'])

print(f"Jumlah hari missing: {len(missing_dates)}")
print("Daftar tanggal missing:")
print(missing_dates)
```
``` text
Jumlah hari missing: 1
Daftar tanggal missing:
DatetimeIndex(['2026-06-01'], dtype='datetime64[ns]', freq='D')
```
Dalam kasus saya ini, terdapat 1 hari missing value. Kita akan mengatasi lagi missing value menggunakan metode Interpolasi Linear. Cara memperbaikinya gunakan code dibawah:
``` python
import pandas as pd

# Pastikan datetime dan sorting
df['date'] = pd.to_datetime(df['date'])
df = df.sort_values('date')

# Buat rentang tanggal lengkap
full_range = pd.date_range(start="2026-04-01", end="2026-06-01", freq='D')

# Reindex agar tanggal yang hilang muncul sebagai NaN
df = df.set_index('date').reindex(full_range)
df.index.name = 'date'

# Interpolasi linear berdasarkan indeks waktu
df['NO2'] = df['NO2'].interpolate(method='time')

# (Opsional) jika masih ada NaN di bagian awal/akhir bisa gunakan forward/backward fill
df['NO2'] = df['NO2'].fillna(method='bfill').fillna(method='ffill')

# Simpan kembali ke CSV
df.to_csv("no2_timeseries_interpolated.csv")
```
### e. Deteksi Outlier IQR
Setelah kita mengisi missing value menggunakan metode Interpolasi Linear, selanjutnya kita akan mendeteksi Outlier menggunakan metode IQR.
``` python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

df = pd.read_csv("no2_timeseries_interpolated.csv")

df['date'] = pd.to_datetime(df['date'])

# Hitung IQR
Q1 = df['NO2'].quantile(0.25)
Q3 = df['NO2'].quantile(0.75)
IQR = Q3 - Q1

lower_bound = Q1 - 1.5 * IQR
upper_bound = Q3 + 1.5 * IQR

# Filter outlier
outliers_iqr = df[
    (df['NO2'] < lower_bound) |
    (df['NO2'] > upper_bound)
]

print("Jumlah Outlier (IQR):", len(outliers_iqr))
print(outliers_iqr[['date', 'NO2']].head())
```
``` text
Jumlah Outlier (IQR): 1
         date       NO2
18 2026-04-19  0.000024
```
Untuk men-visualisasi outlier:
``` python
# === Visualisasi ===
plt.figure(figsize=(15,5))
plt.plot(df['date'], df['NO2'], label="NO2", linewidth=1)

# Titik Outlier
plt.scatter(outliers_iqr['date'], outliers_iqr['NO2'],
            color='red', marker='o', label="Outliers")

# Garis batas atas & bawah
plt.axhline(upper_bound, color='orange', linestyle='dashed', label="Upper Bound (IQR)")
plt.axhline(lower_bound, color='blue', linestyle='dashed', label="Lower Bound (IQR)")

plt.title("Deteksi Outlier Data NO2 (Metode IQR)")
plt.xlabel("Tanggal")
plt.ylabel("Kadar NO2")
plt.legend()
plt.tight_layout()
plt.xticks(
    ticks=[df['date'].iloc[0], df['date'].iloc[-1]],
    labels=[df['date'].iloc[0].strftime('%Y-%m-%d'),
            df['date'].iloc[-1].strftime('%Y-%m-%d')]
)
plt.show()
```
![alt text](image-32.png)
Setelah itu, kita akan menghapus data outlier. Karena data ini merupakan data Time Series, maka data outlier yang dihapus akan diisi kembali menggunakan Interpolasi Linear.
``` python
# Tandai outlier menjadi NaN
df['NO2_cleaned'] = df['NO2'].mask((df['NO2'] < lower_bound) | (df['NO2'] > upper_bound))

print("Jumlah nilai yang dinyatakan sebagai outlier:", df['NO2_cleaned'].isna().sum())

# Interpolasi linear untuk mengisi kembali nilai outlier
df['NO2_filled'] = df['NO2_cleaned'].interpolate(method='linear')

# Jika masih tersisa NaN di ujung data, isi dengan forward/backward fill
df['NO2_filled'] = df['NO2_filled'].bfill().ffill()
# df['NO2_filled'] = df['NO2_filled'].fillna(method='bfill').fillna(method='ffill')

print("Jumlah missing setelah interpolasi:", df['NO2_filled'].isna().sum())
```
``` text
Jumlah nilai yang dinyatakan sebagai outlier: 1
Jumlah missing setelah interpolasi: 0
```
Visualisasi data setelah menghapus Outlier dan mengisi kembali menggunakan Interpolasi Linear:
``` python
plt.figure(figsize=(15,5))
# Plot data hasil interpolasi
plt.plot(df['date'], df['NO2_filled'], label="NO2 (Interpolated)", linewidth=1)
# Tampilkan hanya tanggal awal dan akhir di sumbu X
plt.xticks(
    ticks=[df['date'].iloc[0], df['date'].iloc[-1]],
    labels=[df['date'].iloc[0].strftime('%Y-%m-%d'),
            df['date'].iloc[-1].strftime('%Y-%m-%d')]
)
plt.title("Plot Data NO2 Setelah Outlier Removal & Interpolasi")
plt.xlabel("Tanggal")
plt.ylabel("Kadar NO2")
plt.legend()
plt.tight_layout()
plt.show()
```
![alt text](image-33.png)
## 3. Modeling menggunakan KNN Regression
Dengan data Time Series kadar NO2 harian di daerah Pamekasan, kita akan memprediksi kadar NO2 satu hari yang akan datang. Sekarang kita akan ubah data, mencoba mencari korelasi antara 1 hari dengan 4 hari sebelumnya. Kita juga akan membandingkan apakah semakin banyak hari sebelumnya, model akan lebih bagus?
### a. Uji Korelasi Data
``` python
import pandas as pd

def create_supervised(data, n_lag=4):
    df_supervised = pd.DataFrame()
    
    # Membuat fitur t-4 sampai t-1
    for i in range(n_lag, 0, -1):
        df_supervised[f'NO2(t-{i})'] = data.shift(i)
    
    # Label hari H
    df_supervised['NO2(t)'] = data
    
    # Hapus baris yang masih mengandung NaN akibat shift
    df_supervised.dropna(inplace=True)
    
    return df_supervised

# contoh penggunaan
supervised_df30 = create_supervised(df['NO2_scaled'], n_lag=30)

# Ambil semua lag dan kolom target
lag_cols = supervised_df30.drop(columns="NO2(t)").columns
correlations = supervised_df30[lag_cols].corrwith(supervised_df30['NO2(t)'])

# Tampilkan nilai korelasi
print(correlations)
```
``` text
NO2(t-30)   -0.049386
NO2(t-29)   -0.068898
NO2(t-28)   -0.014762
NO2(t-27)   -0.019433
NO2(t-26)   -0.074270
NO2(t-25)   -0.246123
NO2(t-24)   -0.337322
NO2(t-23)   -0.306557
NO2(t-22)   -0.276465
NO2(t-21)   -0.218725
NO2(t-20)   -0.122040
NO2(t-19)    0.065908
NO2(t-18)    0.197832
NO2(t-17)    0.202368
NO2(t-16)    0.037755
NO2(t-15)   -0.037251
NO2(t-14)   -0.117059
NO2(t-13)   -0.208986
NO2(t-12)   -0.216090
NO2(t-11)    0.025698
NO2(t-10)    0.263926
NO2(t-9)     0.500742
NO2(t-8)     0.536009
NO2(t-7)     0.362440
NO2(t-6)     0.249679
NO2(t-5)     0.319660
NO2(t-4)     0.438739
NO2(t-3)     0.504871
NO2(t-2)     0.519151
NO2(t-1)     0.752811
dtype: float64
```
karena kita menggunakan model KNN Regression, maka perlu normalisasi data menggunakan min-max Scaler.
``` python
from sklearn.preprocessing import MinMaxScaler
import pandas as pd

scaler = MinMaxScaler()

df['NO2_scaled'] = scaler.fit_transform(df[['NO2']])
print(df[['date', 'NO2', 'NO2_scaled']].head())
print("\nInformasi DataFrame:")
df[['date', 'NO2', 'NO2_scaled']].info()
```
Maka data akan di-normalisasi 0-1.
``` text
        date       NO2  NO2_scaled
0 2026-04-01  0.000013    0.184350
1 2026-04-02  0.000012    0.163671
2 2026-04-03  0.000012    0.121694
3 2026-04-04  0.000013    0.187165
4 2026-04-05  0.000015    0.341060

Informasi DataFrame:
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 62 entries, 0 to 61
Data columns (total 3 columns):
 #   Column      Non-Null Count  Dtype         
---  ------      --------------  -----         
 0   date        62 non-null     datetime64[ns]
 1   NO2         62 non-null     float64       
 2   NO2_scaled  62 non-null     float64       
dtypes: datetime64[ns](1), float64(2)
memory usage: 1.6 KB
```

### c. Mengubah Data
Untuk membuat data 4 hari sebelum tinggal tambah code dibawah (ubah parameter n_lag).
``` python
supervised_df = create_supervised(df['NO2_scaled'], n_lag=4)

print(supervised_df)
print(supervised_df.shape)
```
``` text
    NO2(t-4)  NO2(t-3)  NO2(t-2)  NO2(t-1)    NO2(t)
4   0.184350  0.163671  0.121694  0.187165  0.341060
5   0.163671  0.121694  0.187165  0.341060  0.358497
6   0.121694  0.187165  0.341060  0.358497  0.313287
7   0.187165  0.341060  0.358497  0.313287  0.323432
8   0.341060  0.358497  0.313287  0.323432  0.335887
9   0.358497  0.313287  0.323432  0.335887  0.348342
10  0.313287  0.323432  0.335887  0.348342  0.360798
11  0.323432  0.335887  0.348342  0.360798  0.143673
12  0.335887  0.348342  0.360798  0.143673  0.050449
13  0.348342  0.360798  0.143673  0.050449  0.000000
14  0.360798  0.143673  0.050449  0.000000  0.465076
15  0.143673  0.050449  0.000000  0.465076  0.498610
16  0.050449  0.000000  0.465076  0.498610  0.187134
17  0.000000  0.465076  0.498610  0.187134  0.317976
18  0.465076  0.498610  0.187134  0.317976  1.000000
19  0.498610  0.187134  0.317976  1.000000  0.793888
20  0.187134  0.317976  1.000000  0.793888  0.545215
21  0.317976  1.000000  0.793888  0.545215  0.241553
22  1.000000  0.793888  0.545215  0.241553  0.173841
23  0.793888  0.545215  0.241553  0.173841  0.205572
24  0.545215  0.241553  0.173841  0.205572  0.283645
25  0.241553  0.173841  0.205572  0.283645  0.323617
26  0.173841  0.205572  0.283645  0.323617  0.261732
27  0.205572  0.283645  0.323617  0.261732  0.199846
28  0.283645  0.323617  0.261732  0.199846  0.179595
29  0.323617  0.261732  0.199846  0.179595  0.159343
30  0.261732  0.199846  0.179595  0.159343  0.139092
31  0.199846  0.179595  0.159343  0.139092  0.163308
32  0.179595  0.159343  0.139092  0.163308  0.268493
33  0.159343  0.139092  0.163308  0.268493  0.389750
34  0.139092  0.163308  0.268493  0.389750  0.268283
35  0.163308  0.268493  0.389750  0.268283  0.404211
36  0.268493  0.389750  0.268283  0.404211  0.489569
37  0.389750  0.268283  0.404211  0.489569  0.346207
38  0.268283  0.404211  0.489569  0.346207  0.251871
39  0.404211  0.489569  0.346207  0.251871  0.157535
40  0.489569  0.346207  0.251871  0.157535  0.237304
41  0.346207  0.251871  0.157535  0.237304  0.420818
42  0.251871  0.157535  0.237304  0.420818  0.244595
43  0.157535  0.237304  0.420818  0.244595  0.265462
44  0.237304  0.420818  0.244595  0.265462  0.408936
45  0.420818  0.244595  0.265462  0.408936  0.332046
46  0.244595  0.265462  0.408936  0.332046  0.423722
47  0.265462  0.408936  0.332046  0.423722  0.312309
48  0.408936  0.332046  0.423722  0.312309  0.367612
49  0.332046  0.423722  0.312309  0.367612  0.422915
50  0.423722  0.312309  0.367612  0.422915  0.478217
51  0.312309  0.367612  0.422915  0.478217  0.533520
52  0.367612  0.422915  0.478217  0.533520  0.739695
53  0.422915  0.478217  0.533520  0.739695  0.812732
54  0.478217  0.533520  0.739695  0.812732  0.697480
55  0.533520  0.739695  0.812732  0.697480  0.582227
56  0.739695  0.812732  0.697480  0.582227  0.548920
57  0.812732  0.697480  0.582227  0.548920  0.569837
58  0.697480  0.582227  0.548920  0.569837  0.330779
59  0.582227  0.548920  0.569837  0.330779  0.339725
60  0.548920  0.569837  0.330779  0.339725  0.684697
61  0.569837  0.330779  0.339725  0.684697  0.684697
(58, 5)
```
Untuk membuat data 10 hari sebelum tinggal tambah code dibawah (ubah parameter n_lag).
``` python
supervised_df10 = create_supervised(df['NO2_scaled'], n_lag=10)

print(supervised_df10)
print(supervised_df10.shape)
```
``` text
    NO2(t-10)  NO2(t-9)  NO2(t-8)  NO2(t-7)  NO2(t-6)  NO2(t-5)  NO2(t-4)  \
10   0.184350  0.163671  0.121694  0.187165  0.341060  0.358497  0.313287   
11   0.163671  0.121694  0.187165  0.341060  0.358497  0.313287  0.323432   
12   0.121694  0.187165  0.341060  0.358497  0.313287  0.323432  0.335887   
13   0.187165  0.341060  0.358497  0.313287  0.323432  0.335887  0.348342   
14   0.341060  0.358497  0.313287  0.323432  0.335887  0.348342  0.360798   
15   0.358497  0.313287  0.323432  0.335887  0.348342  0.360798  0.143673   
16   0.313287  0.323432  0.335887  0.348342  0.360798  0.143673  0.050449   
17   0.323432  0.335887  0.348342  0.360798  0.143673  0.050449  0.000000   
18   0.335887  0.348342  0.360798  0.143673  0.050449  0.000000  0.465076   
19   0.348342  0.360798  0.143673  0.050449  0.000000  0.465076  0.498610   
20   0.360798  0.143673  0.050449  0.000000  0.465076  0.498610  0.187134   
21   0.143673  0.050449  0.000000  0.465076  0.498610  0.187134  0.317976   
22   0.050449  0.000000  0.465076  0.498610  0.187134  0.317976  1.000000   
23   0.000000  0.465076  0.498610  0.187134  0.317976  1.000000  0.793888   
24   0.465076  0.498610  0.187134  0.317976  1.000000  0.793888  0.545215   
25   0.498610  0.187134  0.317976  1.000000  0.793888  0.545215  0.241553   
26   0.187134  0.317976  1.000000  0.793888  0.545215  0.241553  0.173841   
27   0.317976  1.000000  0.793888  0.545215  0.241553  0.173841  0.205572   
28   1.000000  0.793888  0.545215  0.241553  0.173841  0.205572  0.283645   
29   0.793888  0.545215  0.241553  0.173841  0.205572  0.283645  0.323617   
30   0.545215  0.241553  0.173841  0.205572  0.283645  0.323617  0.261732   
31   0.241553  0.173841  0.205572  0.283645  0.323617  0.261732  0.199846   
32   0.173841  0.205572  0.283645  0.323617  0.261732  0.199846  0.179595   
33   0.205572  0.283645  0.323617  0.261732  0.199846  0.179595  0.159343   
34   0.283645  0.323617  0.261732  0.199846  0.179595  0.159343  0.139092   
35   0.323617  0.261732  0.199846  0.179595  0.159343  0.139092  0.163308   
36   0.261732  0.199846  0.179595  0.159343  0.139092  0.163308  0.268493   
37   0.199846  0.179595  0.159343  0.139092  0.163308  0.268493  0.389750   
38   0.179595  0.159343  0.139092  0.163308  0.268493  0.389750  0.268283   
39   0.159343  0.139092  0.163308  0.268493  0.389750  0.268283  0.404211   
40   0.139092  0.163308  0.268493  0.389750  0.268283  0.404211  0.489569   
41   0.163308  0.268493  0.389750  0.268283  0.404211  0.489569  0.346207   
42   0.268493  0.389750  0.268283  0.404211  0.489569  0.346207  0.251871   
43   0.389750  0.268283  0.404211  0.489569  0.346207  0.251871  0.157535   
44   0.268283  0.404211  0.489569  0.346207  0.251871  0.157535  0.237304   
45   0.404211  0.489569  0.346207  0.251871  0.157535  0.237304  0.420818   
46   0.489569  0.346207  0.251871  0.157535  0.237304  0.420818  0.244595   
47   0.346207  0.251871  0.157535  0.237304  0.420818  0.244595  0.265462   
48   0.251871  0.157535  0.237304  0.420818  0.244595  0.265462  0.408936   
49   0.157535  0.237304  0.420818  0.244595  0.265462  0.408936  0.332046   
50   0.237304  0.420818  0.244595  0.265462  0.408936  0.332046  0.423722   
51   0.420818  0.244595  0.265462  0.408936  0.332046  0.423722  0.312309   
52   0.244595  0.265462  0.408936  0.332046  0.423722  0.312309  0.367612   
53   0.265462  0.408936  0.332046  0.423722  0.312309  0.367612  0.422915   
54   0.408936  0.332046  0.423722  0.312309  0.367612  0.422915  0.478217   
55   0.332046  0.423722  0.312309  0.367612  0.422915  0.478217  0.533520   
56   0.423722  0.312309  0.367612  0.422915  0.478217  0.533520  0.739695   
57   0.312309  0.367612  0.422915  0.478217  0.533520  0.739695  0.812732   
58   0.367612  0.422915  0.478217  0.533520  0.739695  0.812732  0.697480   
59   0.422915  0.478217  0.533520  0.739695  0.812732  0.697480  0.582227   
60   0.478217  0.533520  0.739695  0.812732  0.697480  0.582227  0.548920   
61   0.533520  0.739695  0.812732  0.697480  0.582227  0.548920  0.569837   

    NO2(t-3)  NO2(t-2)  NO2(t-1)    NO2(t)  
10  0.323432  0.335887  0.348342  0.360798  
11  0.335887  0.348342  0.360798  0.143673  
12  0.348342  0.360798  0.143673  0.050449  
13  0.360798  0.143673  0.050449  0.000000  
14  0.143673  0.050449  0.000000  0.465076  
15  0.050449  0.000000  0.465076  0.498610  
16  0.000000  0.465076  0.498610  0.187134  
17  0.465076  0.498610  0.187134  0.317976  
18  0.498610  0.187134  0.317976  1.000000  
19  0.187134  0.317976  1.000000  0.793888  
20  0.317976  1.000000  0.793888  0.545215  
21  1.000000  0.793888  0.545215  0.241553  
22  0.793888  0.545215  0.241553  0.173841  
23  0.545215  0.241553  0.173841  0.205572  
24  0.241553  0.173841  0.205572  0.283645  
25  0.173841  0.205572  0.283645  0.323617  
26  0.205572  0.283645  0.323617  0.261732  
27  0.283645  0.323617  0.261732  0.199846  
28  0.323617  0.261732  0.199846  0.179595  
29  0.261732  0.199846  0.179595  0.159343  
30  0.199846  0.179595  0.159343  0.139092  
31  0.179595  0.159343  0.139092  0.163308  
32  0.159343  0.139092  0.163308  0.268493  
33  0.139092  0.163308  0.268493  0.389750  
34  0.163308  0.268493  0.389750  0.268283  
35  0.268493  0.389750  0.268283  0.404211  
36  0.389750  0.268283  0.404211  0.489569  
37  0.268283  0.404211  0.489569  0.346207  
38  0.404211  0.489569  0.346207  0.251871  
39  0.489569  0.346207  0.251871  0.157535  
40  0.346207  0.251871  0.157535  0.237304  
41  0.251871  0.157535  0.237304  0.420818  
42  0.157535  0.237304  0.420818  0.244595  
43  0.237304  0.420818  0.244595  0.265462  
44  0.420818  0.244595  0.265462  0.408936  
45  0.244595  0.265462  0.408936  0.332046  
46  0.265462  0.408936  0.332046  0.423722  
47  0.408936  0.332046  0.423722  0.312309  
48  0.332046  0.423722  0.312309  0.367612  
49  0.423722  0.312309  0.367612  0.422915  
50  0.312309  0.367612  0.422915  0.478217  
51  0.367612  0.422915  0.478217  0.533520  
52  0.422915  0.478217  0.533520  0.739695  
53  0.478217  0.533520  0.739695  0.812732  
54  0.533520  0.739695  0.812732  0.697480  
55  0.739695  0.812732  0.697480  0.582227  
56  0.812732  0.697480  0.582227  0.548920  
57  0.697480  0.582227  0.548920  0.569837  
58  0.582227  0.548920  0.569837  0.330779  
59  0.548920  0.569837  0.330779  0.339725  
60  0.569837  0.330779  0.339725  0.684697  
61  0.330779  0.339725  0.684697  0.684697  
(52, 11)
```
### d. Modeling dan Evaluation
Sekarang dari 2 data yang sudah kita rubah, kita train menggunakan model KNN Regression.
``` python
from sklearn.neighbors import KNeighborsRegressor
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_squared_error, r2_score
import numpy as np

def MAPE(y_true, y_pred):
    y_true, y_pred = np.array(y_true), np.array(y_pred)
    # Hindari pembagian dengan nol
    nonzero = y_true != 0
    return np.mean(np.abs((y_true[nonzero] - y_pred[nonzero]) / y_true[nonzero])) * 100

def train_knn(df_supervised, model_name=""):
    # Pisahkan fitur & label
    X = df_supervised.drop(columns=['NO2(t)']).values
    y = df_supervised['NO2(t)'].values

    # Split data 80/20
    X_train, X_test, y_train, y_test = train_test_split(
        X, y, test_size=0.2, shuffle=False
    )

    # Model KNN
    knn = KNeighborsRegressor(n_neighbors=5)
    knn.fit(X_train, y_train)

    # Prediksi
    y_pred = knn.predict(X_test)

    # Evaluasi
    mse = mean_squared_error(y_test, y_pred)
    rmse = np.sqrt(mse)
    r2 = r2_score(y_test, y_pred)
    mape = MAPE(y_test, y_pred)

    print(f"\n=== {model_name} ===")
    print(f"Train Size: {len(X_train)} — Test Size: {len(X_test)}")
    print(f"RMSE: {rmse:.6f}")
    print(f"R² Score: {r2:.4f}")
    print(f"MAPE: {mape:.4f}%")

    return knn, y_test, y_pred


# Train model untuk 4 hari sebelumnya
knn_4, y_test_4, y_pred_4 = train_knn(supervised_df, "KNN - 4 Hari Sebelumnya")

# Train model untuk 10 hari sebelumnya
knn_10, y_test_10, y_pred_10 = train_knn(supervised_df10, "KNN - 10 Hari Sebelumnya")
knn_30, y_test_30, y_pred_30 = train_knn(supervised_df30, "KNN - 30 Hari Sebelumnya")
```
``` text

=== KNN - 4 Hari Sebelumnya ===
Train Size: 46 — Test Size: 12
RMSE: 0.266233
R² Score: -2.4203
MAPE: 39.1901%

=== KNN - 10 Hari Sebelumnya ===
Train Size: 41 — Test Size: 11
RMSE: 0.289850
R² Score: -2.9063
MAPE: 38.6996%

=== KNN - 30 Hari Sebelumnya ===
Train Size: 25 — Test Size: 7
RMSE: 0.179532
R² Score: -0.7587
MAPE: 34.8624%
```
### e. Plotting
Plotting untuk visualisasi grafik antara label dan prediksi dari kedua data diatas.<br>
4 hari sebelum:
```python
import matplotlib.pyplot as plt
import numpy as np

plt.figure()
plt.plot(np.arange(len(y_test_4)), y_test_4, label="Actual")
plt.plot(np.arange(len(y_pred_4)), y_pred_4, label="Predicted")
plt.title("KNN Regression - 4 Hari Sebelumnya")
plt.xlabel("Sample Index")
plt.ylabel("NO2 Value")
plt.legend()
plt.show()
```
![alt text](image-34.png)
10 hari sebelum:
``` python
plt.figure()
plt.plot(np.arange(len(y_test_10)), y_test_10, label="Actual")
plt.plot(np.arange(len(y_pred_10)), y_pred_10, label="Predicted")
plt.title("KNN Regression - 10 Hari Sebelumnya")
plt.xlabel("Sample Index")
plt.ylabel("NO2 Value")
plt.legend()
plt.show()
```
![alt text](image-35.png)
30 hari sebelum:
``` python
plt.figure()
plt.plot(np.arange(len(y_test_30)), y_test_30, label="Actual")
plt.plot(np.arange(len(y_pred_30)), y_pred_30, label="Predicted")
plt.title("KNN Regression - 30 Hari Sebelumnya")
plt.xlabel("Sample Index")
plt.ylabel("NO2 Value")
plt.legend()
plt.show()
```
![alt text](image-36.png)
Berdasarkan hasil visualisasi KNN Regression dengan variasi lag 4, 10, dan 30 hari sebelumnya, terlihat bahwa model belum mampu mengikuti pola perubahan data NO₂ secara optimal. Pada model dengan 4 hari sebelumnya, kurva prediksi sudah mulai mengikuti arah tren data aktual, meskipun masih terdapat selisih yang cukup besar pada beberapa titik pengamatan. Hal ini menunjukkan bahwa informasi dari 4 hari sebelumnya masih memiliki hubungan yang cukup kuat dengan nilai NO₂ pada hari berikutnya sehingga model mampu menangkap sebagian pola data.

Pada model dengan 10 hari sebelumnya, performa prediksi cenderung menurun. Kurva prediksi terlihat lebih datar dan tidak mampu mengikuti fluktuasi nilai aktual secara baik, terutama ketika terjadi kenaikan atau penurunan yang cukup tajam. Penambahan jumlah lag menyebabkan model kesulitan menemukan tetangga terdekat yang benar-benar merepresentasikan kondisi data sehingga akurasi prediksi menjadi lebih rendah dibandingkan model lag 4.

Sementara itu, pada model dengan 30 hari sebelumnya, performa model mengalami penurunan yang paling signifikan. Kurva prediksi hampir membentuk garis yang relatif konstan dan tidak mampu menangkap variasi data aktual. Kondisi ini menunjukkan bahwa penggunaan terlalu banyak fitur historis menyebabkan informasi yang relevan menjadi tertutupi oleh fitur-fitur yang kurang berpengaruh. Akibatnya, model KNN cenderung menghasilkan prediksi yang mendekati nilai rata-rata data dan kehilangan kemampuan untuk mengikuti pola perubahan aktual.

Secara keseluruhan, hasil pengujian menunjukkan bahwa model KNN lebih efektif ketika menggunakan jumlah lag yang lebih sedikit, yaitu 4 hari sebelumnya. Penambahan lag menjadi 10 dan 30 hari tidak meningkatkan performa model, bahkan menyebabkan prediksi semakin jauh dari nilai aktual. Hal ini mengindikasikan bahwa hubungan temporal pada data NO₂ lebih banyak dipengaruhi oleh kondisi beberapa hari terakhir dibandingkan oleh data historis yang terlalu panjang. Oleh karena itu, untuk kasus prediksi NO₂ pada penelitian ini, penggunaan lag yang lebih pendek lebih sesuai dibandingkan lag yang panjang. Selain itu, diperlukan eksplorasi model lain seperti Random Forest, XGBoost, LSTM, atau GRU serta optimasi parameter KNN dan proses preprocessing agar diperoleh hasil prediksi yang lebih akurat dan mampu mengikuti pola data secara lebih baik.

# Penjelasan peramal: Pentingnya fitur, Nilai SHAP, dan Plot Ketergantungan Parsial serta menjawab pertanyaannya
Penjelasan pembelajaran mesin, juga dikenal sebagai interpretabilitas, mengacu pada kemampuan untuk memahami, menafsirkan, dan menjelaskan keputusan atau prediksi yang dibuat oleh model pembelajaran mesin dengan cara yang dapat dimengerti manusia. Ini bertujuan untuk menjelaskan bagaimana model sampai pada hasil atau keputusan tertentu.

Karena sifat kompleks dari banyak model pembelajaran mesin modern, seperti metode ansambel, mereka sering berfungsi sebagai kotak hitam, sehingga sulit untuk memahami mengapa prediksi tertentu dibuat. Teknik penjelasan bertujuan untuk mengungkap model-model ini, memberikan wawasan tentang cara kerja batin mereka dan membantu membangun kepercayaan, meningkatkan transparansi, dan memenuhi persyaratan peraturan di berbagai domain. Meningkatkan penjelasan model tidak hanya membantu dalam memahami perilaku model tetapi juga membantu mendeteksi bias, meningkatkan kinerja model, dan memungkinkan pemangku kepentingan membuat keputusan yang lebih tepat berdasarkan wawasan pembelajaran mesin.

skforecast kompatibel dengan beberapa metode interpretabilitas yang paling banyak digunakan: Nilai Shap, kepentingan Permutasi, Plot Dependensi Parsial, dan metode khusus Model.
## Perpustakaan dan data
``` python
# Libraries
# ==============================================================================
import pandas as pd
import matplotlib.pyplot as plt
import shap
from sklearn.inspection import permutation_importance
from sklearn.inspection import PartialDependenceDisplay
from lightgbm import LGBMRegressor
from skforecast.datasets import fetch_dataset
from skforecast.recursive import ForecasterRecursive
```
Data yang digunakan dalam contoh ini telah diperoleh dari paket R tsibbledata. Himpunan data berisi 5 kolom dan 52.608 catatan lengkap. Informasi di setiap kolom adalah:<br>

Waktu: tanggal dan waktu catatan.<br>
Tanggal: tanggal catatan.<br>
Permintaan: permintaan listrik (MW).<br>
Suhu: suhu di Melbourne, ibu kota Victoria.<br>
Hari libur: menunjukkan apakah hari tersebut adalah hari libur nasional.<br>
``` python
# Download data
# ==============================================================================
data = fetch_dataset(name="vic_electricity")
data.head(3)
```
``` text
╭──────────────────────────── vic_electricity ─────────────────────────────╮
│ Description:                                                             │
│ Half-hourly electricity demand for Victoria, Australia                   │
│                                                                          │
│ Source:                                                                  │
│ O'Hara-Wild M, Hyndman R, Wang E, Godahewa R (2022).tsibbledata: Diverse │
│ Datasets for 'tsibble'. https://tsibbledata.tidyverts.org/,              │
│ https://github.com/tidyverts/tsibbledata/.                               │
│ https://tsibbledata.tidyverts.org/reference/vic_elec.html                │
│                                                                          │
│ URL:                                                                     │
│ https://raw.githubusercontent.com/skforecast/skforecast-                 │
│ datasets/main/data/vic_electricity.csv                                   │
│                                                                          │
│ Shape: 52608 rows x 4 columns                                            │
╰──────────────────────────────────────────────────────────────────────────╯
Demand	Temperature	Date	Holiday
Time				
2011-12-31 13:00:00	4382.825174	21.40	2012-01-01	True
2011-12-31 13:30:00	4263.365526	21.05	2012-01-01	True
2011-12-31 14:00:00	4048.966046	20.70	2012-01-01	True

```
``` python
# Aggregation to daily frequency
# ==============================================================================
data = data.resample('D').agg({'Demand': 'sum', 'Temperature': 'mean'})
data.head(3)
```

|Time|Demand|Temperature|
|---|---|---|
|2011-12-31 00:00:00|82531\.745918|21\.047727272727272|
|2012-01-01 00:00:00|227778\.257304|26\.578125|
|2012-01-02 00:00:00|275490\.988882|31\.751041666666666|

``` python
# Split train-test
# ==============================================================================
data_train = data.loc[: '2014-12-21']
data_test = data.loc['2014-12-22':]
```
## Membuat dan melatih peramal
Model peramalan dibuat untuk memprediksi permintaan energi menggunakan 7 nilai terakhir (minggu lalu) dan suhu sebagai variabel eksogen.
``` python
# Create a recursive multi-step forecaster (ForecasterRecursive)
# ==============================================================================
forecaster = ForecasterRecursive(
    estimator=LGBMRegressor(random_state=123, verbose=-1),
    lags=7
)

forecaster.fit(
    y    = data_train['Demand'],
    exog = data_train['Temperature']
)
forecaster
```
<a href="gambar1.ipynb - Colab.html">Buka Hasil Notebook</a>