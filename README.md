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

# 5. Konfigurasi Static Routing
Jalankan command berikut pada masing - masing router.

### Lantai1
```
en
conf t
ip route 0.0.0.0 0.0.0.0 192.168.1.130
do write
```

### Lantai2
```
en
conf t
ip route 192.168.0.128 255.255.255.128 192.168.1.129
ip route 0.0.0.0 0.0.0.0 192.168.1.134
do write
```

### Lantai3
```
en
conf t
ip route 192.168.0.128 255.255.255.128 192.168.1.133
ip route 192.168.1.128 255.255.255.252 192.168.1.133
ip route 192.168.0.0 255.255.255.128 192.168.1.133
ip route 0.0.0.0 0.0.0.0 192.168.1.138
do write
```

### Lantai4
```
en
conf t
ip route 192.168.0.128 255.255.255.128 192.168.1.137
ip route 192.168.1.128 255.255.255.252 192.168.1.137
ip route 192.168.0.0 255.255.255.128 192.168.1.137
ip route 192.168.1.132 255.255.255.252 192.168.1.137
ip route 192.168.1.64 255.255.255.192 192.168.1.137
ip route 0.0.0.0 0.0.0.0 192.168.1.142
do write
```

### Lantai5
```
en
conf t
ip route 192.168.0.128 255.255.255.128 192.168.1.141
ip route 192.168.1.128 255.255.255.252 192.168.1.141
ip route 192.168.0.0 255.255.255.128 192.168.1.141
ip route 192.168.1.132 255.255.255.252 192.168.1.141
ip route 192.168.1.64 255.255.255.192 192.168.1.141
ip route 192.168.1.136 255.255.255.252 192.168.1.141
ip route 192.168.1.192 255.255.255.192 192.168.1.141
ip route 0.0.0.0 0.0.0.0 192.168.1.146
do write
```

### Cabang
```
en
conf t
ip route 0.0.0.0 0.0.0.0 192.168.1.154
do write
```

### Router0
```
en
conf t
ip route 192.168.0.128 255.255.255.128 192.168.1.145
ip route 192.168.1.128 255.255.255.252 192.168.1.145
ip route 192.168.0.0 255.255.255.128 192.168.1.145
ip route 192.168.1.132 255.255.255.252 192.168.1.145
ip route 192.168.1.64 255.255.255.192 192.168.1.145
ip route 192.168.1.136 255.255.255.252 192.168.1.145
ip route 192.168.1.192 255.255.255.192 192.168.1.145
ip route 192.168.1.140 255.255.255.252 192.168.1.145
ip route 192.168.1.0 255.255.255.192 192.168.1.145
ip route 192.168.1.148 255.255.255.252 192.168.1.153
do write
```

Untuk melihat routing yang ada pada router, dapat menggunakan command ```sh ip route```.
### Lantai1
![image](https://github.com/user-attachments/assets/d5ea9375-5ca9-477a-b3a1-65159f0ae03c)

### Lantai2
![image](https://github.com/user-attachments/assets/638aa9b5-0e2a-4d4f-995f-37cb73c0443a)

### Lantai3
![image](https://github.com/user-attachments/assets/8296af54-4de9-4f3f-9be3-badbad7506fd)

### Lantai4
![image](https://github.com/user-attachments/assets/53021947-3a70-4b4a-9b7b-eb00c69812f9)

### Lantai5
![image](https://github.com/user-attachments/assets/c9e4f020-10f0-481a-8fa5-e4cb3e79988f)

### Cabang
![image](https://github.com/user-attachments/assets/20fb55f6-8717-4559-8cf3-c6353e4457f6)

### Router0
![image](https://github.com/user-attachments/assets/5fff69cb-40a5-4b0a-8aad-99fccfe9106c)

# 6. Konfigurasi NAT
Konfigurasi interface inside dan outside serta NAT dari tiap router dengan command berikut.
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
Router0:
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

Jangan lupa untuk atur DNS server pada tiap client menjadi 8.8.8.8.
![image](https://github.com/user-attachments/assets/04049dd1-4e77-4dd3-b624-ecc00ab9dda5)

## Testing
![image](https://github.com/user-attachments/assets/b8f620dd-5989-4e79-9b4b-f15c3f563d97)
![image](https://github.com/user-attachments/assets/fbe5bfad-79e6-4f71-b8a8-b93ca058da96)
