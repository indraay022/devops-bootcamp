## IDCloudHost
IDClodHost adalah salah satu web hosting provider di Indonesia yang juga menawarkan layanan cloud computing dan juga beberapa layanan lainnya.  
![Screen Shot 2022-09-06 at 15 44 25](https://user-images.githubusercontent.com/110447286/188590050-632a115d-a84e-4005-8479-3d8082b1249c.png)  

## Setting Up Service Baru di IDCloudHost
Login di https://console.idcloudhost.com/hub/login dengan akun yang sudah terdaftar  
![Screen Shot 2022-09-06 at 13 05 02](https://user-images.githubusercontent.com/110447286/188590530-260d09bc-abfc-4d89-b5ed-351c7ee780b6.png)  

Klik View More untuk melihat akses dan invitasi yang kita kelola
![Screen Shot 2022-09-06 at 13 06 03](https://user-images.githubusercontent.com/110447286/188591085-11daf0dc-e3fa-4936-9be2-559b4b66668f.png)  

Klik Accept Invitation  
![Screen Shot 2022-09-06 at 13 06 17](https://user-images.githubusercontent.com/110447286/188591693-64f5a4ad-373d-4ff1-bc2a-86c83a341cb5.png)  

Klik Accept  
![Screen Shot 2022-09-06 at 13 06 31](https://user-images.githubusercontent.com/110447286/188592000-271ece02-e137-4ef8-8192-9b62c9f107ee.png)  

Klik Nama User > Act as > email akun lain  
![Screen Shot 2022-09-06 at 13 07 16](https://user-images.githubusercontent.com/110447286/188592572-27180310-d1f9-4da8-b435-134e97ee8ec9.png)  

Klik Start  
![Screen Shot 2022-09-06 at 13 07 23](https://user-images.githubusercontent.com/110447286/188592636-9b15a2e0-2bec-4f0b-b243-8cebe823d839.png)  

Klik Virtual Machine
![Screen Shot 2022-09-06 at 13 10 50](https://user-images.githubusercontent.com/110447286/188593841-e4b59e45-aa84-4929-bba8-9d1221f3c380.png)  

Type > Virtual Machine  
OS > Ubuntu  
![Screen Shot 2022-09-06 at 13 10 56](https://user-images.githubusercontent.com/110447286/188594912-3fdcd35d-fc46-420a-967e-2b4cd9127f4f.png)  

Location > Indonesia  
Size > 1 CPU, 1GB RAM, 20GB Disk  
![Screen Shot 2022-09-06 at 13 12 34](https://user-images.githubusercontent.com/110447286/188594934-17f49168-e34c-4396-90ab-1c420960cf06.png)  

Klik Create a public IPv4 address for the resource  
VPC = Default  
Username = isikan username untuk login ke dalam VM  
Password = isikan password untuk login ke dalam VM  
Resource Name = nama host remote server kita  
Billing Account = Akun yang digunakan untuk membayar  
![Screen Shot 2022-09-06 at 13 19 12](https://user-images.githubusercontent.com/110447286/188596475-8bccb965-364a-4a5b-aa6a-c7e4dbe3f61e.png)  

Tunggu proses building VM selesai  
![Screen Shot 2022-09-06 at 13 19 30](https://user-images.githubusercontent.com/110447286/188596553-41221c00-a57f-47b7-a1ca-bedde69ef191.png)  

VM/Server sudah berhasil di build  
![Screen Shot 2022-09-06 at 13 22 43](https://user-images.githubusercontent.com/110447286/188596733-6638be4f-a2d6-427c-8370-15610971bb08.png)  

## Konfigurasi SSH
Copy IP Publik Server kita  
![Screen Shot 2022-09-06 at 13 22 54](https://user-images.githubusercontent.com/110447286/188610450-9f00b7c5-a499-4fb7-95bd-a516518a7ae9.png)

Kita remote dengan SSH  
`ssh indra@<ip public>`
Ketik yes untuk melanjutkan  
![Screen Shot 2022-09-06 at 13 24 23](https://user-images.githubusercontent.com/110447286/188605385-f4329e15-c69c-4ab7-b898-a56213d36bcb.png)  

Pada lokal kita generate SSH Key  
![Screen Shot 2022-09-06 at 14 29 47](https://user-images.githubusercontent.com/110447286/188597304-d9e67a35-4323-4f07-bf28-f36b1d1f8324.png)  

Masuk ke direktori .ssh  
Buka file `id_rsa.pub` lalu copy isi dari file tersebut
![Screen Shot 2022-09-06 at 14 31 25](https://user-images.githubusercontent.com/110447286/188606449-51f458f3-54a0-4c8c-8c3f-7102d74a43f1.png)

Pada server masuk ke `/home/indra/.ssh/`  
Buat file baru bernama `authorized_keys`  
![Screen Shot 2022-09-06 at 17 07 05](https://user-images.githubusercontent.com/110447286/188608412-1e65adbe-586e-448d-aca8-6db028ea3cdd.png)  

Paste-kan isi dari file `id_rsa.pub` tadi lalu simpan  
![Screen Shot 2022-09-06 at 14 33 25](https://user-images.githubusercontent.com/110447286/188608473-f614d8d1-1e31-4203-bbf9-466a478af956.png)  

Pada lokal kita coba gunakan key `id_rsa` untuk login ke server  
![Screen Shot 2022-09-06 at 17 11 55](https://user-images.githubusercontent.com/110447286/188609364-411c72ae-99d2-4284-bd47-c8cacdc9f0cd.png)  

## Deploy Aplikasi pada server
Clone repository aplikasi dari github  
![Screen Shot 2022-09-06 at 14 52 19](https://user-images.githubusercontent.com/110447286/188612092-1ecb96b7-d3ba-49a8-a711-2afcd9536662.png)  

Install NodeJS machine  
![Screen Shot 2022-09-06 at 14 53 08](https://user-images.githubusercontent.com/110447286/188612276-b3025fce-a910-44ff-8ffb-f83b25176993.png)  

`exec bash`  
Lalu install NVM versi 14  
![Screen Shot 2022-09-06 at 14 53 54](https://user-images.githubusercontent.com/110447286/188612408-8f6b55cf-8ddd-46cd-8807-c2ca8219d57b.png)  

Install juga PM2  
![Screen Shot 2022-09-06 at 14 54 48](https://user-images.githubusercontent.com/110447286/188612783-8e01c9ac-fe80-4071-b6d4-8b6ae0e60976.png)  

Masuk ke dalam folder `dumbflix-frontend`  
Buat file ecosystem PM2  
![Screen Shot 2022-09-06 at 14 56 02](https://user-images.githubusercontent.com/110447286/188613131-7b7b74f0-b797-405c-9111-5b78e718d8a4.png)  

Edit file `ecosystem.config.js`  
![Screen Shot 2022-09-06 at 15 01 31](https://user-images.githubusercontent.com/110447286/188613281-bf994c42-ce72-4f6e-a89e-3dcf37ac5668.png)  

name = "nama aplikasi"  
script = "npm start"  
![Screen Shot 2022-09-06 at 15 02 02](https://user-images.githubusercontent.com/110447286/188613338-40c492fb-9702-463d-baaf-6ec939d31662.png)

Kita build aplikasi  
![Screen Shot 2022-09-06 at 15 02 37](https://user-images.githubusercontent.com/110447286/188613885-1af454f3-5011-400f-8195-2e96577aaa68.png)  

Kita jalankan aplikasi dalam proses background  
![Screen Shot 2022-09-06 at 15 05 00](https://user-images.githubusercontent.com/110447286/188614010-9b53f76a-0264-4db4-b801-dc2ed6caf3ba.png)  

Kita coba buka di browser  
![Screen Shot 2022-09-06 at 15 06 51](https://user-images.githubusercontent.com/110447286/188614083-4ea306f1-4c57-4bc8-a16e-7508662fcab7.png)  

## Konfigurasi Nginx
Install nginx  
![Screen Shot 2022-09-06 at 15 07 50](https://user-images.githubusercontent.com/110447286/188637167-c7755c44-56fe-482f-8ca9-b154af916a81.png)  

Pindah ke direktori `/etc/nginx`  
Buat folder baru `dumbflix/`  
![Screen Shot 2022-09-06 at 15 14 39](https://user-images.githubusercontent.com/110447286/188637320-48256261-15e2-4f2a-b2f5-06ab2e3adafd.png)  

Ubah kepemilikan folder `dumbflix/` dari milik root menjadi milik user indra  
![Screen Shot 2022-09-06 at 15 15 10](https://user-images.githubusercontent.com/110447286/188637838-6641c4df-e247-47b2-ad35-b5e92427fd8c.png)  

Buat file `dumbflix.conf` di dalam folder `dumbflix/`  
![Screen Shot 2022-09-06 at 15 23 46](https://user-images.githubusercontent.com/110447286/188638064-a43c276d-53a9-4ca9-b697-a710b52c0bba.png)

Isikan script reverse proxy seperti di bawah  
![Screen Shot 2022-09-06 at 19 29 57](https://user-images.githubusercontent.com/110447286/188638242-c9555436-4488-4873-a66a-d27d56cc1800.png)  

Edit file `nginx.conf`  
Include-kan konfigurasi di folder `dumbflix/`  
![Screen Shot 2022-09-06 at 15 24 05](https://user-images.githubusercontent.com/110447286/188638589-75d2dbcf-184d-4795-b708-8f9e2791403f.png)  

Periksa konfigurasi apakah berjalan dengan sukses  
![Screen Shot 2022-09-06 at 18 26 56](https://user-images.githubusercontent.com/110447286/188638776-47913ffd-c3f5-4ee4-9b7c-7a33e2a1d07a.png)  

Reload service nginx  
![Screen Shot 2022-09-06 at 18 27 36](https://user-images.githubusercontent.com/110447286/188638888-cd98e2e6-bd2f-4a41-b932-cbe0a14bb1e8.png)

## Konfigurasi Cloudflare
Buka https://dash.cloudflare.com  
Pilih akun pemilik nama domain  
![Screen Shot 2022-09-06 at 17 52 48](https://user-images.githubusercontent.com/110447286/188640315-00eebe22-4d38-4899-aa8e-ea3bd3b7b190.png)  

Pilih domain yang akan digunakan  
![Screen Shot 2022-09-06 at 17 53 00](https://user-images.githubusercontent.com/110447286/188640355-f9fc3421-b6ce-471e-820b-2c5394565116.png)  

Klik DNS  
Klik Add record  
![Screen Shot 2022-09-06 at 17 53 51](https://user-images.githubusercontent.com/110447286/188640777-d6473223-fafc-4eca-a6ad-778943a6ad1d.png)  

Name = indra  
IPv4 = ip public server  
Proxy status = ON  
Save  
![Screen Shot 2022-09-06 at 18 28 24](https://user-images.githubusercontent.com/110447286/188641775-8adcc071-7636-4e3a-bbc9-8e135e713db9.png)  

Kita coba buka https://indra.studentdumbways.my.id di browser  
![Screen Shot 2022-09-06 at 20 00 56](https://user-images.githubusercontent.com/110447286/188641995-534667e8-f910-4304-896b-70369f6e0391.png)  
