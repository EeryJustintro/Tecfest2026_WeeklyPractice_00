NAMA: I MADE ANANTA WIJAYA
NIM: 260530911102
DIVISI: CYBERSECURITY

# Tecfest2026_WeeklyPractice_00
Kategori CTF: Reverse Engineering dan Binary Exploitation \
Tools yang berhasil diinstal: 
- Git
- Github
- Python
- Binary Ninja

## Installasi Python
`python3` sudah otomatis terinstall di Kubuntu, jadi tidak perlu diinstall manual lagi \
<img width="900" height="173" alt="image" src="https://github.com/user-attachments/assets/b01bc81f-9db3-48d7-8879-14e98f941b71" />

## Installasi Git
`git` bisa diinstall dengan perintah `sudo apt install git` di distro linux berbasis Debian seperti Ubuntu. \
<img width="900" height="173" alt="image" src="https://github.com/user-attachments/assets/7264ddd2-037a-468e-b310-1ae9e24a2d3d" />

Cek apakah `git` sudah terinstall dengan benar \
<img width="489" height="49" alt="image" src="https://github.com/user-attachments/assets/9530dcd4-53f8-4126-a610-a641dcac0d70" />


## Pengujian WSL
Karena saya sudah dualboot Linux dan Windows jadi WSL tidak dibutuhkan. Pengerjaan challange dan installasi tools lain akan langsung dilakukan di Linux. Walaupun begitu, saya akan tetap melakukan tahap pengujian, prosesnya sebagai berikut: 
1. Buat folder bernama 'Week0-CyberSec-TecArt' dengan perintah `mkdir` lalu masuk dengan  `cd` \
   <img width="496" height="85" alt="image" src="https://github.com/user-attachments/assets/81a5c1fb-616c-4afa-952f-9c1c192e9371" />
2. Setelah masuk ke folder tersebut, buat file `README.md` dengan perintah `nano` \
   <img width="496" height="85" alt="image" src="https://github.com/user-attachments/assets/0bacc9d0-c6c5-4585-8c0b-85bb2d9f3682" />

4. Text editor yang digunakan adalah Nano, sebuah text editor simpel yang bisa langsung dipakai di terminal \
   <img width="900" height="528" alt="image" src="https://github.com/user-attachments/assets/885c4b93-407c-454d-af0e-22a233784bf8" /> \
5. Untuk menyimpan file, tekan CTRL+S pada keyboard. Kalau berhasil, akan terlihat pop-up 'Wrote - lines' di bawah \
   <img width="900" height="528" alt="image" src="https://github.com/user-attachments/assets/0c2619ff-71f2-4580-8b5d-323ffe30bf51" /> \
6. Untuk keluar dari nano, kita tekan CTRL+X pada keyboard. Untuk mengecek apakah berhasil, kita gunakan perintah `ls ` \
   <img width="900" height="528" alt="image" src="https://github.com/user-attachments/assets/2bbbc06b-b5ce-4677-9a20-18e76eb4c23c" /> \
   File `README.md ` berhasil dibuat!

## Pengujian Python
1. Saya sudah membuat file `test.py` dan menulis kode berikut
   <img width="900" height="528" alt="image" src="https://github.com/user-attachments/assets/f4036897-8df5-42ad-86d7-4d6a99b88c9e" /> \
2. Gunakan perintah `python3` untuk menjalankan file \
   <img width="496" height="113" alt="image" src="https://github.com/user-attachments/assets/a491a5aa-f474-4a61-9ce3-42b850533257" /> \
   Python berhasil menjalankan file tersebut dengan benar

## Challange Undo
Untuk memulai challange, gunakan perintah `nc foggy-cliff.picoctf.net 62814` di terminal. `nc` atau `netcat` adalah sebuah CLI tools yang digunakan untuk menulis data langsung lewat jaringan TCP/UDP
<img width="496" height="113" alt="image" src="https://github.com/user-attachments/assets/b90932cc-0be7-426b-9da3-08c0f6fc0a99" /> \
1. Berdasarkan hint, kita langsung tau bahwa text tersebut telah di encode menggunakan `base64`. Untuk mengembalikannya jadi teks semula, kita bisa menggunakan `base64 -d`
<img width="638" height="206" alt="image" src="https://github.com/user-attachments/assets/2c18d61b-abca-4dda-a372-162edec5bfb1" /> \
2. Hint memberi tahu kita bahwa text tersebut sudah di-reverse (dibalikkan). Oleh karena itu, kita bisa menggunakan `rev` untuk reverse teks tersebut kembali ke bentuk semula
<img width="638" height="90" alt="image" src="https://github.com/user-attachments/assets/94ea00ee-4a49-49c6-b72f-8dcccab8a83b" /> \
3. Semua simbol underscore (_) sudah diganti dengan dash (-) pada string tersebut. Kita bisa menggunakan `tr` untuk mengganti suatu karakter dengan karakter lain pada string
   <img width="638" height="90" alt="image" src="https://github.com/user-attachments/assets/95938f98-bc5f-4bfa-bac0-dbfa3b3c480e" /> \
4. Pada teks, semua curly braces {} sudah diganti dengan parentheses (). Selain mengganti karakter tunggal, `tr` bisa digunakan untuk mengganti kumpulan karakter dengan kumpulan karakter lainnya
   <img width="638" height="90" alt="image" src="https://github.com/user-attachments/assets/7656c0d0-6677-4c8c-ac3f-e1892d357f44" /> \
