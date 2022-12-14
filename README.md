## Tugas Praktikum
Buat program sederhana dengan mengaplikasikan penggunaan class. Buatlah class untuk menampilkan daftar nilai mahasiswa, dengan ketentuan:

- Method tambah() untuk menambah data
- Method tampilkan() untuk menampilkan data
- Method hapus(nama) untuk menghapus data berdasarkan nama
- Method ubah(nama) untuk mengubah data berdasarkan nama
## penjelasan
## PENJELASAN PROGRAM

1. deklarasi dictionary dengan data untuk menampung semua data Mahasiswa.
2. Tambah fungsi def tambah() di isi dengan inputan nama, nim, tugas, uts, uas dan total nilai akhir untuk dan di masukan ke data Mahasiswa.
3. Tambah fungsi def tampilkan() di isi dengan cetak isi dari dictonary.
4. Tambah fungsi def hapus(nama) di isi dengan program untuk menghapus element nama pada data Mahasiswa.
5. gunakan fungsi def ubah(nama) di isi dengan inputan nama dan mengubah isi element pada nama tersebut.
6. gunakan while True untuk menlooping/mengulang statment.
7. gunakan statment if, elif, else, di dalam while True dan panggil fungsi dari masing masing fungsi, contoh:
- tambah()
- tampilkan()
- hapus(nama)
- ubah(nama)
- selesai

## PROGRAM
import os
data = {}
class data_mahasiswa():
    def tambah():
            nama = str(input("Masukan Nama\t\t: "))
            nim = str(input("Masukan Nim\t\t: "))
            tugas = int(input("Masukan Nilai Tugas\t: "))
            uts = int(input("Masukan Nilai UTS\t: "))
            uas = int(input("Masukan Nilai UAS\t: "))
            akhir = (tugas / 3) + (uts / 3.5) + (uas / 3.5)
            data[nama] = nim, tugas, uts, uas, akhir,
            print("\nDATA BERHASIL DI TAMBAHKAN!")
    def tampilkan():
            print("=" * 69)
            print("|" + "\t" * 3 + "DAFTAR NILAI MAHASISWA" + "\t" * 3 +
                    "    |")
            print("=" * 69)
            print("| NO |   \tNAMA\t   |\tNIM \t| TUGAS | UTS | UAS | AKHIR |")
            print("=" * 69)
            for tampil in data.items():
                no = 0
                no += 1
                print("| {6:2} |\t {0:15}   | {1:9} \t| {2:5} | {3:3} | {4:3} | {5:5} |".format(tampil[0], tampil[1][0], tampil[1][1], tampil[1][2], tampil[1][3],"%.2f" % float(tampil[1][4]), no))
                print("=" * 69)
    def hapus(nama):
                del data[nama]
                print("DATA BERHASIL DI HAPUS!")
    
    def ubah(nama):
            if nama in data.keys():
                nim = str(input("Masukan Nim\t: "))
                tugas = int(input("Masukan Nilai Tugas\t: "))
                uts = int(input("Masukan Nilai UTS\t: "))
                uas = int(input("Masukan Nilai UAS\t: "))
                akhir = (tugas / 3) + (uts / 3.5) + (uas / 3.5)
                data[nama] = nim, tugas, uts, uas, akhir
                print("\nDATA BERHASIL DI UBAH!")
            else:
                print("\DATA TIDAK DI TEMUKAN!")

while True:
    lanjut = input(
        "\n 1 - Tambah Data,\t 2 - Tampilkan Data,\t 3 - Hapus Data,\t 4 - Ubah Data, 5 - Keluar \n : "
    )
    os.system("cls")
    if (lanjut.lower() == '1'):
        data_mahasiswa.tambah()

    elif (lanjut.lower() == '4'):
        nama = str(input("Masukan Nama : "))
        data_mahasiswa.ubah(nama)
    elif (lanjut.lower() == '3'):
        nama = str(input("Masukan Nama : "))
        if nama in data.keys():
            data_mahasiswa.hapus(nama)
        else:
            print("DATA TIDAK DI TEMUKAN ".format(nama))
    elif (lanjut.lower() == '2'):
        if data.items():
            data_mahasiswa.tampilkan()
        else:
            print("=" * 69)
            print("|" + "\t" * 3 + "DAFTAR NILAI MAHASISWA" + "\t" * 3 +
                "    |")
            print("=" * 69)
            print("| NO |   \tNAMA\t   |\tNIM \t| TUGAS | UTS | UAS | AKHIR |")
            print("=" * 69)
            print("|    " + "\t" * 3 + "TIDAK ADA DATA!" + "\t" * 4 + "    |")
            print("=" * 69)
    elif (lanjut.lower() == '5'):
        print("\nTERIMA KASIH! \n")
        exit()
    else:
        print("PILIHAN MENU TIDAK ADA!")

## OUTPUT PROGRAM
![Screenshot (43)](https://user-images.githubusercontent.com/115676957/207482927-1199a15a-d288-4b92-b620-9ce7f5299e79.png)
![Screenshot (45)](https://user-images.githubusercontent.com/115676957/207482930-2259be5d-0ca5-44ae-902b-3db82d9c3207.png)


