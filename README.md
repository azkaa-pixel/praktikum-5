# modul praktikum 4

Nama:ghefira azka fardani 

Kelas:TI.24.A5

NIM: 312410521

## praktikum 4

### - flowchart
![foto]( )
### - code program
#### 1. Inisialisasi Dictionary ```mahasiswa:```
```python
mahasiswa = {}

```
Ini adalah dictionary kosong yang akan digunakan untuk menyimpan data mahasiswa.
Kunci dictionary ini adalah NPM (Nomor Pokok Mahasiswa), dan nilai dictionary adalah informasi lainnya seperti nama mahasiswa, nilai tugas, UTS, UAS, dan nilai akhir.

#### 2. Fungsi ```tambah_data:```

Fungsi ini digunakan untuk menambahkan data mahasiswa baru.

~ Meminta input pengguna untuk memasukkan NPM, nama mahasiswa, nilai tugas, UTS, dan UAS.

~ Menghitung nilai akhir berdasarkan bobot yang sudah ditentukan (30% tugas, 35% UTS, dan 35% UAS).

~ Menyimpan data tersebut dalam dictionary mahasiswa dengan NPM sebagai kunci dan data lainnya (nama, tugas, UTS, UAS, nilai akhir) sebagai nilai.

```phython
def tambah_data():
    npm = input("Masukkan NPM: ")
    nama = input("Masukkan Nama: ")
    tugas = float(input("Masukkan Nilai Tugas: "))
    uts = float(input("Masukkan Nilai UTS: "))
    uas = float(input("Masukkan Nilai UAS: "))
    nilai_akhir = (tugas * 0.3) + (uts * 0.35) + (uas * 0.35)
    mahasiswa[npm] = {"nama": nama, "tugas": tugas, "uts": uts, "uas": uas, "nilai_akhir": nilai_akhir}
    print("Data berhasil ditambahkan!")
```
#### 3. fungsi ```ubah data:```

Fungsi ini memungkinkan pengguna untuk mengubah data mahasiswa yang sudah ada.

~ Mengambil input NPM untuk mencari apakah ```mahasiswa``` dengan NPM tersebut ada dalam dictionary.

~ Jika ada, program akan meminta input baru untuk nama, nilai tugas, UTS, dan UAS, lalu menghitung ulang nilai akhirnya.

~ Data lama akan diperbarui dengan data baru.
```python
def ubah_data():
    npm = input("Masukkan NPM: ")
    if npm in mahasiswa:
        nama = input("Masukkan Nama: ")
        tugas = float(input("Masukkan Nilai Tugas: "))
        uts = float(input("Masukkan Nilai UTS: "))
        uas = float(input("Masukkan Nilai UAS: "))
        nilai_akhir = (tugas * 0.3) + (uts * 0.35) + (uas * 0.35)
        mahasiswa[npm] = {"nama": nama, "tugas": tugas, "uts": uts, "uas": uas, "nilai_akhir": nilai_akhir}
        print("Data berhasil diubah!")
    else:
        print("NPM tidak ditemukan!")

```
#### 4. Fungsi ```hapus_data:```
Fungsi ini digunakan untuk menghapus data mahasiswa berdasarkan NPM.

~ Meminta input NPM, kemudian memeriksa apakah NPM tersebut ada dalam dictionary.

~ Jika ada, data mahasiswa akan dihapus. Jika tidak, akan muncul pesan bahwa NPM tidak ditemukan.
```phython
def hapus_data():
    npm = input("Masukkan NPM: ")
    if npm in mahasiswa:
        del mahasiswa[npm]
        print("Data berhasil dihapus!")
    else:
        print("NPM tidak ditemukan!")
```

#### 5. Fungsi ```tampilkan_data:```
Fungsi ini digunakan untuk menampilkan semua data mahasiswa yang ada dalam dictionary.

~ Program akan mencetak daftar mahasiswa yang berisi NPM, nama, nilai tugas, UTS, UAS, dan nilai akhir.
```phython
def tampilkan_data():
    print("Daftar Nilai Mahasiswa:")
    print("NPM\tNama\tTugas\tUTS\tUAS\tNilai Akhir")
    for npm, data in mahasiswa.items():
        print(f"{npm}\t{data['nama']}\t{data['tugas']:.2f}\t{data['uts']:.2f}\t{data['uas']:.2f}\t{data['nilai_akhir']:.2f}")
```
#### 6. Fungsi ```cari_data:```
Fungsi ini digunakan untuk mencari data mahasiswa berdasarkan NPM.

Program akan mencari NPM yang dimasukkan dan jika ditemukan, akan menampilkan nama mahasiswa, nilai tugas, UTS, UAS, dan nilai akhir.
Jika NPM tidak ditemukan, maka program akan menampilkan pesan bahwa data tidak ditemukan.
```python
def cari_data():
    npm = input("Masukkan NPM: ")
    if npm in mahasiswa:
        print("Data ditemukan!")
        print(f"NPM: {npm}")
        print(f"Nama: {mahasiswa[npm]['nama']}")
        print(f"Tugas: {mahasiswa[npm]['tugas']:.2f}")
        print(f"UTS: {mahasiswa[npm]['uts']:.2f}")
        print(f"UAS: {mahasiswa[npm]['uas']:.2f}")
        print(f"Nilai Akhir: {mahasiswa[npm]['nilai_akhir']:.2f}")
    else:
        print("NPM tidak ditemukan!")
```
#### 7. Menu Pilihan:
Di bagian ini, program menampilkan menu untuk memilih tindakan yang diinginkan (tambah, ubah, hapus, tampilkan, cari data, atau keluar).

~ Menggunakan input untuk memilih menu dan menjalankan fungsi yang sesuai berdasarkan pilihan.
```python
while True:
    print("Menu Pilihan:")
    print("1. Tambah Data")
    print("2. Ubah Data")
    print("3. Hapus Data")
    print("4. Tampilkan Data")
    print("5. Cari Data")
    print("6. Keluar")
    pilihan = input("Masukkan pilihan: ")
    if pilihan == "1":
        tambah_data()
    elif pilihan == "2":
        ubah_data()
    elif pilihan == "3":
        hapus_data()
    elif pilihan == "4":
        tampilkan_data()
    elif pilihan == "5":
        cari_data()
    elif pilihan == "6":
        break
    else:
        print("Pilihan tidak valid!")




### - hasil 
