**Add a cover photo like:**
# Topologi
<p align="center">
  <img src="img/1.png">
</p>

# Configure Link Aggregate

## Introduction

✍️ Kali ini kita konfigurasikan High Availability dengan system Active Passiv di Fortigate

## Prerequisite

✍️ Konfigurasi kali ini membutuhkan pengetahuan konfigurasi dasar jaringan

## Use Case

✍️ Digunakan jika ingin membuat high availability antisipasi downtime dengan fortigate


### Step 1 — Konfigurasi Dasar Interface dan IP Address
Konfigurasikan ip dan interface sesuai topologi seperti gambar di bawah pada fortigate

<p align="left">
  <img src="img/2.png">
</p>

<p align="center">
  <img src="img/3.png">
</p>


### Step 2 — Konfigurasi High Availability
Pada menu System >> HA buat HA baru 
<p align="center">
  <img src="img/4.png">
</p>


Selanjutnya pada fortigate ke 2 sama konfigurasikan HA juga dengan nama grub dan password harus sama seperti fortigate 1
<p align="center">
  <img src="img/6.png">
</p>

Setelah berhasil bisa di lihat status HA masih belum sync ya walaupun dari fortigate sudah menerima konfigurasi HA
<p align="center">
  <img src="img/8.png">
</p>

Karena belum synchron kita bisa trigger pada fortigate-2 dengan perintah seperti berikut
<p align="center">
  <img src="img/9.png">
</p>

Setelah di tunggu beberapa saat bisa di lihat berikut hasilnya jika antara 2 fortigate sudah sync
<p align="center">
  <img src="img/10.png">
</p>

### Step 3 — Cek Koneksi Router-1 ke Router-2
Pastikan sebelum melakukan tes koneksi sudah membuat rule acc koneksi dari LAN(Router-1) ke WAN(Router-2) 
<p align="center">
  <img src="img/12.png">
</p>

Selanjutnya aktifkan debug ip icmp untuk melihat paket yang keluar masuk pada Router-2
<p align="center">
  <img src="img/11.png">
</p>

Pada Router-1 tes ping ke Router-2
<p align="center">
  <img src="img/13.png">
</p>

Cek hasilnya pada Router-2 bisa di lihat berhasil sesuai status ping pada Router-1
<p align="center">
  <img src="img/14.png">
</p>

### Step 4 — Pengetesan High Availability (HA)  
Saat kita mencoba melakukan ping sebelumnya berikut kondisi perangkat fortigate virtual saya jadi nyala semua 
<p align="center">
  <img src="img/15  .png">
</p>

Selanjutnya disini pada Router-1 saya mencoba repeat ping 100.000 ke Router-2 sambil mematikan Fortigate-1 yang menjadi jalur utama
Bisa dilihat hasilnya sempat ada timeout sebentar karena perpindahan dari fortigate-1 yang active karena mati jadi pindah ke fortigate-2 jadi active yang sebelumnya passive 
<p align="center">
  <img src="img/16.png">
</p>

Bisa dilihat hostname yang aktif sekarang hanya fortigate-2 karena saya masih mematikan fortigate-1
<p align="center">
  <img src="img/18.png">
</p>

Berikut ini kondisi akhir setelah saya menyalakan kembali fortigate-1 nya
<p align="center">
  <img src="img/19.png">
</p>
