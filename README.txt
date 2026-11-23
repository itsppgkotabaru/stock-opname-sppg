SISTEM STOCK OPNAME SPPG - SUPABASE EDITION

Paket ini menggunakan:
- Frontend: HTML, Bootstrap 5, JavaScript
- Login: Supabase Auth (email/password)
- Database virtual: Supabase PostgreSQL
- Tidak membutuhkan server PHP/MySQL.

CARA MENYIAPKAN:
1. Buat proyek di https://supabase.com/
2. Buka SQL Editor pada proyek Supabase.
3. Salin dan jalankan seluruh isi file supabase_schema.sql.
4. Buka Project Settings > API (atau Data API).
5. Salin Project URL dan anon/public key (jangan pernah gunakan service_role key di browser).
6. Buka index.html dengan editor teks.
7. Ganti:
   ISI_SUPABASE_PROJECT_URL dengan Project URL.
   ISI_SUPABASE_ANON_KEY dengan anon/public/publishable key.
8. Simpan index.html.
9. Upload index.html ke hosting statis seperti GitHub Pages, Netlify, atau Vercel (HTTPS).
10. Buka alamat website, daftar akun dengan email dan password.
11. Jika konfirmasi email aktif, verifikasi email terlebih dahulu.
12. Di Supabase SQL Editor jalankan:
   update public.profiles set role='admin' where email='EMAIL_ADMIN_ANDA';
13. Login dan mulai input master barang serta transaksi.

FITUR:
- Akun login dan pendaftaran melalui Supabase Auth
- Database cloud bersama
- Master bahan/barang, satuan bebas, batas minimum per barang
- Stok awal
- Transaksi masuk/keluar dengan tanggal
- Ringkasan harian: stok awal, masuk, keluar, sisa, status
- Status Aman hijau jika sisa >= minimum; Tidak aman merah jika sisa < minimum
- Laporan tanggal pilihan dan export CSV yang dapat dibuka di Excel

PENTING:
- Jangan pernah memasukkan service_role key ke index.html atau kode browser.
- SQL di atas memberi semua pengguna terautentikasi akses bersama untuk membaca dan mengelola barang/transaksi. Ini cocok untuk MVP internal, tetapi role belum membatasi tindakan secara berbeda. Sebelum penggunaan produksi, perlu kebijakan RLS berbasis role, audit log, validasi transaksi stok di sisi database, dan prosedur koreksi transaksi.
- Penghitungan saldo berjalan dari seluruh transaksi sampai tanggal laporan. Koreksi transaksi lama akan memengaruhi saldo tanggal setelahnya.
- Buat backup database berkala dan aktifkan konfirmasi email.
