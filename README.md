📘 Panduan Lengkap: Cara Menjalankan Sistem Verifikasi Dokumen di Komputer Anda
🎯 Untuk Siapa Panduan Ini?
Untuk Anda yang baru belajar pemrograman web, tidak familiar dengan XAMPP/PHP, atau ingin mencoba sistem ini dari nol.

🛠️ Langkah 1: Instalasi XAMPP (Web Server Lokal)
Apa itu XAMPP?
XAMPP adalah paket yang berisi:

Apache (web server)

PHP (bahasa pemrograman sistem ini)

MySQL (database, tidak digunakan di sistem ini)

phpMyAdmin (tools database)

Cara Install XAMPP:
Untuk Windows:
Download XAMPP dari situs resmi:

Kunjungi: https://www.apachefriends.org

Klik "Download" untuk Windows

Jalankan installer yang sudah didownload

Klik Next > Next

Pilih folder instalasi: Biarkan default (C:\xampp)

Centang semua komponen (Apache, MySQL, PHP, phpMyAdmin)

Selesaikan instalasi

Tunggu sampai selesai

Jangan centang "Learn more about Bitnami"

Klik Finish

Buka XAMPP Control Panel

Cari di Start Menu: "XAMPP Control Panel"

Atau buka C:\xampp\xampp-control.exe

Untuk macOS:
Download XAMPP dari situs yang sama

Drag aplikasi ke folder Applications

Buka dari Applications folder

Untuk Linux:
bash
sudo apt-get update
sudo apt-get install apache2 php libapache2-mod-php mysql-server phpmyadmin
🚀 Langkah 2: Menjalankan XAMPP
Windows/macOS:
Buka XAMPP Control Panel

Start Apache (klik tombol "Start" di sebelah Apache)

Jika berhasil, background akan hijau

Jika ada error port 80/443, biasanya karena Skype/Teams. Tutup aplikasi tersebut.

Cek apakah XAMPP berjalan:
Buka browser (Chrome/Firefox)

Ketik: http://localhost

Jika muncul halaman XAMPP, berarti sukses!

📂 Langkah 3: Menyiapkan File Proyek
Cara 1: Download dari GitHub (Jika tersedia)
bash
1. Download ZIP dari GitHub
2. Extract ZIP ke folder
3. Copy folder "hashing-dokumen" ke:
   - Windows: C:\xampp\htdocs\
   - macOS: /Applications/XAMPP/htdocs/
   - Linux: /var/www/html/
Cara 2: Buat Manual (Jika tidak ada file)
Buka folder htdocs:

text
C:\xampp\htdocs\
Buat folder baru dengan nama hashing-dokumen

Di dalam folder tersebut, buat 3 file:

upload.php

verify.php

style.css

Copy-paste kode dari dokumen yang diberikan ke masing-masing file

🖥️ Langkah 4: Membuat File Manual (Step-by-Step)
File 1: style.css
Buka Notepad atau text editor

Copy semua kode CSS dari halaman 1-2 dokumen

Save dengan nama: style.css

Pastikan ekstensi .css, bukan .css.txt

File 2: upload.php
Buat file baru

Copy kode dari halaman 2-3 dokumen (baris 1-47)

Save dengan nama: upload.php

File 3: verify.php
Buat file baru

Copy kode dari halaman 3-4 dokumen (baris 1-52)

Save dengan nama: verify.php

File 4: Buat folder storage
Di dalam folder hashing-dokumen, klik kanan → New → Folder

Beri nama: storage

✅ Langkah 5: Testing Sistem
Test 1: Akses Halaman
Pastikan XAMPP Apache sedang running (hijau)

Buka browser

Ketik: http://localhost/hashing-dokumen/upload.php

Jika muncul form upload, berarti sukses!

Test 2: Coba Upload Dokumen
Di halaman upload, klik "Choose File"

Pilih file PDF/DOCX/PPTX (bisa dokumen apapun)

Klik "Register Document"

