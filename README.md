# Big-Data
Tugas - Tugas Mata Kuliah Big Data

## Chapter 5
Real-Time Analytics with Spark Streaming and Structured Streaming

<hr/>

**0. Persiapan**
<table border="0">
<tr>
    <th colspan="2" align="center"><b>Menjalankan Spark Daemons</b></th>
 </tr>
 <tr>
    <td><b style="font-size:30px">Code</b></td>
    <td><b style="font-size:30px">Output</b></td>
 </tr>
 <tr>
    <td>cd /home/cloudera/spark-2.0.0-bin-hadoop2.7/sbin <br>
sudo ./start-all.sh</td>
    <td><img src="https://github.com/onynovianti/spark-sql-big-data/blob/master/00_images/0.1.%20Menjalankan%20Spark%20Daemons.png"></td>
 </tr>
</table><br>

**1. Praktik Dasar Spark Streaming**
<table border="0">
 <tr>
    <th colspan="2" align="center"><b>Metode 1 : Mode Stateless Stream Processing</b></th>
 </tr>
 <tr>
    <td><b style="font-size:30px">Code</b></td>
    <td><b style="font-size:30px">Output</b></td>
 </tr>
 <tr>
    <td>https://github.com/onynovianti/spark-sql-big-data/blob/5be0ff9c4407c5e78a1dd301b06aed51cd4b7518/01_dataframes.py#L1-L4</td>
    <td><img src="https://github.com/onynovianti/spark-sql-big-data/blob/master/00_images/kode%201.png"></td>
 </tr>
</table><br>

<table border="0">
 <tr>
    <th colspan="2" align="center"><b>Metode 1 : Mode Stateless Stream Processing >> Mengganti Interval Waktu</b></th>
 </tr>
 <tr>
    <td><b style="font-size:30px">Code</b></td>
    <td><b style="font-size:30px">Output</b></td>
 </tr>
 <tr>
    <td>https://github.com/onynovianti/spark-sql-big-data/blob/5be0ff9c4407c5e78a1dd301b06aed51cd4b7518/01_dataframes.py#L6-L7</td>
    <td><img src="https://github.com/onynovianti/spark-sql-big-data/blob/master/00_images/kode%202.png"></td>
 </tr>
 <tr>
    <td><b style="font-size:30px">Kode</b></td>
    <td><b style="font-size:30px">Keterangan</b></td>
 </tr>
 <tr>
    <td>spark</td>
    <td>Merujuk pada builder spark dengan SparkSession</td>
 </tr>
 <tr>
    <td>createDataFrame</td>
    <td>Membuat data frame manual dan mengambil objek RDD sebagai argumennya</td>
 </tr>
</table><br>

<table border="0">
 <tr>
    <th colspan="2" align="center"><b>Metode 2 : Mode Stateful Stream Processing </b></th>
 </tr>
 <tr>
    <td><b style="font-size:30px">Code</b></td>
    <td><b style="font-size:30px">Output</b></td>
 </tr>
 <tr>
    <td>https://github.com/onynovianti/spark-sql-big-data/blob/5be0ff9c4407c5e78a1dd301b06aed51cd4b7518/01_dataframes.py#L9-L10</td>
    <td><img src="https://github.com/onynovianti/spark-sql-big-data/blob/master/00_images/kode%203.png"></td>
 </tr>
 <tr>
    <td><b style="font-size:30px">Kode</b></td>
    <td><b style="font-size:30px">Keterangan</b></td>
 </tr>
 <tr>
    <td>parallelize</td>
    <td>Membuat RDD dari list collection</td>
 </tr>
 <tr>
    <td>toDF</td>
    <td>Membuat data frame dari RDD yang sudah ada</td>
 </tr>
</table><br>

