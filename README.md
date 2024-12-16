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
