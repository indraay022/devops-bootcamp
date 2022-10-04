### Definisikan apa itu Terminal menurut pemahamanmu
Terminal bisa juga disebut command prompt atau shell merupakan sebuah tool yang dapat digunakan user untuk berinteraksi dengan komputer.
  
***
### Jelaskan keuntungan menguasai Terminal
- Kita dapat mengontrol komputer kita lebih advanced
- Pekerjaan lebih cepat selesai dengan otomatisasi
- Dapat memberikan perintah yang lebih spesifik kepada komputer
- Sangat bermanfaat apabila bekerja di bidang IT

***
### Text Manipulation
### `cat` 
- `cat` umumnya dipakai untuk menampilkan isi file  
![Screen Shot 2022-09-02 at 00 08 48](https://user-images.githubusercontent.com/110447286/187984634-8feebf3d-d44b-4140-a50a-253932487deb.png)  

- kita juga bisa membuat file baru dengan perintah `cat > <namafile>`  
kemudian kita dapat mengedit isi dari file tersebut  
isikan minimal 1 baris lalu tekan enter agar dapat tersimpan  
Gunakan CTRL+C untuk keluar  
![Screen Shot 2022-09-02 at 00 09 16](https://user-images.githubusercontent.com/110447286/187984940-b5449543-8b9b-4923-9d08-fe1dfc4b1ede.png)  

- kita juga bisa menampilan isi suatu file dan menyimpannya ke sebuah file baru  
`cat <namafileinput1> <namafileinput2> > <namafileoutput>`  
![Screen Shot 2022-09-02 at 00 09 38](https://user-images.githubusercontent.com/110447286/187985814-23e4357d-4496-4d2a-83f1-0162c9de949d.png)  
  
  
### `sed`
Dapat digunakan untuk mereplace suatu kata dalam isi keseluruhan file menjadi kata baru dengan perintah `sed -i 's/<kataawal/<katabaru>/g' <namafile>`  
![Screen Shot 2022-09-02 at 00 15 13](https://user-images.githubusercontent.com/110447286/187986446-5186d45d-a6fe-449d-af0f-122ccfff782c.png)  
  
### `grep`
umumnya dipakai untuk mencari suatu kata dalam keseluruhan file atau folder  
`grep <kata> <namafile>`  
![Screen Shot 2022-09-02 at 00 16 05](https://user-images.githubusercontent.com/110447286/187986772-eda6ca86-7863-4227-a77f-4835ec192e6c.png)  
  
kita juga dapat menghitung jumlah kata yang muncul dalam suatu file  
`grep -c <kata> <namafile>`  
![Screen Shot 2022-09-02 at 00 16 54](https://user-images.githubusercontent.com/110447286/187987077-4144aa58-1db5-4090-8359-73b881d12af3.png)  

`grep` juga dapat digunakan untuk mencari kata dalam seluruh file yang ada di dalam folder  
`grep <kata> *`  
![Screen Shot 2022-09-02 at 00 16 54](https://user-images.githubusercontent.com/110447286/187987317-5d0f4d95-dda9-4b57-a77f-d6f873a49cbd.png)  

### sort
Digunakan untuk mngurutkan semua baris dalam file berdasarkan value terkecil hingga terbesar  
`sort <namafile>`  
![Screen Shot 2022-09-02 at 00 19 05](https://user-images.githubusercontent.com/110447286/187987636-b5d73b00-9dfd-40c0-b35d-810e3845c064.png)  

Kita juga dapat me-reverse urutan sebaliknya (terbesar - terkecil)  
`sort -r <namafile>`  
![Screen Shot 2022-09-02 at 00 19 15](https://user-images.githubusercontent.com/110447286/187987837-4ebe621a-3ea8-4ad3-a937-227fb5c123c7.png)  
  
***
### Monitoring Server
Monitoring server dilakukan untuk memeriksa kondisi, beban kerja, dan proses apa saja yang dijalankan oleh server baik itu proses system atau proses lainnya yang dijalankan oleh user.  
Kali ini kita mencoba untuk memonitoring server dengan perintah `htop`  
Monitoring di `htop` bersifat realtime sehingga kita dapat melihat update apa saja yang dijalankan oleh server secara interaktif  
![Screen Shot 2022-09-02 at 00 31 59](https://user-images.githubusercontent.com/110447286/187993290-493ffc12-e9af-4c63-9c6d-7c5a41c3aeb4.png)  
- **CPU** > status penggunaan CPU.  
Biru adalah proses yang bersifat 'low priority' yang berarti bahwa proses tersebut dapat dialokasikan oleh proses lain yang lebih penting  
Hijau adalah proses yang dijalankan oleh user  
Merah adalah proses yang dijalankan oleh kernel/sistem  
- **Mem** > status penggunaaan memori/ram.
- **Swp** > status partisi swap. 
- **Task** > total task dan thread yang sedang berjalan.  
- **Load average** > rata-rata penggunaan atau muatan sistem dalam beberapa menit sebelumnya  
- **Uptime** > total durasi server berjalan  
- **PID** > ID dari suatu proses  
- **USER** > pemilik dari suatu proses  
- **PRI** > tingkat prioritas proses skala 0-139 semakin kecil angka maka semakin tinggi prioritasnya  
- **NI** > nice value yang mempengaruhi prioritas  
- **VIRT** > total virtual memori yang digunakan oleh proses  
- **RES** > total memori yang digunakan oleh proses dalam satuan KB
- **SHR** > total shared memori yang digunakan oleh proses  
- **S** > status proses. R = Runnable, S=Sleep  
- **%CPU** > persentase penggunaan CPU  
- **%MEM** > persentase penggunaan Memori  
- **TIME+** > total durasi CPU yang digunakan oleh proses  
- **COMMAND** > perintah yang digunakan untuk mentrigger proses  
- 
***
### Buat sebuah file bash sederhana yang bertugas untuk update dan upgrade sistem
Kita buat file bash baru bernama `update.sh`  
`nano update.sh`
![Screen Shot 2022-08-30 at 21 23 34](https://user-images.githubusercontent.com/110447286/187472059-9b0744c1-3335-4f57-aac2-0c9e278bc7db.png)  

Di dalamnya kita isi perintah `sudo apt upgrade && sudo apt update`  
![Screen Shot 2022-08-30 at 21 23 07](https://user-images.githubusercontent.com/110447286/187472317-f465e77e-9e53-435d-b7da-00b8bbc6ef0b.png)  
  
Setelah itu kita bisa jalankan file bash tersebut dengan perintah `sudo bash <namafile.sh>`  
![Screen Shot 2022-08-30 at 21 46 26](https://user-images.githubusercontent.com/110447286/187472596-bda5b500-4bbb-4462-b401-66aa6e9b18a7.png)  
  
***
###  Buat sebuah file bash sederhana yang bertugas untuk mencari file bernama `sysctl.conf`
Kita buat file bash baru bernama `finder.sh`
`nano finder.sh`
![Screen Shot 2022-08-30 at 22 13 13](https://user-images.githubusercontent.com/110447286/187477030-93a32924-67cc-47fc-99c4-172aed909a90.png)  
  
Masukkan script berikut lalu save  
![Screen Shot 2022-08-30 at 22 22 21](https://user-images.githubusercontent.com/110447286/187477086-dd6f3d1f-34f6-4d95-83a1-0cb0635132f3.png)  
  
Kita coba jalankan file bash tersebut dengan perintah `bash finder.sh`  
Kemudian isikan nama file yang ingin dicari yaitu `sysctl.conf`  
Maka akan muncul file yang kita cari  
![Screen Shot 2022-08-30 at 22 28 09](https://user-images.githubusercontent.com/110447286/187478371-64dbe940-a247-4ab9-a592-a447a576767f.png)  
  
***
### Buat sebuah file bash serderhana yang bertugas untuk membuat firewall port 22, 80 dan 443 
Sebelumnya kita enable dulu firewall server kita dengan perintah `sudo ufw enable`  
![Screen Shot 2022-09-01 at 23 42 43](https://user-images.githubusercontent.com/110447286/187982611-86a9e51f-87b9-4640-b2dd-23819192d862.png)  
  
Kita buat file bash baru bernama `firewall.sh`  
![Screen Shot 2022-09-01 at 23 35 51](https://user-images.githubusercontent.com/110447286/187982669-c123a3ab-bd80-443f-8dbc-77ebb2a387b4.png)  
  
Masukkan script berikut lalu save  
![Screen Shot 2022-09-01 at 23 40 51](https://user-images.githubusercontent.com/110447286/187983064-3c69d604-d249-4340-8ae5-90b9960e91e5.png)  
  
Kita coba jalankan file tersebut dengan perintah `bash firewall.sh`  
Kemudian isikan port dan action yang ingin ditetapkan  
![Screen Shot 2022-09-01 at 23 43 28](https://user-images.githubusercontent.com/110447286/187983826-e00c232c-80e4-460d-996a-b5302c77dad7.png)
  
