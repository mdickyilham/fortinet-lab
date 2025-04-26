**Add a cover photo like:**
# Topologi Basic
<p align="center">
  <img src="img/topologi.png">
</p>

# Configure Basic

## Introduction

✍️ Kali ini kita konfigurasikan dasar dari Fortinet dengan menggunakan VMWare dan Install Pnetlab

## Prerequisite

✍️ Konfigurasi kali ini membutuhkan pengetahuan konfigurasi dasar jaringan

## Use Case

✍️ Digunakan saat pertama kali konfigurasi di perangkat Fortinet 



### Step 1 — Konfigurasi DHCP-Client dan Allowaccess
Konfigurasikan port1 (wan) bisa dengan static/dhcp disini saya menggunakan dhcp dan allow access untuk service yang ingin kita gunakan

<p align="left">
  <img src="img/1.png">
</p>

### Step 2 — Cek IP dari DHCP-Server
Karena saya menggunakan dhcp pastikan sudah mendapatkan ip dari dhcp-server 

<p align="left">
  <img src="img/2.png">
</p>


### Step 3 — Cek Dashboard Web Fortinet
Jika sudah mendapatkan ip dari dhcp-server mari coba kita akses di website dengan tampilan dashboard sebagai berikut

<p align="left">
  <img src="img/5.png">
</p>

### Step 4 — Konfigurasi IP LAN dan DMZ
Untuk konfigurasi ip ke arah LAN dan DMZ kita konfigurasikan via GUI di web

<p align="left">
  <img src="img/6.png">
</p>

Dibawah ini untuk konfigurasi IP arah LAN

<p align="left">
  <img src="img/8.png">
</p>

Dibawah ini untuk konfigurasi IP arah DMZ

<p align="left">
  <img src="img/9.png">
</p>

Berikut hasil dari IP LAN dan DMZ

<p align="left">
  <img src="img/10.png">
</p>

### Step 5 — Tes Konektifitas dari Fortinet ke LAN dan DMZ
Cek ping ke arah router di LAN dan DMZ

<p align="left">
  <img src="img/11.png">
</p>

### Step 6 — Konfigurasi NAT di segmentasi LAN
Kita cek router di LAN belum bisa terhubung ke internet karena belum ada NAT

<p align="left">
  <img src="img/12.png">
</p>

Konfigurasikan NAT pada Fortigate

<p align="left">
  <img src="img/13.png">
</p>

<p align="left">
  <img src="img/13.1.png">
</p>

Cek lagi koneksi di Router-2 apakah sudah bisa terhubung ke internet ?

<p align="left">
  <img src="img/14.png">
</p>

### Step 7 — Policy LAN ke DMZ
Cek dari segmentasi LAN apakah bisa terhubung ke segmentaasi DMZ ?

<p align="left">
  <img src="img/15.png">
</p>

Belum bisa karena kita belum membuat rule untuk menerima paket dari LAN menuju DMZ harus kita buat di policy Fortigate

<p align="left">
  <img src="img/16.png">
</p>

Kita cek lagi dari Router-2 menujue ke segmentasi DMZ

<p align="left">
  <img src="img/17.png">
</p>

### Step 8 — Summary dari Policy NAT dan ACC LAN ke DMZ
Berikut hasil dari konfigurasi NAT dan Policy LAN ke DMZ

<p align="left">
  <img src="img/18.png">
</p>
