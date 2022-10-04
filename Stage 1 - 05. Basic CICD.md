Melakukan konfigurasi CI/CD menggunakan Cloudflare Pages.

### Definisikan apa itu Cloudflare Pages menurut pemahamanmu
Cloudflare adalah layanan hosting website yang dapat digunakan untuk mendeploy web-app yang source codenya tersimpan di project management service seperti github dan gitlab.

### Fork repository berikut ke akun GitHub Anda https://github.com/dumbwaysdev/wayshub-frontend
Pertama kita buka https://github.com/dumbwaysdev/wayshub-frontend lalu klik **fork**  
![Screen Shot 2022-08-30 at 15 06 51](https://user-images.githubusercontent.com/110447286/187390537-857b6a3c-1648-452a-be53-89eb2455c2a7.png)  
  
Lalu kita akan diredirect ke halaman Create New Fork  
Disini kita akan membuat repository baru di akun kita  
![Screen Shot 2022-08-30 at 15 08 02](https://user-images.githubusercontent.com/110447286/187391212-fca4a277-1c4e-49f7-b3f9-5090bbbce76e.png)  
  
### Deploy aplikasi yang sudah difork menggunakan Cloudflare Pages
Sebelumnya kita perlu regitrasi terlebih dahulu sebelum menggunakan layanan cloudflare  
Kita perlu mengisikan email dan password kemudian verifikasi melalui email yang digunakan untuk mendaftar  
![Screen Shot 2022-08-30 at 14 24 23](https://user-images.githubusercontent.com/110447286/187393029-3a9985a5-01cb-41c9-a2da-db7aa188cd75.png)  
  
Setelah membuat akun kita dapat mulai mencoba untuk mendeploy aplikasi yang ada di github kita  
Klik **Pages** lalu klik **Connect to Git**  
![Screen Shot 2022-08-30 at 14 27 34](https://user-images.githubusercontent.com/110447286/187393787-54c9eeef-84d5-4a79-86ea-f52fd75e034e.png)
  
Selanjutnya kita klik **Connect GitHub**  
![Screen Shot 2022-08-30 at 14 27 52](https://user-images.githubusercontent.com/110447286/187394310-92380521-eb46-41de-9c5e-2c4e45cdfd8e.png)  
  
Kita akan diminta untuk login ke akun GitHub kita  
Kita masukkan username dan password akun GitHub  
![Screen Shot 2022-08-30 at 14 28 18](https://user-images.githubusercontent.com/110447286/187394538-0421075b-0509-45b4-a42a-7a3e93e0feb0.png)
  
Selanjutnya kita dapat memilih untuk menambahkan semua repository kita atau salah satu repository kita.  
Kali ini kita pilih untuk menambahkan repository aplikasi kita saja.  
![Screen Shot 2022-08-30 at 15 08 41](https://user-images.githubusercontent.com/110447286/187397843-8a598dd5-8d6b-438c-884f-42af4ff15929.png)  
  
Kita pilih repository yang akan kita deploy, Kemudian klik **Begin Setup**  
![Screen Shot 2022-08-30 at 15 10 03](https://user-images.githubusercontent.com/110447286/187398184-ce0028e8-2aaf-417b-9188-e138f8a5e41d.png)  

Setelah itu kita dapat meng-edit nama project kita dan memilih branch mana yang akan kita deploy.  
![Screen Shot 2022-08-30 at 15 10 29](https://user-images.githubusercontent.com/110447286/187398587-806ec560-583e-4ef4-ad4a-99ef8236be3b.png)  
  
Pada bagian Build Settings kita diminta untuk memilih framework yang digunakan pada aplikasi kita.  
Karena aplikasi kita menggunakan framework React, maka kita pilih **Create React App**  
Pada build command kita isikan `npm run build` dan build foldernya kita set ke /build  
Jika selesai maka klik **Save and Deploy**
![Screen Shot 2022-08-30 at 15 12 17](https://user-images.githubusercontent.com/110447286/187398848-70d9d465-9750-45b0-8081-1fb9c4ce3c8e.png)  
  
Selanjutnya cloudflare akan memulai proses **Building and Deploying**. Kita tunggu hingga proses selesai.  
![Screen Shot 2022-08-30 at 15 12 39](https://user-images.githubusercontent.com/110447286/187400641-461641f2-45fe-4cbc-acba-5cf4f6daa053.png)  
  
Jika proses build berhasil maka akan muncul pemberitahuan Success beserta nama domain dari aplikasi kita.  
![Screen Shot 2022-08-30 at 15 15 25](https://user-images.githubusercontent.com/110447286/187401132-df43fba4-f58d-4f4b-a1c7-da9fa0562938.png)  
  
Kita buka domain tersebut maka akan muncul aplikasi yang berhasil kita deploy.  
![Screen Shot 2022-08-30 at 15 16 30](https://user-images.githubusercontent.com/110447286/187401346-69b21d77-0bd9-49fd-8d22-1106314db7c2.png)  
  
### Lakukan perubahan pada file `/public/index.html` bagian `<title>WaysHub</title>` menjadi `<title>WaysHub - Nama Anda</title>`. Push perubahan tersebut ke repository aplikasi Anda
Kita buka repository aplikasi kita yang ada di GitHub   
Buka folder /public lalu buka file `index.html`  
Klik edit untuk meng-edit file  
![Screen Shot 2022-08-30 at 15 18 28](https://user-images.githubusercontent.com/110447286/187404709-c08839dc-154a-4afc-aa5f-9c6d80fe5f4d.png)  

Pada bagian `<title>WaysHub</title>` kita ubah menjadi `<title>WaysHub - Indra AY</title>`  
![Screen Shot 2022-08-30 at 16 20 19](https://user-images.githubusercontent.com/110447286/187405568-a4ebcce6-54ba-452f-8620-44ee1e92144d.png)  
  
Setelah itu kita klik **Commit Changes** untuk menyimpan perubahan file tersebut  
![Screen Shot 2022-08-30 at 15 19 56](https://user-images.githubusercontent.com/110447286/187405952-e3fbb815-0182-43b9-9c56-0b6f95590088.png)  
  
### Pasikan CI/CD berjalan dengan baik hingga perubahan pada aplikasi terjadi secara otomatis
Setelah kita melakukan commit maka pada layanan cloudflare akan mendeteksi perubahan yang terjadi pada repository kita dan memulai untuk re-build aplikasi kita.
Kita tunggu proses selesai untuk melihat perubahan yang terjadi di aplikasi.  
![Screen Shot 2022-08-30 at 15 20 34](https://user-images.githubusercontent.com/110447286/187406863-7c533da4-da13-49a2-9931-53fe33dcdf4e.png)  
  
Setelah proses selesai, kita dapat membuka domain name untuk melihat perubahan yang terjadi.  
![Screen Shot 2022-08-30 at 16 53 54](https://user-images.githubusercontent.com/110447286/187407448-4e06d517-2cf1-4cde-bc5b-21fa5eff416f.png)

