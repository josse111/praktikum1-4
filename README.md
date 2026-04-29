# praktikum1-4
# Dokumentasi Lengkap Praktikum Pemrograman Web 2
## Sistem Informasi Portal Berita - CodeIgniter 4

Dokumentasi ini disusun sebagai laporan komprehensif pengerjaan Modul 1 hingga Modul 5. Proyek ini mendemonstrasikan transisi dari website statis menuju aplikasi web dinamis berbasis **MVC (Model-View-Controller)**.

---

## 👤 IDENTITAS SAYA :
* **Nama:** Zaki Fauzan Akhbari
* **NIM:** 312410348
* **Kelas:** TI.24.A4/I241D
* **Matkul:** Pemrograman Website 2

---

## 🛠️ Analisis Struktur Modul Praktikum

### 🟢 Modul 1: Fondasi MVC & Routing
Pada tahap awal, fokus utama adalah memindahkan paradigma PHP Native ke Framework.
* **Logika:** User meminta URL -> `Routes.php` mengarahkan ke `Controller` -> Controller memanggil `View`.
* **Implementasi:** Membuat `Controller Page.php` untuk menangani halaman statis (Home, About, Contact).
* **Pelajaran Penting:** Memahami bahwa logika bisnis tidak boleh diletakkan di dalam View.

### 🔵 Modul 2: CRUD & Interaksi Database
Tahap ini mengubah website menjadi dinamis dengan kemampuan mengelola data di MySQL.
* **Logika:** Membuat `ArtikelModel.php` sebagai jembatan ke tabel `artikel`.
* **Fitur Admin:** * **Create:** Form untuk input berita baru.
    * **Read:** Menampilkan data dari database ke dalam tabel HTML.
    * **Update:** Mengambil data berdasarkan ID untuk diedit kembali.
    * **Delete:** Menghapus data permanen dari database.
* **Konfigurasi:** Mengatur koneksi database pada file `.env`.

### 🟡 Modul 3: Templating (View Layout & View Cell)
Menerapkan prinsip **DRY (Don't Repeat Yourself)** agar kode lebih bersih.
* **View Layout:** Menggunakan satu file induk `layout/main.php`. Halaman lain hanya perlu "mengisi" bagian konten menggunakan `$this->extend()`.
* **View Cell:** Membuat komponen modular `ArtikelTerkini`. Komponen ini bisa dipanggil di halaman mana pun tanpa harus menulis ulang query database di setiap Controller.
* **Manfaat:** Jika ada perubahan pada Header atau Footer, cukup edit satu file saja.

### 🔴 Modul 4: Autentikasi & Security Filter
Melindungi area sensitif (Dashboard Admin) dari akses tanpa izin.
* **Alur Login:** Validasi `userpassword` menggunakan Session.
* **Filters:** Implementasi `AuthFilter.php`. Jika user mencoba akses `/admin` tanpa login, sistem otomatis menendang balik ke halaman `/login`.
* **Database:** Pembuatan tabel `user` untuk menyimpan kredensial admin.

### 🟣 Modul 5: Optimasi UX (Pagination & Searching)
Menyempurnakan antarmuka saat data sudah berjumlah banyak.
* **Pagination:** Mengganti `findAll()` menjadi `paginate(10)`. Ini mencegah *lag* pada browser jika data mencapai ribuan.
* **Searching:** Menggunakan metode `like()` pada query SQL untuk memfilter judul artikel berdasarkan kata kunci dari user.
* **Persistence:** Menggunakan `pager->only(['q'])` agar saat user pindah ke halaman 2, hasil pencarian kata kunci 'q' tidak hilang.

---

## 💻 Cara Instalasi Proyek

1.  **Clone & Setup:**
    ```bash
    git clone [https://github.com/josse111/Lab7Web.git](https://github.com/josse111/Lab7Web.git)
    cd Lab7Web
    ```
2.  **Database:**
    * Buat database bernama `lab_ci4`.
    * Import file `.sql` yang ada di folder `database/`.
3.  **Environment:**
    * Rename `env` menjadi `.env`.
    * Atur `database.default.username` dan `database.default.password` sesuai XAMPP kamu.
4.  **Run:**
    ```bash
    php spark serve
    ```

---

## DI KARENAKAN FILE NYA TIDAK BISA DI UPLOAD SEMUA KE DALAM GITHUB, JADI SAYA MEMBUAT LINK UNTUK MENGAKSES SEMUA FILE NYA :
**https://drive.google.com/drive/folders/1Ykv6ji9g2z9rLGGT300JYbav39uYaoRM?usp=sharing**

## 📸 Bukti Hasil Praktikum

1. **Tampilan Home User:**
<img width="1765" height="1025" alt="Screenshot 2026-04-27 092018" src="https://github.com/user-attachments/assets/cf8febac-a59e-48af-b150-a145820ec274" />


**TAMPILAN ARTIKEL:**
<img width="1501" height="954" alt="Screenshot 2026-04-27 092223" src="https://github.com/user-attachments/assets/118c19fe-5026-48b6-9094-5247b9bac2d1" />

**TAMPILAN CONTACT:**
<img width="1490" height="973" alt="Screenshot 2026-04-27 092242" src="https://github.com/user-attachments/assets/ecb0efb6-0cd5-4b46-85d6-97fbe085d53e" />



2. **Dashboard Admin:**
<img width="1577" height="841" alt="Screenshot 2026-04-27 092257" src="https://github.com/user-attachments/assets/a85f3d6f-1eb8-4f6d-a447-424136d9b39d" />

**TAMPILAN TAMBAH ARTIKEL:**
<img width="1515" height="965" alt="Screenshot 2026-04-27 092342" src="https://github.com/user-attachments/assets/6007a34e-5aad-4208-b97a-16cd347dec88" />

**TAMPILAN UBAH ARTIKEL**
<img width="1531" height="972" alt="Screenshot 2026-04-27 092322" src="https://github.com/user-attachments/assets/414f6e14-6241-4045-9fc0-2c5d22862444" />


4. **Halaman Login:**
<img width="1493" height="873" alt="Screenshot 2026-04-27 092402" src="https://github.com/user-attachments/assets/6bbfb40f-4161-4120-9129-6d0e3bf0a5e9" />


---
**Status Proyek:** Selesai (Modul 1-4) ✅
