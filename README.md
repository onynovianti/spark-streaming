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
    <td>https://github.com/onynovianti/spark-streaming/blob/7098a02a7be2a4dcde39fa373f21832e53cf1026/network_wordcount.py#L28-L49</td>
    <td><img src="https://github.com/onynovianti/spark-streaming/blob/master/00_images/method1.png"></td>
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
    <td>https://github.com/onynovianti/spark-streaming/blob/7098a02a7be2a4dcde39fa373f21832e53cf1026/network_wordcount_ganti_interval.py#L28-L49</td>
    <td><img src="https://github.com/onynovianti/spark-streaming/blob/master/00_images/method2.png"></td>
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
    <td>https://github.com/onynovianti/spark-streaming/blob/be7fa7a73e1dde001da1712c1b82d76c58c9a7af/stateful_network_wordcount.py#L63-L121</td>
    <td><img src="https://github.com/onynovianti/spark-streaming/blob/master/00_images/stateful.png"></td>
 </tr>
</table><br>

**2. Melakukan Transformasi di Spark Streaming**
<table border="0">
 <tr>
    <th colspan="2" align="center"><b>Metode 1 : Mode Stateless Stream Processing</b></th>
 </tr>
 <tr>
    <td><b style="font-size:30px">Code</b></td>
    <td><b style="font-size:30px">Output</b></td>
 </tr>
 <tr>
    <td>https://github.com/onynovianti/spark-streaming/blob/7098a02a7be2a4dcde39fa373f21832e53cf1026/network_wordcount.py#L28-L49</td>
    <td><img src="https://github.com/onynovianti/spark-streaming/blob/master/00_images/method1.png"></td>
 </tr>
</table><br>

**3. TUGAS PRAKTIKUM**
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