## Install Ansible
Install HomeBrew  
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```  
![Screen Shot 2022-09-20 at 17 43 27](https://user-images.githubusercontent.com/110447286/191598780-afa198a0-b862-4aae-82e8-31932c64999b.png)  

Install Ansible  
```brew install ansible```  
![Screen Shot 2022-09-20 at 17 45 48](https://user-images.githubusercontent.com/110447286/191598873-beed3f75-0cec-49cb-9340-de4b8584d1bc.png)  

Lihat versi Ansible  
```ansible --version```  
![Screen Shot 2022-09-20 at 18 02 57](https://user-images.githubusercontent.com/110447286/191599093-8e82de8c-d38f-441c-a8ef-2f2fc209333e.png)  

## Konfigurasi SSH Local dengan Server
Generate public key `id_rsa.pub`  
Copy `id_rsa.pub` ke server  
![Screen Shot 2022-09-22 at 03 08 11](https://user-images.githubusercontent.com/110447286/191600782-8887f5d1-88be-4e38-a6b9-75f43dc36a39.png)

Coba login  
![Screen Shot 2022-09-20 at 18 14 34](https://user-images.githubusercontent.com/110447286/191600914-d3e2b7d8-1fd1-4afd-aa4d-ba5dcb43cbed.png)

## Menambahkan server ke dalam hosts
Buat direktori ansible  
![Screen Shot 2022-09-20 at 18 17 19](https://user-images.githubusercontent.com/110447286/191601198-f50aa007-51f7-4d7e-a08c-73d45f146116.png)  

Buat file `/etc/ansible/hosts`  
![Screen Shot 2022-09-20 at 18 27 32](https://user-images.githubusercontent.com/110447286/191601248-89121570-5759-4049-a1bd-f8777610e3f7.png)  
![Screen Shot 2022-09-20 at 18 33 56](https://user-images.githubusercontent.com/110447286/191601379-cdb61044-1e51-4310-acb9-3903a85a7980.png)  

Coba jalankan ping function  
```
ansible all -m ping
```  
![Screen Shot 2022-09-20 at 18 34 14](https://user-images.githubusercontent.com/110447286/191601550-e04a42de-3b8e-437b-abc6-12762a4fc50b.png)

## Menambahkan user melalui ansible
Buat file `create_user.yml`  
```
- hosts: indra_app
  become: true
  vars:
    username: indraay
  
  tasks:
        - name : creating new user indraay
          ansible.builtin.user:
            name: '{{username}}'
            password: $6$ZCEKoHm9Nds.u9ey$GEUtLaW33nhmIRsrRlhG.PRMCw7uq7cNKU9XcT7dMZOq8dvldNNySBssWQMb.tL2MJLm6oIRco12ZoP9uTSO/1
            home: '/home/{{username}}'

```  

Jalankan dengan ansible-playbook  
![Screen Shot 2022-09-20 at 20 57 49](https://user-images.githubusercontent.com/110447286/191602188-94a4a765-d63c-4893-a253-ff4610209fdd.png)  

Cek pada server apakah user baru berhasil ditambakan  
![Screen Shot 2022-09-20 at 21 01 35](https://user-images.githubusercontent.com/110447286/191602590-c23ce329-f7cd-436d-9c4e-f3b17a652e99.png)  

