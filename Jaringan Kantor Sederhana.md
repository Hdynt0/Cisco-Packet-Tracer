# 📚 Dokumentasi Jaringan Kantor

**Topik:** Perancangan Jaringan kantor Sederhana dengan Subnetting di Cisco Packet Tracer

---

## 🎯 Tujuan Pembelajaran

Hari ini saya mempelajari cara membangun jaringan kantor sederhana yang mencakup dua departemen (Akun dan Pengiriman). Tujuan utamanya adalah:

- Memahami konsep subnetting
- Mengkonfigurasi alamat IP, subnet mask, dan default gateway
- Menghubungkan perangkat melalui topologi jaringan
- Menguji konektivitas antar subnet

---

## 🛠️ Tools yang Digunakan

| Nama | Keterangan |
|------|------------|
| Cisco Packet Tracer | Simulator jaringan untuk membangun dan menguji jaringan |
| Command Line Interface (CLI) | Untuk konfigurasi router |
| Desktop IP Configuration | Untuk konfigurasi perangkat end-device |

---

## 🧭 Langkah-langkah Implementasi

### 1. Persiapan dan Perencanaan
- Membagi jaringan menjadi dua subnet: Akun & Pengiriman
- Menentukan rentang alamat IP: `192.168.40.0/24`
- Subnetting menjadi dua subnet: `/25` (mask: `255.255.255.128`)

| Subnet | Network ID | Rentang Host | Broadcast |
|--------|------------|--------------|-----------|
| Akun | 192.168.40.0 | 192.168.40.1 – 192.168.40.126 | 192.168.40.127 |
| Pengiriman | 192.168.40.128 | 192.168.40.129 – 192.168.40.254 | 192.168.40.255 |

### 2. Pembuatan Topologi
- Router (contoh: 2911)
- 2 Switch (untuk masing-masing subnet)
- 4 PC (2 per departemen)
- Printer (opsional)

### 3. Pengkabelan
- Gunakan kabel **Straight-Through**
- Hubungkan:
  - Router ⇄ Switch
  - Switch ⇄ PC/Printer

### 4. Konfigurasi Router (via CLI)
```bash
enable
configure terminal

interface GigabitEthernet0/0
ip address 192.168.40.1 255.255.255.128
no shutdown

interface GigabitEthernet0/1
ip address 192.168.40.129 255.255.255.128
no shutdown

exit
copy running-config startup-config
```