<table border="0">
 <tr>
    <th colspan="2" align="center"><b>Kode 4 : Copy File people.txt yang Terletak Di Folder Examples/Resources Ke Hdfs</b></th>
 </tr>
 <tr>
    <td><b style="font-size:30px">Code</b></td>
    <td><b style="font-size:30px">Output</b></td>
 </tr>
 <tr>
    <td>hadoop fs -put /home/cloudera/Downloads/examples/resources/people.txt people.txt </td>
    <td><img src="https://github.com/onynovianti/spark-sql-big-data/blob/master/00_images/4.%20Copy%20File%20people.txt.png"></td>
 </tr>
 <tr>
    <td><b style="font-size:30px">Kode</b></td>
    <td><b style="font-size:30px">Keterangan</b></td>
 </tr>
 <tr>
    <td>hadoop</td>
    <td>Hadoop Distributed File System (HDFS)</td>
 </tr>
 <tr>
    <td>fs</td>
    <td>Command line untuk memanipulasi file pada HDFS</td>
 </tr>
 <tr>
    <td>put</td>
    <td>Menyalin file dari berkas lokal ke HDFS</td>
 </tr>
</table><br>

<table border="0">
 <tr>
    <th colspan="2" align="center"><b>Kode 5 : Read Data From A File, Infer Schema And Convert To Dataframe</b></th>
 </tr>
 <tr>
    <td><b style="font-size:30px">Code</b></td>
    <td><b style="font-size:30px">Output</b></td>
 </tr>
 <tr>
    <td>https://github.com/onynovianti/spark-sql-big-data/blob/5be0ff9c4407c5e78a1dd301b06aed51cd4b7518/01_dataframes.py#L14-L21</td>
    <td><img src="https://github.com/onynovianti/spark-sql-big-data/blob/master/00_images/5.%20Read%20Data%20From%20A%20File%2C%20Infer%20Schema%20And%20Convert%20To%20Dataframe.png"></td>
 </tr>
 <tr>
    <td><b style="font-size:30px">Kode</b></td>
    <td><b style="font-size:30px">Keterangan</b></td>
 </tr>
 <tr>
    <td>pyspark.sql</td>
    <td>Modul python yang digunakan untuk bekerja dengan Spark SQL</td>
 </tr>
 <tr>
    <td>SQLContext</td>
    <td>Membuat atau mengelola struktur data Spark SQL, seperti DataFrames dan tabel</td>
 </tr>
 <tr>
    <td>createOrReplaceTempView</td>
    <td>Membuat atau mengganti temporary view dari DataFrame</td>
 </tr>
 <tr>
    <td>show</td>
    <td>Menampilkan hasil dari perintah sebelumnya (hasil dari DataFrame) dalam format tabel</td>
 </tr>
</table><br>

<table border="0">
 <tr>
    <th colspan="2" align="center"><b>Kode 6 : Membaca Data Dari File, Lalu Assign Schema Secara Programmatically</b></th>
 </tr>
 <tr>
    <td><b style="font-size:30px">Code</b></td>
    <td><b style="font-size:30px">Output</b></td>
 </tr>
 <tr>
    <td>https://github.com/onynovianti/spark-sql-big-data/blob/5be0ff9c4407c5e78a1dd301b06aed51cd4b7518/01_dataframes.py#L24-L38</td>
    <td><img src="https://github.com/onynovianti/spark-sql-big-data/blob/master/00_images/6.%20Membaca%20Data%20Dari%20File%2C%20Lalu%20Assign%20Schema%20Secara%20Programmatically.png"></td>
 </tr>
 <tr>
    <td><b style="font-size:30px">Kode</b></td>
    <td><b style="font-size:30px">Keterangan</b></td>
 </tr>
 <tr>
    <td>textFile</td>
    <td>Membaca teks sebagai RDD</td>
 </tr>
 <tr>
    <td>map</td>
    <td>Menerapkan sebuah fungsi pada setiap elemen dan menghasilkan RDD baru</td>
 </tr>
 <tr>
    <td>lambda</td>
    <td>Fungsi tanpa menggunakan kata "def", biasanya dikombinasikan untuk digunakan pada argumen fungsi </td>
 </tr>
 <tr>
    <td>strip</td>
    <td>Menghapus karakter whitespace pada awal dan akhir string</td>
 </tr>
 <tr>
    <td>StructField</td>
    <td>Membuat objek kolom dengan memiliki 3 parameter, yaitu : nama kolom, tipe data, dan opsi tambahan</td>
 </tr>
 <tr>
    <td>StringType</td>
    <td>Mendefinisikan tipe data kolom sebagai String dalam DataFrame</td>
 </tr>
