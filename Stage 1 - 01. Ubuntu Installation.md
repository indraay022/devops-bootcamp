## Pengertian DevOps
Devops adalah gabungan dari Development dan Operation yang bertugas menghubungkan antara Development dengan Operation sehingga menjadi lebih efektif dan Efisien.  

## Konfigurasi Virtual Box
Pada tampilan utama VirtualBox pilih New
![Image_23_08_2022 17_30_41](https://user-images.githubusercontent.com/110447286/186136456-2460b6ab-43a4-4fd0-8721-c6930564a223.png)

***
Pada tampilan Name and Operating System isikan sebagai berikut
- **Name** kita isi dengan nama Virtual Machine kita. Kali ini kita isi dengan 'ubuntu server'.
- **Machine Folder** diisi dengan lokasi penyimpanan file Virtual Machine kita.
- **Type** kita pilih platform Linux
- **Version** kita pilih Ubuntu (64bit)

![Screenshot 2022-08-22 184901](https://user-images.githubusercontent.com/110447286/186149831-e5441966-c925-4edc-b272-04e1ada1718d.png)

***
Kita atur memory size yang akan digunakan oleh Virtual Machine
- Kali ini kita gunakan ukuran 2048MB atau 2GB.

![Screenshot 2022-08-22 185016](https://user-images.githubusercontent.com/110447286/186150711-72293888-f54a-4c23-a0dc-9d59486353cd.png)

***
Pada tampilan Hard disk kita dapat menambahkan virtual hard disk untuk virtual machine kita. Yaitu dengan memilih opsi **Create a virtual hard disk now**.
- Opsi **Do not add a virtual hard disk** artinya kita tidak menambahkan hard disk pada virtual machine kita.
- Opsi **Use an existing virtual hard disk** artinya kita menambahkan virtual hard disk yang telah ada.

![Screenshot 2022-08-22 185034](https://user-images.githubusercontent.com/110447286/186151422-ee11ca32-5651-4367-be32-6a035e0e2b26.png)

***
Kita akan menentukan tipe file virtual hard disk yang akan dibuat. 
- VDI (VirtualBox Disk Image) adalah format virtual hard disk yang digunakan dalam Oracle VirtualBox.
- VHD (Virtual Hard Disk) adalah format virtual hard disk yang digunakan dalam Microsoft Virtual PC.
- VMDK (Virtual Machine Disk) adalah format virtual hard disk yang digunakan dalam VMware.  
  
Kali ini kita pilih opsi VDI (VirtualBox Disk Image).

![Screenshot 2022-08-22 185058](https://user-images.githubusercontent.com/110447286/186153004-99d3ab0c-9c6a-4743-a2e3-6a8da7a086b4.png)

***
Kita akan menentukan apakah virtual hard disk yang kita buat akan bersifat Dynamically allocated atau Fixed size (Ukuran tetap). 
- Dynamically allocated hanya akan memakan space sesuai penggunaan virtual machine kita hingga batas maksimum yang ditetapkan.
- Fixed size akan memakan space sesuai dengan ukuran yang ditetapkan di awal.  
  
Kali ini kita pilih Dynamically allocated.

![Screenshot 2022-08-22 185125](https://user-images.githubusercontent.com/110447286/186154060-d29d9af3-b71f-46b4-8f7c-89dd0b35d142.png)

***
Kita akan menentukan letak dan ukuran virtual hard disk yang akan digunakan.
- Lokasi kali ini kita letakkan di dalam folder virtual machine
- Ukurannya kali ini kita gunakan 10GB 

![Screenshot 2022-08-22 185139](https://user-images.githubusercontent.com/110447286/186154627-8abdcafa-171d-4750-9e25-ed037f949d96.png)

***
Pada tampilan berikutnya kita setting lebih lanjut virtual machine kita sebelum kita start.

![Screenshot 2022-08-22 185205](https://user-images.githubusercontent.com/110447286/186160981-1cbbe6b0-37c5-4387-8f10-fcb137a0f4a6.png)

***
Pada menu system kita pilih bilah Processor lalu kita atur agar virtual machine kita menggunakan 2 CPU.

![Screenshot 2022-08-22 185544](https://user-images.githubusercontent.com/110447286/186161348-0c7b16d4-cf14-480e-9257-5e84dae99276.png)

***
Pada menu display kita pilih bilah screen lalu kita atur video memorynya menjadi 64MB

![Screenshot 2022-08-22 185601](https://user-images.githubusercontent.com/110447286/186161603-99206254-9bfe-47e3-af9e-d49b0760b923.png)

***
Pada menu network kita enable adapter 1 lalu kita atur Attached to menjadi Bridged adapter. Setelah itu kita submit dengan klik tombol OK.

![Screenshot 2022-08-22 185620](https://user-images.githubusercontent.com/110447286/186161884-547f86ab-e839-4878-91b1-686a621ede6d.png)

***
Setelah selesai konfigurasi virtual machine, kita klik tombol start untuk memulai virtual machine kita.

![Screenshot 2022-08-22 185815](https://user-images.githubusercontent.com/110447286/186162228-c1209aa8-f9f2-4ac1-9d84-cac058881ca7.png)

***
Akan muncul pop up Select start-up disk, lalu kita klik ikon folder^.  

![Screenshot 2022-08-22 185902](https://user-images.githubusercontent.com/110447286/186162654-1676d342-7bc4-4204-bf2d-4f08dd60c2bb.png)

Pada jendela Optical disk selector kita klik tombol Add.

![Screenshot 2022-08-22 185950](https://user-images.githubusercontent.com/110447286/186162802-55185ea6-2ed3-4c78-b3b3-4dd70c141841.png)

Pilih file disc image (ISO) yang akan kita gunakan untuk booting, lalu klik open.

![Screenshot 2022-08-22 190020](https://user-images.githubusercontent.com/110447286/186162972-b4a2bef1-199e-4160-86dd-79421f625538.png)

Selanjutnya kita pilih file disc image (ISO) tadi lalu klik tombol choose untuk lanjut.

![Screenshot 2022-08-22 190044](https://user-images.githubusercontent.com/110447286/186163278-6e80ad80-343a-4a1c-82e4-f509e3f20105.png)

Klik start.

![Screenshot 2022-08-22 190104](https://user-images.githubusercontent.com/110447286/186163620-4dd8b820-569a-4759-bfcf-4268a75dca46.png)

***
## Instalasi Ubuntu Server
Kita sudah masuk ke proses instalasi Ubuntu. Tunggu hingga proses selesai.

![vlcsnap-2022-08-23-20h00m28s707](https://user-images.githubusercontent.com/110447286/186164620-aa88fd1e-94d0-47b2-8528-4c20e99f4061.png)

***
Pilih bahasa yang akan digunakan. Selama proses instalasi gunakan keyboard untuk navigasi.

![vlcsnap-2022-08-22-20h49m42s704](https://user-images.githubusercontent.com/110447286/186166062-aaae5f7c-2ece-4605-a01e-20ad7eaaa218.png)

***
Pilih continue without updating untuk mengabaikan update.

![vlcsnap-2022-08-22-20h50m09s646](https://user-images.githubusercontent.com/110447286/186166306-571197f4-dcc4-4169-b594-7a1b3380fc22.png)

***
Atur layout keyboard yang kita gunakan. Kali ini kita gunakan English (US) layout lalu pilih Done.

![vlcsnap-2022-08-22-20h50m28s775](https://user-images.githubusercontent.com/110447286/186166792-d0d223b5-7baf-4052-8161-ae99b2194aa2.png)

***
Pada sesi Network connections kita atur interface IPv4 dengan memilih Edit IPv4.

![vlcsnap-2022-08-22-20h52m30s270](https://user-images.githubusercontent.com/110447286/186167168-f8e82cad-2986-4d75-a099-96093af3b166.png)

IPv4 method kita pilih manual

![vlcsnap-2022-08-22-20h52m41s119](https://user-images.githubusercontent.com/110447286/186167330-98cde397-6d8a-46b0-88ce-81f72238051d.png)

Kita atur IPv4 Ubuntu Server menjadi satu jaringan dengan Akses Poin (Router/Modem) agar Ubuntu Server kita dapat terkoneksi dengan Internet  
  
Berikut adalah konfigurasi IPv4 perangkat Akses Poin  
![Screenshot 2022-08-22 210126](https://user-images.githubusercontent.com/110447286/186168627-730169b1-0072-4bf9-b32f-6c9ad1f8e53a.png)  

Maka kita konfigurasi IPv4 Ubuntu Server kita menjadi seperti berikut  
![vlcsnap-2022-08-22-20h53m31s777](https://user-images.githubusercontent.com/110447286/186168258-5196d777-9989-4fb3-b725-3fc13e11fa28.png)  
  
Setelah itu kita pilih Done  
![vlcsnap-2022-08-22-21h30m10s757](https://user-images.githubusercontent.com/110447286/186169411-eae1ad51-3efe-4df0-983d-ab91aa8513bf.png)
***
Pada sesi configure proxy kita skip dengan langsung memilih Done  
![vlcsnap-2022-08-22-21h30m19s997](https://user-images.githubusercontent.com/110447286/186169602-2ede82fb-c3ad-4514-a5ca-257cb8873d4c.png)
***
Pada sesi configure Ubuntu Archive mirror kita biarkan mirror addressnya default. Setelah itu kita pilih Done.  
![vlcsnap-2022-08-22-21h30m31s502](https://user-images.githubusercontent.com/110447286/186169839-b645eb57-e672-4c26-80e5-e480838df813.png)
***
Kita masuk sesi Partisi  
Pilih custom storage layout untuk mengkustomisasi partisi. Lalu pilih Done  
![vlcsnap-2022-08-22-21h31m00s947](https://user-images.githubusercontent.com/110447286/186170162-7c96839f-7b9b-49b4-bf94-162f1c621dd7.png)   
  
Pada baris free space kita Add GPT Partition untuk membuat partisi root.  
![vlcsnap-2022-08-22-21h31m20s548](https://user-images.githubusercontent.com/110447286/186170369-631580ee-0d13-4736-9938-a6ca4a5b02c6.png)  
  
Size : 8G  
Format : ext4  
Mount : /  
- Artinya kita atur partisi yang kita buat sebagai root dengan format ext4 dan ukuran partisi 8GB  
Jika selesai kita pilih create  
![vlcsnap-2022-08-22-21h31m51s061](https://user-images.githubusercontent.com/110447286/186171109-fb7194c1-685e-45c8-b5c2-9a8dad88a089.png)  

Untuk kedua kalinya pada baris free space kita Add GPT Partition untuk membuat partisi swap.  
![vlcsnap-2022-08-23-20h34m11s697](https://user-images.githubusercontent.com/110447286/186172255-2de38a7f-1000-47d0-93bf-cca60698e9c1.png)  

Size : 1.997G (sisa free space)
Format : swap
- Artinya kita atur partisi yang kedua sebagai swap dengan ukuran 1.997GB 
- swap adalah partisi yang difungsikan sebagai memori tambahan disaat memori utama sedang penuh  
![vlcsnap-2022-08-22-21h33m36s055](https://user-images.githubusercontent.com/110447286/186173219-54303aa8-979f-42c4-b021-b7b09c4c84e6.png)  
  
Kita sudah membuat partisi root dan swap lalu pilih Done  
![vlcsnap-2022-08-22-21h33m51s964](https://user-images.githubusercontent.com/110447286/186173300-1575cffe-b9dc-4b5e-b66e-957c0c5cd073.png)  
  
Setelah itu kita diminta untuk konfirmasi dengan memilih Continue  
![vlcsnap-2022-08-22-21h34m19s081](https://user-images.githubusercontent.com/110447286/186173817-a7af2518-9803-417a-adce-f012f5b39268.png)  
***
Pada sesi Profile Setup kita diminta untuk mengatur username, server name, dan password.
- Name adalah nama user kita
- Server name adalah nama host server kita
- username adalah nama user yang kita gunakan untuk login
- password adalah kata sandi user yang kita gunakan untuk login  
Jika selesai, maka pilih Done.
![vlcsnap-2022-08-22-21h35m35s413](https://user-images.githubusercontent.com/110447286/186174188-62950f6a-2bc5-41f5-85ba-6553a7c73ae4.png)  
***
Pada sesi Enable Ubuntu Advantage kita skip dengan langsung memilh Done.  
![vlcsnap-2022-08-22-21h35m55s351](https://user-images.githubusercontent.com/110447286/186175045-53ff2b26-299b-475e-860a-100dd71f1fa0.png)
***
Pada sesi SSH setup kita enable opsi Install OpenSSH server agar kita dapat meremote server kita dengan SSH.  
Untuk opsi Import SSH identity kita pilih NO terlebih dahulu. Lalu pilih  Done.  

![vlcsnap-2022-08-22-21h36m09s679](https://user-images.githubusercontent.com/110447286/186175595-e08a4d64-e428-4ee0-995d-08ffe6bc2123.png)
***
Pada sesi Featured Server Snaps kita dapat memilih aplikasi apa saja yang kita perlukan untuk server.  
Kali ini kita skip dengan langsung memilih Done.  

![vlcsnap-2022-08-22-21h37m08s266](https://user-images.githubusercontent.com/110447286/186176004-a330060c-766d-4e91-81ea-02b1c9fb538d.png)
***
Setup sedang dalam proses instalasi system, kita tunggu hingga selesai.  

![vlcsnap-2022-08-22-21h37m25s231](https://user-images.githubusercontent.com/110447286/186176182-2135d998-1ad3-4911-be33-da848111111a.png)  

Pada sesi ini Instalasi sudah selesai dan system sedang melakukan update.  
Kita dapat melewati update dengan memilih Cancel update and reboot.  
Namun kali ini kita tunggu hingga update selesai saja.  
![vlcsnap-2022-08-22-21h45m15s963](https://user-images.githubusercontent.com/110447286/186176926-6a8b1973-1844-41da-bca8-370a5987d30c.png)  
Setelah update selesai kita pilih Reboot Now  
![vlcsnap-2022-08-22-21h57m06s983](https://user-images.githubusercontent.com/110447286/186177059-4ea5a224-9dbb-4291-b9a0-691e8f09fdac.png)  
***
## Login ke Ubuntu Server  
Setelah proses booting selesai kita akan masuk ke halaman login  
- Pada baris ubuntuvm login kita isikan username kita  
- Pada baris Password kita isikan password yang telah kita atur untuk username tersebut  
Jika login berhasil maka akan muncul baris username@hostname:~$  
![vlcsnap-2022-08-22-21h58m07s491](https://user-images.githubusercontent.com/110447286/186177971-12e620ee-6c2a-4bb8-81c3-0fc2874ce21b.png)  
***
Kita coba ping google dengan perintah berikut  
> ping 8.8.8.8  
Jika muncul 64 bytes from 8.8.8.8 .... artinya kita berhasil terkoneksi dengan google

![vlcsnap-2022-08-22-21h58m19s797](https://user-images.githubusercontent.com/110447286/186178850-7ddb978b-f181-43a1-90fa-a53d1c354d4e.png)  

Sekian, terima kasih.
