## Definisikan apa itu Application menurut pemahamanmu
Aplikasi adalah sebuah perangkat lunak komputer yang dibuat untuk melakukan fungsi spesifik.
***
## Siapkan environment untuk aplikasi NodeJS, Python dan Go. Buatlah sebuah aplikasi sederhana menggunakan NodeJS, Python dan Golang. Jalankan aplikasi NodeJS, Python dan Go pada server dan pastikan dapat di akses
### NodeJS
Pertama kita install curl terlebih dahulu  
`sudo apt insall curl`  
![Screenshot from 2022-08-25 18-03-23](https://user-images.githubusercontent.com/110447286/186704840-1f851038-ab00-4a15-b892-b30ae53baa6d.png)


Kemudian kita instal NVM meenggunakan perintah curl  
`curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash`  
![Screenshot from 2022-08-25 18-03-55](https://user-images.githubusercontent.com/110447286/186704885-0eda7018-3de7-468a-ae14-82ba18e7e620.png)

  
Kita jalankan perintah exec bash  
Lalu kita install NVM versi 16  
`nvm install 16`  
![Screenshot from 2022-08-25 18-04-58](https://user-images.githubusercontent.com/110447286/186704923-4e1fef73-ec6b-416a-82dc-3cc3ae972da7.png)  

Setelah itu kita buat folder untuk aplikasi nodejs  
`mkdir nodejs`  
Lalu kita pindah ke folder nodejs  
`cd nodejs/`  
Kita masukkan perintah `npm init -y` pada folder tersebut untuk setup project baru  
Maka akan muncul file package.json yang berfungsi untuk menampung informasi mengenai project  

![Screenshot from 2022-08-25 20-17-01](https://user-images.githubusercontent.com/110447286/186707364-5f7d18cd-6ea6-4b9a-9cdd-c577bc551f46.png)  

Setelah itu kita install framework nodejs yaitu Express JS  
masukkan perintah `npm install express --save`

![Screenshot from 2022-08-25 20-17-34](https://user-images.githubusercontent.com/110447286/186707830-80ece146-05d5-4a53-9ffe-57a53ae52606.png)

Kita buat file index.js dengan perintah `nano index.js`  

![Screenshot from 2022-08-25 22-33-25](https://user-images.githubusercontent.com/110447286/186708229-2feb4578-2c5b-4aaa-a565-d571c475c39d.png)  

Berikut adalah skrip yang digunakan dalam file index.js  
![Screenshot from 2022-08-25 20-18-05](https://user-images.githubusercontent.com/110447286/186708423-41ab576a-18a8-4959-83aa-c9c0c8dce5bc.png)  

Kita jalankan index.js dengan perintah `node index.js`  

![Screenshot from 2022-08-25 20-18-43](https://user-images.githubusercontent.com/110447286/186708598-0a2af832-452e-4fa5-9f24-49a1aa82def9.png)  

Pada browser kita akses ip address server di port 3000
![Screenshot from 2022-08-25 20-20-20](https://user-images.githubusercontent.com/110447286/186708923-c673a906-df32-42c1-92f9-1137b3b1305f.png)  
Aplikasi berhasil dijalankan  

###Golang
Pertama kita install golang-go pada server dengan perintah `sudo apt install golang-go`  

![Screenshot from 2022-08-25 20-42-51](https://user-images.githubusercontent.com/110447286/186709730-e898cd27-c0a2-46a0-b173-8c74e98b7e9d.png)  
  
Masukkan perintah `go version` untuk melihat versi Golang yang telah terinstall  
![Screenshot from 2022-08-25 20-43-11](https://user-images.githubusercontent.com/110447286/186710101-f06a0838-b62c-4564-8e4e-d05894cf3229.png)  

Kita edit file .bashrc pada direktori /home/<user>  
masukkan perintah `sudo nano .bashrc`  
![Screenshot from 2022-08-25 22-45-49](https://user-images.githubusercontent.com/110447286/186711246-ccad3a89-3103-4fe2-bca1-ad2f346e61b8.png)

Pada baris terakhir kita tambahkan keterangan berikut  
`export PATH=$PATH:/usr/local/go/bin`  

![Screenshot from 2022-08-25 20-38-05](https://user-images.githubusercontent.com/110447286/186711561-5cd07c71-d9cd-4be4-a57c-607ec3cf6d8a.png)


Kita buat folder baru untuk aplikasi golang  
Lalu kita pindah ke folder tersebut  
![Screenshot from 2022-08-25 20-21-08](https://user-images.githubusercontent.com/110447286/186709409-e055d9b7-d513-480e-a9f3-238bab421610.png)  

Kita buat file index.go dengan editor nano  
Masukkan perintah `nano index.go`  
![Screenshot from 2022-08-25 20-43-37](https://user-images.githubusercontent.com/110447286/186711882-f534a583-dc6f-4a2d-9d4e-8586559796a0.png)  

Masukkan script seperti berikut kedalam file index.go  
![Screenshot from 2022-08-25 20-44-03](https://user-images.githubusercontent.com/110447286/186712025-0c0dfa26-f4e4-489b-ba4c-ba4f77b15588.png)  

Selanjutnya kita coba jalankan index.go tersebut dengan perintah `go run index.go`  

![Screenshot from 2022-08-25 20-44-19](https://user-images.githubusercontent.com/110447286/186712238-4a0d64b6-1692-42cc-b27c-09e081789055.png)  

### Python
Karena secara default Ubuntu sudah terinstall python3 maka kita tidak perlu menginstall python pada server ubuntu kita  

Buat folder baru untuk aplikasi python yang akan kita buat  
Masukkan perintah `mkdir python`  
Lalu pindah ke folder tersebut dengan perintah `cd python`  
Jalankan perintah `python -V` untuk melihat versi python3 yang terinstall  

![Screenshot from 2022-08-25 20-47-47](https://user-images.githubusercontent.com/110447286/186713343-bdfb4aa6-5f8b-4023-8d8e-377fd73c0852.png)  

Kita install Package installer for python dengan perintah `sudo apt install python3-pip`  
![Screenshot from 2022-08-25 20-48-41](https://user-images.githubusercontent.com/110447286/186713676-6726ec79-04c4-430d-8287-f8ae6f6ca570.png)  

Kita gunakan pip untuk menginstall framework flask  
Masukkan perintah `pip install flask`  
![Screenshot from 2022-08-25 20-49-11](https://user-images.githubusercontent.com/110447286/186714022-c5428282-d7a0-4aad-bd10-ced294716f24.png)  

Kita buat file index.py dengan nano text editor  
Masukkan perintah `nano index.py`  
![Screenshot from 2022-08-25 20-49-26](https://user-images.githubusercontent.com/110447286/186714312-5d8581b6-271b-4a1d-8c93-247108ea479b.png)  

Berikut adalah script python yang kita gunakan  
![Screenshot from 2022-08-25 22-03-41](https://user-images.githubusercontent.com/110447286/186714608-0ff30008-f4fb-4bcf-a056-28a762cd4eca.png)  

Kita coba jalankan aplikasi yang kita buat dengan perintah `python3 index.py`  
![Screenshot from 2022-08-25 22-04-18](https://user-images.githubusercontent.com/110447286/186715210-dfad1c35-c72d-4206-bb07-e60780e006ca.png)  

Pada browser kita akses ip address server di port 8000 (sesuai konfigurasi pada script index.py)  
![Screenshot from 2022-08-25 22-04-21](https://user-images.githubusercontent.com/110447286/186715466-e17291c9-119d-4043-872a-c3ae9925c9e7.png)  
Aplikasi berhasil dijalankan

***
## Aplikasi yang sudah berhasil di akses, perlu untuk dikonfigurasi agar dapat berjalan secara daemon menggunakan PM2. Gunakan localtunnel agar aplikasi tersebut dapat di akses secara publik. Aplikasi yang sudah berhasil di konfigurasi dengan PM2 wajib dapat di akses melalui web browser

Pertama kita install localtunnel dan pm2 (Process Manager) terlebih dahulu  
`npm install -g localtunnel`  
![Screenshot from 2022-08-25 21-40-09](https://user-images.githubusercontent.com/110447286/186716693-fbd31e22-bae9-4c7a-b769-244170b59fd4.png)  
`npm install pm2 -g`  
![Screenshot from 2022-08-25 21-41-25](https://user-images.githubusercontent.com/110447286/186717121-d79303b2-aa92-44ef-a597-bb462ae85bf7.png)  

### NodeJS
Kita pindah ke folder nodejs yang telah kita buat  
`cd nodejs/`  
Lalu kita buat bash file bernama lt-nodejs.sh  
`nano lt-nodejs.sh`
![Screenshot from 2022-08-25 21-53-50](https://user-images.githubusercontent.com/110447286/186717599-148a5997-fa38-403f-91e8-6a86b80e7909.png)  

Pada file lt-nodejs.sh kita masukkan script berikut  
`lt -p 3000 > url`  
![Screenshot from 2022-08-25 21-53-55](https://user-images.githubusercontent.com/110447286/186717902-5ccf4863-c2a0-4dfe-a3f4-3c53324ab66b.png)  

Setelah itu pada folder nodejs kita gunakan pm2 untuk menjalankan aplikasi index.js dan lt-nodejs.sh di dalam background  
`pm2 start index.js`  
`pm2 start lt-nodejs.sh`  
Dengan perintah di atas kita menjalankan aplikasi index.js secara background dan aplikasi tersebut dapat diakses secara publik menggunakan localtunnel  
![Screenshot from 2022-08-25 21-54-40](https://user-images.githubusercontent.com/110447286/186718828-f4ef81cc-6eea-4706-862c-f8d14d1615e4.png)  

Output dari localtunnel yang kita jalankan secara background tersimpan pada file url  
Jadi untuk melihat url public kita gunakan perintah cat pada file url  
`cat url`  
![Screenshot from 2022-08-25 21-54-52](https://user-images.githubusercontent.com/110447286/186719430-d4d06a11-c761-4ec0-9a0e-9d4f28e65407.png)  

Kita coba buka url tersebut melalui browser  
![Screenshot from 2022-08-25 21-55-08](https://user-images.githubusercontent.com/110447286/186719547-a93f50ad-353c-4276-8c34-00209946aab3.png)  
![Screenshot from 2022-08-25 21-55-15](https://user-images.githubusercontent.com/110447286/186719582-32db41a5-9bf0-4f04-9e6f-ca0aa61a3de2.png)  

Aplikasi berhasil dijalankan secara background dan dapat diakses secara public  

### Python
Kita pindah ke folder python yang telah kita buat  
`cd python/`  
Lalu kita buat dua bash file bernama python.sh dan lt-python.sh 
`nano python.sh`
![Screenshot from 2022-08-25 22-05-05](https://user-images.githubusercontent.com/110447286/186720750-c194c0d8-5620-4fc0-a536-9ab97bc9b9c4.png)  
`nano lt-python.sh`  
![Screenshot from 2022-08-25 22-05-46](https://user-images.githubusercontent.com/110447286/186720955-7dfdc944-19cc-4a13-89f4-be743d960063.png)  

Setelah itu pada folder python kita gunakan pm2 untuk menjalankan bash file python.sh dan lt-python.sh di dalam background  
`pm2 start python.sh`  
`pm2 start lt-python.sh`  
Dengan perintah di atas kita menjalankan aplikasi index.py secara background dan aplikasi tersebut dapat diakses secara publik menggunakan localtunnel  
 ![Screenshot from 2022-08-25 22-08-07](https://user-images.githubusercontent.com/110447286/186721398-e7a66db5-acc3-419d-b7b3-fbbd49372d1d.png)  

Output dari localtunnel yang kita jalankan secara background tersimpan pada file url  
Jadi untuk melihat url public kita gunakan perintah cat pada file url  
`cat url`  
![Screenshot from 2022-08-25 23-38-32](https://user-images.githubusercontent.com/110447286/186721763-0181bb53-ac29-4334-a048-ccf3630242b8.png)  


Kita coba buka url tersebut melalui browser  
![Screenshot from 2022-08-25 22-08-32](https://user-images.githubusercontent.com/110447286/186721823-1207b3e9-98d4-4a6b-aab6-c42cd6f52606.png)  
![Screenshot from 2022-08-25 22-08-36](https://user-images.githubusercontent.com/110447286/186721855-5cd1de61-af74-4eb3-ac83-87f034019b42.png)  


Aplikasi berhasil dijalankan secara background dan dapat diakses secara public  

***
