**Add a cover photo like:**
# Topologi
<p align="center">
  <img src="img/1.png">
</p>

# Configure Sub Vlan Interface

## Introduction

✍️ Kali ini kita konfigurasikan Sub Vlan Interface untuk kebutuhan segmentasi network yang berbeda di DMZ

## Prerequisite

✍️ Konfigurasi kali ini membutuhkan pengetahuan konfigurasi dasar jaringan

## Use Case

✍️ Digunakan saat ingin memisahkan segmentasi menjadi 2 jaringan atau lebih



### Step 1 — Konfigurasi Vlan
Konfigurasikan new interface yag nantinya akan vlan akan tertambat di port 3

<p align="left">
  <img src="img/2.png">
</p>

Buat vlan 10 dan vlan 20 dengan ip sesuai topologi untuk gateway

<p align="left">
  <img src="img/3.png">
</p>

<p align="left">
  <img src="img/4.png">
</p>

Berikut hasil hasil dari vlan 10 dan 20 di interface port 3

<p align="left">
  <img src="img/5.png">
</p>

### Step 2 — Koneksi Fortigate ke Sub Vlan
Kita tes koneksi fortigate ke sub vlan di vlan 10 dan vlan 20

<p align="left">
  <img src="img/6.png">
</p>

### Step 3 — Policy LAN ke DMZ
Kita tes koneksi dari Router-2 di segmentasi LAN menuju segmentasi DMZ dengan Sub Vlan

<p align="left">
  <img src="img/7.png">
</p>

Karena belum ada policy untuk allow dari LAN ke DMZ kita perlu membuatnya di Policy Fortigate untuk mengarah ke vlan 10 dan vlan 20

<p align="left">
  <img src="img/8.png">
</p>

<p align="left">
  <img src="img/9.png">
</p>

Berikut hasil dari konfigurasi policy

<p align="left">
  <img src="img/10.png">
</p>

Kita tes lagi koneksi dari segmentasi LAN ke DMZ dengan Sub Vlan

<p align="left">
  <img src="img/11.png">
</p>

Bisa dilihat dari segmentasi LAN sudah bisa terhubung ke segmentasi DMZ dengan Sub Vlan
