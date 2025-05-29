 **Add a cover photo like:**
# Topologi
<p align="center">
  <img src="img/1.png">
</p>

# Configure DNAT Virtual IP

## Introduction

✍️ Kali ini kita konfigurasikan DNAT menggunakan Virtual IP pada Fortigate
## Prerequisite

✍️ Konfigurasi kali ini membutuhkan pengetahuan konfigurasi dasar jaringan

## Use Case

✍️ Digunakan jika ingin mengakses sistem kita dari luar jaringan (public)



### Step 1 — Buat Virtual IP
Konfigurasi Virtua IP di menu Virtual IP

<p align="left">
  <img src="img/2.png">
</p>

Buat virtual ip untuk keperluan dnat ke arah 10.0.137.249 yang mengarah ke ip segmentasi vlan 10 DMZ

<p align="center">
  <img src="img/3.png">
</p>

Buat virtual ip untuk keperluan dnat ke arah 10.0.137.249 yang mengarah ke ip segmentasi vlan 20 DMZ

<p align="center">
  <img src="img/4.png">
</p>

Cek lagi konfigurasi Virtual IP

<p align="center">
  <img src="img/5.png">
</p>

### Step 2 - Policy Untuk Akses dari Luar
Cek koneksi jika kita ping dari luar ke ip virtual sesuai topologi yang nanti kita buat masih belum ada jawaban response dari router tujuan

<p align="center">
  <img src="img/9.png">
</p>

<p align="center">
  <img src="img/10.png">
</p>

Buat policy baru di menu Firewall Policy

<p align="center">
  <img src="img/6.png">
</p>

Policy untuk menerima akses dari WAN Public ke segmentasi vlan 10 DMZ

<p align="center">
  <img src="img/7.png">
</p>

Policy untuk menerima akses dari WAN Public ke segmentasi vlan 20 DMZ

<p align="center">
  <img src="img/8.png">
</p>

Cek ulang konfigurasi policy nya

<p align="center">
  <img src="img/11.png">
</p>


### Step 3 — Cek Ulang Koneksi dari WAN
Bisa dilihat dibawah ketika mengontak ke IP yang telah kita set sudah ada jawaban atau mengarah ke ip tujuan sesuai dnat yang dibuat

<p align="center">
  <img src="img/12.png">
</p>

<p align="center">
  <img src="img/13.png">
</p>
