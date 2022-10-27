# Laporan Proyek Machine Learning - Winaya Zarkasih

## Project Overview

Berdasarkan informasi yang disampaikan pada Kompas.com, menurut Kemenparekraf jumlah penonton bioskop mulai pulih usai pandemi COVID-19 berakhir.
Berikut data yang disampaikan oleh Kemenparekraf:

* Tahun 2019: 29.646.450 penonton 
* Tahun 2020: 12.059.127 penonton 
* Tahun 2021: 4.226.025 penonton 
* Tahun 2022: 21.212.199 penonton

Melihat peningkatan jumlah penonton yang hampir pulih seperti sebelum ada pandemi tersebut, diperlukan sistem rekomendasi yang dapat merekomendasikan film sesuai degan preferensi pribadi agar memberikan kepuasan kepada penonton terhadap film yang ditonton.

## Business Understanding

### Problem Statements

- Bagaimana cara membuat sistem yang dapat merekomendasikan film dari film - film yang pernah kita tonton sebelumnya?
- Bagaimana cara mendapatkan rekomendasi film yang memiliki genre yang mungkin sama?

### Goals

- Membuat sistem yang dapat merekomendasikan film dari film - film yang pernah ditonton sebelumnya.
- Membuat sistem yang dapat merekomendasikan film dengan genre yang sama dengan film yang pernah kita tonton sebelumnya.

## Data Understanding

Dataset yang digunakan pada pada proyek ini merupakan dataset film FilmTV yang diperoleh dari salah situs penyedia data yaitu kaggle: [FilmTV movies dataset](https://www.kaggle.com/datasets/stefanoleone992/filmtv-movies-dataset?select=filmtv_movies+-+ENG.csv)

Informasi dari data sebagai berikut:

- filmtv_id : Merupakan id dari film
- title : Merupakan judul dari film
- year : Merupakan tahun rilis film
- genre : Merupakan genre film
- duration : Merupakan durasi film
- country : Merupakan negara dari film
- directors : Merupakan direktur dari film
- actors : Merupakan kumpulan aktor dari film
- avg_vote : Merupakan rata - rata voting
- critics_vote : Merupakan voting kritik
- public_vote : Merupakan voting publik
- total_votes : Merupakan total voting pada film
- description : Merupakan deskripsi film
- notes : Merupakan catatan pada film
- humor : Merupakan tingkat humor film
- rhythm : Merupakan tingkat irama film
- effort : Merupakan tingkat upaya film
- tension : Merupakan tingkat ketegangan film
- erotisme : Merupakan tingkat erotisme film

#### Unvariate Analysis

<img width="349" alt="Screen Shot 2022-10-27 at 14 35 28" src="https://user-images.githubusercontent.com/60729013/198220145-ea5506a2-6e9c-4db4-b68d-02942fd348a6.png">

Dari visualisasi diatas dapat kita simpulkan bahwa pada dataset ini sebagian besar film memiliki genre Drama dan Comedy. untuk genre lainya tidak terlalu dominan

#### Multivariate Analysis

<img width="823" alt="Screen Shot 2022-10-27 at 14 52 19" src="https://user-images.githubusercontent.com/60729013/198223738-d1f982df-02cb-4261-879b-40be781d0d13.png">

Dari visualisasi diatas dapat kita simpulkan bahwa hanya fitur critic_vote dengan fitur avg_vote yang memiliki pola pada data.

## Data Preparation

Berikut adalah hal - hal yang dilakukan pada proses data preparation :

- Dropna, digunakan membuang seluruh row yang memiliki nilai NaN. 
- Drop Duplicates, digunakan untuk membuang data - data yang terduplikasi.
- Dataframe dari film diubah menjadi sebuah list dengan menggunakan .tolist() method. Proses ini diperlukan karena list ini akan digunakan pada tahap selanjutnya menjadi dictionary baru yg akan menjadi landasan pada sistem rekomendasi.
- Memasukkan list ke Dictionary digunakan untuk mementukan pasangan key dan value pada filmtv_id, title, genre, year.

## Modeling

Pada tahapan ini kita akan menggunakan TF-IDF Vectorizer untuk membangun sistem rekomendasi berdasarkan genre film. 

TF-IDF (Term Frequency-Inverse Document Frequency) memiliki fungsi untuk mengukur seberapa pentingnya suatu kata terhadap kata - kata lain dalam dokumen. Kita umumnya menghitung skor untuk setiap kata untuk menandakan pentingnya dalam dokumen. Metode ini sering digunakan dalam Information Retrieval dan Text Mining. Fungsi pada TF-IDF yang digunakan pada proyek ini menghasilkan kata - kata penting dari kolom genre, setelah itu kata yang didapatkan akan dimasukkan ke dalam matriks. Pada proyek ini, saya menggunakan tfidf_matrix sebagai matriks.
Dalam sistem rekomendasi, kita perlu mencari cara supaya item yang kita rekomendasikan tidak terlalu jauh dari data pusat, oleh karena itu kita butuh derajat kesamaan pada item, dalam proyek ini, mengunakan cosine similarity.

Kemudian saya membuat fungsi author_recommendation untuk mendapatkan 5 rekomendasi dari film yang sebelumnya ditonton.

Berikut 5 rekomendasi film hasil dari sistem yang kita buat untuk judul film "Border Shootout/Law at Randado"

|  | title | genre |
| ----------- | :---------: | ----------: |
| 0 | Badman's Territory | Western |
| 1 | The Hunting Party | Western|
| 2 | The Hunting Party | Drama|
| 3 | The Good Guys and the Bad Guys | Western |
| 4 | Tedeum | Western |


## Evaluation

Pada sistem rekomendasi dengan pendekatan Content Based Filtering dibuat, saya menggunakan akurasi sebagai metrik evaluasi. 
Rumus yang digunakan untuk mendapatkan akurasi pada Content Based Filtering yaitu: 
Akurasi = Jumlah Film yang direkomendasikan sesuai dengan Genre Film / Jumlah Film yang direkomendasikan.

Berikut akurasi yang didapatkan dari sistem rekomendasi yang dibuat

<img width="413" alt="Screen Shot 2022-10-27 at 16 05 22" src="https://user-images.githubusercontent.com/60729013/198242451-1bc2a4c8-0173-4b53-b6f7-a4cdd52c9da9.png">


Daftar Refensi:

- [Kemenparekraf Jumlah Penonton Bioskop Sudah Pulih, Hampir Seperti Sebelum Pandemi Covid-19](https://nasional.kompas.com/read/2022/07/04/14351401/kemenparekraf-jumlah-penonton-bioskop-sudah-pulih-hampir-seperti-sebelum) 
