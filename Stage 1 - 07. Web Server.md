### Definisikan apa itu Web Server menurut pemahamanmu
Web server adalah sebuah layanan atau software yang berfungsi sebagai perantara antara user dengan server/database. User dapat meminta informasi atau data yang berkaitan dengan web pages atau web app dalam bentuk http/https. Kemudian web server memproses permintaan tersebut dengan menampilkan dari database.  

### Buatlah 3 buah server (server gateway, server aplikasi1, server aplikasi2)
Kali ini kita gunakan multipass untuk virtualisasi server1 dan server2  
`multipass launch lts --name <namaserver> --mem <ukuranmemori> --disk <ukuran disk> --cpus <jumlahcpu>`  
![Screen Shot 2022-08-31 at 22 07 43](https://user-images.githubusercontent.com/110447286/188051105-333c77d4-0872-4059-b75c-4be42d071d0d.png)  
![Screen Shot 2022-08-31 at 22 09 13](https://user-images.githubusercontent.com/110447286/188051121-8d8937ae-273b-44fa-a520-ffea77acc1b4.png)  

Kita jalankan `multipass ls` untuk melihat vm multipass yang sedang berjalan  
Disini kita akan gunakan `ubuntuvm` sebagai gateway, `server1` sebagai server aplikasi1, dan `server2` sebagai server aplikasi2.  
![Screen Shot 2022-08-31 at 22 11 00](https://user-images.githubusercontent.com/110447286/188051237-41d95127-f4cb-4f22-97b0-5d53043107c9.png)  

### Instal web server nginx pada server gateway
Kemudian kita masuk ke shell `ubuntuvm` dengan perintah `multipass shell ubuntuvm`  
Lalu kita install webserver nginx dengan perintah `sudo apt install nginx`  
![Screen Shot 2022-08-31 at 22 12 58](https://user-images.githubusercontent.com/110447286/188051605-6e6cf41f-408b-4ce0-baa5-28ef96c54ba1.png)  

### Instal aplikasi nodejs pada server aplikasi1 dan server aplikasi2
Kita asumsikan pada server 1 sudah terinstall nvm, npm, node, dan pm2  
![Screen Shot 2022-09-02 at 10 17 08](https://user-images.githubusercontent.com/110447286/188052072-2113c2e4-8db6-4538-8865-8585f1d6cad0.png)  

Selanjutnya kita clone nodejs app yang ada di github kita  
`git clone <urlrepository>`
![Screen Shot 2022-08-31 at 22 23 17](https://user-images.githubusercontent.com/110447286/188052191-6fe401af-1307-4094-91ce-3c2051a1496a.png)  

Kita masuk ke direktori baru (repository yang sudah kita clone)  
Lalu dalam folder tersebut kita jalankan perintah `npm install` untuk membuild webapp kita  
![Screen Shot 2022-08-31 at 22 40 10](https://user-images.githubusercontent.com/110447286/188052426-d571be10-a205-4494-b5dd-59c40322521b.png)

Setelah aplikasi selesai di build kita buat file bash baru `start.sh` untuk mentrigger webapp agar dapat berjalan  
`nano start.sh` 
![Screen Shot 2022-08-31 at 22 45 29](https://user-images.githubusercontent.com/110447286/188053047-128f9ad1-4e5f-4439-8a11-b4ce5027d093.png)  

Di dalam file bash tersebut kita isikan perintah `npm start`  
![Screen Shot 2022-08-31 at 22 45 40](https://user-images.githubusercontent.com/110447286/188053116-63e46749-6885-47b5-86c8-4d2f98ff8d0f.png)  

Kemudian kita jalankan file bash tersebut dengan pm2  
`pm2 start start.sh`  
Disini kita sudah dapat menjalankan webapp tersebut di background  
![Screen Shot 2022-08-31 at 22 46 41](https://user-images.githubusercontent.com/110447286/188053251-a1090b4b-6a07-4eb4-b88c-c4a7d71d342a.png)  

Lakukan langkah yang sama kepada server2  

***

### Buatlah sebuah konfigurasi reverse proxy pada server gateway yang mengarah ke server aplikasi1 dengan domain dumbways.xyz
### Buatlah sebuah konfigurasi load balancing pada server gateway yang mengarah ke server aplikasi2 dengan domain loadbalance.dumbways.xyz
Pada server gateway `ubuntuvm` kita pindah ke direktori `/etc/nginx`  
Lalu kita buat folder baru katakanlah `nodeapp` dengan perintah `sudo mkdir nodeapp`  
![Screen Shot 2022-08-31 at 23 03 19](https://user-images.githubusercontent.com/110447286/188053649-3a4319e8-5ff9-49b3-99f5-8908a1452bfe.png)  

Kita ganti kepemilikan folder `nodeapp` tersebut menjadi milik user `indra` (user saat ini)  
`sudo chown indra:indra nodeapp/`  
Lalu kita masuk ke dalam folder `nodeapp` dengan perintah `cd nodeapp/`  
Didalam folder nodeapp ini kita akan simpan konfigurasi reverse proxy webapp kita  
![Screen Shot 2022-08-31 at 23 04 48](https://user-images.githubusercontent.com/110447286/188053967-18d83706-c632-448a-bae4-a5731a13094c.png)  

Kita buat file baru dengan nama `nodeapp.conf`  
Didalamnya kita isikan script konfigurasi reverse proxy kita beserta loadbalance yang diterapkan  
![Screen Shot 2022-09-02 at 12 44 37](https://user-images.githubusercontent.com/110447286/188067420-437895a4-4b6b-4540-89e2-2751c08e91b8.png)  


Setelah itu kita mundur satu direktori dengan perintah `cd ..`  
Maka kita akan berada di direktori /etc/nginx  
Kita ubah file `nginx.conf` dengan perintah `sudo nano nginx.conf`  
![Screen Shot 2022-08-31 at 23 10 03](https://user-images.githubusercontent.com/110447286/188065216-6cd4e00c-5b44-490d-8c9d-6e7210e2cf80.png)  

Pada baris `include /etc/nginx/sites-enabled/*;` dibawahnya kita tambahkan baris include baru sesuai lokasi konfigurasi reverse proxy dari webapp yang kita buat  
`include /etc/nginx/nodeapp/*;`  
Simbol * artinya kita akan meload apa saja yang ada di dalam folder tersebut  
![Screen Shot 2022-08-31 at 23 10 35](https://user-images.githubusercontent.com/110447286/188065603-db61c2c5-a20e-46aa-80f2-8c25e6a5f88c.png)  
  
Selanjutnya kita cek konfigurasi nginx kita dengak perintah `sudo nginx -t`  
![Screen Shot 2022-08-31 at 23 11 58](https://user-images.githubusercontent.com/110447286/188065672-a0a0543a-c2c4-4a1f-872d-d47b6197ccd9.png)  

Lalu kita reload nginx dengan perintah `sudo systemctl reload nginx`  
![Screen Shot 2022-08-31 at 23 12 50](https://user-images.githubusercontent.com/110447286/188065777-d537dce4-2a50-482b-8aad-a1b1093c2c83.png)  

Selanjutnya pada file hosts lokal kita tambahkan nama domain dari webapp yang kita buat beserta resolve addressnya  
`sudo nano /etc/hosts`
kita tambahkan  
`192.168.64.3 dumbways.xyz`  
`192.168.64.3 loadbalance.dumbways.xyz`  
![Screen Shot 2022-09-02 at 12 39 50](https://user-images.githubusercontent.com/110447286/188067833-f19167e3-39ff-4874-b6d3-953eb1500bc9.png)  

setelah itu kita coba akses `http://dumbways.xyz`  
![Screen Shot 2022-09-02 at 12 59 18](https://user-images.githubusercontent.com/110447286/188069099-ef06a6c9-24c5-4546-9fd8-2891344e5bbc.png)  

Untuk memeriksa loadbalance berhasil kita coba matikan aplikasi pada server1  
Pada server1 `pm2 delete start`  
Maka layanan aplikasi akan dihapus dari proses background  
![Screen Shot 2022-09-02 at 13 04 38](https://user-images.githubusercontent.com/110447286/188069615-084d60b7-9709-4961-8509-c31dec91d9da.png)  

Sekarang kita coba akses lagi `http://dumbways.xyz`  
Maka webapp masih dapat berjalan  
![Screen Shot 2022-09-02 at 13 06 24](https://user-images.githubusercontent.com/110447286/188070005-1ec126fa-8ab4-4aec-82b8-7c527821afd2.png)  

