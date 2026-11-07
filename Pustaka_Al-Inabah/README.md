# Pustaka Al-Inabah

Website perpustakaan digital untuk SMP IT & SMK Al-Inabah Ponorogo.

## Teknologi dan konfigurasi
- Frontend HTML, CSS, dan JavaScript.
- Supabase Auth untuk akun siswa/admin.
- Tabel `public.buku` untuk metadata koleksi.
- Supabase Storage bucket privat `buku-digital` untuk sampul dan PDF.
- PDF dibuka melalui signed URL setelah pengguna login.

Konfigurasi browser memakai Supabase publishable key. Jangan pernah menaruh `service_role key`, password admin, atau rahasia server di file frontend.

## Menjalankan secara lokal
1. Unduh/clone repository.
2. Buka folder `Pustaka_Al-Inabah`.
3. Jalankan melalui server lokal statis (misalnya Live Server), bukan dengan mengandalkan file lokal.
4. Pastikan konfigurasi Supabase dan kebijakan RLS/Storage sudah sesuai.

## Pengelolaan admin
Tidak ada akun admin demo atau password bawaan di kode. Akun admin harus dibuat melalui Supabase Auth, lalu identitas UUID pengguna yang sesuai harus dimasukkan ke `public.admin_users` melalui proses tepercaya di Supabase (misalnya SQL Editor oleh pengelola proyek). Jangan memberikan hak admin kepada akun siswa melalui frontend.

## Status fitur pada branch percobaan
- Autentikasi siswa/admin: terhubung ke Supabase Auth.
- Koleksi buku: membaca metadata dari `public.buku`.
- Tambah/edit/hapus buku: memerlukan role admin dan kebijakan RLS yang benar.
- PDF: disimpan pada bucket privat dan dibuka setelah login.
- Sampul: saat ini memakai signed URL; karena bucket privat, pratinjau sampul pada pengunjung anonim dapat tidak tampil sampai kebijakan/penyimpanan sampul publik disiapkan secara terpisah.
- Misi, poin, riwayat, berita: masih menggunakan penyimpanan lokal browser, belum tersinkron antarperangkat.
- Daftar pengguna dan statistik pembaca: belum dihubungkan ke tabel profil pengguna.
- Asisten AI: masih pencarian koleksi berbasis kata kunci, bukan layanan AI generatif.

## Sebelum rilis
Branch ini masih untuk pengujian. Belum boleh digabung ke `main` atau dipublikasikan sebelum:
1. Admin dibuat dan diuji dengan aman.
2. RLS dan Storage diuji memakai akun siswa dan admin terpisah.
3. Alur daftar, login, logout, CRUD buku, dan akses PDF diuji.
4. Fitur misi, berita, dan statistik yang masih lokal diputuskan untuk disimpan di server.
5. Website diuji pada desktop dan ponsel.
