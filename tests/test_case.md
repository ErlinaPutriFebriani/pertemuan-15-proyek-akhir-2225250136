# Laporan Pengujian dan Hasil Eksekusi Test Case

## Tabel Pengujian
| ID | Fitur | Input / Kondisi | Expected Result | Actual Result | Status |
|---|---|---|---|---|---|
| TC01 | Reading & Parsing | File `nilai_contoh.txt` berisi data valid | Seluruh data terbaca sempurna | Data terbaca dan diolah | PASS |
| TC02 | Rentang Batas | Nilai `0` dan `100` | Diterima sebagai nilai valid | Diterima sebagai nilai valid | PASS |
| TC03 | Batas KKM | Nilai `60` | Dinyatakan TUNTAS | Dinyatakan TUNTAS | PASS |
| TC04 | Batas KKM | Nilai `59.9` | Dinyatakan BELUM TUNTAS | Dinyatakan BELUM TUNTAS | PASS |
| TC05 | Validasi Nilai | Nilai `-5` atau `105` | Baris dilewati dengan peringatan | Baris dilewati dengan peringatan | PASS |
| TC06 | File Handling | File input tidak ditemukan | FileNotFoundError ditangani | Menampilkan pesan error aman | PASS |
| TC07 | Type Conversion | Data nilai non-numerik `A004,Deni,abc` | ValueError ditangani per baris | Baris dilewati tanpa crash | PASS |

## Log Perbaikan Bug (Bug Log)
- **BUG-01**: `ModuleNotFoundError` saat memanggil modul lokal dalam folder `src/`.
  - *Perbaikan*: Menambahkan penyesuaian `sys.path` pada `main.py` dan menyesuaikan import relatif pada `data_io.py`.
- **BUG-02**: Pembagian nol (`ZeroDivisionError`) jika seluruh data dalam file input invalid/kosong.
  - *Perbaikan*: Menambahkan pengondisian `if not data` sebelum menghitung statistik.