</table><br>

**2. Membuat DataFrame dari Database Eksternal**
<table border="0">
 <tr>
    <th colspan="2" align="center"><b>Kode 7 : Membuat DataFrame dari Database eksternal - Metode Pertama</b></th>
 </tr>
 <tr>
    <td><b style="font-size:30px">Code</b></td>
    <td><b style="font-size:30px">Output</b></td>
 </tr>
 <tr>
    <td>https://github.com/onynovianti/spark-sql-big-data/blob/b130c4f9f24a422157ab882c8922a95564620841/02_dataframe_mysql.py#L3-L5</td>
    <td><img src="https://github.com/onynovianti/spark-sql-big-data/blob/master/00_images/7.%20Membuat%20DataFrame%20dari%20Database%20eksternal%20-%20Metode%20Pertama.png"></td>
 </tr>
 <tr>
    <td><b style="font-size:30px">Kode</b></td>
    <td><b style="font-size:30px">Keterangan</b></td>
 </tr>
 <tr>
    <td>spark.read.format</td>
    <td>Membaca data dari berbagai sumber data seperti json, dan csv, dan lain-lain</td>
 </tr>
 <tr>
    <td>jdbc</td>
    <td>Sumber data berasal dari jdbc (Java Database Connectivity)</td>
 </tr>
 <tr>
    <td>options</td>
    <td>Opsi konfigurasi untuk mengkoneksikan ke JDBC</td>
 </tr>
 <tr>
    <td>load</td>
    <td>Membaca data ke dalam DataFrame</td>
 </tr>
</table><br>

<table border="0">
 <tr>
    <th colspan="2" align="center"><b>Kode 8 : Membuat DataFrame dari Database eksternal - Metode Kedua</b></th>
 </tr>
 <tr>
    <td><b style="font-size:30px">Code</b></td>
    <td><b style="font-size:30px">Output</b></td>
 </tr>
 <tr>
    <td>https://github.com/onynovianti/spark-sql-big-data/blob/b130c4f9f24a422157ab882c8922a95564620841/02_dataframe_mysql.py#L7-L9</td>
    <td><img src="https://github.com/onynovianti/spark-sql-big-data/blob/master/00_images/8.%20Membuat%20DataFrame%20dari%20Database%20eksternal%20-%20Metode%20Kedua.png"></td>
 </tr>
 <tr>
    <td><b style="font-size:30px">Kode</b></td>
    <td><b style="font-size:30px">Keterangan</b></td>
 </tr>
 <tr>
    <td>show</td>
    <td>Menampilkan konten, pada kode diatas yaitu menampilkan isi DataFrame df2</td>
 </tr>
</table><br>

**3. Mengonversi DataFrames ke RDDs**
<table border="0">
 <tr>
    <th colspan="2" align="center"><b>Kode 9 : Konversi dari DataFrames ke RDD</b></th>
 </tr>
 <tr>
    <td><b style="font-size:30px">Code</b></td>
    <td><b style="font-size:30px">Output</b></td>
 </tr>
 <tr>
    <td>https://github.com/onynovianti/spark-sql-big-data/blob/b130c4f9f24a422157ab882c8922a95564620841/03_convert_df_rdd.py#L1-L12</td>
    <td><img src="https://github.com/onynovianti/spark-sql-big-data/blob/master/00_images/9.%20Konversi%20dari%20DataFrames%20ke%20RDD.png"></td>
 </tr>
 <tr>
    <td><b style="font-size:30px">Kode</b></td>
    <td><b style="font-size:30px">Keterangan</b></td>
 </tr>
 <tr>
    <td>collect</td>
    <td>Mengumpulkan baris data dan mereturn list</td>
 </tr>
 <tr>
    <td>rdd</td>
    <td>Pada kode diatas rdd digunakan untuk merubah DataFrame ke dalam RDD</td>
 </tr>
 <tr>
    <td>take</td>
    <td>Mengambil baris dalam RDD. take(2) berarti mengambil 2 baris pertama dan mereturn dalam bentuk list</td>
 </tr>