Jika muncul hash SHA-256, berarti berhasil!

Test 3: Verifikasi Dokumen
Buka: http://localhost/hashing-dokumen/verify.php

Upload file yang sama

Harus muncul "DOKUMEN ASLI"

Coba upload file berbeda

Harus muncul "DOKUMEN PALSU"

⚠️ Solusi Masalah Umum
Masalah 1: Localhost tidak bisa diakses
text
Solusi:
1. Cek XAMPP Control Panel, pastikan Apache hijau
2. Buka Command Prompt, ketik: ping localhost
3. Jika tidak bisa, coba: 127.0.0.1/hashing-dokumen/upload.php
Masalah 2: Error saat upload file
text
Solusi:
1. Pastikan folder "storage" ada
2. Cek permission folder (klik kanan → Properties → Security)
3. Beri full control untuk folder "storage"
Masalah 3: File tidak bisa disimpan
text
Solusi:
1. Buka XAMPP Control Panel
2. Klik "Shell" di sebelah kanan
3. Ketik: chmod 777 /opt/lampp/htdocs/hashing-dokumen/storage
   (untuk Linux/macOS)
Masalah 4: Tampilan aneh/berantakan
text
Solusi:
1. Pastikan file style.css ada
2. Buka browser, tekan F12 → Console
3. Lihat apakah ada error loading CSS
4. Cek path CSS di HTML: <link rel="stylesheet" href="style.css">
🎓 Penjelasan Sederhana untuk Pemula
Apa yang sebenarnya terjadi?
Upload file → Sistem baca isi file → Hitung "sidik jari digital" (hash)

Simpan sidik jari ke original_hash.txt

Verifikasi → Hitung sidik jari file baru → Bandingkan dengan yang tersimpan

Jika sama → Dokumen asli

Jika beda → Dokumen palsu/berubah

Analoginya:
File = Dokumen fisik

Hash = Cap/stempel basah

Verifikasi = Cocokkan cap dengan database cap resmi

📱 Versi Alternatif (Tanpa XAMPP)
Untuk yang tidak mau install XAMPP:
Option 1: Online PHP Tester
Kunjungi: https://phptester.net/

Copy kode PHP ke editor online

Catatan: Sistem file tidak akan bekerja penuh

Option 2: PHP Built-in Server
Install PHP saja (bukan XAMPP)

Buka Command Prompt di folder proyek

Ketik: php -S localhost:8000

Akses: http://localhost:8000/upload.php

🔧 Tips untuk Development Lanjutan
Jika mau modifikasi kode:
Gunakan Visual Studio Code (gratis) atau Notepad++

Untuk debug, tambahkan di kode PHP:

php
error_reporting(E_ALL);
ini_set('display_errors', 1);
Jika mau deploy ke hosting:
Pilih hosting yang support PHP (Hostinger, Niagahoster, dll)

Upload semua file ke public_html

Pastikan folder storage writable

Akses via: namadomain.com/upload.php

📚 Sumber Belajar Tambahan
Belajar PHP Dasar: W3Schools PHP Tutorial

Tutorial XAMPP: YouTube: Cara Install XAMPP

GitHub untuk Pemula: GitHub Guides

🆘 Butuh Bantuan?
Langkah-langkah jika stuck:
Screenshot error yang muncul

Cari di Google dengan kata kunci error

Cek video tutorial di YouTube: "Install XAMPP Windows 10"

Tanya di forum: Stack Overflow, Discord programmer

🎉 Selamat!
Jika semua berjalan lancar, Anda sekarang memiliki sistem verifikasi dokumen yang berfungsi penuh di komputer lokal Anda!

Coba-coba:

Upload berbagai jenis file

Modifikasi file yang sudah diupload, lalu verifikasi

Coba dengan file besar (>100MB)

📍 Ingat: Sistem ini hanya untuk edukasi dan lingkungan lokal. Untuk produksi, perlu pengembangan lebih lanjut!

Happy Coding! 🚀

