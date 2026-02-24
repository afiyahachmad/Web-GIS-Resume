# Web-GIS-Resume

Resume tentang WebGIS dan relevansinya terhadap QA Testing

---

# 1. Pengertian WebGIS

## Penjelasan Umum

WebGIS (Web Geographic Information System) adalah sistem informasi geografis yang dapat diakses melalui internet menggunakan browser. Sistem ini memungkinkan pengguna untuk mengumpulkan, menyimpan, mengelola, menganalisis, dan menampilkan data spasial secara online.

Berbeda dengan GIS desktop, WebGIS memiliki karakteristik:

- Berbasis client–server
- Multiuser
- Real-time
- Dapat diakses tanpa instalasi software khusus
- Mendukung integrasi sistem melalui API

WebGIS menggabungkan teknologi:

- Web development
- Sistem informasi geografis
- Basis data spasial

---

# 2. Komponen Utama WebGIS

WebGIS terdiri dari tiga komponen utama yang saling terintegrasi untuk menampilkan, mengelola, dan memproses data geospasial melalui web.

---

## 1. Client Side (Frontend)

Client side merupakan bagian yang berinteraksi langsung dengan pengguna melalui browser.

### Fungsi Utama:

- Menampilkan peta
- Mengontrol layer
- Navigasi peta (zoom, pan)
- Menampilkan informasi objek

---

## 2. Server Side (Backend)

Server side adalah bagian yang menangani logika sistem dan pemrosesan data.

### Fungsi:

- Mengelola permintaan dari client
- Mengakses database spasial
- Memproses analisis spasial
- Menyediakan layanan API

Backend memastikan data yang dikirim ke frontend akurat, terproses dengan benar, dan aman.

---

## 3. Database Spasial

Database spasial merupakan tempat penyimpanan data geografi beserta atributnya.

### Jenis Data yang Disimpan:

- Koordinat lokasi
- Layer peta
- Informasi atribut objek

Database ini memungkinkan penyimpanan dan pengelolaan data berbasis lokasi secara efisien.

---

## Relevansi untuk QA Testing

Quality Assurance (QA) perlu memahami ketiga komponen ini karena potensi bug dapat terjadi pada:

- Tampilan antarmuka (Frontend/UI)
- Proses pengolahan data (Backend)
- Kesalahan data spasial (Database)

Dengan memahami struktur dan alur kerja setiap komponen, QA dapat:

- Mengidentifikasi sumber masalah dengan lebih cepat
- Menentukan apakah bug berasal dari UI, logic backend, atau data
- Melakukan pengujian yang lebih terstruktur dan efektif

---

# 3. Arsitektur WebGIS