</table><br>

**4. Membuat Datasets**
<table border="0">
 <tr>
    <th colspan="2" align="center"><b>Kode 10 : Membuat Dataset dan DataFrame dari RDD Menggunakan Scala</b></th>
 </tr>
 <tr>
    <td><b style="font-size:30px">Code</b></td>
    <td><b style="font-size:30px">Output</b></td>
 </tr>
 <tr>
    <td>https://github.com/onynovianti/spark-sql-big-data/blob/b130c4f9f24a422157ab882c8922a95564620841/04_datasets.scala#L3-L9</td>
    <td><img src="https://github.com/onynovianti/spark-sql-big-data/blob/master/00_images/10.%20Membuat%20Dataset%20dan%20DataFrame%20dari%20RDD%20Menggunakan%20Scala.png"></td>
 </tr>
 <tr>
    <td><b style="font-size:30px">Kode</b></td>
    <td><b style="font-size:30px">Keterangan</b></td>
 </tr>
 <tr>
    <td>makeRDD</td>
    <td>Membuat RDD dari list atau array</td>
 </tr>
 <tr>
    <td>Seq</td>
    <td>Tipe data collection atau urutan dalam Scala</td>
 </tr>
 <tr>
    <td>createDataset</td>
    <td>Membuat dataset baru</td>
 </tr>
</table><br>

<table border="0">
 <tr>
    <th colspan="2" align="center"><b>Kode 11 : Datasets RDD</b></th>
 </tr>
 <tr>
    <td><b style="font-size:30px">Code</b></td>
    <td><b style="font-size:30px">Output</b></td>
 </tr>
 <tr>
    <td>https://github.com/onynovianti/spark-sql-big-data/blob/b130c4f9f24a422157ab882c8922a95564620841/04_datasets.scala#L13-L30</td>
    <td><img src="https://github.com/onynovianti/spark-sql-big-data/blob/master/00_images/11.%20Datasets%20RDD.png"></td>
 </tr>
 <tr>
    <td><b style="font-size:30px">Kode</b></td>
    <td><b style="font-size:30px">Keterangan</b></td>
 </tr>
 <tr>
    <td>filter</td>
    <td>Melakukan filter pada sebuah Dataset dengan kondisi yang diberikan</td>
 </tr>
 <tr>
    <td><b style="font-size:30px">Soal</b></td>
    <td><b style="font-size:30px">Jawab</b></td>
 </tr>
 <tr>
    <td>Pada Kode 11 di baris akhir terjadi error, jelaskan pada laporan praktikum Anda mengapa ini bisa terjadi ?</td>
    <td>Hal tersebut terjadi karena pada struktur Dept yang sudah dilakukan pada kode sebelumnya, tidak menunjukkan adanya kolom bernama dept_location. Yang ada hanya kolom dept_id dan dept_name</td>
 </tr>
</table><br>

