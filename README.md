# Sistem Rekomendasi Buku Menggunakan Algoritma Word2Vec
Untuk menjalankan code, pastikan library berikut sudah terinstall.
- pandas
- re
- gensim
- numpy
- scipy
- nltk

``` Run Pmsteyol.ipynb code in Jupyter Notebook ```

## Deskripsi Dataset
Dataset tersimpan dalam format .csv, dimana terdapat 21.559 data dengan 15 atribut. Dataset kemudian diterapkan tahap preparation dan preprocessing, meliputi:
- Drop NULL value (menggunakan fillna)
- Drop Duplicate value (menggunakan drop_duplicates)
- Case Folding (menggunakan casefold)
- Remove Punctuation (menggunakan replace & re.sub)
- Tokenization (menggunakan SpaceTokenizer)

Dari proses preparation dan preprocessing, didapatkan data sebanyak 21.559 data dengan 5 atribut yang akan digunakan dalam sistem rekomendasi. Atribut-atribut tersebut adalah sebagai berikut.
- ID
- book_title
- book_rating
- genre
- review_vocabs (yang didapat dari hasil tokenisasi atribut review)

## Build Model
Model dibangun menggunakan algoritma Word2Vec untuk proses word embedding terhadap atribut review untuk mendapatkan nilai vector. Kemudian dari nilai vector tersebut akan didapatkan cosine_similarity sebagai acuan dalam mencari rekomendasi buku.

## Book Recommendation
Sistem akan meminta input berupa judul buku dan akan mengeluarkan output berupa 10 judul buku hasil rekomendasi berdasarkan tingkat cosine_similarity tertinggi.

Input yang dapat digunakan untuk mencari rekomendasi buku yang terdapat dalam dataset antara lain:
```
- A Crown of Wishes
- Love Me in the Dark
- Afraid to Fly
- Beyond Reckless
```