# Laporan Final Project Komunikasi Data dan Jaringan Komputer 

## ***KELOMPOK 3B***
| Nama      | NRP         |
|-----------|-------------|
| Muhammad Faqih Husain | 5027231023 |  
| Furqon Aryadana | 5027231024 |
| Haidar Rafi Aqyla | 5027231029 |
| Benjamin Khawarizmi Habibi | 5027231078 |

# Daftar Isi
- [Kelompok 3B](#kelompok-3b)
- [Topologi Jaringan](#1-topologi-jaringan)
- [Routing dan Subnetting](#2-routing-dan-subnetting)
- [Konfigurasi Static IP](#3-konfigurasi-static-ip)
- [Konfigurasi DHCP](#4-konfigurasi-dhcp)
- [Konfigurasi Static Routing](#5-konfigurasi-static-routing)
- [Konfigurasi NAT](#6-konfigurasi-nat)
- [Konfigurasi GRE Tunnel](#7-konfigurasi-gre-tunnel)

# 1. Topologi Jaringan
![topo cpt fp jarkom](https://github.com/user-attachments/assets/c2e361e6-f63f-4519-8e0c-acf92f9b568e)

# 2. Routing dan Subnetting
Untuk subnetting menggunakan VLSM.

[Spreadsheet Routing dan Subnetting](https://docs.google.com/spreadsheets/d/13Pj18YQFvxAKhhVn5XzF5B-OAwWyuGGdb9itGGfaz1o/edit?gid=1522356619#gid=1522356619)

## Routing
![image](https://github.com/user-attachments/assets/1fb9ae55-bd2f-456a-8d1a-9ae188f6c868)

## Pembagian IP VLSM
![image](https://github.com/user-attachments/assets/d59ede5a-6e4a-433f-aa2f-673a4cd5af37)

## VLSM Tree
![VLSM TREE FP Jarkom](https://github.com/user-attachments/assets/8c68beca-a3d7-40d2-b924-d2b45aa85e7c)

## Topologi Jaringan (setelah subnetting)
![topo cpt fp jarkom subnet](https://github.com/user-attachments/assets/15a5b9ed-82fa-4533-b2d3-bcd4409bfe64)

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

Untuk mengecek apakah konfigurasi static IP berhasil, cek IP address pada interface router dengan command ``sh ip int brief``. <br/>
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
![image](https://github.com/user-attachments/assets/55a1966f-e2c0-4963-8a83-56c8c907fc52)

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
Untuk konfigurasi DCHP pada router Lantai2, jalankan command berikut pada CLI router Lantai2.
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

# 5. Konfigurasi Static Routing
Jalankan command berikut pada masing - masing CLI router.

### Lantai1
```
en
conf t
#A3
ip route 192.168.0.0 255.255.255.128 192.168.1.130

#A4
ip route 192.168.1.132 255.255.255.252 192.168.1.130

#A5
ip route 192.168.1.64 255.255.255.192 192.168.1.130

#A6
ip route 192.168.1.136 255.255.255.252 192.168.1.130

#A7
ip route 192.168.1.192 255.255.255.192 192.168.1.130

#A8
ip route 192.168.1.140 255.255.255.252 192.168.1.130

#A9
ip route 192.168.1.0 255.255.255.192 192.168.1.130

#A10
ip route 192.168.1.144 255.255.255.252 192.168.1.130

#A11
ip route 192.168.1.148 255.255.255.252 192.168.1.130

#A12
ip route 192.168.1.152 255.255.255.252 192.168.1.130

#A13
ip route 192.168.1.156 255.255.255.252 192.168.1.130

do write
```

### Lantai2
```
en
conf t
#A1
ip route 192.168.0.128 255.255.255.128 192.168.1.129

#A5
ip route 192.168.1.64 255.255.255.192 192.168.1.134

#A6
ip route 192.168.1.136 255.255.255.252 192.168.1.134

#A7
ip route 192.168.1.192 255.255.255.192 192.168.1.134

#A8
ip route 192.168.1.140 255.255.255.252 192.168.1.134

#A9
ip route 192.168.1.0 255.255.255.192 192.168.1.134

#A10
ip route 192.168.1.144 255.255.255.252 192.168.1.134

#A11
ip route 192.168.1.148 255.255.255.252 192.168.1.134

#A12
ip route 192.168.1.152 255.255.255.252 192.168.1.134

#A13
ip route 192.168.1.156 255.255.255.252 192.168.1.134

do write
```

### Lantai3
```
en
conf t
#A1
ip route 192.168.0.128 255.255.255.128 192.168.1.133

#A2
ip route 192.168.1.128 255.255.255.252 192.168.1.133

#A3
ip route 192.168.0.0 255.255.255.128 192.168.1.133

#A7
ip route 192.168.1.192 255.255.255.192 192.168.1.138

#A8
ip route 192.168.1.140 255.255.255.252 192.168.1.138

#A9
ip route 192.168.1.0 255.255.255.192 192.168.1.138

#A10
ip route 192.168.1.144 255.255.255.252 192.168.1.138

#A11
ip route 192.168.1.148 255.255.255.252 192.168.1.138

#A12
ip route 192.168.1.152 255.255.255.252 192.168.1.138

#A13
ip route 192.168.1.156 255.255.255.252 192.168.1.138

do write
```

### Lantai4
```
en
conf t
#A1
ip route 192.168.0.128 255.255.255.128 192.168.1.137

#A2
ip route 192.168.1.128 255.255.255.252 192.168.1.137

#A3
ip route 192.168.0.0 255.255.255.128 192.168.1.137

#A4
ip route 192.168.1.132 255.255.255.252 192.168.1.137

#A5
ip route 192.168.1.64 255.255.255.192 192.168.1.137

#A9
ip route 192.168.1.0 255.255.255.192 192.168.1.142

#A10
ip route 192.168.1.144 255.255.255.252 192.168.1.142

#A11
ip route 192.168.1.148 255.255.255.252 192.168.1.142

#A12
ip route 192.168.1.152 255.255.255.252 192.168.1.142

#A13
ip route 192.168.1.156 255.255.255.252 192.168.1.142

do write
```

### Lantai5
```
en
conf t
#A1
ip route 192.168.0.128 255.255.255.128 192.168.1.141

#A2
ip route 192.168.1.128 255.255.255.252 192.168.1.141

#A3
ip route 192.168.0.0 255.255.255.128 192.168.1.141

#A4
ip route 192.168.1.132 255.255.255.252 192.168.1.141

#A5
ip route 192.168.1.64 255.255.255.192 192.168.1.141

#A6
ip route 192.168.1.136 255.255.255.252 192.168.1.141

#A7
ip route 192.168.1.192 255.255.255.192 192.168.1.141

#A11
ip route 192.168.1.148 255.255.255.252 192.168.1.146
ip route 192.168.1.148 255.255.255.252 192.168.1.158

#A12
ip route 192.168.1.152 255.255.255.252 192.168.1.146

do write
```

### Cabang
```
en
conf t
#A1
ip route 192.168.0.128 255.255.255.128 192.168.1.154
ip route 192.168.0.128 255.255.255.128 192.168.1.157

#A2
ip route 192.168.0.128 255.255.255.128 192.168.1.154
ip route 192.168.0.128 255.255.255.128 192.168.1.157

#A3
ip route 192.168.0.0 255.255.255.128 192.168.1.154
ip route 192.168.0.0 255.255.255.128 192.168.1.157

#A4
ip route 192.168.1.132 255.255.255.252 192.168.1.154
ip route 192.168.1.132 255.255.255.252 192.168.1.157

#A5
ip route 192.168.1.64 255.255.255.192 192.168.1.154
ip route 192.168.1.64 255.255.255.192 192.168.1.157

#A6
ip route 192.168.1.136 255.255.255.252 192.168.1.154
ip route 192.168.1.136 255.255.255.252 192.168.1.157

#A7
ip route 192.168.1.192 255.255.255.192 192.168.1.154
ip route 192.168.1.192 255.255.255.192 192.168.1.157

#A8
ip route 192.168.1.140 255.255.255.252 192.168.1.154
ip route 192.168.1.140 255.255.255.252 192.168.1.157

#A9
ip route 192.168.1.0 255.255.255.192 192.168.1.154
ip route 192.168.1.0 255.255.255.192 192.168.1.157

#A10
ip route 192.168.1.144 255.255.255.252 192.168.1.154
ip route 192.168.1.144 255.255.255.252 192.168.1.157

do write
```

### Router0
```
en
conf t
#A1
ip route 192.168.0.128 255.255.255.128 192.168.1.145

#A2
ip route 192.168.1.128 255.255.255.252 192.168.1.145

#A3
ip route 192.168.0.0 255.255.255.128 192.168.1.145

#A4
ip route 192.168.1.132 255.255.255.252 192.168.1.145

#A5
ip route 192.168.1.64 255.255.255.192 192.168.1.145

#A6
ip route 192.168.1.136 255.255.255.252 192.168.1.145

#A7
ip route 192.168.1.192 255.255.255.192 192.168.1.145

#A8
ip route 192.168.1.140 255.255.255.252 192.168.1.145

#A9
ip route 192.168.1.0 255.255.255.192 192.168.1.145

#A11
ip route 192.168.1.148 255.255.255.252 192.168.1.153

#A13
ip route 192.168.1.156 255.255.255.252 192.168.1.145
ip route 192.168.1.156 255.255.255.252 192.168.1.153

do write
```

Untuk melihat routing yang ada pada router, dapat menggunakan command ```sh ip route```.
### Lantai1
![image](https://github.com/user-attachments/assets/75acac61-e381-4b44-b12a-8e78ad438e2f)

### Lantai2
![image](https://github.com/user-attachments/assets/a3992e5e-da29-4921-ae3a-9d2bc899b153)

### Lantai3
![image](https://github.com/user-attachments/assets/6edeab89-3cd9-4466-a0d2-aa096befbd9e)

### Lantai4
![image](https://github.com/user-attachments/assets/6f252225-0c2b-4057-a119-7eb747ad3915)

### Lantai5
![image](https://github.com/user-attachments/assets/88d257e3-b86b-40e9-a675-ff9a921fbe3e)

### Cabang
![image](https://github.com/user-attachments/assets/b43e860e-c8b0-468f-8c63-1a1b36effe9f)

### Router0
![image](https://github.com/user-attachments/assets/b0014d7e-92df-404f-9cd4-1628d92d3ec9)

# 6. Konfigurasi NAT
Konfigurasi interface inside dan outside serta NAT dari tiap router dengan command berikut pada CLI router.
### Lantai1
```
en
conf t
int f0/0
ip nat outside
exit
int f0/1
ip nat inside
exit
ip nat inside source list 1 interface f0/0 overload
```

### Lantai2
```
en
conf t
int f0/0
ip nat outside
exit
int f0/1
ip nat inside
exit
int f1/0
ip nat inside
exit
ip nat inside source list 1 interface f0/0 overload
```

### Lantai3
```
en
conf t
int f0/0
ip nat outside
exit
int f0/1
ip nat inside
exit
int f1/0
ip nat inside
exit
ip nat inside source list 1 interface f0/0 overload
```

### Lantai4
```
en
conf t
int f0/0
ip nat outside
exit
int f0/1
ip nat inside
exit
int f1/0
ip nat inside
exit
ip nat inside source list 1 interface f0/0 overload
```

### Lantai5
```
en
conf t
int f0/0
ip nat outside
exit
int f0/1
ip nat inside
exit
int f1/0
ip nat inside
exit
ip nat inside source list 1 interface f0/0 overload
```

### Cabang
```
en
conf t
int f0/0
ip nat outside
exit
int f0/1
ip nat inside
exit
ip nat inside source list 1 interface f0/0 overload
```

### Router0
```
en
conf t
int f0/0
ip nat outside
exit
int f0/1
ip nat inside
exit
int f1/0
ip nat inside
exit
access-list 1 permit any
ip nat inside source list 1 interface f0/0 overload
```

Atur DNS server pada tiap client menjadi 8.8.8.8.
![image](https://github.com/user-attachments/assets/04049dd1-4e77-4dd3-b624-ecc00ab9dda5)

Konfigurasikan server internet yang terhubung dengan Router0 dengan konfigurasi berikut.
![image](https://github.com/user-attachments/assets/9f5ee0d1-1d99-4b36-88c7-51c725f2a56e)

Setelah itu, konfigurasikan tiap router agar dapat melakukan ping ke 8.8.8.8 dengan command berikut.
### Lantai5
```
en
conf t
int f0/0
ip route 8.8.8.0 255.255.255.0 192.168.1.146
exit
```

### Lantai4
```
en
conf t
int f0/0
ip route 8.8.8.0 255.255.255.0 192.168.1.142
exit
```

### Lantai3
```
en
conf t
int f0/0
ip route 8.8.8.0 255.255.255.0 192.168.1.138
exit
```

### Lantai2
```
en
conf t
int f0/0
ip route 8.8.8.0 255.255.255.0 192.168.1.134
exit
```

### Lantai1
```
en
conf t
int f0/0
ip route 8.8.8.0 255.255.255.0 192.168.1.130
exit
```

### Cabang
```
en
conf t
int f0/0
ip route 8.8.8.0 255.255.255.0 192.168.1.154
exit
```

## Testing
![image](https://github.com/user-attachments/assets/b8f620dd-5989-4e79-9b4b-f15c3f563d97)
![image](https://github.com/user-attachments/assets/ca243e7d-62b5-4590-a593-108f3fce6421)
![image](https://github.com/user-attachments/assets/fbe5bfad-79e6-4f71-b8a8-b93ca058da96)

# 7. Konfigurasi GRE Tunnel
Jalankan command berikut pada CLI router Lantai5 dan Cabang untuk mengonfigurasi GRE Tunnel yang dapat menghubungkan router Lantai5 dan Cabang.

### Lantai5:
```
en
conf t
int tunnel 0
ip address 192.168.1.157 255.255.255.252
tunnel source f0/0
tunnel destination 192.168.1.153
tunnel mode gre ip
no shutdown
```

### Cabang:
```
en
conf t
int tunnel 0
ip address 192.168.1.158 255.255.255.252
tunnel source f0/0
tunnel destination 192.168.1.145
tunnel mode gre ip
no shutdown
```

## Testing
![image](https://github.com/user-attachments/assets/dc5f876e-7b71-442b-8ee5-310eab2c91ce)
![image](https://github.com/user-attachments/assets/915dd27a-1f66-4374-acaf-4709687f1ebe)


## Link Youtube
[https://youtu.be/fkeiKkmD0VU](https://youtu.be/fkeiKkmD0VU)
