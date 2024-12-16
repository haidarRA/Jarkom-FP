# Jarkom-FP

## ***KELOMPOK 3B***
| Nama      | NRP         |
|-----------|-------------|
| Muhammad Faqih Husain | 5027231023 |  
| Furqon Aryadana | 5027231024 |
| Haidar Rafi Aqyla | 5027231029 |
| Benjamin Khawarizmi Habibi | 5027231078 |

# 1. Topologi Jaringan
![topo cpt fp jarkom](https://github.com/user-attachments/assets/86efd2c0-c450-4341-a9df-1fe193f3eeca)

# 2. Routing dan Subnetting
Untuk subnetting menggunakan VLSM.

[Spreadsheet Routing dan Subnetting](https://docs.google.com/spreadsheets/d/13Pj18YQFvxAKhhVn5XzF5B-OAwWyuGGdb9itGGfaz1o/edit?gid=1522356619#gid=1522356619)

## Routing
![image](https://github.com/user-attachments/assets/d03a916c-3e89-4927-b9ed-ed0da8d6791c)

## Pembagian IP VLSM
![image](https://github.com/user-attachments/assets/3fc1d6c9-4afb-4eb0-85f8-813356d7628c)

## Topologi Jaringan (setelah subnetting)
![topo cpt fp jarkom subnet](https://github.com/user-attachments/assets/36b7d8b9-d49f-46a9-bd78-04d3649f0cde)

# 3. Konfigurasi Static IP

## Konfigurasi Router
Jalankan command berikut pada CLI router untuk konfigurasi static IP pada interface tertentu (untuk contoh pada router Lantai1 interface FastEthernet0/1)
```
en
conf t
int f0/1
ip address 192.168.0.254 255.255.255.128
no shutdown
```
![image](https://github.com/user-attachments/assets/86e6d4ca-1637-4340-a5df-afbb0b605719)

Untuk mengecek apakah konfigurasi static IP berhasil, cek IP address pada interface router dengan command ``sh ip int brief``.
![image](https://github.com/user-attachments/assets/7824009b-b128-4da2-bce5-d4ea542e8251)

Lakukan hal yang sama untuk masing - masing interface pada setiap router yang ada pada topologi jaringan sesuai dengan subnet yang ada.

### Lantai1
![image](https://github.com/user-attachments/assets/2579ef74-e2b0-44d2-a7f0-04c798237ad9)

### Lantai2
![image](https://github.com/user-attachments/assets/a564b864-9ff2-4b94-8653-8ebe453801d2)

### Lantai3
![image](https://github.com/user-attachments/assets/f62b4f8e-6bc4-43e5-9fcb-95d1de6f78f2)

### Lantai4
![image](https://github.com/user-attachments/assets/5c3ac7f8-b4ff-49e5-a427-a8c067b2b542)

### Lantai5
![image](https://github.com/user-attachments/assets/a927e9b2-7664-48c4-be82-ec596e38870e)

### Cabang
![image](https://github.com/user-attachments/assets/b48787e2-c9f1-4aea-95c8-a31eb2ce4464)

### Router0
![image](https://github.com/user-attachments/assets/a2afdc46-670a-4a0e-9d41-75326ff366c1)

## Konfigurasi Client
Klik node client, kemudian klik tab Config dan isi IP dari gateway dan IP dari interface yang ada beserta subnet masknya (biasanya hanya FastEthernet0).
Sebagai contoh, berikut adalah konfigurasi untuk client **Ruang Server dan Data**.
![image](https://github.com/user-attachments/assets/10a6a094-9796-412b-b8a4-4688b5342fd4)

![image](https://github.com/user-attachments/assets/ada524fc-92e5-42be-81c9-343a3c6b7c7a)

Lakukan hal yang sama untuk setiap node client yang ada pada topologi jaringan sesuai dengan subnet yang ada (kecuali pada subnet A3 yang terhubung dengan Lantai2 yang menggunakan IP DHCP).
### Ruang Server dan Data
![image](https://github.com/user-attachments/assets/c3bb03df-043d-4c78-bc88-13cfd5c1e647)

### Dept. HR2
![image](https://github.com/user-attachments/assets/e48b3683-16cd-45c5-b91e-4d352426800c)

### Dept. IT
![image](https://github.com/user-attachments/assets/b8d9ff66-0ec5-4ffc-85b9-a42673a6859d)

### Dept. Legal
![image](https://github.com/user-attachments/assets/e706319f-74ba-4eed-bdea-7d5f75273427)

### Dept. Keuangan
![image](https://github.com/user-attachments/assets/cc387922-09b6-43ba-aeb5-7ce84c1ebe76)

### Dept. Customer Support
![image](https://github.com/user-attachments/assets/68d8524f-e877-4852-811b-7b344f340af9)

### Dept. Manajemen
![image](https://github.com/user-attachments/assets/72a5d9ce-188f-401b-845e-bc46e994075d)

### Ruang Meeting
![image](https://github.com/user-attachments/assets/bf6fa4a4-a3b6-46d5-ad3f-7a72bd5c6caa)

### Dept. HR1
![image](https://github.com/user-attachments/assets/12c8a010-b1f2-424a-bde3-0f10cf6292c9)

### Dept. Cybersecurity
![image](https://github.com/user-attachments/assets/deac44ca-4757-4bff-9d7b-b5cc6290cc7f)

### Subnet Cabang
![image](https://github.com/user-attachments/assets/42899c57-ddc4-4161-a52b-908c62c664a9)

# 4. Konfigurasi DHCP
Untuk konfigurasi DCHP pada router Lantai2, jalankan command berikut.
```
en
conf t
service dhcp
ip dhcp pool Lantai2
network 192.168.0.0 255.255.255.128
default-router 192.168.0.126
dns-server 192.168.0.126
```
![image](https://github.com/user-attachments/assets/65965e7c-7bdc-410c-a92f-1ee6c7007b0e)

Untuk mengecek apakah konfigurasi DHCP berhasil, gunakan IP DHCP pada client yang ada pada subnet A3 dan pastikan apakah client - client tersebut mendapatkan IP DHCP.
### Dept. Penjualan
![image](https://github.com/user-attachments/assets/70a25a95-6f5e-4397-bd90-6fbe28fae045)

### Dept. Pemasaran
![image](https://github.com/user-attachments/assets/fbce927a-61ab-4953-9150-4270eec081f3)

### Dept. R&D
![image](https://github.com/user-attachments/assets/f99bff01-6aa9-4d7c-9b26-e0b2b8c0afc0)
