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
<p>gambar di atas merupakan hasil dari menghitung jarak pada data iris dimana prosesnya sama dengan yang tadi </p>
<img src="_static/image-9.png"/>
<p>gambar di atas merupakan visualiasi pengukuran jarak pada orange, tetapi sementara saya menggunakan widget csv file impor untuk mengimpor data iris bukan menggunakan sql table karena widget tersebut masih ada erornya atau tidak bisa di pakai dan belum menemukan solusinya</p>

## menyelesaikan Missing values dengan WKNN (manual)  dan code menghitung WKNN
<h3>Tabel Data Asli untuk mencari missing values</h3>
<table border="1">
  <thead>
    <tr>
      <th>No</th>
      <th>Nama</th>
      <th>IPK</th>
      <th>Penghasilan_OT</th>
      <th>Nilai_Tugas</th>
      <th></th>
      <th>No</th>
      <th>Nama</th>
      <th>IPK'</th>
      <th>Penghasilan'</th>
      <th>Nilai_Tugas</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>Andi</td>
      <td>3.50</td>
      <td>5000</td>
      <td>80</td>
      <td></td>
      <td>1</td>
      <td>Andi</td>
      <td>0.7586</td>
      <td>0.5385</td>
      <td>80</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Budi</td>
      <td>2.75</td>
      <td>2000</td>
      <td>65</td>
      <td></td>
      <td>2</td>
      <td>Budi</td>
      <td>0.2414</td>
      <td>0.0769</td>
      <td>65</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Citra</td>
      <td>3.85</td>
      <td>8000</td>
      <td>92</td>
      <td></td>
      <td>3</td>
      <td>Citra</td>
      <td>1.0000</td>
      <td>1.0000</td>
      <td>92</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Deni</td>
      <td>2.40</td>
      <td>1500</td>
      <td>55</td>
      <td></td>
      <td>4</td>
      <td>Deni</td>
      <td>0.0000</td>
      <td>0.0000</td>
      <td>55</td>
    </tr>
    <tr>
      <td>5</td>
      <td>Eva</td>
      <td>3.10</td>
      <td>3500</td>
      <td>75</td>
      <td></td>
      <td>5</td>
      <td>Eva</td>
      <td>0.4828</td>
      <td>0.3077</td>
      <td>75</td>
    </tr>
    <tr>
      <td>6</td>
      <td>Fajar</td>
      <td>3.60</td>
      <td>6000</td>
      <td>85</td>
      <td></td>
      <td>6</td>
      <td>Fajar</td>
      <td>0.8276</td>
      <td>0.6923</td>
      <td>85</td>
    </tr>
    <tr>
      <td>7</td>
      <td>Gina</td>
      <td>2.90</td>
      <td>2500</td>
      <td>?</td>
      <td></td>
      <td>7</td>
      <td>Gina</td>
      <td>0.3448</td>
      <td>0.1538</td>
      <td>?</td>
    </tr>
    <tr>
      <td>8</td>
      <td>Hadi</td>
      <td>3.20</td>
      <td>4000</td>
      <td>78</td>
      <td></td>
      <td>8</td>
      <td>Hadi</td>
      <td>0.5517</td>
      <td>0.3846</td>
      <td>78</td>
    </tr>
    <tr>
      <td>9</td>
      <td>Indah</td>
      <td>3.75</td>
      <td>7500</td>
      <td>88</td>
      <td></td>
      <td>9</td>
      <td>Indah</td>
      <td>0.9310</td>
      <td>0.9231</td>
      <td>88</td>
    </tr>
    <tr>
      <td>10</td>
      <td>Joko</td>
      <td>2.55</td>
      <td>1800</td>
      <td>60</td>
      <td></td>
      <td>10</td>
      <td>Joko</td>
      <td>0.1034</td>
      <td>0.0462</td>
      <td>60</td>
    </tr>
  </tbody>
</table>

### penyelesaian menggunakan WKNN manual
<h3>Langkah 1: Hitung Jarak dan Kemiripan (s<sub>i</sub>)</h3>

<p>Gunakan rumus jarak Euclidean untuk data multi-dimensi:</p>
<p>d² = Σ(x<sub>i</sub> - x<sub>j</sub>)²<br>
s<sub>i</sub> = 1/d²</p>

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
    <tr style="background-color: #f2f2f2;">
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
    <tr style="background-color: #f2f2f2;">
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