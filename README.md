# Laporan Proyek Machine Learning - Winaya Zarkasih

## Domain Proyek
*Cryptocurrency* telah menjadi fenomena global saat ini. Berdasarkan hasil Survei GlobalWebIndex
menyebutkan bahwa ada sekitar 10% pengguna internet di Indonesia telah memiliki mata uang digital.
Persentase tersebut membuat Indonesia menempati peringkat 5 pengguna cryptocurrency terbanyak di
dunia. Menurut (Syamsiah, 2017) cryptocurrency adalah system mata uang virtual yang
berfungsi seperti mata uang standar yang memungkinkan penggunanya untuk melakukan
pembayaran secara virtual atas transaksi bisnis yang terjadi tanpa biaya jasa namun tetap
memiliki otoritas kepercayaan yang terpusat. *Dogecoin* adalah salah satu jenisnya. Karakteristik unik *Dogecoin* adalah fluktuasi harga harian dan selalu berubah setiap hari. 

Referensi dari domain proyek pada laporan ini dapat dilihat pada tautan berikut :
[Risiko dan Tingkat Keuntungan Investasi Cryptocurrency](https://www.researchgate.net/profile/Nurul-Huda-32/publication/349116193_Risiko_dan_Tingkat_Keuntungan_Investasi_Cryptocurrency/links/60214094a6fdcc37a8110680/Risiko-dan-Tingkat-Keuntungan-Investasi-Cryptocurrency.pdf)

## Business Understanding

### Problem Statements

Bagaimana memprediksi harga *Dogecoin* dimasa yang akan datang?

### Goals

Menentukan model machine learning yang paling sesuai yang dapat digunakan dengan baik untuk memprediksi harga *Dogecoin* dimasa mendatang

## Data Understanding

Dataset yang digunakan pada pada proyek ini merupakan dataset riwayat harga mata uang dogecoin yang diperoleh dari salah situs penyedia data yaitu kaggle: [Cryptocurrency Historical Prices.](https://www.kaggle.com/datasets/sudalairajkumar/cryptocurrencypricehistory?select=coin_Bitcoin.csv)

Informasi dari dara sebagai berikut:
- Format dataset yaitu CSV (Comma-Seperated Values).
- Jumlah kolom pada data yaitu 10, antara lain: SNo, Name, Symbol, Date, High, Low, Open, Close, Volume, Marketcap.
- Jumlah sample yang terdapat didalam dataset 2760. 
- Terdapat 6 kolom data yang memiliki tipe data Float yaitu (High, Low, Open, Close, Volume, Marketcap).
- Terdapat 1 kolom data yang memiliki tipe data Integer yaitu (SNo)
- Terdapat 2 kolom data yang memiliki tipe data Object atau String yaitu (Name, Symbol)
- Tidak terdapat missing value pada dataset

## Variabel-variabel pada Cryptocurrency Historical Prices dataset adalah sebagai berikut:
- Name: Nama mata uang kripto
- Symbol: Simbol mata uang kripto
- Date: Tanggal pencatatan data
- High : Harga tertinggi pada hari tertentu
- Low : Harga terendah pada hari tertentu
- Open : Harga pembukaan pada hari tertentu
- Close : Harga penutupan pada hari tertentu
- Volume : Volume transaksi pada hari tertentu
- Mastercap : Kapitalisasi pasar dalam USD

## Data Preparation

Teknik data preparation yang dilakukan sebagai berikut:

- Menangani Outlier

![Visualisasi Outlier](https://user-images.githubusercontent.com/60729013/197669355-c0c8ca9c-7a5a-4679-96a2-dccb7789edf8.png)

Berdasarkan visualisasi diatas beberapa data numeric memiliki data outlier. Disini saya menggunakan teknik IQR Method yaitu dengan menghapus data yang berada diluar interquartile range. Interquartile merupakan range diantara kuartil pertama(25%) dan kuartil ketiga(75%).

![Unvariate Analysis](https://user-images.githubusercontent.com/60729013/197670526-c163a31c-e90e-4c69-9bf8-f7be5dfacb2e.png)

Fitur Close Price pada harga Dogecoin menjadi target prediksi kali ini, maka dapat disimpulkan bahwa peningkatan harga Dogecoin sebanding dengan penurunan jumlah sampel.

![Multi Variate Analysis](https://user-images.githubusercontent.com/60729013/197671118-47178c86-0269-4f4e-97a7-9371816c5ff7.png)

Korelasi yang terdapat dalam fitur Close pada sumbu y dengan fitur High, Low, Open, dan Marketcap termasuk korelasi yang tinggi. Sedangkan fitur Volume korelasi nya cukup lemah, sebaran datanya tidak membentuk pola.

![Heatmap](https://user-images.githubusercontent.com/60729013/197671485-0ef38f77-e359-4f63-9a35-6f20d3025e86.png)

Pada matriks korelasi di atas dapat disimpulkan bahwa kebanyakan variabel memiliki keterikatan dan korelasi yang kuat antar variabel lainnya, dimana nilai korelasi antar variabel bernilai lebih dari 0.6 atau mendekati 1.
