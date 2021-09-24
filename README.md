# Jarkom-Modul-1-A03-2021

## Soal 1




## Soal 2




## Soal 3




## Soal 4




## Soal 5




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




## Soal 12




## Soal 13




## Soal 14




## Soal 15