**5. TUGAS PRAKTIKUM**
<table border="0">
 <tr>
    <th colspan="2" align="center"><b>Jelaskan perbedaan spark streaming dengan metode stateless dan stateful stream processing!</b></th>
 </tr>
 <tr>
    <td>Perbedaannya adalah jika pada stateful, state dari peristiwa sebelumnya tetap ada dan memengaruhi peristiwa selanjutnya. sedangkan dalam stateless, state tidak persisten.</td>
 </tr>
 </table>
 <table border="0">
 <tr>
    <th colspan="2" align="center"><b>Jelasakan masing-masing maksud kode berikut sesuai nomor kodenya!</b></th>
 </tr>
 <tr>
    <td><b style="font-size:30px">Nomor Kode</b></td>
    <td><b style="font-size:30px">Kode</b></td>
    <td><b style="font-size:30px">Keterangan</b></td>
 </tr>
 <tr>
    <td rowspan="8">1</td>
    <td>sys.argv</td>
    <td>sys.argv adalah list pada python yang berisi semua perintah pada command-line</td>
 </tr>
 <tr>
    <td>sys.stderr</td>
    <td>sys.stderr mencetak langsung ke konsol berupa pesan pengecualian (exception) dan kesalahan</td>
    <tr>
    <td>StreamingContext</td>
    <td>StreamingContext mewakili koneksi ke cluster Spark dan dapat digunakan untuk membuat berbagai sumber input DStream</td>
 </tr>
 <tr>
    <td>sc</td>
    <td>Default dari PySpark SparkContext</td>
 </tr>
 <tr>
    <td>socketTextStream</td>
    <td>Buat input dari nama host sumber TCP: port. Data diterima menggunakan soket TCP dan menerima byte ditafsirkan sebagai UTF8 yang disandikan \n baris yang dibatasi.</td>
 </tr>
 <tr>
    <td>reduceByKey</td>
    <td>Transformasi digunakan untuk menggabungkan nilai setiap kunci menggunakan fungsi pengurangan asosiatif pada PySpark RDD.</td>
 </tr>
 <tr>
    <td>lambda line</td>
    <td></td>
 </tr>
 <tr>
    <td>awaitTermination</td>
    <td>Menunggu penghentian kueri ini, baik dengan kueri. stop() atau dengan pengecualian. Jika kueri telah diakhiri dengan pengecualian, maka pengecualian akan dilemparkan.</td>
 </tr>
 <tr>
    <td rowspan="2">2</td>
    <td>nc</td>
    <td>Utilitas nc (atau netcat) digunakan untuk apa saja di bawah matahari yang melibatkan TCP atau UDP. Itu dapat membuka koneksi TCP, mengirim paket UDP, mendengarkan port TCP dan UDP yang sewenang-wenang, melakukan pemindaian port, dan menangani IPv4 dan IPv6</td>
 </tr>
 <tr>
    <td>lk</td>
    <td>-l adalah untuk listen pada port, sedangkan -k untuk menjaga agar listener terbuka</td>
    <tr>
 </tr>
 <tr>
    <td rowspan="3">3</td>
    <td>spark-submit</td>
    <td>Skrip spark-submit di direktori bin Spark digunakan untuk meluncurkan aplikasi di cluster</td>
 </tr>
 <tr>
    <td>master</td>
    <td>URL master untuk kluster</td>
    <tr>
 </tr>
 <tr>
    <td>local[*]</td>
    <td>Menjalankan Spark secara lokal dengan thread pekerja sebanyak inti logis di mesin Anda.</td>
    <tr>
 </tr>
 <tr>
    <td rowspan="4">4</td>
    <td>ssc.checkpoint</td>
    <td>Mengatur direktori pos pemeriksaan</td>
 </tr>
 <tr>
    <td>parallelize</td>
    <td>PySpark parallelize() adalah fungsi di SparkContext dan digunakan untuk membuat RDD dari kumpulan daftar</td>
    <tr>
 </tr>
 <tr>
    <td>updateStateByKey</td>
    <td>Kembalikan DStream "status" baru di mana status untuk setiap kunci diperbarui dengan menerapkan fungsi yang diberikan pada status kunci sebelumnya dan nilai baru untuk kunci tersebut. Ini dapat digunakan untuk memelihara data status arbitrer untuk setiap kunci.</td>
    <tr>
 </tr>
 <tr>
    <td>flatMap</td>
    <td>flatMap() adalah operasi transformasi yang meratakan RDD/DataFrame (array/memetakan kolom DataFrame) setelah menerapkan fungsi pada setiap elemen dan mengembalikan PySpark RDD/DataFrame baru.</td>
    <tr>
 </tr>
 <tr>
    <td rowspan="3">3</td>
    <td>rdd.take(5)</td>
    <td>Ambil 5 elemen pertama dari RDD</td>
 </tr>
 <tr>
    <td>transform</td>
    <td>ransform() digunakan untuk menerapkan transformasi pada kolom bertipe Array.</td>
    <tr>
 </tr>
 <tr>
    <td>rdd.sortByKey(False)</td>
    <td>Sort dengan descending order</td>
    <tr>
 </tr>
</table>