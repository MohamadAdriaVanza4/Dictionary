 # Latihan Dictionary pada python membuat program crud sederhana
1. Pertama kita buat buat folder Dictionary dan didalam kita buat file bernama Latihan1.py dan Praktikum.py.
 ![Dicti](https://user-images.githubusercontent.com/115931631/204122777-a10be051-152e-4411-9c7e-e23e728386cc.png)
2. Lalu buka Pratikum.py dan masukan coding sebagai berikut lalu run dengan mengetikan perintah berikut diterminal python Pratikum.py:
 
          print("===================================================================")
          print("Nama         :   Mohamad Adria Vanza")
          print("NIM          :   312210171")
          print("Kelas        :   TI.22.B1")
          print("Mata Kuliah  :   Bahasa Pemrograman")
          print("===================================================================")

           # import tabulate 
          from tabulate import tabulate
           # membuat dictionary
          dict = {'Nama' : ['Ari', 'Dina'], 'Nomor Telepon' : [6281267888, 6287677776]}

           # menampilkan kontak ari pada dictionary
          print("menampilkan Nomor Telepon Ari")
          print(dict['Nomor Telepon'][0])
          print('')

           # menambah data baru Nama dan Nomor telepon
          print("Menambahkan data baru")
          dict['Nama'].append('Riko')
          dict['Nomor Telepon'].append('6287654544')
          print(dict)

           # merubah kontak dina 
           # mencari nama dina apakah didalam data Dictionary
          if 'Dina' in dict ['Nama']:
              # jika ada cari position dina ada di index berapa
              DinaIndex = dict['Nama'].index('Dina')
              # lalu dapatkan index untuk merubah no telepon
              dict['Nomor Telepon'][DinaIndex] =  6288999776
          else:
              print("Tidak ada namanya dina")
          print("Merubah Nomor telepon dina")
          print(dict)

           # menampilkan semua nama
          print("Menampilkan semua Nama")
          print(dict['Nama'])

           # menampilkan semua nomor
          print("Menampilkan semua Nomor")
          print(dict['Nomor Telepon'])

           # menampilkan semua Nama & Nomor Telepon
          print("Menampilkan semua Nama & Nomor Telepon")
          print(tabulate(dict, headers=["Nama", "Nomor Telepon"], tablefmt="fancy_grid"))

   dan berikut hasilnya :
  ![No Telp](https://user-images.githubusercontent.com/115931631/204122869-8d3c3ca6-74d9-49b3-94ee-aee471da5f26.png)
  
3. Selanjutnya kita akan buat program crud sederhana dan berikut flowchart program yang akan dibuat
  ![Flow](https://user-images.githubusercontent.com/115931631/204122940-01c10220-609f-4fbd-93ba-16586cfe7889.png)
  
4. Lalu buka file Praktikum1.py dan masukan codingan sebagai berikut lalu run dengan mengetikan perintah berikut diterminal python Praktikum1.py
    from prettytable import PrettyTable

          baris = []
          x = PrettyTable()

          while True:
             print("[ (L)ihat , (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar ]")
             tanya = input("Masukkan Pilihan : ")
             if tanya == "L":
                 print("==== Daftar Nilai ====")
                 no = 0
                 no += 1
                 x.field_names = ["No", "NIM", " NAMA", "TUGAS", "UTS", "UAS", "AKHIR"]
                 if not baris:
                     x.field_names = ["No", "NIM", " NAMA", "TUGAS", "UTS", "UAS", "AKHIR"]
                     print("Not Data")
                 else:
                     for data in baris:
                         x.add_row([no, data["nim"], data["nama"], data["tugas"], data["uts"], data["uas"], data["akhir"]])
                     print(x)
             elif tanya == "T":
                 print("Tambah Data ")
                 nim_v = input("NIM : ")
                 nama_v = input("Nama Lengkap : ")
                 uts_v = input("Nilai UTS : ")
                 uas_v = input("Nilai UAS : ")
                 tugas_v = input("Nilai Tugas : ")
                 akhir_v = 0.3 * float(tugas_v) + 0.35 * float(uts_v) + 0.35 * float(uas_v)
                 baris.append({"nim": nim_v, "nama": nama_v, "tugas": tugas_v, "uts": uts_v, "uas": uas_v, "akhir": akhir_v})
                 print()
                 print("==== Daftar Nilai ====")
                 i = 0
                 for data in baris:
                     i += 1
                     x.field_names = ["No", "NIM", " NAMA", "TUGAS", "UTS", "UAS", "AKHIR"]
                     x.add_row([i, data["nim"], data["nama"], data["tugas"], data["uts"], data["uas"], data["akhir"]])
                 print(x)
             elif tanya == "U":
                 print("Edit File")
                 print("Data siapa yang akan diubah ?")
                 siapa = input("Masukkan NIM Mahasiswa yang akan diubah : ")

                 print("Data apa yang akan diubah ? : ")
                 mhs = input(" 1. Nama \n 2. Nilai Tugas \n 3. Nilai UTS \n 4. Nilai UAS\n Pilih dengan angka (1/2/3/4) : ")
                 if mhs == "1":
                     ubahnama = input("Silahkan masukan nama yang benar : ")
                     i = 0
                     d = next(item for item in baris if item['nim'] == siapa)
                     d['nama'] = ubahnama
                     x.field_names = ["No", "NIM", " NAMA", "TUGAS", "UTS", "UAS", "AKHIR"]
                     i += 1
                     x.add_row([i, d["nim"], d["nama"], d["tugas"], d["uts"], d["uas"], d["akhir"]])
                     print(x)
                 elif mhs == "2":
                     ubahtugas = input("Masukkan Nilai Tugas yang benar : ")
                     i = 0
                     d = next(item for item in baris if item['nim'] == siapa)
                     d['tugas'] = ubahtugas
                     lihatuts = d['uts']
                     lihatuas = d['uas']
                     lihatakhir = 0.3 * float(ubahtugas) + 0.35 * float(lihatuts) + 0.35 * float(lihatuas)
                     d['akhir'] = lihatakhir
                     x.field_names = ["No", "NIM", " NAMA", "TUGAS", "UTS", "UAS", "AKHIR"]
                     for data in baris:
                         i += 1
                     x.add_row([i, data["nim"], data["nama"], data["tugas"], data["uts"], data["uas"], data["akhir"]])
                     print(x)
                 elif mhs == "3":
                     ubahuts = input("Masukkan Nilai UTS yang benar : ")
                     i = 0
                     d = next(item for item in baris if item['nim'] == siapa)
                     d['uts'] = ubahuts
                     lihattugas = d['tugas']
                     lihatuas = d['uas']
                     lihatakhir = 0.3 * float(lihattugas) + 0.35 * float(ubahuts) + 0.35 * float(lihatuas)
                     d['akhir'] = lihatakhir
                     x.field_names = ["No", "NIM", " NAMA", "TUGAS", "UTS", "UAS", "AKHIR"]
                     for data in baris:
                         i += 1
                         x.add_row([i, data["nim"], data["nama"], data["tugas"], data["uts"], data["uas"], data["akhir"]])
                     print(x)
                 elif mhs == "4":
                     ubahuas = input("Masukkan Nilai UAS yang benar : ")
                     i = 0
                     d = next(item for item in baris if item['nim'] == siapa)
                     d['uas'] = ubahuas
                     lihattugas = d['tugas']
                     lihatuts = d['uts']
                     lihatakhir = 0.3 * float(lihattugas) + 0.35 * float(lihatuts) + 0.35 * float(ubahuas)
                     d['akhir'] = lihatakhir
                     x.field_names = ["No", "NIM", " NAMA", "TUGAS", "UTS", "UAS", "AKHIR"]
                     for data in baris:
                         i += 1
                         x.add_row([i, data["nim"], data["nama"], data["tugas"], data["uts"], data["uas"], data["akhir"]])
                     print(x)
                 else:
                     print("Pilihan Salah")

             elif tanya == "C":
                 print(" ========== Pencarian Data ==========")
                 print(" Pencarian berdasarkan NIM ")
                 carinim = input("Masukkan NIM yang akan dicari : ")
                 xdata = next(item for item in baris if item['nim'] == carinim)
                 print("NIM : ", carinim)
                 print("Nama : ", xdata['nama'])
                 print("Nilai Tugas : ", xdata['tugas'])
                 print("Nilai UTS : ", xdata['uts'])
                 print("Nilai UAS : ", xdata['uas'])
                 print("Nilai Akhir : ", xdata['akhir'])
             elif tanya == "H":
                 print("Hapus Data Berdasarkan NIM")
                 datahapus = input("Masukkan NIM data yang akan dihapus : ")
                 xhapus = next(item for item in baris if item['nim'] == datahapus)
                 del xhapus['nim']
                 del xhapus['nama']
                 del xhapus['tugas']
                 del xhapus['uts']
                 del xhapus['uas']
                 del xhapus['akhir']
                 print("Data Berhasil Dihapus")
                 no = 0
                 no += 1
                 x.field_names = ["No", "NIM", " NAMA", "TUGAS", "UTS", "UAS", "AKHIR"]
                 if not baris:
                     x.field_names = ["No", "NIM", " NAMA", "TUGAS", "UTS", "UAS", "AKHIR"]
                     print("Not Data")
                 else:
                     for data in baris:
                         x.add_row([no, data["NIM"], data["NAMA"], data["TUGAS"], data["UTS"], data["UAS"], data["AKHIR"]])
                     print(x)

             elif tanya == "K":
                 print("Anda Keluar Dari Aplikasi")
                 break
             else:
                 print("Anda Memilih Pilihan Yang Salah")

dan Berikut hasilnya :

- Jika pilih (T) untuk menambahkan data, dan hasilnya seperti berikut ini :
![T](https://user-images.githubusercontent.com/115931631/204125702-f1652daf-ebd8-4a15-9b97-79ce0cf707ed.png)
- Jika pilih (L) untuk melihat data, dan hasilnya seperti berikut ini :
![L](https://user-images.githubusercontent.com/115931631/204125728-9e075652-b809-4b83-8fbf-1f6d0bbaa24d.png)
- Jika pilih (U) untuk merubah data, dan hasilnya seperti berikut ini :
![U](https://user-images.githubusercontent.com/115931631/204125752-7f7edea9-47c0-4fcd-a299-04454f50ddc3.png)
- Jika pilih (C) untuk mencari data yang telah diinput, dan hasilnya seperti berikut ini :
![C](https://user-images.githubusercontent.com/115931631/204125767-6c2928fd-8a53-4af2-9b0f-794c9a7ba7c2.png)
- Jika pilih (H) untuk menghapus data yang ingin di hapus, hasilnya seperti berikut ini :
![H](https://user-images.githubusercontent.com/115931631/204125781-f48cfd5b-1512-41cd-8c3b-aefb9e9dc980.png)

# Selesai.  Seperti itulah program crud sederhana yang kita buat,



