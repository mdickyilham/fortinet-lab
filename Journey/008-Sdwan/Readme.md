**Add a cover photo like:**
# Topologi
<p align="center">
  <img src="img/1.png">
</p>

# Configure SD-Wan Dasar

## Introduction

✍️ Kali ini kita konfigurasikan SD-Wan Dasar pada Fortigate

## Prerequisite

✍️ Konfigurasi kali ini membutuhkan pengetahuan konfigurasi dasar jaringan

## Use Case

✍️ Digunakan jika ingin membuat 2 ISP baik saling backup atau mencari best quality content dari salah satu isp dan fungsi lainya lagi


### Step 1 — Konfigurasi Interface dan IP
Konfigurasikan Interface dan IP Sesuai topologi
<p align="left">
  <img src="img/2.png">
</p>


### Step 2 — Konfigurasi SD-Wan Zone
Buat SD-Wan baru pada menu SD-Wan Zones
<p align="center">
  <img src="img/3.png">
</p>

Cukup berikan nama pada SD-WAN nya
<p align="center">
  <img src="img/4.png">
</p>

Berikut hasilnya
<p align="center">
  <img src="img/5.png">
</p>

### Step 3 — Konfigurasi SD-Wan Member
Setelah membuat SD-Wan Zone buat SD-Wan Membernya masih pada menu yang sama
<p align="center">
  <img src="img/6.png">
</p>

Tambahkan ISP-1 dan ISP-2 beserta gateway nya 
<p align="center">
  <img src="img/7.png">
</p>

<p align="center">
  <img src="img/8.png">
</p>

Berikut hasilnya dari penambahan member SD-Wan Member
<p align="center">
  <img src="img/9.png">
</p>

### Step 4 — Konfigurasi SD-Wan Rules
Buat baru SD-Wan Rules untuk keperluan kita mengatur SLA dari internet yang kita gunakan
<p align="center">
  <img src="img/10.png">
</p>

Isikan parameter yang di perlukan seperti source-address, destination, pilih strategi yang digunakan juga pada pilihan yang disediakan disini saya memilih load balance. Pada "Required SLA Target" kita perliu membuat SLA Target baru 
<p align="center">
  <img src="img/11.png">
</p>

Berikut SLA Target yang saya tetapkan untuk lab ini ke dns google
<p align="center">
  <img src="img/12.png">
</p>

Tambahkan pada Required SLA Target
<p align="center">
  <img src="img/13.png">
</p>

Setelah selesai berikut hasilnya
<p align="center">
  <img src="img/14.png">
</p>

### Step 5 — Verifikasi Performance SLA
Bisa dilihat pada menu Performance SLA bisa dilihat bagaimana hasilnya, disini karena virtual dan melewati hotspot jadi seperti yang bisa di lihat sangat tinggi ya latency ping jitter ke dns google haha
<p align="center">
  <img src="img/15.png">
</p>


### Step 6 — Cek Load Balance 
Pastikan sudah membuat rule acc dari LAN ke SDWAN
<p align="center">
<img src="img/16.png">
</p>

<p align="center">
<img src="img/17.png">
</p>

Buat juga def-route ke arah SD-WAN
<p align="center">
<img src="img/18.png">
</p>

<p align="center">
<img src="img/19.png">
</p>

Kita lihat dulu traffic awal yang sudah lewat pada SD-WAN Zones seperti berikut ya nilainya
<p align="center">
  <img src="img/21.png">
</p>

Selanjutnya tes kita ping apakah kedua isp berjalan ? jika berjalan kedua traffic akan bertambah ya
<p align="center">
  <img src="img/22.png">
</p>

Lihat hasilnya ya kedua traffic ISP sama-sama bertambah karena sesuai tujuan kita melakukan load balance
<p align="center">
  <img src="img/23.png">
</p>

Setelah rule policy allow di buat tes lagi apakah sudah bisa koneksi ke DMZ

<p align="center">
<img src="img/21.png">
</p>
