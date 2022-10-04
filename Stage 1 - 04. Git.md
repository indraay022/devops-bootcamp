## Definisikan apa itu Git menurut pemahamanmu
Git adalah tool VCS (Version Control System) yang berfungsi untuk memantau dan mencatat perubahan yang terjadi pada file project.

## Konfigurasi koneksi GIT lokal dengan GitHub
Secara default tool git sudah terinstall di ubuntu server.  
Jadi, kita tidak perlu menginstall terlebih dahulu.  
  
Pertama kita konfigurasikan pengguna tool git lokal dengan akun Github yang akan dihubungkan dengan cara memasukkan data username dan email yang terdaftar  
`git config --global user.name <username github>`  
`git config --global user.email <email yang terdaftar>`  
  
Untuk mengecek daftar konfigurasi dapat menggunakan `git config --list`  
![Screenshot from 2022-08-26 01-54-56](https://user-images.githubusercontent.com/110447286/186764942-0a51697e-284f-4946-966f-0f742c5bddb9.png)
  
Selanjutnya kita generate kunci ssh dengan perintah `ssh-keygen`  
![Screenshot from 2022-08-26 01-56-18](https://user-images.githubusercontent.com/110447286/186753199-fd3d6499-da72-4650-8924-5271078d3784.png)  
  
Kunci yang digenerate tersimpan di direktori .ssh/ dengan nama file id_rsa.pub  
Jadi kita gunakan perintah `cat .ssh/id_rsa.pub` untuk melihat kunci yang digenerate  
![Screenshot from 2022-08-26 01-56-43](https://user-images.githubusercontent.com/110447286/186753765-f71ee1c5-ad9d-47f9-b9f1-48ca3462101c.png)  
  
Selanjutnya kita buka https://github.com/settings/keys lalu pilih tombol **New SSH key** untuk menambahkan ssh key pada akun github kita  
![Screenshot from 2022-08-26 01-57-32](https://user-images.githubusercontent.com/110447286/186754099-0477c92f-3a34-4bdd-9549-7ede302e2edb.png)  
  
Isi judul kunci sesuai informasi kunci  
Kita copy ssh key yang ada di terminal lalu kita paste pada field **Key**  
Setelah itu submit **Add SSH key**  
![Screenshot from 2022-08-26 01-58-55](https://user-images.githubusercontent.com/110447286/186754445-3e33c352-5afe-479c-beed-403f71c25f3a.png)  
  
SSH keys sudah berhasil ditambahkan  
![Screenshot from 2022-08-26 01-59-47](https://user-images.githubusercontent.com/110447286/186754589-cfe4cde9-8864-4f73-bf48-746929b6d278.png)  
  
Gunakan perintah `ssh -T git@github.com` untuk mengecek status koneksi antara git local dengan GitHub  
<img width="682" alt="git8" src="https://user-images.githubusercontent.com/110447286/186755072-45d5ca6e-93e4-4d47-bbaa-83ad14e0d068.png">  
  
Kali ini kita akan mencoba untuk menambahkan folder nodejs/ ke dalam git repository  
Kita mulai dengan masuk ke dalam folder nodejs/ dengan perintah `cd nodejs`  
Lalu masukkan perintah `git init` untuk menginisialisasikan folder nodejs/ sebagai git repository lokal  
![Screenshot from 2022-08-26 02-01-46](https://user-images.githubusercontent.com/110447286/186756213-264e05af-6638-4940-a7d2-2854191cd953.png)  
  
Gunakan `ls` untuk mengecek isi folder  
Lalu `git status` untuk melihat status dari file/folder yang ada dalam folder  
![Screenshot from 2022-08-26 02-03-09](https://user-images.githubusercontent.com/110447286/186757016-36cf7c53-4065-47d3-bed8-6d330bcab16e.png)  
  
Kita buat file .gitignore dimana didalamnya kita nanti dapat menambahkan list file/folder yang dikecualikan dalam penggunaan git  
`touch .gitignore`  
Dalam kasus ini kita atur agar folder node_modules/ masuk dalam pengecualian git  
`echo "node_modules/" > .gitignore`  
Setelah itu kita gunakan `git status` untuk melihat status terbaru git dimana folder node_modules/ sudah dikecualikan  
![Screenshot from 2022-08-26 02-04-55](https://user-images.githubusercontent.com/110447286/186758169-8f46ef71-d226-487d-a5f0-5cfea448f903.png)  
  
Kita coba tambahkan file index.js ke dalam fase staging dimana dalam fase ini setiap perubahan dalam file akan dipantau oleh git  
`git add index.js`  
Kita lihat dengan `git status` nampak file index.js sudah masuk ke fase staging dan siap untuk di commit
![Screenshot from 2022-08-26 02-06-28](https://user-images.githubusercontent.com/110447286/186758753-f0995df7-24bf-48e7-b076-09748f8f693d.png)  
  
Untuk menambahkan semua file yang ada di dalam folder kedalam fase staging kita dapat menggunakan perintah `git add .`  
Kita lihat dengan `git status` nampak semua file sudah masuk ke fase staging  
![Screenshot from 2022-08-26 02-07-50](https://user-images.githubusercontent.com/110447286/186759307-7d168884-fe3e-403b-b4a2-81b1e5087217.png)  
  
Selanjutnya kita akan melakukan commit pada semua file di fase staging  
`git commit -m "first commit"`  
Lalu ita lihat dengan `git status` nampak sudah tidak ada lagi file yang dapat di commit  

Setelah selesai dengan git local kita akan mengupload file yang sudah di commit ke dalam repository github  
Buka https://github.com lalu klik tombol **+** lalu pilih **New repository**  
![Screenshot from 2022-08-26 02-09-54](https://user-images.githubusercontent.com/110447286/186760331-a712f739-6664-46bc-a0e9-2306927eb21c.png)  
  
Pada **Repository name** kita isikan nama repository  
Lalu **Create repository**  
![Screenshot from 2022-08-26 02-10-36](https://user-images.githubusercontent.com/110447286/186760643-26b1ce54-eb53-4075-9b91-a4c64af446b0.png)  
  
Pada tampilan awal repository klik tombol SSH lalu copy alamat yang muncul disebelahnya  
![Screenshot from 2022-08-26 02-11-22](https://user-images.githubusercontent.com/110447286/186760953-32f1533d-2afe-4601-85ba-a1d7dcece8e5.png)  
  
Kita remote repository kita dengan perintah `git remote add <nama remote> <alamat>`  
Gunakan `git remote -v` untuk melihat remote yang digunakan  
![Screenshot from 2022-08-26 02-12-42](https://user-images.githubusercontent.com/110447286/186761252-54d32469-3c60-4c59-861a-56584c13e8f5.png)  
  
Setelah terhubung dengan repository github, kita akan mengupload file yang sudah dicommit ke repository GitHub  
`git push origin master`  
![Screenshot from 2022-08-26 02-13-49](https://user-images.githubusercontent.com/110447286/186762311-df43ac7b-a7e2-4803-9e00-3c01c9b0e57a.png)  

Kita lihat pada repository github, file git lokal yang sudah tercommit akan masuk ke dalam repository GitHub  
![Screenshot from 2022-08-26 02-14-08](https://user-images.githubusercontent.com/110447286/186762536-90ddb173-d345-4e68-9b2f-923d7ab0c220.png)  
  
Kita akan membuat branch baru bernama development  
`git branch development`
Kita dapat berpindah branch dengan perintah  
`git checkout <nama branch>`  
Untuk melihat semua branch kita dapat menggunakan perintah  
`git branch -a`  
![Screenshot from 2022-08-26 02-18-27](https://user-images.githubusercontent.com/110447286/186763009-2826a4d7-5966-4538-b3a6-2607f6a33ed5.png)  
  
Kali ini kita upload branch development menuju repository github  
`git push <nama remote> development`  
![Screenshot from 2022-08-26 02-19-36](https://user-images.githubusercontent.com/110447286/186763245-92201ec8-ec64-47a4-81a6-86203f4c096e.png)  
  
Kita buat lagi branch dengan nama staging dan production  
`git branch staging`  
`git branch production`  
lalu kita upload kedua branch tersebut  
`git push <nama remote> staging`  
`git push <nama remote> production`  
![Screenshot from 2022-08-26 02-21-33](https://user-images.githubusercontent.com/110447286/186763692-18945d8f-b091-443d-97e5-d5c74bc068e6.png)  
  
Kita lihat pada repository github terdapat 3 branch baru yaitu developmrnt, staging, dan production  
![Screenshot from 2022-08-26 02-22-56](https://user-images.githubusercontent.com/110447286/186763891-6c3436dc-3a6e-4c39-9462-14cad1ed2493.png)

