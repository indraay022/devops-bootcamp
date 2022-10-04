## Definisikan apa itu Computer Network menurut pemahamanmu  
Computer Network adalah kumpulan komputer yang saling terhubung melalui media kabel atau nirkabel sehingga dapat saling berkomunikasi dan berbagi resource.

***
## Buatlah daftar perintah linux yang membantumu untuk memanagement linux server
- **sudo** -> menjalankan perintah atau aplikasi sebagai superuser(root)
- **mkdir** -> membuat direktori baru
- **ls** -> melihat daftar file atau folder yang ada di direktori
- **ls -la** -> untuk melihat semua daftar file atau folder baik yang tersembunyi ataupun tidak
- **cd** -> pindah ke direktori lain
- **cd ..** -> mundur satu direktori dari direktori yang sedang aktif
- **touch** -> membuat suatu file
- **cp** -> mengcopy file atau folder
- **mv** -> memindahkan lokasi file dan juga dapat digunakan untuk mengubah nama file
- **echo** -> menampilkan string dan juga dapat digunakan untuk menyisipkan string ke dalam file
- **cat** -> melihat isi dari suatu file
- **find** -> mencari file atau direktori
- **grep** -> mencari suatu teks dalam sebuah file atau seluruh direktori
- **chmod** -> mengganti izin/permission suatu file atau folder ataupun direktori
- **chown** -> mengganti kepemilikan suatu file atau folder untuk user tertentu
- **history** -> melihat riwayat perintah yang telah digunakan
- **ping** -> memeriksa koneksi dengan host lain
- **wget** -> mendownload suatu file
- **unzip** -> meng-ekstak file zip
- **zip** -> meng-compress file ke dalam zip

***
## Ganti IP server lama menjadi IP server baru
Pada shell server masukkan perintah `sudo nano /etc/netplan/00-installer-config.yaml`  
![VirtualBox_Ubuntu Server 2_25_08_2022_17_57_07](https://user-images.githubusercontent.com/110447286/186662993-b33a04b5-83f7-4e5b-a38a-497fba3ef95f.png)  

Berikut adalah config IPv4 yang digunakan  
![VirtualBox_Ubuntu Server 2_25_08_2022_17_57_25](https://user-images.githubusercontent.com/110447286/186663028-eadee555-d1e3-41e4-ad13-44c5cd3603bb.png)  

Untuk keluar dan menyimpan perubahan tekan `CTRL+X` lalu tekan `Y`  
  
Selanjutnya masukkan perintah `sudo netplan apply` untuk mengapply perubahan  
coba ping 8.8.8.8 untuk mengecek koneksi internet  
![VirtualBox_Ubuntu Server 2_25_08_2022_17_58_35](https://user-images.githubusercontent.com/110447286/186663171-1f0b7718-f2ae-4705-9f9a-1032b8ef4628.png)

***
## Lakukan remote server tersebut menggunakan IP baru
Pada kali ini server akan kita remote melalui terminal Ubuntu desktop  
Buka terminal lalu masukkan perintah `ssh <username>@<ip address>`  
Lalu ketik `Yes` dan masukkan password server  
![Screenshot from 2022-08-25 17-55-25](https://user-images.githubusercontent.com/110447286/186663502-c3788419-75da-43c2-9cbf-7edb7b8927a9.png)  

Jika berhasil maka hostname akan berubah menjadi hostname server  


## Install aplikasi web server apache di linux server
Sebelumnya kita masukkan perintah `sudo apt update` untuk mengupdate repository  
![Screenshot from 2022-08-25 18-00-45](https://user-images.githubusercontent.com/110447286/186663584-3c60ec44-2fa3-4197-ab00-51e036aa0474.png)  

Untuk menginstall Web Server masukkan perintah `sudo apt install apache2` lalu ketik `y` kemudian `enter`  
![Screenshot from 2022-08-25 18-01-52](https://user-images.githubusercontent.com/110447286/186663626-437e436b-e0fe-42f2-a568-9b7f6a62eaa6.png)  
***
## Akses aplikasi web server apache2 menggunakan browser melalui IP
Kita dapat mengakses alamat ip kita melalui browser untuk mengecek apakah apache2 sudah terinstall dan berjalan di server  
![Screenshot from 2022-08-25 18-02-42](https://user-images.githubusercontent.com/110447286/186663737-321244a5-371f-4b87-a79c-8f6d4f9f31ef.png)


***
## Buatlah localtunnel pada web server apache2
Untuk menginstall localtunnel kita perlu menginstall curl terlebih dahulu  
masukkan perintah `sudo apt install curl`  
![Screenshot from 2022-08-25 18-03-23](https://user-images.githubusercontent.com/110447286/186663805-b0d18da3-9726-4dcb-b520-cfbfce7bed22.png)


Selanjutnya kita instal Node Version Manager(nvm)
Masukkan perintah `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash`  
![Screenshot from 2022-08-25 18-03-55](https://user-images.githubusercontent.com/110447286/186663859-06a6b2f8-b5f6-4ed0-ae4b-3a48b4c35889.png)
  

Masukkan perintah `exec bash` untuk menghentikan perintah bash yang berjalan  
Gunakan perintah `nvm install 16` untuk mengintall Node Version Manager versi 16  
`nvm -v` untuk melihat versi nvm  
`node -v` untuk melihat versi node  
`npm -v` untuk melihat versi npm  
![Screenshot from 2022-08-25 18-05-42](https://user-images.githubusercontent.com/110447286/186663916-21db4889-ecbe-4c43-81ff-7d61cbfd1127.png)
  

Lalu kita install aplikasi localtunnel menggunakan perintah  `npm install -g localtunnel`  
![Screenshot from 2022-08-25 18-06-05](https://user-images.githubusercontent.com/110447286/186663954-d811bc0a-1e26-4494-ab22-b9e80f87aea2.png)
  
Jalankan local tunnel di port 80(http/https) agar Webserver kita dapat diakses melalui public  
masukkan perintah `lt -p 80` lalu akan muncul url untuk mengakses webserver kita lewat public  
![Screenshot from 2022-08-25 18-06-45](https://user-images.githubusercontent.com/110447286/186664062-de86865c-1095-4608-a2f9-087c6adfb629.png)  


Kita coba buka url tersebut melalui browser tekan tombol Click to continue  
![Screenshot from 2022-08-25 18-07-08](https://user-images.githubusercontent.com/110447286/186664249-69110187-41d6-444d-a045-923bfee3a510.png)  
![Screenshot from 2022-08-25 18-07-16](https://user-images.githubusercontent.com/110447286/186664286-97c101ae-29c7-40f4-8212-8069a1ef5288.png)
  
***

## Akses aplikasi web server apache2 menggunakan localtunnel lewat HP
Kita coba akses aplikasi webserver public kita melalui browser HP  
![Screenshot_20220825-180931](https://user-images.githubusercontent.com/110447286/186665119-c3223f0b-5edf-4a37-b60e-712f120abdb5.png)



