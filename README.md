# sistem_cinema
Berikut **README.md** yang rapi, jelas, dan cocok untuk dipush ke GitHub ✨
Bahasanya formal–santai dan sesuai proyek database sekolah/kuliah.

---

# 🎬 DB Cinema – Database Film Sederhana (MariaDB/MySQL)

DB Cinema adalah proyek **database sederhana** menggunakan **MariaDB/MySQL** yang menyimpan data film, sutradara, dan genre.
Proyek ini dibuat sebagai latihan **DDL, DML, dan JOIN SQL**.

---

## 📌 Fitur Database

* Manajemen data **sutradara**
* Manajemen data **genre film**
* Manajemen data **film**
* Relasi antar tabel menggunakan **FOREIGN KEY**
* Contoh penggunaan:

  * `INNER JOIN`
  * `LEFT JOIN`
  * `RIGHT JOIN`

---

## 🗂️ Struktur Database

### 1️⃣ Tabel `sutradara`

Menyimpan data sutradara film.

| Kolom          | Tipe Data    | Keterangan     |
| -------------- | ------------ | -------------- |
| id_sutradara   | INT (PK)     | ID sutradara   |
| nama_sutradara | VARCHAR(100) | Nama sutradara |
| negara_asal    | VARCHAR(50)  | Negara asal    |
| tahun_lahir    | INT          | Tahun lahir    |

---

### 2️⃣ Tabel `genre`

Menyimpan data genre film.

| Kolom      | Tipe Data   | Keterangan      |
| ---------- | ----------- | --------------- |
| id_genre   | INT (PK)    | ID genre        |
| nama_genre | VARCHAR(50) | Nama genre      |
| keterangan | TEXT        | Deskripsi genre |

---

### 3️⃣ Tabel `film`

Menyimpan data film dan relasinya.

| Kolom        | Tipe Data          | Keterangan          |
| ------------ | ------------------ | ------------------- |
| id_film      | INT (PK)           | ID film             |
| judul_film   | VARCHAR(150)       | Judul film          |
| tahun_rilis  | INT                | Tahun rilis         |
| durasi_menit | INT                | Durasi film         |
| id_sutradara | INT (FK)           | Relasi ke sutradara |
| id_genre     | INT (FK, NULLABLE) | Relasi ke genre     |

---

## 🔗 Relasi Antar Tabel

* **film → sutradara** (Many to One)
* **film → genre** (Many to One, boleh `NULL`)

---

## 🛠️ Teknologi yang Digunakan

* **MariaDB 10.4**
* **MySQL Client**
* **XAMPP**
* **Command Line (CMD)**

---

## ▶️ Cara Menjalankan Project

1. Jalankan **XAMPP** dan aktifkan **MySQL**
2. Masuk ke folder MySQL:

   ```bash
   cd xampp/mysql/bin
   ```
3. Login ke MySQL:

   ```bash
   mysql -u root
   ```
4. Buat dan gunakan database:

   ```sql
   CREATE DATABASE db_cinema;
   USE db_cinema;
   ```
5. Jalankan query pembuatan tabel dan insert data

---

## 📊 Contoh Query JOIN

### INNER JOIN

```sql
SELECT film.judul_film, sutradara.nama_sutradara, genre.nama_genre
FROM film
INNER JOIN sutradara ON film.id_sutradara = sutradara.id_sutradara
INNER JOIN genre ON film.id_genre = genre.id_genre;
```

### LEFT JOIN

```sql
SELECT sutradara.nama_sutradara, film.judul_film
FROM sutradara
LEFT JOIN film ON sutradara.id_sutradara = film.id_sutradara;
```

### RIGHT JOIN

```sql
SELECT genre.nama_genre, film.judul_film
FROM genre
RIGHT JOIN film ON genre.id_genre = film.id_genre;
```

---

## 📌 Catatan Penting

* Film **boleh tidak memiliki genre** (`id_genre = NULL`)
* Data sutradara bisa tampil walaupun **belum memiliki film**
* Cocok untuk latihan **relasi database & SQL JOIN**

---

## 👤 Author

**Nama:** M. Azka F. A.
**Project:** Database Cinema
**Tujuan:** Pembelajaran Database MySQL/MariaDB

---

Kalau mau, aku juga bisa:

* Buat **ERD (diagram relasi)**
* Versi **README Bahasa Inggris**
* Tambahin **screenshot hasil query**
* Buatin **file .sql siap import**

Tinggal bilang 👍
