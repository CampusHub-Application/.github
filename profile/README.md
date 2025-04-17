# CampusHub

## Caption ini ditulis oleh ChatGPT, yang biasa buat caption lagi sibuk melamun

Selamat datang di **CampusHub**, platform berbagi momen kampus yang intuitif dan andal. Dibangun khusus untuk komunitas kampus, CampusHub memudahkan setiap anggota untuk mengabadikan, menyimpan, dan menampilkan foto-foto kenangan terbaik mereka.

---

## Daftar Isi

1. [Fitur Utama](#fitur-utama)
2. [Cara Kerja Singkat](#cara-kerja-singkat)
3. [Mengapa CampusHub?](#mengapa-campushub)
4. [Teknologi yang Digunakan](#teknologi-yang-digunakan)
5. [Kontak & Dukungan](#kontak--dukungan)

---

## Fitur Utama

**1. Manajemen Pengguna Canggih**  
- **Role-Based Access Control**: Dua level akses, **admin** dan **non-admin**, memastikan kontrol yang tepat.  
- **Admin Panel**: Tambah, ubah, atau hapus akun dengan sekali klik.  
- **Profil Pribadi**: Non-admin dapat mengubah nama, foto profil, dan password tanpa mengganggu data pengguna lain.

**2. Upload & Penyimpanan Foto Handal**  
- **Upload Cepat**: Dukungan drag-and-drop langsung dari browser.  
- **Penyimpanan Terdistribusi**: File gambar disimpan di EC2 Volume untuk performa tinggi.  
- **Metadata Rinci**: Setiap unggahan mencatat `user_id`, URL file, dan timestamp di AWS RDS.

**3. Profil Publik Dinamis**  
- **Galeri Otomatis**: Tampilkan semua foto di halaman profil pengguna dengan layout responsif.  
- **URL Publik**: Setiap profil memiliki tautan publik yang dapat dibagikan ke teman dan kolega.

**4. Otentikasi & Keamanan Terpercaya**  
- **Login Modern**: Mendukung **JWT** dan **session-based** authentication.  
- **Proteksi Akses**: Middleware verifikasi role mencegah tindakan tidak sah.

---

## Cara Kerja Singkat

1. **Daftar & Login**: Pengguna mendaftar, memilih role, lalu masuk ke dashboard.  
2. **Unggah Foto**: Klik tombol "Upload" untuk memilih file, lalu sistem memproses dan menyimpan.  
3. **Lihat Profil**: Foto muncul otomatis di profil; bagikan tautan publik untuk memamerkan momen Anda.

---

## Mengapa CampusHub?

- **Skalabilitas AWS**: Memanfaatkan EC2 dan RDS untuk ketersediaan tinggi dan kemudahan skala.  
- **Antarmuka Ramah Pengguna**: Desain minimalis, cepat, dan mudah dipahami.  
- **Keamanan Data**: Enkripsi data sensitif dan kontrol akses granular.

---

## Teknologi yang Digunakan

- **Frontend**: React (HTML/CSS/JS)  
- **Backend**: Node.js + Express  
- **Database**: MySQL di AWS RDS  
- **Storage**: EC2 Volume  
- **Deployment**: AWS EC2 (t2.micro) dengan Nginx/PM2

---

## Kontak & Dukungan

Butuh bantuan? Kirim email ke **support@campushub.example.com** atau bergabung dengan kanal Slack kami untuk diskusi dan laporan bug.


> Bersama CampusHub, abadikan dan bagikan setiap cerita kampus dengan mudah!
