Anggota Kelompok:
- Dimas Setiawan
- Rimbhiatho Aurindra
- M Araka Ridhwan Akbar

# Aplikasi Restoran Nusantara (Kasir & Admin)

Aplikasi web kasir dan panel admin yang dirancang untuk mengelola operasional restoran dengan berbagai macam menu khas Indonesia.

---

Fitur Aplikasi

Bagian Kasir (Dioperasikan oleh Staf)
-   **Login Staf:** Sistem login terpusat untuk kasir dan admin.
-   **Pemesanan Atas Nama:** Mengidentifikasi pesanan berdasarkan nama pelanggan, cocok untuk alur "pesan & bayar di kasir".
-   **Tampilan Menu Dinamis:**
    -   Produk ditampilkan dalam grid yang responsif.
    -   Navigasi menu berdasarkan kategori (Makanan Berat, Cemilan, Minuman, dll.).
    -   Info stok real-time ditampilkan di setiap kartu produk dengan indikator warna (menipis/habis).
-   **Keranjang Pesanan Interaktif:**
    -   Menambah dan mengurangi kuantitas item.
    -   Validasi otomatis untuk mencegah pemesanan melebihi stok.
    -   Total harga dan jumlah item terupdate secara real-time.
-   **Fitur Pencarian:** Mencari produk dengan cepat berdasarkan nama.
-   **Proses Pembayaran:** Alur pembayaran yang terintegrasi langsung di halaman kasir untuk memproses transaksi.
-   **Sesi Kasir:** Menampilkan nama kasir yang sedang login dan menyediakan opsi logout.

 Bagian Admin (Dilindungi Login)
-   **Dashboard Ringkas:** Menampilkan data penjualan kunci (Pendapatan, Transaksi, Item Terjual) dan stok kritis untuk hari ini, dilengkapi grafik pendapatan dan produk terlaris.
-   **Manajemen Menu (CRUD):** Fungsi penuh untuk Tambah, Lihat, Edit, dan Hapus menu beserta detailnya (nama, kategori, harga, stok, deskripsi, gambar).
-   **Manajemen Kategori (CRUD):** Mengelola semua kategori menu.
-   **Manajemen Staf (CRUD):** Mengelola akun staf dengan peran (Admin/Kasir).
-   **Laporan Penjualan Detail:** Menampilkan riwayat semua transaksi dengan fitur filter berdasarkan rentang tanggal.

---

 Struktur Rute (Routes) API

Semua interaksi antara frontend dan backend terjadi melalui API di folder `/api/`.

| Metode | URL Endpoint                   | Aksi                                                                  |
|:-------|:-------------------------------|:----------------------------------------------------------------------|
| POST   | `/api/login_process.php`       | Memverifikasi kredensial staf dan membuat session.                    |
| POST   | `/api/logout_process.php`      | Menghancurkan session dan logout.                                     |
| GET    | `/api/get_products.php`        | Mengambil daftar semua produk yang tersedia.                          |
| GET    | `/api/get_categories.php`      | Mengambil daftar semua kategori menu.                                 |
| POST   | `/api/process_transaction.php` | Memproses pesanan dari kasir, mengurangi stok, dan menyimpan transaksi. |
| GET    | `/api/get_dashboard_data.php`  | Mengambil data ringkasan dan chart untuk dashboard admin.             |
| GET    | `/api/get_report_data.php`     | Mengambil riwayat transaksi (mendukung filter tanggal via query string). |
| POST   | `/api/crud_product.php`        | Menangani aksi **tambah**, **update**, dan **hapus** produk.               |
| POST   | `/api/crud_categories.php`     | Menangani aksi **tambah**, **update**, dan **hapus** kategori.             |
| GET/POST| `/api/crud_staf.php`           | Menangani aksi **lihat**, **tambah**, **update**, dan **hapus** staf.     |
| GET/POST| `/api/crud_pengaturan.php`     | Menangani aksi **baca** dan **simpan** pengaturan restoran.            |
