# Program Rekap dan Analisis Nilai Matematika Kelas

Nama: Erlina Putri Febriani  
NIM: 2225250136  
Kelas: 3B  

## Deskripsi
Program berbasis Console Python ini dibuat untuk membantu guru matematika membaca data nilai siswa dari file teks, memvalidasi rentang nilai (0–100), menghitung statistik dasar kelas (rata-rata, nilai minimum, nilai maksimum), mengklasifikasikan ketuntasan berdasarkan KKM, serta menghasilkan file rekapitulasi laporan secara otomatis.

## Fitur Utama
- **Membaca File & Validasi**: Membaca file input berformat `NIM,Nama,Nilai` dan memvalidasi rentang nilai valid 0–100.
- **Analisis Statistik Kelas**: Menghitung jumlah siswa valid, nilai rata-rata, nilai minimum, dan nilai maksimum.
- **Analisis Ketuntasan**: Menghitung jumlah siswa tuntas dan belum tuntas berdasarkan KKM = 60.
- **Simpan Laporan Otomatis**: Menyimpan hasil ringkasan rekapitulasi ke dalam file teks `output/laporan_rekap.txt`.

## Persyaratan Sistem
- Python 3.x
- Visual Studio Code

## Cara Menjalankan
1. Buka terminal di Visual Studio Code pada root folder proyek `pertemuan-15-proyek-akhir-2225250136`.
2. Jalankan perintah berikut:
```bash
python src/main.py