5. ROT13 adalah teknik substitusi sederhana yang menggeser setiap huruf sejauh 13 posisi dalam alfabet (26 huruf). Karena 26 dibagi 2 sama dengan 13, menerapkan ROT13 dua kali akan mengembalikan teks ke bentuk aslinya, sehingga proses encode dan decode ROT13 menggunakan command yang sama persis. Pada teks, semua huruf sudah digeser 13 posisi menggunakan ROT13. Untuk membalikkannya, digunakan command tr yang memetakan kumpulan huruf besar dan kecil ke posisi hasil geseran 13 langkah \
<img width="638" height="89" alt="image" src="https://github.com/user-attachments/assets/3ffe830e-a48f-4e8c-8d6e-49848d39a678" /> \

Semua stepsnya sudah kita lakukan, original flagnya adalah `picoCTF{Revers1ng_t3xt_Tr4nsf0rm@t10ns_0ea42cd0}`
<img width="638" height="89" alt="image" src="https://github.com/user-attachments/assets/0fc3df2f-e409-4358-ab6d-d24f155c890e" />

## Challange Reverse Engineering dan Binary Exploitation
Program yang digunakan adalah Binary Ninja, yaitu program yang dipakai untuk membedah, menganalisis, dan memahami program yang sudah dikompilasi (file executable/binary) tanpa perlu source code-nya. Bisa diunduh di https://binary.ninja/free/

## Challange Icibos Tekart 0
Jalankan program terlebih dahulu
<img width="889" height="70" alt="image" src="https://github.com/user-attachments/assets/870dae80-fbfe-4f03-841b-d8b42de0b4e8" /> \
Saat program ini dijalankan, kita bisa melihat bahwa program ini meminta input berupa kata ajaib. Karena ini adalah challange reverse engineering, jadi kita akan coba lihat isi binarynya sebelum mencoba input satu persatu. Biasanya, String yang di-hardcode dalam kode disimpan sebagai teks mentah di dalam binary. Coba kita buka program tersebut di Binary Ninja.
<img width="1174" height="794" alt="image" src="https://github.com/user-attachments/assets/b9741c44-d808-4478-bf26-d54765fe6ac4" /> \
Program mendeklarasikan sebuah konstanta string `p` bernilai "iniString". Setelah itu program menampilkan pesan dan meminta input dari user, disimpan ke variabel `r`. Setelah itu ada for loop yang membandingkan setiap karakter di variabel `p` dengan variabel `r`. Jika ada satu saja karakter yang berbeda antara `p` dan `r` pada posisi yang sama, flag `isCorrect` akan diubah menjadi `0`, menandakan input salah. Setelah loop selesai, program melakukan pengecekan akhir untuk menentukan hasilnya. Jika isCorrect bernilai 0, atau jika panjang input tidak tepat 9 karakter (meski isinya cocok), program akan menampilkan "password salah!". Baru jika kedua syarat terpenuhi, program memberikan output "password benar!" dan "tecart{1ntr0_to_R3vEr1n9}". \

Dapat disimpulkan bahwa "iniString" merupakan kata ajaib yang dimaksud. Sekarang kita melakukan pengecekan
<img width="903" height="100" alt="image" src="https://github.com/user-attachments/assets/bdd11842-7ac6-46be-9c5e-e5592a26f2a1" /> \
Ternyata benar, "iniString" merupakan kata ajaib yang dimaksud. Jika kita lihat, ada tanda % setelah "tecart{1ntr0_to_R3vEr1n9}". % itu bukan bagian dari flag, melainkan penanda dari shell (biasanya zsh) yang menunjukkan bahwa output program tidak diakhiri dengan newline (\n).

## Challange Icibos Tekart 1
Jalankan program terlebih dahulu
<img width="914" height="90" alt="image" src="https://github.com/user-attachments/assets/11398637-221d-4889-be68-17068b95144a" /> \
Sama seperti challange 0, program ini juga meminta input berupa kata ajaib. Saya akan menggunakan Binary Ninja untuk melihat kode program dengan lebih jelas
<img width="1280" height="845" alt="image" src="https://github.com/user-attachments/assets/7f833e62-3e15-4bb0-9d50-1f9eec9a91b2" /> \
Dalam `main()`, kita bisa melihat beberapa string, yaitu "bukanString", "Belajar reversing lagi", "Masukan kata ajaib: ", dan "password salah!". Di bagian awal, program menyalin "bukanString" ke variabel lokal `p`. Selanjutnya program menampilkan pesan dan meminta input dari user, lalu menyimpannya ke variabel `r`. Setelah itu ada for loop yang membandingkan setiap karakter di variabel `p` dengan variabel `r`. Jika ada satu saja karakter yang berbeda antara `p` dan `r` pada posisi yang sama, flag `isCorrect` akan diubah menjadi `0`, menandakan input salah. Setelah loop selesai, program melakukan pengecekan akhir untuk menentukan hasilnya. Jika `isCorrect` bernilai 0, program langsung menampilkan pesan "password salah!". Namun jika seluruh karakter cocok, program melakukan satu pengecekan lagi yaitu memastikan panjang input tepat 0xb (11 dalam desimal) karakter. Baru jika kedua syarat terpenuhi, fungsi `win(&r)` dipanggil.

Dapat disimpulkan bahwa "bukanString" merupakan kata ajaib yang dimaksud. Sekarang kita melakukan pengecekan
<img width="909" height="87" alt="image" src="https://github.com/user-attachments/assets/286c11c5-0148-4f31-8968-73ef742d3711" /> \
Ternyata benar, "bukanString" merupakan kata ajaib yang dimaksud.