![webgis1](https://github.com/user-attachments/assets/ece252b7-5162-4147-a610-101c023b85ca)

Berdasarkan diagram, WebGIS menggunakan arsitektur terpisah antara **Client**, **Server**, dan **Spatial Database**. Arsitektur ini termasuk dalam model **3-tier architecture** yang memisahkan sistem berdasarkan tanggung jawabnya.

---

## 1. Client Layer

Client berada di sisi pengguna dan berjalan melalui:

- Browser (web-based)
- Aplikasi standalone

### Karakteristik:

- Mengirim request ke server melalui HTTP
- Tidak mengakses database secara langsung
- Bertanggung jawab pada tampilan (visualisasi peta dan UI)

Client hanya menangani presentation layer, bukan pemrosesan data.

---

## 2. Server Layer

Server menjadi pusat pengolahan sistem dan terdiri dari dua komponen utama:

### a. Web Server

- Menangani komunikasi HTTP
- Menerima dan merespons request dari client

### b. GIS Component

- Memproses data spasial
- Menjalankan query ke database
- Melakukan analisis spasial
- Menyusun response (JSON, GeoJSON, dll.)

Server bertindak sebagai penghubung antara client dan database.

---

## 3. Spatial Database Layer

Database spasial menyimpan:

- Data geometri (titik, garis, poligon)
- Layer peta
- Data atribut
- Metadata spasial

Database hanya dapat diakses oleh server, bukan langsung oleh client.

---

## Pola Arsitektur

Arsitektur ini menunjukkan pola:

Client ⇄ Server ⇄ Spatial Database

Karakteristik utama:

- Pemisahan tanggung jawab (separation of concerns)
- Database terisolasi dari akses langsung pengguna
- Server menjadi pusat kontrol logika sistem
- Komunikasi berbasis protokol HTTP

---

## Keunggulan Arsitektur Ini

- Lebih aman (database tidak terekspos langsung)
- Lebih mudah dikembangkan
- Mudah dilakukan scaling pada server
- Memudahkan debugging karena tiap layer memiliki tanggung jawab jelas

---

## Relevansi untuk QA Testing

QA perlu memahami arsitektur ini karena sumber masalah tidak selalu berada di tempat yang terlihat.

Contoh kemungkinan permasalahan:

- Masalah tampilan peta dapat disebabkan oleh respons backend yang tidak sesuai
- Data tidak muncul bisa terjadi karena kegagalan API
- Error dapat muncul pada salah satu layer (presentation, application, atau data)

Dengan memahami pembagian layer, QA dapat:

- Melakukan isolasi masalah dengan lebih sistematis
- Menentukan titik pengujian yang tepat
- Mengurangi waktu analisis bug

---

# 4. Alur Kerja Sistem WebGIS

Alur kerja WebGIS secara umum:

1. User membuka aplikasi WebGIS
2. Client mengirim permintaan ke server
3. Server mengambil data dari database
4. Server mengirimkan data melalui API
5. Client menampilkan data dalam bentuk peta

---

# 5. Teknologi dalam WebGIS

WebGIS dibangun menggunakan kombinasi teknologi pada tiga lapisan utama: **Client (Frontend)**, **Server (Backend)**, dan **Database Spasial**. Berikut ringkasan teknologi yang umum digunakan pada masing-masing layer.

---

## 1 Client Side (Frontend)

Frontend bertanggung jawab pada tampilan peta dan interaksi pengguna.

### Teknologi Dasar:

- **HTML** → Struktur halaman web
- **CSS** → Styling dan layout
- **JavaScript** → Interaksi dan kontrol logika di sisi client

### Library / Framework Pemetaan:

- **Leaflet** → Library JavaScript ringan untuk menampilkan peta interaktif
- **OpenLayers** → Library pemetaan dengan fitur lebih kompleks

### Fungsi Utama:

- Menampilkan layer peta
- Navigasi (zoom, pan)
- Menampilkan popup informasi
- Mengontrol visibilitas layer

---

## 2 Server Side (Backend)

Backend menangani logika sistem dan pemrosesan data.

### Teknologi Umum:

- **Node.js** → Runtime JavaScript untuk server
- **Python (Django / Flask)** → Framework backend berbasis Python
- **PHP** → Digunakan pada beberapa implementasi WebGIS

### GIS Server / Engine:

- **GeoServer** → Server open-source untuk layanan data spasial (WMS, WFS, WCS)
- **MapServer** → Platform publikasi data spasial berbasis web

### Fungsi:

- Mengelola request dan response
- Menyediakan API
- Memproses analisis spasial
- Menghubungkan client dengan database

---

## 3 Database Spasial

Database menyimpan data geografis dan atributnya.

### Teknologi yang Umum Digunakan:

- **PostgreSQL + PostGIS** → Database relasional dengan ekstensi spasial
- **MySQL (Spatial Extension)** → Mendukung tipe data spasial
- **SpatiaLite** → Versi ringan berbasis SQLite

### Jenis Data:

- Titik, garis, poligon
- Koordinat geografis
- Data atribut
- Layer peta

---

## 4 Protokol & Standar Geospasial

WebGIS biasanya menggunakan standar dari OGC (Open Geospatial Consortium):

- **WMS (Web Map Service)** → Layanan tampilan peta
- **WFS (Web Feature Service)** → Layanan data fitur spasial
- **WCS (Web Coverage Service)** → Layanan data raster

---

# 6. Data Spasial

![Jenis data spasial](https://github.com/user-attachments/assets/cfbc5dd9-a2a2-4f4e-a190-c5f7ae72b8cf)

Data spasial adalah data yang memiliki informasi lokasi atau posisi geografis di permukaan bumi. Data ini digunakan dalam sistem GIS untuk merepresentasikan objek, fenomena, atau wilayah tertentu.

---

## Jenis Utama Data Spasial

### 1 Vector Data

Vector data menyimpan informasi lokasi dalam bentuk koordinat geografis (x, y) dan direpresentasikan sebagai geometri.

#### Karakteristik:

- Presisi tinggi
- Cocok untuk batas wilayah dan objek diskrit
- Dapat memiliki atribut (nama, luas, jenis, dll.)

#### Contoh:

- Titik lokasi (misalnya: lokasi sekolah, rumah sakit)
- Garis jalan
- Area wilayah (misalnya: batas desa, kecamatan, provinsi)

---

### 2 Raster Data

Raster data berbentuk grid atau piksel dan biasanya berupa citra atau gambar.

#### Karakteristik:

- Tersusun dari kumpulan piksel
- Setiap piksel memiliki nilai tertentu
- Cocok untuk data kontinu

#### Contoh:

- Foto udara
- Citra satelit
- Peta elevasi (DEM)

---

# 7. Fitur dan Operasi WebGIS

WebGIS menyediakan berbagai fitur interaktif yang memungkinkan pengguna untuk menampilkan, mengelola, dan menganalisis data spasial secara langsung melalui browser.

---

### 1 Zoom dan Pan

- **Zoom** → Memperbesar atau memperkecil tampilan peta.
- **Pan** → Menggeser tampilan peta ke area lain.

---

### 2 Pencarian Lokasi

- Nama tempat
- Koordinat
- Kata kunci tertentu

---

### 3 Pengelolaan Layer

- Mengaktifkan atau menonaktifkan layer
- Mengatur urutan layer
- Mengubah transparansi layer

---

### 4 Query Data

- Klik pada objek
- Filter berdasarkan atribut
- Pencarian berdasarkan kriteria tertentu

---

### 5 Analisis Spasial

- Pengukuran jarak dan luas
- Buffering (membuat zona tertentu di sekitar objek)
- Overlay antar layer
- Analisis pola sebaran

---

# 8. API dalam WebGIS

API (*Application Programming Interface*) digunakan sebagai penghubung komunikasi antara **client** dan **server** dalam sistem WebGIS.

Client tidak mengakses database secara langsung, melainkan mengirimkan permintaan (request) ke server melalui API, lalu menerima respons (response) dalam format tertentu seperti JSON atau GeoJSON.

---

## Fungsi API

### 1 Mengambil Data Spasial

- Mengambil layer peta
- Mengambil data koordinat
- Mengambil atribut objek spasial
- Request data lokasi berdasarkan ID
- Request data dalam radius tertentu

### 2 Mengirim Data

- Menambahkan lokasi baru
- Mengunggah data spasial
- Mengirim hasil input pengguna

### 3 Memperbarui Informasi

- Update atribut data
- Edit geometri (titik/garis/poligon)
- Menghapus data tertentu

Metode HTTP yang digunakan:

- GET → mengambil data
- POST → menambahkan data
- PUT/PATCH → memperbarui data
- DELETE → menghapus data

---

## Relevansi untuk QA Testing

### 1. Validasi Akurasi Data

- Memastikan data yang dikirim sesuai dengan database
- Memastikan tidak ada data yang hilang atau salah

### 2. Validasi Format Respons

- Memastikan struktur JSON/GeoJSON sesuai standar
- Memastikan status code HTTP sesuai (200, 404, 500, dll.)

### 3. Uji Performa dan Stabilitas

- Menguji waktu respons API
- Menguji beban tinggi (load testing)
- Memastikan API tidak crash saat menerima banyak request

---

# 9. UI dalam WebGIS

UI WebGIS mencakup:

- Tampilan peta
- Menu layer
- Tool navigasi
- Informasi popup

---

# 10. Potensi Permasalahan pada WebGIS

Permasalahan umum:

- Data tidak sinkron
- Layer tidak muncul
- Koordinat tidak akurat
- Performa lambat
- Error pada API

---

# 11. Peran QA dalam WebGIS

Quality Assurance (QA) berperan memastikan website berfungsi dengan baik, sesuai kebutuhan, dan memberikan pengalaman pengguna yang optimal. QA tidak hanya mencari bug, tetapi juga menjaga kualitas sistem secara menyeluruh.

---

## 1 Memastikan Fungsionalitas Berjalan Sesuai Kebutuhan

- Semua fitur berjalan sesuai spesifikasi
- Tidak ada error pada proses input dan output
- Alur sistem sesuai dengan requirement
- Form dapat mengirim data dengan benar
- API merespons sesuai permintaan
- Navigasi halaman berjalan normal

---

## 2 Menguji Tampilan dan User Interface (UI)

- Tampilan konsisten di berbagai browser
- Responsif di desktop dan mobile
- Tidak ada elemen yang rusak atau tidak sejajar

---

## 3 Menguji Integrasi Sistem

- API
- Database
- Layanan pihak ketiga

---

## 4 Melakukan Pengujian Performa

- Kecepatan loading halaman
- Waktu respons server
- Stabilitas saat diakses banyak pengguna

---

## 5 Mengidentifikasi dan Mendokumentasikan Bug

- Menemukan bug
- Menganalisis penyebabnya
- Mendokumentasikan detail error
- Memberikan laporan yang jelas kepada tim developer

---

## 6 Meningkatkan Kualitas dan Keamanan Sistem

- Validasi input berjalan baik
- Tidak ada celah keamanan sederhana
- Data pengguna terlindungi

---

# 12. Kesimpulan

WebGIS adalah sistem kompleks yang mengintegrasikan teknologi web, data spasial, dan sistem server. Pemahaman menyeluruh terhadap komponen, arsitektur, alur kerja, dan potensi permasalahan sangat penting, terutama bagi QA, untuk memastikan sistem berjalan dengan baik dan menghasilkan data yang akurat.
