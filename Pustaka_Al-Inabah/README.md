# Pustaka Al-Inabah

Website perpustakaan digital sekolah dengan tampilan teal-putih.

## Menjalankan
1. Ekstrak ZIP.
2. Buka `index.html` menggunakan browser modern (Chrome/Edge).
3. Login admin untuk mencoba dashboard.

## Akun admin demo
- Username: `Happyadmindigy`
- Password: `MinDygipusinabah`

## Fitur
- Beranda, pencarian, statistik koleksi, berita.
- Koleksi buku dengan rak Fiksi dan Non-Fiksi.
- Login admin dan pendaftaran/login pengguna.
- Pembaca PDF (pengguna harus login; admin dapat langsung membaca setelah login admin).
- Misi literasi, pemeriksaan jawaban, poin, riwayat, dan lencana.
- Admin mengelola buku, metadata DDC, sampul, PDF, misi, pengguna, dan berita.
- Asisten pencarian koleksi berbasis kata kunci.

## Catatan penting sebelum dipakai sungguhan
Paket ini adalah **prototype front-end** yang menyimpan data pada `localStorage` browser. Artinya data hanya tersimpan pada browser/perangkat yang sama, belum tersinkron untuk seluruh siswa. Berkas yang diunggah dibatasi 8 MB agar penyimpanan browser tetap ringan.

Kredensial admin pada prototype berada di JavaScript dan dapat dilihat dari browser. **Jangan gunakan kredensial ini untuk sistem produksi.** Untuk penggunaan sekolah, sambungkan ke backend seperti Supabase:
- autentikasi admin/siswa di server (jangan menyimpan password mentah);
- tabel buku, misi, pengguna, berita, riwayat misi;
- Supabase Storage untuk sampul dan PDF;
- Row Level Security agar hanya admin dapat mengelola data;
- validasi role admin dari server, bukan dari kode browser.

Asisten AI di paket ini adalah pencarian koleksi berbasis kata kunci, bukan model AI yang terhubung ke layanan eksternal. Tautan berita contoh perlu diganti admin dengan berita yang benar-benar dipilih.
