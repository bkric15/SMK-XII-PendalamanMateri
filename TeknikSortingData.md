Berikut adalah penyusunan materi lengkap dari pengantar, langkah demi langkah setiap metode, hingga motivasi penutup untuk siswa SMK Jurusan Perangkat Lunak dan Gim (PLG).

---

## Modul Pembelajaran: Metode Sorting (Pengurutan Data)

### 1. Pengantar Algoritma Sorting

**Sorting** adalah proses mengatur sekumpulan data atau elemen ke dalam urutan tertentu, baik secara **Ascending** (terurut dari terkecil ke terbesar: $A \rightarrow Z$ atau $1 \rightarrow 10$) maupun **Descending** (terurut dari terbesar ke terkecil: $Z \rightarrow A$ atau $10 \rightarrow 1$).

Dalam pengembangan aplikasi dan gim, algoritma sorting digunakan untuk berbagai fitur penting:

* **Papan Skor (Leaderboard):** Mengurutkan skor pemain dari tertinggi ke terendah.
* **Sistem Inventaris (Inventory System):** Mengurutkan item berdasarkan nama, kejarangan (*rarity*), atau nilai jual.
* **Manajemen Render Gim:** Mengurutkan objek dari yang terdekat hingga terjauh dari kamera (*Z-sorting*).

---

### 2. Penjelasan Langkah demi Langkah Setiap Metode

#### A. Bubble Sort

* **Konsep:** Membandingkan dua elemen yang bersebelahan secara berulang dan menukarnya jika urutannya salah. Elemen terbesar akan "mengapung" ke posisi paling kanan seperti gelembung udara.

**Langkah demi Langkah (Contoh data: `[5, 2, 8, 1]`):**

* **Iterasi 1:**
1. Bandingkan `5` dan `2`. Karena $5 > 2$, tukar posisinya $\rightarrow$ `[2, 5, 8, 1]`
2. Bandingkan `5` dan `8`. Karena $5 < 8$, posisi tetap $\rightarrow$ `[2, 5, 8, 1]`
3. Bandingkan `8` dan `1`. Karena $8 > 1$, tukar posisinya $\rightarrow$ `[2, 5, 1, 8]`
*(Angka `8` berhasil dikunci di posisi akhir)*


* **Iterasi 2:**
1. Bandingkan `2` dan `5`. Karena $2 < 5$, posisi tetap $\rightarrow$ `[2, 5, 1, 8]`
2. Bandingkan `5` dan `1`. Karena $5 > 1$, tukar posisinya $\rightarrow$ `[2, 1, 5, 8]`
*(Angka `5` dikunci di posisi kedua dari belakang)*


* **Iterasi 3:**
1. Bandingkan `2` dan `1`. Karena $2 > 1$, tukar posisinya $\rightarrow$ `[1, 2, 5, 8]`


* **Hasil Akhir:** `[1, 2, 5, 8]`



---

#### B. Selection Sort

* **Konsep:** Mencari nilai terkecil dari seluruh daftar yang belum terurut, lalu menempatkannya di posisi paling depan yang belum terkunci.

**Langkah demi Langkah (Contoh data: `[64, 25, 12, 22]`):**

* **Langkah 1 (Posisi ke-0):**
1. Cari angka terkecil di seluruh array `[64, 25, 12, 22]`.
2. Angka terkecil adalah `12`.
3. Tukar `12` dengan angka pertama (`64`) $\rightarrow$ `[12, 25, 64, 22]`


* **Langkah 2 (Posisi ke-1):**
1. Cari angka terkecil dari sisa array `[25, 64, 22]`.
2. Angka terkecil adalah `22`.
3. Tukar `22` dengan angka kedua (`25`) $\rightarrow$ `[12, 22, 64, 25]`


* **Langkah 3 (Posisi ke-2):**
1. Cari angka terkecil dari sisa array `[64, 25]`.
2. Angka terkecil adalah `25`.
3. Tukar `25` dengan angka ketiga (`64`) $\rightarrow$ `[12, 22, 25, 64]`


* **Hasil Akhir:** `[12, 22, 25, 64]`



---

#### C. Insertion Sort

* **Konsep:** Ambil satu elemen, lalu sisipkan ke posisi yang tepat di antara elemen-elemen sebelumnya yang sudah terurut (seperti mengurutkan kartu di tangan).

