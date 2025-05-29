**Add a cover photo like:**
# Topologi
<p align="center">
  <img src="img/1.png">
</p>

# Configure VPN IPSEC Fortigate

## Introduction

✍️ Kali ini kita konfigurasikan VPN IPSEC antar Fortigate

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

### Step 2 — Buat Policy dari Virtual IP
Cek koneksi dari WAN Public untuk akses ke ip dari yang kita konfigurasi sesuai topologi masih belum bisa

<p align="center">
  <img src="img/10.png">
</p>

<p align="center">
  <img src="img/11.png">
</p>

Buat Firewall Policy di menu Policy & Object

<p align="center">
  <img src="img/6.png">
</p>

Buat policy untuk membuat akses dari WAN Public saat akses 10.0.137.250:2323 dan mengarah ke telnet 192.168.10.2:23

<p align="center">
  <img src="img/7.png">
</p>

Buat policy untuk membuat akses dari WAN Public saat akses 10.0.137.250:2424 dan mengarah ke telnet 192.168.20.2:23

<p align="center">
  <img src="img/8.png">
</p>

### Step 3 — Cek Koneksi Telnet dari Public
Bisa dilihat dibawah saat kita akses ip di fortigate dan dengan port forwarding kita otomatis mengakses ke ip sesuai tujuan

<p align="center">
  <img src="img/12.png">
</p>

<p align="center">
  <img src="img/13.png">
</p>
