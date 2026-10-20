Materi **Pendalaman Database (Basis Data)** ini dirancang khusus untuk siswa SMK Jurusan Perangkat Lunak dan Gim (PLG). Setelah menguasai logika algoritma, pemahaman basis data yang kuat adalah kunci utama dalam membangun aplikasi dan gim skala besar.

---

## Modul Pendalaman Materi: Basis Data (Database)

### 1. Pengantar & Konsep Dasar Basis Data

**Database** adalah kumpulan data yang terstruktur dan saling berhubungan, yang disimpan secara digital dan dikelola menggunakan **DBMS** (*Database Management System*) seperti MySQL, PostgreSQL, atau SQLite.

Dalam dunia nyata dan industri gim/pengembangan perangkat lunak:

* **Sistem Informasi (E-Commerce/Media Sosial):** Menyimpan data pengguna, riwayat transaksi, katalog produk, dan komentar.
* **Gim (Online/Offline):** Menyimpan profil pemain, data inventaris, statistik status (*HP, Mana, Level*), serta *save state* permainan.

---

### 2. Jenis-Jenis Database Utama

| Kategori | Deskripsi | Contoh Teknologi | Penggunaan Ideal |
| --- | --- | --- | --- |
| **Relational (RDBMS)** | Data disimpan dalam bentuk tabel (baris & kolom) yang saling terhubung melalui relasi. Menggunakan bahasa **SQL**. | MySQL, PostgreSQL, SQLite | Sistem Keuangan, E-Commerce, Sistem Akademik, Leaderboard Gim. |
| **Non-Relational (NoSQL)** | Data disimpan tanpa skema yang kaku (bisa berupa dokumen JSON, key-value, atau grafik). | MongoDB, Redis, Firebase Firestore | *Real-time chat*, data inventaris gim yang dinamis, sistem *caching*. |

---

### 3. Komponen Utama RDBMS & Relasi Data

#### A. Struktur Tabel

* **Primary Key (PK):** Kolom unik yang menjadi identitas tunggal untuk setiap baris data (contoh: `id_pemain`, `nisn`).
* **Foreign Key (FK):** Kolom yang menghubungkan tabel tersebut dengan *Primary Key* di tabel lain.

#### B. Jenis-Jenis Relasi (Relationships)

1. **One-to-One (1:1):** Satu baris data di Tabel A hanya terhubung ke satu baris data di Tabel B.
* *Contoh:* 1 Akun Pemain $\rightarrow$ 1 Profil Detail Pemain.


2. **One-to-Many (1:M):** Satu baris data di Tabel A bisa terhubung ke banyak baris data di Tabel B.
* *Contoh:* 1 Pemain $\rightarrow$ Banyak Item Inventaris.


3. **Many-to-Many (M:N):** Banyak baris data di Tabel A terhubung ke banyak baris di Tabel B (membutuhkan *tabel penghubung / junction table*).
* *Contoh:* Banyak Karakter $\rightarrow$ Bisa mempelajari Banyak *Skill*.



---

### 4. Perintah Dasar Structured Query Language (SQL)

SQL dibagi menjadi beberapa kelompok perintah utama:

#### A. DDL (Data Definition Language) - Membangun Struktur Database

Perintah untuk membuat, mengubah, atau menghapus tabel/database.

* `CREATE DATABASE nama_db;`
* `CREATE TABLE pemain (id_pemain INT PRIMARY KEY, nama VARCHAR(50), level INT);`
* `DROP TABLE pemain;`

#### B. DML (Data Manipulation Language) - Mengelola Data

Perintah untuk menambah, membaca, memperbarui, dan menghapus isi data (**CRUD**).

```sql
-- 1. Create (Menambah Data)
INSERT INTO pemain (id_pemain, nama, level) VALUES (1, 'ShadowNinja', 15);

-- 2. Read (Membaca Data)
SELECT nama, level FROM pemain WHERE level > 10 ORDER BY level DESC;

-- 3. Update (Mengubah Data)
UPDATE pemain SET level = 16 WHERE id_pemain = 1;

-- 4. Delete (Menghapus Data)
DELETE FROM pemain WHERE id_pemain = 1;

```

---

### 5. Konsep Normalisasi Data

**Normalisasi** adalah teknik merancang basis data agar tidak terjadi redundansi (penumpukan data yang sama) dan menjaga konsistensi data.

* **1NF (First Normal Form):** Memastikan setiap kolom hanya berisi nilai tunggal (tidak ada data bertumpuk/array dalam satu sel).
* **2NF (Second Normal Form):** Memastikan semua kolom non-PK bergantung sepenuhnya pada *Primary Key*.
* **3NF (Third Normal Form):** Memastikan tidak ada ketergantungan antar kolom non-PK (*transitive dependency*).

---

### 6. Penutup: Mengapa Database Sangat Vital?

1. **Persistensi Data (Data Persistence):** Tanpa database, semua progres pemain atau data transaksi akan hilang begitu aplikasi/gim ditutup.
2. **Keamanan Data:** Database menyediakan hak akses (*user privilege*) dan sistem enkripsi untuk melindungi data sensitif seperti *password* dan transaksi keuangan.
3. **Peluang Karir:** Penguasaan database membuka peluang karir sebagai *Backend Developer*, *Database Administrator (DBA)*, maupun *Data Engineer*.
