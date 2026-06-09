# Analisis Perbaikan

Nama: [Muhamad Faizal Khabibi]   

NIM: [H1H024003]

---

## Permasalahan 1

Docker Compose gagal dijalankan dan muncul error YAML.
Yang disebabkan keyword services tidak diakhiri tanda titik dua (:).
services -> services:

---

## Permasalahan 2

Terjadi beberapa kesalahan penulisan apache pada file docker web1 daan web 3.
web-1  
php:8.2-apach

web-3  
php:8.2-apche

---

## Permasalahan 3

### Gejala
Web1 gagal terhubung ke database.
Yang disebabkan DB_HOST menggunakan mysql padahal nama service database adalah db.
Maka dari itu dilakukan peerubahan pada DB_HOST 
DB_HOST=mysql -> DB_HOST=db

---

## Permasalahan 4

### Gejala
Web2 gagal melakukan autentikasi database.
Disebabkan oleh Password database salah.
DB_PASS=wrongpassword dimana seharusnya -> DB_PASS=student123

---

## Permasalahan 5   

### Gejala   

Container web3 gagal dibuat dikarenakan kesalahan penulisan alamat folder.   
Yang seharusnya ./web3 tertulis ./web33 sehingga harus dilakukan perbaikan agar web 3 bisa bejalan.

---

## Permasalahan 6   

### Gejala   

Volume database tidak terdeteksi yang disebabkan nama volume yang gak konsisten antara defenisi dan penggunaannya. Maka dari itu perlu dilakukan penyamaan nama volume menjadi db_data.

## Permasalahan 7

### Gejala
Nginx gagal dijalankan.   
Karena file nginx.conf mengandung konfigurasi yang tidak valid dan referensi backend yang tidak sesuai.
Untuk mengatasi hal tersebut perlu dilakukan perbaikan konfigurasi upstream dan memastikan seluruh backend menggunakan port yang benar.

---

## Hasil Pengujian

### Docker Container

Seluruh container berhasil berjalan:

- nginx-lb
- web1
- web2
- web3
- mysql-db

### Load Balancer

Nginx berhasil melakukan load balancing menggunakan metode Round Robin.

### Database

Ketiga web server berhasil mengakses database yang sama.

## Kesimpulan

Seluruh service berhasil dijalankan menggunakan Docker Compose dan sesuai arahan yang diberikan.

