# CampusHub 🎓📸

Selamat datang di **CampusHub**, platform berbagi momen kampus yang intuitif dan andal. Dibangun khusus untuk komunitas kampus, CampusHub memudahkan setiap anggota untuk mengabadikan, menyimpan, dan menampilkan foto-foto kenangan terbaik mereka.

---

## Pre-requisite

1. Install Docker Engine & Docker Compose
2. Unduh File Docker dari [Drive ini](https://drive.google.com/drive/u/1/folders/1EBlpWSUUwHYn4ze_LGonflacQlYoLzfA)
3. Clone Project dari repository CampusHub-Application

## Cara Menjalankan Aplikasi Lokal dengan Docker Compose

1. Pastikan Docker Engine dan Docker Compose sudah terinstall di sistem Anda
2. Clone repository dengan perintah:

   ```bash
   git clone https://github.com/CampusHub-Application/User-Interface
   git clone https://github.com/CampusHub-Application/API
   git clone https://github.com/CampusHub-Application/Reverse-Proxy
   ```
   
4. Salin file `.env.example` pada direktori User-Interface menjadi `.env` dan sesuaikan konfigurasi.
   ```bash
   cp User-Interface/.env.example .env
   ```
      
   Isikan .env dengan konfigurasi yang sesuai.
   ```
   VITE_API_URL={Sesuaikan dengan IP dan PORT container Reverse Proxy anda} (localhost:1234)
   VITE_SANCTUM_URL={Sesuaikan dengan IP dan PORT container Reverse Proxy anda}/sanctum/csrf-cookie (localhost:1234/sanctum/csrf-cookie)
   ```
6. Salin file `.env.example` pada direktori API menjadi `env_api` dan sesuaikan konfigurasi.
      ```bash
   cp API/.env.example env_api
   ```
   
   Isikan env_api dengan konfigurasi yang sesuai.
   ```
   APP_URL={Sesuaikan dengan IP dan PORT container API anda} (localhost:8000)
   DB_HOST={Sesuaikan dengan IP database anda} (172.17.0.1)
   DB_PORT={Sesuaikan dengan Port database anda} (3306}
   DB_DATABASE={Sesuaikan dengan nama database anda}
   DB_USERNAME={Sesuaikan dengan username database anda}
   DB_PASSWORD={Sesuaikan dengan password database anda}
   ```
8. Buat file baru bernama env_db sebagai berikut.
   ```bash
   nano env_db
   ```

   Isikan env_db dengan konfigurasi yang sesuai.
   ```
   MARIADB_DATABASE={Sesuaikan dengan nama database anda}
   MARIADB_USER={Sesuaikan dengan username database anda}
   MARIADB_PASSWORD={Sesuaikan dengan password database anda}
   MARIADB_RANDOM_ROOT_PASSWORD=true
   ```
9. Jalankan aplikasi dengan Docker Compose:
   docker compose up -d
   
10. Akses aplikasi melalui browser di `http://{sesuaikan dengan IP container Reverse Proxy anda}:1234`
    
12. Untuk menghentikan aplikasi:
    docker compose down

## Penjelasan Singkat

- Dockerfile: Membuatkan image custom untuk aplikasi CampusHub.
- Docker-Compose: Mengatur deployment semua container.

## Struktur dan Fungsi Komponen

### Backend

- **API Service**: Berperan sebagai penyedia endpoint RESTful API untuk komunikasi dengan frontend.
- **Database**: Menggunakan MariaDB untuk penyimpanan data.

### Frontend

- **Web Interface**: Antarmuka pengguna berbasis web menggunakan React.js
- **Styling**: Tailwind CSS untuk styling aplikasi.
  
### Infrastruktur

- **Nginx**: Web server sebagai reverse proxy
- **Docker**: Kontainerisasi untuk memudahkan deployment

### Komponen Docker

- **ui**: Container utama yang menjalankan aplikasi CampusHub
- **api**: Container yang menyediakan layanan API
- **db**: Container database MySQL untuk penyimpanan data
- **proxy**: Container web server sebagai reverse proxy

### Alur Kerja

1. Request dari pengguna diterima oleh Nginx
2. Nginx meneruskan request ke container aplikasi yang sesuai
3. Aplikasi memproses request dan berinteraksi dengan database jika diperlukan
4. Response dikirimkan kembali ke pengguna melalui Nginx

## ✨ Fitur Utama

**1. 👥 Manajemen Pengguna Canggih**  
- **Role-Based Access Control**: Dua level akses, **admin** 🔑 dan **non-admin** 🧑‍🎓, memastikan kontrol yang tepat.  
- **Admin Panel**: Tambah ➕, ubah ✏️, atau hapus ❌ akun dengan sekali klik.  
- **Profil Pribadi**: Non-admin dapat mengubah nama, foto profil, dan password tanpa mengganggu data pengguna lain.

**2. 📤 Upload & 💾 Penyimpanan Foto Handal**  
- **Upload Cepat**: Dukungan drag-and-drop langsung dari browser.  
- **Penyimpanan Terdistribusi**: File gambar disimpan di EC2 Volume untuk performa tinggi.  
- **Metadata Rinci**: Setiap unggahan mencatat `user_id`, URL file, dan timestamp ⏰ di AWS RDS.

**3. 🌟 Profil Publik Dinamis**  
- **Galeri Otomatis**: Tampilkan semua foto di halaman profil pengguna dengan layout responsif.  
- **URL Publik**: Bagikan tautan 🔗 ke teman dan kolega.

**4. 🔒 Otentikasi & Keamanan Terpercaya**  
- **Login Modern**: Mendukung **session-based** authentication.  
- **Proteksi Akses**: Middleware verifikasi role mencegah tindakan yang semena-mena.

---

## ⚡ Cara Penggunaan Aplikasi

1. **📝 Daftar & Login**: Pengguna mendaftar, memilih role, lalu masuk ke dashboard.  
2. **📷 Unggah Foto**: Klik tombol "Upload" untuk memilih file, lalu sistem memproses dan menyimpan.  
3. **🌐 Lihat Profil**: Foto muncul otomatis di profil; bagikan tautan publik untuk memamerkan momen Anda.

---
