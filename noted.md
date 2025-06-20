# 📘 Dokumentasi Dasar CLI Cisco Router

Dokumen ini menjelaskan fungsi dari perintah-perintah dasar Cisco CLI yang sering digunakan saat konfigurasi jaringan, khususnya pada router dan switch.

## 🔧 Daftar Perintah dan Fungsinya
### 🔹 `enable`
- **Fungsi:** Masuk dari **User EXEC mode** ke **Privileged EXEC mode**.
- Mode ini memberikan akses penuh untuk melihat konfigurasi dan menjalankan perintah-perintah lanjutan.
- **Prompt berubah** dari `>` menjadi `#`.
```
Router> enable
Router#
```
### 🔹 configure terminal
Fungsi: Masuk ke Global Configuration Mode untuk mengubah konfigurasi perangkat.
Digunakan setelah enable.
```
Router# configure terminal
Router(config)#
```
### 🔹 interface fa0/0 atau interface gig0/0
Fungsi: Masuk ke konfigurasi sebuah interface (port) untuk mengatur IP, status, dll.
fa = FastEthernet, gig = GigabitEthernet.
```
Router(config)# interface fa0/0
Router(config-if)#
```
### 🔹 no shutdown
Fungsi: Mengaktifkan interface. Default-nya interface dalam kondisi shutdown (nonaktif).
Harus diketik di dalam mode konfigurasi interface.
```
Router(config-if)# no shutdown
```
### 🔹 ip route
Fungsi: Menambahkan static route ke tabel routing router.
Format umum:
```
ip route [network_tujuan] [subnet_mask] [next_hop_ip]
```
Contoh:
```
Router(config)# ip route 192.168.20.0 255.255.255.0 10.10.10.10
```
### 🔹 end
Fungsi: Keluar dari semua mode konfigurasi dan kembali ke Privileged EXEC mode.
Alternatif lain: tekan Ctrl + Z.
```
Router(config)# end
Router#
```