**Langkah demi Langkah (Contoh data: `[4, 3, 2, 1]`):**

* **Langkah 1 (Elemen `3`):**
1. Kunci target: `3`.
2. Bandingkan `3` dengan `4`. Karena $3 < 4$, geser `4` ke kanan.
3. Sisipkan `3` di depan $\rightarrow$ `[3, 4, 2, 1]`


* **Langkah 2 (Elemen `2`):**
1. Kunci target: `2`.
2. Bandingkan `2` dengan `4` dan `3`, geser keduanya ke kanan.
3. Sisipkan `2` di paling depan $\rightarrow$ `[2, 3, 4, 1]`


* **Langkah 3 (Elemen `1`):**
1. Kunci target: `1`.
2. Bandingkan `1` dengan `4`, `3`, dan `2`, geser semuanya ke kanan.
3. Sisipkan `1` di paling depan $\rightarrow$ `[1, 2, 3, 4]`


* **Hasil Akhir:** `[1, 2, 3, 4]`



---

#### D. Quick Sort

* **Konsep:** Menggunakan pendekatan *Divide and Conquer*. Pilih satu elemen sebagai **Pivot**, pisahkan data menjadi kelompok lebih kecil dan lebih besar dari pivot, lalu urutkan secara rekursif.

**Langkah demi Langkah (Contoh data: `[7, 2, 1, 6, 8, 5]`):**

* **Langkah 1 (Partisi Utama):**
1. Pilih Pivot tengah $\rightarrow$ `6`.
2. Kelompok Kiri (`< 6`): `[2, 1, 5]`
3. Kelompok Tengah (`== 6`): `[6]`
4. Kelompok Kanan (`> 6`): `[7, 8]`


* **Langkah 2 (Urutkan Kiri `[2, 1, 5]`):**
1. Pilih Pivot $\rightarrow$ `1`.
2. Kiri (`< 1`): `[]` | Tengah (`== 1`): `[1]` | Kanan (`> 1`): `[2, 5]`
3. Hasil bagian kiri terurut: `[1, 2, 5]`


* **Langkah 3 (Urutkan Kanan `[7, 8]`):**
1. Pilih Pivot $\rightarrow$ `8`.
2. Kiri (`< 8`): `[7]` | Tengah (`== 8`): `[8]` | Kanan (`> 8`): `[]`
3. Hasil bagian kanan terurut: `[7, 8]`


* **Langkah 4 (Penggabungan):**
* Gabungkan: `[1, 2, 5]` + `[6]` + `[7, 8]`
* **Hasil Akhir:** `[1, 2, 5, 6, 7, 8]`



---

### 3. Penutup: Manfaat Sorting di Dunia Riil

Mengapa programmer harus menguasai algoritma sorting padahal sudah ada fungsi bawaan di bahasa pemrograman?

1. **Efisiensi Sistem & Penghematan Resource:**
Di dunia nyata, aplikasi seperti **Mobile Legends** atau **E-Commerce (Shopee/Tokopedia)** menangani jutaan data setiap detik. Algoritma sorting yang salah bisa membuat aplikasi *lag*, boros baterai, atau bahkan *crash*. Pemilihan algoritma yang tepat (seperti *Quick Sort*) membuat sistem berjalan dalam hitungan milidetik.
2. **Pengalaman Pengguna (User Experience):**
Bayangkan bermain gim tanpa leaderboard yang terurut, atau belanja *online* tanpa fitur "Urutkan Harga Terendah". Sorting adalah fondasi utama yang membuat aplikasi terasa intuitif dan nyaman digunakan oleh manusia.
3. **Fondasi Algoritma Pencarian (Search Optimization):**
Pencarian data tercepat di dunia (*Binary Search*) **tidak akan bisa berjalan** jika datanya belum terurut. Menguasai sorting adalah kunci pertama untuk membangun fitur pencarian berkecepatan tinggi di gim maupun sistem *database*.

> **Pesan untuk Siswa:**
> *Sebagai calon Software Engineer dan Game Developer, logika sorting bukan sekadar menghafal rumus, melainkan melatih cara berpikir terstruktur untuk menyelesaikan masalah (*computational thinking*). Kode yang baik bukan hanya kode yang berjalan, tapi kode yang efisien!*
