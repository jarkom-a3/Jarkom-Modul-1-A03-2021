# Jarkom-Modul-1-A03-2021

## Soal 1
Sebutkan webserver yang digunakan pada "ichimarumaru.tech"!
- Jalankan filter command  
```http contains "ichimarumaru.tech"```
![image](https://user-images.githubusercontent.com/62937814/134695495-6612dab8-409f-4bdf-a30b-c18e79b121c4.png)

- Klik kanan dan pilih menu Follow > TCP Stream
![image](https://user-images.githubusercontent.com/62937814/134695585-090bbeee-de6f-40ff-bf91-f6b55e172845.png)
![image](https://user-images.githubusercontent.com/62937814/134695612-358a855e-5ad3-4b2d-a4d1-ce35d9bed91a.png)

- Diketahui webserver yang digunakan adalah __nginx/1.18.0 (Ubuntu)__ dengan __destination port 80__
- Untuk mendapat informasi lebih spesifik, jalankan filter command  
```http.host == "ichimarumaru.tech"```
![image](https://user-images.githubusercontent.com/62937814/134696050-8100c26b-05ec-4951-a979-6472d04f01ff.png)

## Soal 2
Temukan paket dari web-web yang menggunakan basic authentication method!
- Jalankan filter command  
``http.authbasic``
![image](https://user-images.githubusercontent.com/62937814/134696206-2eb30b33-ee2d-4853-9fcc-bf1a725bd2b4.png)

## Soal 3
Ikuti perintah di basic.ichimarumaru.tech! Username dan password bisa didapatkan dari file .pcapng!
- Jalankan filter command  
```http.authbasic```
![image](https://user-images.githubusercontent.com/62937814/134696332-52462663-810a-481f-8b1b-d09d670a07f6.png)

- Lihat Hypertext Transfer Protocol -> Authorization
![image](https://user-images.githubusercontent.com/62937814/134696467-d0ccbd8e-3946-4aff-8e77-45f2025c7159.png)

- Dapat kita lihat bahwa terdapat Credentials dengan format username:password  
Username : __kuncimenujulautan__  
Password : __tQKEJFbgNGC1NCZlWAOjhyCOm6o3xEbPkJhTciZN__

- Setelah melakukan login, kita akan mendapatkan halaman yang merupakan pertanyaan untuk menjawab urutan konfigurasi pengkabelan T568A
![image](https://user-images.githubusercontent.com/62937814/134696719-f0edd01f-2d90-4179-ab99-08e88c317e5d.png)
- Jawaban dari kelompok kami untuk urutan konfigurasi pengkabelan T568A adalah:  
Urutan T568A :  
Urutan ke 1 : Putih Hijau  
Urutan ke 2 : Hijau  
Urutan ke 3 : Putih Orange  
Urutan ke 4 : Biru  
Urutan ke 5 : Putih Biru  
Urutan ke 6 : Orange  
Urutan ke 7 : Putih Coklat  
Urutan ke 8 : Coklat  

## Soal 4
Temukan paket __mysql__ yang mengandung __perintah query select!__
- Jalankan filter command  
```mysql.query contains "SELECT" or mysql.query contains "select"```
![image](https://user-images.githubusercontent.com/62937814/134697043-ecd06fcf-2cfb-45ad-a555-2180bee25528.png)

- Untuk melihat isi dari masing-masing paket, klik dua kali pada paket yang ingin diketahui detailnya
![image](https://user-images.githubusercontent.com/62937814/134697128-c1f96df9-a1f9-48e9-9f1d-3f023c3c5087.png)
ditemukan terdapat 3 paket yang mengandung perintah __query select__

## Soal 5
Login ke portal.ichimarumaru.tech kemudian ikuti perintahnya! Username dan password bisa didapat dari query insert pada table users dari file .pcap!
- Jalankan filter command  
```mysql.query contains "INSERT" or mysql.query contains "insert"```
![image](https://user-images.githubusercontent.com/62937814/134697356-a122bf99-c68a-4b20-8ee9-8ff4de7e1758.png)
- Pilih salah satu paket, lalu klik kanan dan pilih menu Follow > TCP Stream
![image](https://user-images.githubusercontent.com/62937814/134697425-0619b7b3-d46c-4226-b2c5-a045781e0159.png)
![image](https://user-images.githubusercontent.com/62937814/134697460-272a06b2-a572-4256-bf7f-0613bce417c3.png)

- Diketahui data yang di-insert ke table users memiliki username __akakanomi__ dan password __pemisah4lautan__
- Login ke portal.ichimarumaru.tech menggunakan username dan password yang telah diketahui
- Lalu akan muncul halaman seperti ini
![image](https://user-images.githubusercontent.com/62937814/134697623-5df6290b-8f61-4410-b8b6-686a8b66be83.png)
Jawaban dari kelompok kami untuk urutan konfigurasi pengkabelan T568B adalah:  
Urutan T568B :  
Urutan ke 1 : Putih Orange  
Urutan ke 2 : Orange  
Urutan ke 3 : Putih Hijau  
Urutan ke 4 : Biru  
Urutan ke 5 : Putih Biru  
Urutan ke 6 : Hijau  
Urutan ke 7 : Putih Coklat  
Urutan ke 8 : Coklat  


## Soal 6
Cari username dan password ketika melakukan login ke FTP Server!
- Menggunakan display filter<br>
  ```ftp contains "USER" || ftp contains "PASS"```
  ![Soal6](https://user-images.githubusercontent.com/68326540/134659274-3145a2f0-e2f1-48ea-a7c7-7bd9f46ec763.jpg)

  Sehingga diperoleh<br>
  username = secretuser<br>
  password = aku.pengen.pw.aja


## Soal 7
Ada 500 file zip yang disimpan ke FTP Server dengan nama 0.zip, 1.zip, 2.zip, ..., 499.zip. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya "Real.pdf")
- Menggunakan display filter<br>
  ```ftp-data contains "Real.pdf"```
  ![Soal7-1](https://user-images.githubusercontent.com/68326540/134659517-c6bbe80e-605c-4405-863e-e0e961e2eed2.jpg)
  File dengan nama “Real.pdf” ditemukan di dalam file “201.zip”
- Klik kanan kemudian ``Follow > TCP Stream`` dan pilih ``Show data as Raw``<br>
  ![Soal7-2](https://user-images.githubusercontent.com/68326540/134659786-6babbf9c-0c9f-4f65-85a3-30af89bbab04.jpg)
- Save as dengan nama "201.zip"<br>
  ![Soal7-3](https://user-images.githubusercontent.com/68326540/134660293-d0cf7d04-57b4-40fd-a05c-520f1c23fcd9.jpg)
- Buka file “Real.pdf” yang ada di dalam file “201.zip”<br>
  ![Soal7-4](https://user-images.githubusercontent.com/68326540/134660436-8d962f1a-4785-4479-9ea7-95142cbd3a04.jpg)


## Soal 8
Cari paket yang menunjukan pengambilan file dari FTP tersebut!
- Menggunakan display filter<br>
  ```ftp-data.command contains "RETR"```
  ![Soal8](https://user-images.githubusercontent.com/68326540/134660703-c8d9d6c1-dd70-4b5b-8e38-8b0494fb436a.jpg)
  Tidak ditemukan paket pengambilan file dari FTP tersebut

## Soal 9
Dari paket-paket yang menuju FTP terdapat inidkasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut!
- Menggunakan display filter<br>
  ```ftp-data.command contains secret.zip```
  ![Soal9-1](https://user-images.githubusercontent.com/68326540/134661293-047424c1-464a-432a-aa54-289573458c13.jpg)
 
- Klik kanan kemudian ``Follow > TCP Stream`` dan pilih ``Show data as Raw``<br>
  ![Soal9-2](https://user-images.githubusercontent.com/68326540/134661435-cea70208-ae44-47b4-8322-702755b2ae5d.jpg)

- Save as dengan nama "secret.zip"<br>
  ![Soal9-3](https://user-images.githubusercontent.com/68326540/134661611-fcc2d75b-9592-4392-a201-c9f4504d6de3.jpg)

- Buka file “secret.zip”<br>
  ![Soal9-4](https://user-images.githubusercontent.com/68326540/134661731-ff740f1e-4fa7-4317-87d7-7b123f3582d1.jpg)
  Terdapat file Wanted.pdf namun membutuhkan password untuk membukanya

## Soal 10
Selain itu terdapat "history.txt" yang kemungkinan berisi history bash server tersebut! Gunakan isi dari "history.txt" untuk menemukan password untuk membuka file rahasia yang ada di "secret.zip"!
- Menggunakan display filter<br>
  ```ftp-data.command contains "history.txt"```
  ![Soal10-1](https://user-images.githubusercontent.com/68326540/134661942-f42548ae-3a04-47ef-bb7d-12b57a214354.jpg)

- Klik kanan kemudian ``Follow > TCP Stream``<br>
  ![Soal10-2](https://user-images.githubusercontent.com/68326540/134662136-cd0f383f-2830-40fd-b0f5-c0a1356ff3f2.jpg)
  Terlihat bahwa secret.zip dibuat dari command zip dengan parameter -P (untuk mengatur password dari zip) yang diberi nilai dari variabel ``$key``. Variabel ``$key`` memiliki   nilai ``"$(tail -1 bukanapaapa.txt)"`` yang berarti membutuhkan suatu nilai pada baris terakhir dari file “bukanapaapa.txt”

- Menggunakan display filter untuk mencari file “bukanapaapa.txt” <br>
  ```ftp-data.command contains "bukanapaapa.txt"```
  ![Soal10-3](https://user-images.githubusercontent.com/68326540/134662419-43ceab0b-df3e-4582-9f96-dfbb4ca29a60.jpg)

- Klik kanan kemudian ``Follow > TCP Stream``<br>
  ![Soal10-4](https://user-images.githubusercontent.com/68326540/134662580-de7f109b-e8be-416a-8926-9e4550068a80.jpg)
  Diperoleh baris terakhir “d1b1langbukanapaapajugagapercaya” yang merupakan password dari file “Wanted.pdf”

- Membuka File “Wanted.pdf”<br>
  ![Soal10-5](https://user-images.githubusercontent.com/68326540/134662781-b3f60690-a460-4ce2-b395-c8fcf6d34532.jpg) 
  ![Soal10-6](https://user-images.githubusercontent.com/68326540/134662806-12e3abd9-6e66-4839-b22d-30c2fd268a7f.jpg)
 

## Soal 11

Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80! 

1. Menggunakan capture filter

```
src port 80
```

![image](https://user-images.githubusercontent.com/58259649/134700754-911b05a0-62b5-414e-b71a-64c4f7eb2981.png)

2. Hasilnya adalah sebagai berikut

![image](https://user-images.githubusercontent.com/58259649/134700765-a9cd6f83-6217-461c-b7b8-6a0a22464d6d.png)

## Soal 12

Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!

1. Menggunakan capture filter

```
port 21
```

![image](https://user-images.githubusercontent.com/58259649/134700886-2e39d5a2-384d-4a8f-b047-8de221c69bda.png)

2. Hasilnya adalah sebagai berikut

![image](https://user-images.githubusercontent.com/58259649/134700891-496138e5-a75c-4ce5-b213-6ab6e067c6d6.png)

## Soal 13

Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!

1. Menggunakan capture filter

```
dst port 443
```

2. Hasilnya adalah sebagai berikut

![image](https://user-images.githubusercontent.com/58259649/134700940-9e4896a7-0959-4885-bf99-fa9cdb867571.png)

## Soal 14

Filter sehingga wireshark hanya mengambil paket yang tujuannya ke kemenag.go.id!

1. Menggunakan capture filter

```
dst host kemenag.go.id
```

![image](https://user-images.githubusercontent.com/58259649/134700977-711b9e2a-eacb-4c10-ac95-b997b3b11c26.png)

2. Hasilnya adalah sebagai berikut

![image](https://user-images.githubusercontent.com/58259649/134700994-a67dff0a-e9e1-4e34-bb1d-5e728907686e.png)

## Soal 15

Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!

1. Cek IP dengan ipconfig

![image](https://user-images.githubusercontent.com/58259649/134701013-be40d9f8-c5f3-415f-893a-a68b539fec0c.png)

2. Menggunakan capture filter

```
src host 192.168.5.37 
```

![image](https://user-images.githubusercontent.com/58259649/134701027-81bd836c-8004-4608-827f-15eb568b8f79.png)

3. Hasilnya adalah sebagai berikut

![image](https://user-images.githubusercontent.com/58259649/134701078-8cd2ed52-0b5b-49c9-81b3-d00cddfafe8e.png)
