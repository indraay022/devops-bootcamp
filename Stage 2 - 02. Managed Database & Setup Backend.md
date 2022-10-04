## Buat server baru yang berperan sebagai Database Server
![Screen Shot 2022-09-08 at 11 32 05](https://user-images.githubusercontent.com/110447286/189039711-26e3b6ec-e42a-403a-98af-631c4c4980b3.png)

## Setup SSH
Dari lokal login ke server aplikasi  
![Screen Shot 2022-09-08 at 12 17 04](https://user-images.githubusercontent.com/110447286/189040151-bffa366a-400d-4c8d-bd1a-e5dbaf795105.png)  

Copy konfigurasi SSH key dari server aplikasi ke server database  
![Screen Shot 2022-09-08 at 11 51 57](https://user-images.githubusercontent.com/110447286/189040309-99b53ea4-aec5-4969-ac1c-87205549dfff.png)  

Coba login dari server aplikasi ke server database  
![Screen Shot 2022-09-08 at 12 22 21](https://user-images.githubusercontent.com/110447286/189040828-d723196c-c86d-4ed3-bf89-7a13b92dbd12.png)  

## Setup Hostname
Edit file /etc/hosts pada lokal  
Tambahkan 2 baris IP dan hostname milik server aplikasi dan server database  
![Screen Shot 2022-09-08 at 12 06 42](https://user-images.githubusercontent.com/110447286/189041264-023ee4af-1e94-459e-81c9-b6a7510787f4.png)  

Coba login dari lokal ke server aplikasi menggunakan user@hostname  
![Screen Shot 2022-09-08 at 12 20 49](https://user-images.githubusercontent.com/110447286/189041351-da08e3a5-7a93-4d05-af8a-993eb807201f.png)  

Pada server aplikasi kita edit /etc/hosts  
Tambahkan IP dan hostname milik server database agar dapat berpindah remote dengan mudah  
![Screen Shot 2022-09-08 at 12 04 21](https://user-images.githubusercontent.com/110447286/189041746-a0b554d1-69f1-4734-8862-882b3f815693.png)  

Coba login dari server aplikasi ke server database menggunakan user@hostname  
![Screen Shot 2022-09-08 at 12 05 03](https://user-images.githubusercontent.com/110447286/189041866-8ce34ac8-f90b-4578-a784-009b7e47f135.png)  

Untuk kembali lagi ke server aplikasi kita tinggal exit saja  

## Setup database MySQL Server
Install aplikasi MySQL-server  
![Screen Shot 2022-09-08 at 12 35 55](https://user-images.githubusercontent.com/110447286/189106873-dcd681aa-7e5e-4ea0-a191-81a37f1a6c76.png)  

Jalankan MySQL  
![Screen Shot 2022-09-08 at 12 47 11](https://user-images.githubusercontent.com/110447286/189106928-588fb4b2-8c17-48f1-a500-d92720090a5c.png)

Atur password MySQL untuk root  
![Screen Shot 2022-09-08 at 12 56 34](https://user-images.githubusercontent.com/110447286/189107567-073ea895-2ee3-4b8a-b1df-fc220182fb59.png)  

Jalankan secure installation untuk aplikasi MySQL  
![Screen Shot 2022-09-08 at 13 02 18](https://user-images.githubusercontent.com/110447286/189108925-dc27b217-4396-4451-aea2-1e088d980673.png)

Jalankan MySQL sebagai root  
Buat user baru dan atur passwordnya  
![Screen Shot 2022-09-08 at 13 07 49](https://user-images.githubusercontent.com/110447286/189109213-a6681f9b-c350-4157-a532-635e154190bd.png)  

Beri privilege pada user agar dapat mengatur database  
![Screen Shot 2022-09-08 at 13 16 57](https://user-images.githubusercontent.com/110447286/189109432-c83b9ca2-c11d-4ff4-ab35-07291f941b8e.png)  

Coba jalankan MySQL sebagai user baru  
![Screen Shot 2022-09-08 at 13 17 59](https://user-images.githubusercontent.com/110447286/189109551-085d7960-88cc-4a8b-8333-7e7d1a591984.png)  

Buat database baru `dumbflix`  
![Screen Shot 2022-09-08 at 13 23 59](https://user-images.githubusercontent.com/110447286/189109652-55927edf-14ae-463c-a836-424d7ef5b8da.png)  

Edit file konfigurasi MySQL  
![Screen Shot 2022-09-08 at 13 27 36](https://user-images.githubusercontent.com/110447286/189110194-b2edeeef-b228-4e4a-99be-b2ddcbf2c698.png)  

Atur aplikasi MySQL agar dapat diakses oleh jaringan luar / undefined address  
![Screen Shot 2022-09-08 at 13 28 32](https://user-images.githubusercontent.com/110447286/189110262-89bacaf0-ce46-468c-a8ae-717d5b414514.png)  

Restart aplikasi MySQL dan lihat statusnya  
![Screen Shot 2022-09-08 at 13 31 53](https://user-images.githubusercontent.com/110447286/189110369-75417f3c-2f41-4008-8433-cd97b90003a1.png)  

## Setup Aplikasi Backend  
Clone aplikasi backend dari github  
![Screen Shot 2022-09-08 at 13 33 19](https://user-images.githubusercontent.com/110447286/189110538-e83abdf5-3489-47d0-8614-681e89d1717e.png)

Masuk ke direktori aplikasi  
Lihat requirement aplikasi di README.md  
![Screen Shot 2022-09-08 at 13 34 38](https://user-images.githubusercontent.com/110447286/189111215-4f7bf5e7-ee0e-4dd0-9a14-1b1a1466b3e6.png)  

Install Sequelize  
![Screen Shot 2022-09-08 at 14 19 01](https://user-images.githubusercontent.com/110447286/189111302-c8cc11a7-ae53-46da-b283-5fd9941561d1.png)  

Install NVM versi 10  
![Screen Shot 2022-09-08 at 14 22 55](https://user-images.githubusercontent.com/110447286/189111365-9f893f79-d876-41c2-ab0f-d278dd584e83.png)  

Build aplikasi backend  
![Screen Shot 2022-09-08 at 14 26 32](https://user-images.githubusercontent.com/110447286/189113379-3b216ddc-6f25-43d6-adca-668a2a5a7889.png)  

Buat file ecosystem  
![Screen Shot 2022-09-08 at 14 24 32](https://user-images.githubusercontent.com/110447286/189113436-d2b5e12f-fcaf-4ac8-b636-a84b54798757.png)  

Edit file ecosystem  
![Screen Shot 2022-09-08 at 14 24 54](https://user-images.githubusercontent.com/110447286/189113507-0c159c81-0248-419f-a569-b355e9d78910.png)

Edit nama aplikasi dan script-nya  
![Screen Shot 2022-09-08 at 14 25 35](https://user-images.githubusercontent.com/110447286/189113578-7745edba-68e8-4e66-b6da-a796c1c6db26.png)  

Edit file config/config.json  
![Screen Shot 2022-09-08 at 14 09 00](https://user-images.githubusercontent.com/110447286/189111563-eed6f672-98ed-4387-b078-3614ea1ee8b9.png)  

Isikan kredensial aplikasi MySQL yang sudah kita setup  
![Screen Shot 2022-09-08 at 14 27 41](https://user-images.githubusercontent.com/110447286/189111704-5b16bc8b-47ce-4e0f-a92c-66bdea6363c7.png)   

Migrate isi database aplikasi backend ke database server  
![Screen Shot 2022-09-08 at 14 28 10](https://user-images.githubusercontent.com/110447286/189111900-29a96c60-80df-400e-9c6e-01657c97bb81.png)  

Cek apakah isi database aplikasi sudah masuk ke database server  
Masuk ke server database  
![Screen Shot 2022-09-08 at 14 29 13](https://user-images.githubusercontent.com/110447286/189112415-e62cdf27-87b6-4b32-996b-335fc9339d98.png)  

Jalankan aplikasi MySQL sebagai user baru  
![Screen Shot 2022-09-08 at 14 29 31](https://user-images.githubusercontent.com/110447286/189112723-3054e74f-1fae-448a-98f5-0e2f9fe1bea3.png)  

Lihat isi dari database `dumbflix`  
![Screen Shot 2022-09-08 at 14 32 50](https://user-images.githubusercontent.com/110447286/189112867-dcaef7d0-203a-47ab-9423-b2b8e338d033.png)  

Kembali ke server aplikasi  
Jalankan file ecosystem  
![Screen Shot 2022-09-08 at 14 33 54](https://user-images.githubusercontent.com/110447286/189114054-8d6e0dc1-4446-4de0-b60d-5cd8a0a01fb9.png)  

Coba akses aplikasi backend melalui browser  
![Screen Shot 2022-09-08 at 14 34 46](https://user-images.githubusercontent.com/110447286/189114077-eafc210b-6e9d-4a4c-83ae-8c3348112b01.png)  

## Konfigurasi Reverse Proxy Aplikasi Backend  
Pada server aplikasi masuk ke direktori nginx  
Duplikat file konfigurasi aplikasi frontend menjadi file baru yang nantinya digunakan untuk menampung konfigurasi aplikasi backend  
![Screen Shot 2022-09-08 at 14 36 56](https://user-images.githubusercontent.com/110447286/189114823-ce94cd7f-d189-4e4e-b8fa-de27d80288aa.png)  

Edit file baru tersebut sesuai konfigurasi aplikasi backend  
![Screen Shot 2022-09-08 at 14 37 25](https://user-images.githubusercontent.com/110447286/189115061-d94e283a-f5ea-48d0-bd66-3ee10c62aff7.png)  

Test konfigurasi nginx  
![Screen Shot 2022-09-08 at 14 38 28](https://user-images.githubusercontent.com/110447286/189115156-ef6f96cb-66d2-40c8-a283-9fa48f879508.png)  

Pada cloudflare kita buat record baru  
![Screen Shot 2022-09-08 at 14 41 56](https://user-images.githubusercontent.com/110447286/189115284-76305126-a8da-43c6-b163-f0557fca895f.png)  

Coba akses domain aplikasi backend  
Disini kita perlu mendeploy ssl certificate ke domain kita agar koneksi aman terenkripsi  
![Screen Shot 2022-09-08 at 14 42 29](https://user-images.githubusercontent.com/110447286/189115410-847fe1d1-c751-44d8-b689-6d7d7b6f405a.png)  

## Setup Certbot  
Install snapd  
![Screen Shot 2022-09-08 at 14 42 29](https://user-images.githubusercontent.com/110447286/189115682-040a102a-177a-4c71-8a04-bb98a42bac6c.png)  

Install core kemudian refresh core  
![Screen Shot 2022-09-08 at 14 55 55](https://user-images.githubusercontent.com/110447286/189115834-8380797c-d1c5-432e-a1b3-fdf650a6e86a.png)  

Install certbot  
![Screen Shot 2022-09-08 at 14 56 54](https://user-images.githubusercontent.com/110447286/189115913-a4fd5313-1eee-4676-b565-c87525096ac6.png)  

Cek apakah certbot dapat dijalankan  
![Screen Shot 2022-09-08 at 14 57 22](https://user-images.githubusercontent.com/110447286/189116013-57e7a8f9-adb0-418a-bb89-e93c6d17e080.png)  

Jalankan certbot  
Isi informasi yang diminta oleh certbot  
![Screen Shot 2022-09-08 at 15 17 30](https://user-images.githubusercontent.com/110447286/189116112-2d4e1c0a-f74f-49ce-b9a3-f9efe4c06e3c.png)  
![Screen Shot 2022-09-08 at 15 17 22](https://user-images.githubusercontent.com/110447286/189116227-41a84cb7-9b9a-4f97-a884-88ae96698b2f.png)  

Pada cloudflare kita matikan proxy dan atur menjadi DNS only  
![Screen Shot 2022-09-08 at 15 40 49](https://user-images.githubusercontent.com/110447286/189116683-0a588c27-f079-45b4-bbae-ce51ee3075ce.png)  

Reload/restart nginx  
![Screen Shot 2022-09-08 at 15 18 35](https://user-images.githubusercontent.com/110447286/189116277-381546c7-9e1e-4a9b-b826-31be636a8833.png)

Coba buka aplikasi backend melalui browser  
![Screen Shot 2022-09-08 at 16 02 42](https://user-images.githubusercontent.com/110447286/189116876-e2f6bfce-51db-40b2-a27d-f3afafa45d01.png)

## Integrasi aplikasi frontend dengan backend  
Pada server aplikasi masuk ke direktori aplikasi frontend  
Edit file /src/config/api.js  
![Screen Shot 2022-09-08 at 16 15 32](https://user-images.githubusercontent.com/110447286/189117448-abff7773-5409-48d9-b7a9-875c371d227c.png)  

Edit baseURL sesuai domain aplikasi backend  
![Screen Shot 2022-09-08 at 16 18 32](https://user-images.githubusercontent.com/110447286/189117622-9861d017-8511-4640-8b4c-ec1c4ae05ec4.png)  

Buka domain aplikasi frontend melalui browser  
Coba daftarkan user baru  
![Screen Shot 2022-09-08 at 16 27 36](https://user-images.githubusercontent.com/110447286/189117878-a4651099-1d7e-4a75-9968-49376837a7b3.png)  

Kita lihat profile apakah data sudah tersimpan  
![Screen Shot 2022-09-08 at 16 27 46](https://user-images.githubusercontent.com/110447286/189117931-c52bc0be-1e7f-4ea8-ad01-63fada2ef2ec.png)  
