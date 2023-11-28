# Latihan 1
### Input
![Screenshot 2023-11-28 182144](https://github.com/Pynixz/praktikum5/assets/147568964/d5d07b3f-3c80-4148-a95f-dfe502869734)
### Output
![Screenshot 2023-11-28 182136](https://github.com/Pynixz/praktikum5/assets/147568964/b9689ee6-706f-45ca-8916-f1ef88536b9b)

Membuat dictionary Daftar kontak

# Praktikum 5
### Program Data Mahasiswa

Pada praktikum 5, kita akan membuat program sederhana untuk membuat data mahasiswa menggunakan Dictionary dengan Python.

### Codingan Praktikum5

```python
class Mahasiswa:
    def __init__(self, nim, nama, nilai_tugas, nilai_uts, nilai_uas):
        self.nim = nim
        self.nama = nama
        self.nilai_tugas = nilai_tugas
        self.nilai_uts = nilai_uts
        self.nilai_uas = nilai_uas
        self.akhir = (nilai_tugas + nilai_uts + nilai_uas) / 3

def tampilkan_daftar_nilai(daftar_nilai):
    print("=====================================================================================")
    print("| No | Nama                  |    NIM     |    Tugas   |  UTS  |  UAS  |    Akhir   |")
    print("=====================================================================================")
    if not daftar_nilai:
        print("|                                   TIDAK ADA DATA                                  |")
    else:
        for idx, mahasiswa in enumerate(daftar_nilai, start=1):
            print(f"| {idx}  | {mahasiswa.nama:20} | {mahasiswa.nim:10} |  {mahasiswa.nilai_tugas:5}     |{mahasiswa.nilai_uts:5}  |{mahasiswa.nilai_uas:5}  |    {mahasiswa.akhir:5.2f}   |")
    print("=====================================================================================")

def tambah_data(daftar_nilai):
    nim = input("NIM        : ")
    nama = input("NAMA       : ")
    tugas = int(input("NILAI TUGAS : "))
    uts = int(input("NILAI UTS   : "))
    uas = int(input("NILAI UAS   : "))
    mahasiswa_baru = Mahasiswa(nim, nama, tugas, uts, uas)
    daftar_nilai.append(mahasiswa_baru)
    print("\nData mahasiswa telah ditambahkan!\n")

def ubah_data(daftar_nilai):
    print("=== Ubah Data ===")
    nim = input("Masukkan NIM mahasiswa yang akan diubah: ")
    for mahasiswa in daftar_nilai:
        if mahasiswa.nim == nim:
            print(f"Data mahasiswa dengan NIM {nim} ditemukan:")
            print(f"Nama       : {mahasiswa.nama}")
            print(f"Nilai Tugas : {mahasiswa.nilai_tugas}")
            print(f"Nilai UTS   : {mahasiswa.nilai_uts}")
            print(f"Nilai UAS   : {mahasiswa.nilai_uas}")

            # Input new data
            mahasiswa.nama = input("Nama baru       : ")
            mahasiswa.nilai_tugas = int(input("Nilai Tugas baru : "))
            mahasiswa.nilai_uts = int(input("Nilai UTS baru   : "))
            mahasiswa.nilai_uas = int(input("Nilai UAS baru   : "))
            mahasiswa.akhir = (mahasiswa.nilai_tugas + mahasiswa.nilai_uts + mahasiswa.nilai_uas) / 3

            print(f"\nData mahasiswa dengan NIM {nim} telah diubah!\n")
            return

    print(f"Mahasiswa dengan NIM {nim} tidak ditemukan.")

def cari_data(daftar_nilai):
    print("=== Cari Data ===")
    nim = input("Masukkan NIM mahasiswa yang akan dicari: ")
    for mahasiswa in daftar_nilai:
        if mahasiswa.nim == nim:
            print("Data mahasiswa ditemukan:")
            print(f"Nama       : {mahasiswa.nama}")
            print(f"Nilai Tugas : {mahasiswa.nilai_tugas}")
            print(f"Nilai UTS   : {mahasiswa.nilai_uts}")
            print(f"Nilai UAS   : {mahasiswa.nilai_uas}")
            print(f"Akhir      : {mahasiswa.akhir}")
            return

    print(f"Mahasiswa dengan NIM {nim} tidak ditemukan.")

def hapus_data(daftar_nilai):
    print("=== Hapus Data ===")
    nim = input("Masukkan NIM mahasiswa yang akan dihapus: ")
    for mahasiswa in daftar_nilai:
        if mahasiswa.nim == nim:
            daftar_nilai.remove(mahasiswa)
            print(f"Data mahasiswa dengan NIM {nim} telah dihapus!\n")
            return

    print(f"Mahasiswa dengan NIM {nim} tidak ditemukan.")

daftar_nilai = []

while True:
    print("\nProgram Input Nilai\n--------------------")
    print("[ (L)ihat, (T)ambah, (U)bah, (C)ari, (H)apus, (K)eluar ]:", end="")
    perintah = input().lower()

    if perintah == 'l':
        tampilkan_daftar_nilai(daftar_nilai)
    elif perintah == 't':
        tambah_data(daftar_nilai)
    elif perintah == 'u':
        ubah_data(daftar_nilai)
    elif perintah == 'c':
        cari_data(daftar_nilai)
    elif perintah == 'h':
        hapus_data(daftar_nilai)
    elif perintah == 'k':
        print("Program selesai, keluar.")
        break
    else:
        print("Perintah tidak dikenali. Silakan coba lagi.")
```
### Penjelasan

1. **Class `Mahasiswa`:**
   - Kelas ini merepresentasikan seorang mahasiswa (`Mahasiswa`) dengan atribut seperti `nim` (Nomor Induk Mahasiswa), `nama` (nama), `nilai_tugas` (nilai tugas), `nilai_uts` (nilai ujian tengah semester), `nilai_uas` (nilai ujian akhir semester), dan `akhir` (nilai akhir).
   - Metode `__init__` menginisialisasi objek dengan atribut yang diberikan.

2. **Fungsi `tampilkan_daftar_nilai(daftar_nilai)`:**
   - Fungsi ini menampilkan tabel yang diformat dengan data mahasiswa.
   - Fungsi ini memeriksa apakah daftar `daftar_nilai` kosong dan mencetak pesan jika tidak ada data.
   - Jika ada data, itu melalui daftar dan mencetak informasi setiap mahasiswa dalam tabel yang diformat.

3. **Fungsi `tambah_data(daftar_nilai)`:**
   - Fungsi ini memungkinkan pengguna untuk memasukkan data untuk seorang mahasiswa baru dan menambahkan objek `Mahasiswa` baru ke dalam daftar `daftar_nilai`.

4. **Fungsi `ubah_data(daftar_nilai)`:**
   - Fungsi ini memungkinkan pengguna untuk memperbarui data seorang mahasiswa yang sudah ada.
   - Fungsi ini meminta pengguna untuk memasukkan NIM (Nomor Induk Mahasiswa) mahasiswa yang ingin diperbarui.
   - Jika mahasiswa ditemukan dalam daftar, itu menampilkan data saat ini dan meminta pengguna untuk memasukkan data baru.
   - Setelah memperbarui data, menghitung kembali atribut `akhir` dan mencetak pesan konfirmasi.

5. **Fungsi `cari_data(daftar_nilai)`:**
   - Fungsi ini memungkinkan pengguna untuk mencari seorang mahasiswa berdasarkan NIM yang dimasukkan.
   - Jika mahasiswa ditemukan, menampilkan informasi mereka.

6. **Fungsi `hapus_data(daftar_nilai)`:**
   - Fungsi ini memungkinkan pengguna untuk menghapus data seorang mahasiswa berdasarkan NIM yang dimasukkan.
   - Jika mahasiswa ditemukan, menghapus mahasiswa dari daftar dan mencetak pesan konfirmasi.

7. **Program Utama:**
   - Program dimulai dengan menginisialisasi sebuah daftar kosong `daftar_nilai` untuk menyimpan objek mahasiswa.
   - Masuk ke dalam loop di mana pengguna diminta untuk memilih aksi dari menu (`(L)ihat`, `(T)ambah`, `(U)bah`, `(C)ari`, `(H)apus`, `(K)eluar`).
   - Bergantung pada pilihan pengguna, itu memanggil fungsi yang sesuai atau keluar dari program.
   - Loop berlanjut sampai pengguna memilih untuk keluar.

Program ini menyediakan antarmuka baris perintah sederhana untuk mengelola data mahasiswa, memungkinkan pengguna untuk melihat, menambahkan, memperbarui, mencari, dan menghapus catatan mahasiswa.

# Tampilan Program saat dijalankan

### Memasukan Program Input Nilai tanpa memasukan Data 
![Screenshot 2023-11-28 182458](https://github.com/Pynixz/praktikum5/assets/147568964/592962a8-c47c-4b01-91b3-0952d7993791)

### Memasukan Program Input Nilai dengan Menambahkan Data 
![Screenshot 2023-11-28 182545](https://github.com/Pynixz/praktikum5/assets/147568964/abcac787-f573-4877-9845-ea21b0c17283)

### Mencari Program Input Nilai Data yang telah dimasukan
![Screenshot 2023-11-28 182637](https://github.com/Pynixz/praktikum5/assets/147568964/e8491496-b1a3-4c43-873b-f0cedd41ff45)

### Mengubah Program Input Nilai Data yang telah dimasukan
![Screenshot 2023-11-28 182857](https://github.com/Pynixz/praktikum5/assets/147568964/41df7a54-fdeb-432e-ae9b-1a102fc27905)

