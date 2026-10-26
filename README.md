# 🌌 Kalkulator & Simulasi Gerak Jatuh Bebas (GJB)

Aplikasi web interaktif untuk menghitung dan mensimulasikan fenomena fisika **Gerak Jatuh Bebas (GJB)** secara visual, matematis, dan grafis secara *real-time*. Dilengkapi dengan visualisasi objek jatuh, breakdown langkah perhitungan rumus, serta grafik interaktif berbasis Chart.js.

---

## 📋 Daftar Isi
1. [Tentang Aplikasi](#-tentang-aplikasi)
2. [Fitur Utama](#-fitur-utama)
3. [Konsep & Rumus Fisika](#-konsep--rumus-fisika)
4. [Petunjuk Penggunaan Lengkap](#-petunjuk-penggunaan-lengkap)
   - [1. Cara Menjalankan Aplikasi](#1-cara-menjalankan-aplikasi)
   - [2. Mengisi Variabel Input](#2-mengisi-variabel-input)
   - [3. Melakukan Submit Hitung ("Hitung Hasil")](#3-melakukan-submit-hitung-hitung-hasil)
   - [4. Melihat Konsep Fisika ("Show Konsep")](#4-melihat-konsep-fisika-show-konsep)
   - [5. Menggunakan Tombol Reset & Start Simulasi Kembali](#5-menggunakan-tombol-reset--start-simulasi-kembali)
   - [6. Interaksi & Hover pada Grafik](#6-interaksi--hover-pada-grafik)
   - [7. Mengganti Variabel Input & Hitung Ulang](#7-mengganti-variabel-input--hitung-ulang)
5. [Teknologi yang Digunakan](#-teknologi-yang-digunakan)
6. [Struktur File](#-struktur-file)

---

## 💡 Tentang Aplikasi

Aplikasi ini dirancang untuk mempermudah siswa, mahasiswa, maupun pengajar dalam memahami konsep dasar kinematika, khususnya Gerak Jatuh Bebas. Pengguna tidak hanya memperoleh nilai akhir waktu tempuh ($t$) dan kecepatan akhir ($v_t$), tetapi juga dapat melihat animasi jatuhnya benda, skala ketinggian dinamis, serta kurva perubahan kecepatan dan posisi terhadap waktu.

---

## ✨ Fitur Utama

- **Kalkulator Otomatis**: Menghitung lama waktu jatuh ($t$) dan kecepatan akhir ($v_t$) dalam sekejap.
- **Breakdown Langkah Perhitungan**: Menampilkan rumus dan proses kalkulasi matematika langkah demi langkah dengan format konsol bergaya kode.
- **Simulasi Animasi Real-time**: Visualisasi bola jatuh bebas dengan pelacakan garis ketinggian (*Y-cursor*) dan indikator status *live* (waktu & kecepatan).
- **Grafik Interaktif Ganda**:
  - Grafik Kecepatan terhadap Waktu ($v-t$).
  - Grafik Ketinggian terhadap Waktu ($y-t$).
- **Fitur Hover Grafik**: Detail data kecepatan dan ketinggian pada setiap detik dapat diinspeksi secara presisi lewat tooltip kursor.
- **URL Query Persistence**: Nilai input tersimpan pada URL browser (`?h=...&m=...`), sehingga data tidak hilang saat halaman di-refresh atau dibagikan.

---

## 📐 Konsep & Rumus Fisika

Gerak Jatuh Bebas (GJB) adalah gerak lurus berubah beraturan (GLBB) pada lintasan vertikal dari ketinggian tertentu tanpa kecepatan awal ($v_0 = 0$) dan hanya dipengaruhi oleh percepatan gravitasi bumi ($g$).

| Parameter | Simbol | Nilai / Satuan | Keterangan |
| :--- | :---: | :---: | :--- |
| **Kecepatan Awal** | $v_0$ | $0\text{ m/s}$ | Syarat mutlak GJB (benda dilepas, bukan dilempar) |
| **Percepatan Gravitasi** | $g$ | $9.8\text{ m/s}^2$ | Konstanta gravitasi bumi |
| **Tinggi Awal** | $h$ | meter ($\text{m}$) | Jarak awal benda ke permukaan tanah |
| **Lama Waktu Jatuh** | $t$ | sekon ($\text{s}$) | $t = \sqrt{\frac{2h}{g}}$ |
| **Kecepatan Akhir** | $v_t$ | $\text{m/s}$ | $v_t = g \times t = \sqrt{2gh}$ |
| **Posisi Ketinggian** | $y(t)$ | meter ($\text{m}$) | $y(t) = h - \frac{1}{2}gt^2$ |

> **Catatan Fisika Penting**: Pada kondisi ideal (hampa udara / tanpa gesekan udara), **massa benda ($m$) tidak mempengaruhi waktu jatuh maupun kecepatan akhir**. Benda ringan (seperti bulu) dan benda berat (seperti bola besi) akan menyentuh tanah secara bersamaan jika dijatuhkan dari ketinggian yang sama.

---

## 📖 Petunjuk Penggunaan Lengkap

### 1. Cara Menjalankan Aplikasi
1. Unduh atau clone repositori ini ke komputer Anda.
2. Buka berkas [index.html](file:///d:/projects/gjb/index.html) menggunakan browser modern favorit Anda (Google Chrome, Mozilla Firefox, Microsoft Edge, dll).
   * *Opsi Alternatif:* Anda juga dapat menjalankannya melalui ekstensi VS Code seperti **Live Server**.

---

### 2. Mengisi Variabel Input
Pada panel sebelah kiri (**Panel Kontrol & Hasil**), isi kolom input yang tersedia:
1. **Tinggi Awal ($h$) dalam meter** *(Wajib)*:
   - Masukkan angka ketinggian jatuhnya benda dalam meter (misalnya: `100` atau `45.5`).
   - Nilai harus lebih besar dari `0`.
2. **Massa Benda ($m$) dalam kg** *(Opsional)*:
   - Masukkan massa benda (misalnya: `5` atau `2.5`).
   - *Pengingat:* Massa tidak mempengaruhi hasil perhitungan matematis GJB ideal, namun disediakan sebagai sarana edukasi pemahaman konsep massa.

---

### 3. Melakukan Submit Hitung ("Hitung Hasil")
1. Setelah mengisi nilai tinggi awal, klik tombol biru **Hitung Hasil**.
2. Sistem akan menjalankan serangkaian aksi:
   - **Validasi Input**: Memastikan angka yang dimasukkan valid dan positif.
   - **Pembaruan URL**: Menambahkan query parameter (misal `?h=100&m=5`) ke bilah alamat browser.
   - **Tampilan Hasil Numerik**:
     - Kartu hijau menampilkan **Lama Waktu Jatuh ($t$)** dalam detik.
     - Kartu oranye menampilkan **Kecepatan Akhir ($v_t$)** dalam m/s.
   - **Langkah Perhitungan**: Panel gelap bertuliskan **PROSES PERHITUNGAN** akan membedah substitusi angka ke dalam rumus $t$ dan $v_t$.
   - **Memulai Animasi**: Animasi bola jatuh pada panel kanan akan otomatis bergerak meluncur ke bawah bersamaan dengan grafik yang mulai terisi.

---

### 4. Melihat Konsep Fisika ("Show Konsep")
1. Di bawah tombol *Hitung Hasil*, terdapat panel akordeon dengan label **❗️ Konsep Fisika**.
2. **Klik pada baris judul "❗️ Konsep Fisika"** untuk membuka/menutup rangkuman materi fisika GJB.
3. Di dalamnya dijelaskan:
   - Mengapa massa benda tidak mempengaruhi waktu jatuh di ruang hampa.
   - Bagaimana percepatan konstan ($g$) menambah kecepatan benda secara linear tiap detik.
   - Bagaimana perpindahan posisi turun secara kuadratik terhadap waktu.

---

### 5. Menggunakan Tombol Reset & Start Simulasi Kembali
Di bagian atas panel **Visualisasi Simulasi** (kolom sebelah kanan), terdapat dua tombol kontrol:

- 🔄 **Tombol "Reset Animasi"**:
  - Menghentikan seketika animasi yang sedang berjalan.
  - Mengembalikan posisi bola merah ke posisi paling atas ($h$).
  - Mengosongkan data pada **Grafik Kecepatan** dan **Grafik Ketinggian**.
  - Mereset indikator waktu ke `0.00 s` dan kecepatan ke `0.0 m/s`.
  - Menyembunyikan kursor penunjuk garis ketinggian.
- ▶️ **Tombol "Mulai Animasi"**:
  - Menjalankan kembali simulasi animasi dan pembentukan grafik dari awal dengan nilai variabel input yang sedang aktif di formulir, tanpa perlu me-refresh halaman web.

---

### 6. Interaksi & Hover pada Grafik
Aplikasi menyediakan dua grafik visualisasi interaktif dari pustaka **Chart.js**:
1. **Grafik Kecepatan ($v-t$)**:
   - Garis berwarna merah.
   - Menunjukkan grafik linear naik (kecepatan bertambah seiring bertambahnya waktu).
2. **Grafik Ketinggian ($y-t$)**:
   - Garis berwarna biru.
   - Menunjukkan kurva parabola melengkung ke bawah (benda jatuh semakin cepat mendekati tanah).

#### 🖱️ Cara Melakukan Hover:
- Gerakkan dan arahkan kursor mouse ke sepanjang garis kurva grafik.
- **Tooltip interaktif** akan muncul secara otomatis dan menampilkan:
  - Nilai sumbu $X$: **Waktu (s)** secara presisi.
  - Nilai sumbu $Y$: **Kecepatan (m/s)** atau **Ketinggian (m)** pada detik tersebut.
- Hal ini sangat berguna untuk menganalisis kecepatan atau posisi benda pada waktu tertentu sebelum menyentuh tanah.

---

### 7. Mengganti Variabel Input & Hitung Ulang
Jika Anda ingin mencoba skenario baru (misalnya menguji ketinggian dari gedung 50 m dibandingkan dengan tebing 200 m):
1. Cukup klik pada kotak input **Tinggi Awal (h)** dan masukkan angka baru (contoh: ubah dari `100` menjadi `50`).
2. *(Opsional)* Ubah atau kosongkan nilai pada kolom **Massa Benda (m)**.
3. Klik tombol **Hitung Hasil** (atau tombol **Mulai Animasi**).
4. Aplikasi akan secara otomatis:
   - Mereset animasi dan grafik lama.
   - Mengkalibrasi ulang skala ketinggian visual (angka skala $H\text{ m}$ dan $\frac{H}{2}\text{ m}$ pada sisi kiri canvas simulasi).
   - Menyesuaikan batas skala maksimum pada sumbu grafik ($x_{\max}$ dan $y_{\max}$).
   - Menghitung ulang rumus dan memperbarui angka hasil serta animasi baru.

---

## 🛠️ Teknologi yang Digunakan

- **HTML5**: Struktur semantik halaman web.
- **Vanilla CSS & Tailwind CSS (CDN)**: Tata letak responsif, palet warna modern, dan komponen UI yang bersih.
- **Vanilla JavaScript (ES6+)**: Logika kalkulasi fisika, manipulasi DOM dinamis, sinkronisasi URL parameter, dan siklus animasi visual menggunakan `requestAnimationFrame`.
- **Chart.js**: Pustaka visualisasi grafik garis interaktif dengan dukungan *tooltip on hover* dan *dynamic datasets*.

---

## 📂 Struktur File

```text
gjb/
├── index.html        # Berkas utama aplikasi web (HTML, CSS, JS terintegrasi)
└── README.md         # Dokumentasi petunjuk penggunaan dan referensi teknis
```

---

*Dibuat untuk memudahkan pembelajaran fisika mekanika secara visual, interaktif, dan intuitif.* 🚀
