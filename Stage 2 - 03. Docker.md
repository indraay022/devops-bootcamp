## Skrip instalasi docker 
```
#!/bin/bash
sudo apt-get update
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

## Login Docker
```
docker login
```

## Instalasi docker image MySQL dan setup docker compose MySQL

```
docker pull mysql:8
```

Kita buat folder baru `mysql` dan file baru bernama `docker-compose.yml`  
Isi dari file `docker-compose.yml`  
```
version: '3.7'

services:
 db:
   container_name: database
   image: mysql:8
   environment:
     MYSQL_ROOT_PASSWORD: 'kelompok5'
     MYSQL_DATABASE: 'dumbplay'
   volumes:
     - /home/indra/mysql:/var/lib/mysql
   ports:
     - 3306:3306
```

Jalankan docker compose  
```
docker compose up -d
```

Kita lihat proses status docker  
```
docker ps -a
```

## Deploy aplikasi Frontend dan Backend
Clone aplikasi dari github  
```
git clone https://github.com/dumbwaysdev/dumbplay-frontend
```
```
git clone https://github.com/dumbwaysdev/dumbplay-backend
```

Masuk ke direktori aplikasi frontend   
edit file pada `src/config/api.js`  
![image](https://user-images.githubusercontent.com/110447286/190430507-f5d648de-7e14-4a39-8193-67ce18db595b.png)

buat file bernama `Dockerfile`  
```
FROM node:10-alpine
WORKDIR /home/root
COPY . .
RUN npm install
EXPOSE 3000
CMD [ "npm", "start" ]

```
![image](https://user-images.githubusercontent.com/110447286/190430829-50c79a6b-a815-40df-8c28-550ed5fb5198.png)

Build image  
```
docker build -t <namaimage>:<tag> .
```

Buat file `docker-compose.yml`  
```
version: '3.7'
services:
 frontend-dumbplay:
   container_name: frontend-dumbplay2
   image: <namaimage>:<tag>
   stdin_open: true
   ports:
     - 3000:3000
```
Jalankan docker compose secara daemon
```
docker compose up -d
```

Pindah ke direktori Backend
Edit file pada `config/config.js`
![image](https://user-images.githubusercontent.com/110447286/190443328-da3842c5-067b-45bc-8e3e-263241a4c809.png)  

Buat Dockerfile  
```
FROM node:10-alpine
WORKDIR /home/root/
COPY . .
RUN npm install
RUN npm install sequelize-cli -g
RUN npx sequelize db:migrate
EXPOSE 5000
CMD [ "npm", "start" ]
```
