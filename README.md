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
        print("Perintah tidak dikenali. Silakan coba lagi.")```
