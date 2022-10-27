# Laporan Proyek Machine Learning - Winaya Zarkasih

## Project Overview

Berdasarkan informasi yang disampaikan pada Kompas.com, menurut Kemenparefkraf jumlah penonton bioskop mulai pulih usai pandemi COVID-19 berakhir.
Berikut data yang disampaikan oleh Kemenparekraf:

* Tahun 2019: 29.646.450 penonton 
* Tahun 2020: 12.059.127 penonton 
* Tahun 2021: 4.226.025 penonton 
* Tahun 2022: 21.212.199 penonton

Melihat peningkatan jumlah penonton yang hampir pulih seperti sebelum ada pandemi tersebut, diperlukan sistem rekomendasi yang dapat merekomendasikan film sesuai degan preferensi pribadi agar memberikan kepuasan kepada penonton terhadap film yang ditonton.

Referensi dari project overview pada laporan ini dapat dilihat pada tautan berikut: [Kemenparekraf: Jumlah Penonton Bioskop Sudah Pulih, Hampir Seperti Sebelum Pandemi Covid-19]([https://scholar.google.com/](https://nasional.kompas.com/read/2022/07/04/14351401/kemenparekraf-jumlah-penonton-bioskop-sudah-pulih-hampir-seperti-sebelum)) 

## Business Understanding

### Problem Statements

- Bagaimana cara membuat sistem yang dapat merekomendasikan film dari film - film yang pernah kita tonton sebelumnya?
- Bagaimana cara mendapatkan rekomendasi film yang memiliki genre yang sama?

### Goals

- Membuat sistem yang dapat merekomendasikan film dari film - film yang pernah ditonton sebelumnya.
- Membuat sistem yang dapat merekomendasikan film dengan genre yang sama dengan film yang pernah kita tonton sebelumnya.

## Data Understanding

Dataset yang digunakan pada pada proyek ini merupakan dataset film FilmTV yang diperoleh dari salah situs penyedia data yaitu kaggle: [FilmTV movies dataset](https://www.kaggle.com/datasets/stefanoleone992/filmtv-movies-dataset?select=filmtv_movies+-+ENG.csv)

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



