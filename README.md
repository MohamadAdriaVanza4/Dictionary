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

