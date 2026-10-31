# Proposal Proyek: Program Rekap dan Analisis Nilai Matematika Kelas

## 1. Judul Proyek
Program Rekap dan Analisis Nilai Matematika Kelas Sederhana Berbasis Console.

## 2. Latar Belakang
Guru matematika memerlukan alat bantu otomatisasi untuk membaca data nilai siswa dari file teks, memvalidasi rentang nilai, menghitung statistik dasar kelas, menentukan status ketuntasan siswa berdasarkan KKM, dan menghasilkan file rekap secara cepat serta konsisten.

## 3. Pengguna dan Tujuan
- **Pengguna Utama**: Guru Matematika.
- **Tujuan**: Mempercepat proses rekapitulasi nilai dan penentuan ketuntasan belajar tanpa kesalahan perhitungan manual.

## 4. Ruang Lingkup
- Program berjalan berbasis terminal/console Python.
- Membaca file input berformat `NIM,Nama,Nilai`.
- Memvalidasi rentang nilai valid (0 - 100).
- Menghitung rata-rata, nilai minimum, nilai maksimum, dan ketuntasan (KKM = 60).
- Menyimpan hasil rekapitulasi ke file laporan teks.

## 5. Kebutuhan Fungsional & Nonfungsional
- **F01 (Wajib)**: Membaca file teks data nilai.
- **F02 (Wajib)**: Memvalidasi nilai pada rentang 0-100.
- **F03 (Wajib)**: Menghitung statistik kelas (rata-rata, min, max).
- **F04 (Wajib)**: Menghitung statistik ketuntasan siswa (KKM 60).
- **F05 (Wajib)**: Menyimpan laporan ke file output.
- **Nonfungsional**: Bebas crash akibat FileNotFoundError / ValueError dan pesan error informatif.

## 6. Input, Proses, Output (IPO)
- **Input**: Berkas `data/nilai_contoh.txt` berisi data siswa (NIM, Nama, Nilai).
- **Proses**: Pengecekan file -> Parsing baris -> Validasi rentang 0-100 -> Perhitungan statistik -> Klasifikasi KKM -> Format laporan.
- **Output**: Ringkasan di console dan file `output/laporan_rekap.txt`.

## 7. Algoritma (Pseudocode)
```text
MULAI
  Set path_input = "data/nilai_contoh.txt"
  Set path_output = "output/laporan_rekap.txt"
  
  Buka dan baca file path_input
  JIKA file tidak ada MAKA
    Tampilkan "File tidak ditemukan"
    SELESAI
  END JIKA
  
  UNTUK setiap baris DALAM file DO
    Bersihkan karakter newline
    Pisahkan baris berdasarkan koma
    JIKA format valid DAN nilai >= 0 DAN nilai <= 100 MAKA
      Simpan data ke dictionary
    LAINNYA
      Abaikan baris dan catat pesan peringatan
    END JIKA
  END UNTUK
  
  Hitung rata-rata, minimum, dan maksimum
  Hitung jumlah siswa tuntas (nilai >= 60) dan belum tuntas (nilai < 60)
  
  Tampilkan ringkasan statistik ke console
  Tulis ringkasan ke file path_output
SELESAI