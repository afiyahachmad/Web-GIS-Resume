# QA Tools untuk Pengujian WebGIS (API & UI)

Dokumen ini berisi daftar tools yang digunakan dalam kegiatan Quality Assurance (QA) untuk pengujian aplikasi WebGIS, khususnya pada pengujian **User Interface (UI)** dan **Application Programming Interface (API)**.

---

## 1. Tools Pengujian API

### Postman

**Deskripsi:**  
Postman adalah aplikasi yang digunakan untuk melakukan pengujian layanan backend (API) secara langsung tanpa melalui tampilan website.

**Fungsi Utama:**
- Mengirim request API (GET, POST, PUT, DELETE)
- Mengecek response data dalam format JSON
- Memvalidasi status code API (200, 404, 500, dll)
- Menguji parameter query seperti filter data, bounding box (bbox), dan layer ID
- Memastikan integrasi antara frontend dan backend berjalan dengan baik

**Peran dalam QA WebGIS:**  
Digunakan untuk memastikan data spasial dan layanan peta dapat diakses dengan benar oleh sistem.

---

## 2. Tools Pengujian UI

### Browser & Chrome DevTools

**Deskripsi:**  
DevTools merupakan fitur bawaan browser yang digunakan untuk menganalisis tampilan dan perilaku sistem secara langsung.

**Fungsi Utama:**
- Melihat request API secara realtime dari UI
- Mengecek error JavaScript pada Console
- Inspect elemen peta dan layer
- Memantau loading tile dan performa peta
- Menganalisis masalah tampilan dan responsivitas

**Peran dalam QA WebGIS:**  
Digunakan untuk memastikan tampilan peta, interaksi pengguna, dan integrasi dengan API berjalan dengan normal.

---

## 3. Tools Dokumentasi Pengujian

### Text Editor (VS Code / Notion / Google Docs)

**Deskripsi:**  
Digunakan untuk mendokumentasikan seluruh aktivitas pengujian agar proses QA terstruktur dan mudah ditelusuri.

**Fungsi Utama:**
- Menulis test scenario dan test case
- Mencatat hasil pengujian
- Menyimpan daftar bug
- Membuat checklist testing

---

## 4. Tools Version Control

### Git & GitHub

**Deskripsi:**  
Digunakan untuk menyimpan dan mengelola dokumentasi pengujian secara terpusat.

**Fungsi Utama:**
- Menyimpan laporan hasil testing
- Melacak perubahan file
- Mendukung kolaborasi tim
- Menjadi bukti progres pekerjaan

---

## 5. Tools Pemahaman Sistem

### Enterprise Architect

**Deskripsi:**  
Merupakan tools pemodelan sistem yang digunakan untuk memahami struktur dan alur kerja aplikasi.

**Fungsi Utama:**
- Memahami alur sistem secara menyeluruh
- Melihat hubungan antara UI, API, dan database
- Menganalisis arsitektur sistem
- Menentukan titik-titik pengujian


---

## Kesimpulan

Tools QA dalam pengujian WebGIS memiliki peran yang berbeda namun saling melengkapi, yaitu:

- **API Testing:** memastikan layanan backend dan data spasial berjalan dengan benar
- **UI Testing:** memastikan tampilan dan interaksi pengguna berfungsi sesuai kebutuhan
- **Dokumentasi:** memastikan proses pengujian tercatat dengan rapi
- **System Understanding:** membantu QA memahami sistem sebelum testing dimulai

Penggunaan tools ini memungkinkan proses Quality Assurance dilakukan secara sistematis, terstruktur, dan efektif.
