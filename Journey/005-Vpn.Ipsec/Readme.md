**Add a cover photo like:**
# Topologi
<p align="center">
  <img src="img/1.png">
</p>

# Configure VPN IPSEC Fortigate

## Introduction

✍️ Kali ini kita konfigurasikan VPN IPsec antar Fortigate

## Prerequisite

✍️ Konfigurasi kali ini membutuhkan pengetahuan konfigurasi dasar jaringan

## Use Case

✍️ Digunakan jika ingin menghubungkan jaringan di 2 site berbeda dengan aman



### Step 1 — Konfigurasi Dasar
Konfigurasikan awal sesuai topologi untuk ip address di masing-masing interface di Fortiage HQ atau Branch

<p align="left">
  <img src="img/2.png">
</p>

<p align="center">
  <img src="img/3.png">
</p>

Tes Koneksi dari Router HQ dan Router Branch yang masih belum bisa terhubung

<p align="center">
  <img src="img/4.png">
</p>

<p align="center">
  <img src="img/5.png">
</p>

### Step 2 — Konfigurasi VPN IPsec pada Fortigate HQ Office
Buat VPN nya di menu VPN >> IPsec Wizard, pilih nama VPN dan perangkat VPN di sisi remote menggunakan apa kali ini kita menggunakan FortiGate jadi pilih Fortigate
<p align="center">
  <img src="img/6.png">
</p>

Pilih Remote Address alamat IP Fortigate sisi lawan yang ingin dilakukan vpn dan tambahkan pre-shared key untuk keamanan
<p align="center">
  <img src="img/7.png">
</p>

Selanjutnya pilih local-address dan remote address sebagai tujuan koneksi mana yang akan diizinkan di sisi local dan remote
<p align="center">
  <img src="img/8.png">
</p>

Ini hasil review konfigurasi IPsec Wizard yang kita konfig pastikan benar parameter" yang digunakan
<p align="center">
  <img src="img/9.png">
</p>


### Step 3 — Konfigurasi VPN IPsec pada Fortigate Branch Office
Buat VPN nya di menu VPN >> IPsec Wizard, pilih nama VPN dan perangkat VPN di sisi remote menggunakan apa kali ini kita menggunakan FortiGate jadi pilih Fortigate
<p align="center">
  <img src="img/10.png">
</p>

Pilih Remote Address alamat IP Fortigate sisi lawan yang ingin dilakukan vpn dan tambahkan pre-shared key untuk keamanan
<p align="center">
  <img src="img/11.png">
</p>

Selanjutnya pilih local-address dan remote address sebagai tujuan koneksi mana yang akan diizinkan di sisi local dan remote
<p align="center">
  <img src="img/12.png">
</p>

Ini hasil review konfigurasi IPsec Wizard yang kita konfig pastikan benar parameter" yang digunakan
<p align="center">
  <img src="img/13.png">
</p>

### Step 4 — Aktifkan VPN HQ-Office dan Branch-Office di HQ-Office
Untuk mengaktifkanya kita perlu membuat state up pada phase 2 sesuai tanda merah di menu IPsec Tunnel klik phase2
<p align="center">
  <img src="img/14.png">
</p>

Pilih bring up pada phase 2 
<p align="center">
  <img src="img/15.png">
</p>

Pastikan tanda up sudah beruhan dari tanda down sebelumnya
<p align="center">
<img src="img/16.png">
</p>

### Step 5 — Show Firewall Policy 
Kita cek firewall policy di HQ dan Branch
<p align="center">
<img src="img/19.png">
</p>

<p align="center">
<img src="img/20.png">
</p>

### Step 6 — Cek lagi koneksi Router HQ dan Router Branch 
Setelah di lakukan VPN untuk kedua site kita cek lagi koneksi vpn antar router hq dan branch
<p align="center">
<img src="img/17.png">
</p>

<p align="center">
<img src="img/18.png">
</p>

Bisa di lihat sudah terhubung koneksi antar office dengan menggunakan VPN IPsec dengan Fortigate

<p align="center">
<img src="img/21.png">
</p>

Dari hasil di atas juga sudah bit packet yang melewati jalur vpn saat kita coba lakukan tes koneksi ulang antar router office
