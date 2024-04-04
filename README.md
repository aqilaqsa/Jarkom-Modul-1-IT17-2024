# Write Up Modul 1 Praktikum Jaringan Komputer Wireshark through CTFd
## Kelompok IT17
1. Aqila Aqsa (5027211032)
2. Mutiara Nurhaliza (5027221010)

### 1 - Malwleowleo

``` Flag: JARKOM2024{beC4refUl_0f_m4lwAr3_cJw8XzAti6Jo88Y} ```

### Pengerjaan
a. Buka file pcap di wireshark, lalu klik di TCP stream
<img src="/images/malw-1-a.png" alt="1" style="width: 800;">

b. Lakukan screening untuk mencari string yang berisi nama **`malware`**
<img src="/images/malw-1-b.png" alt="1" style="width: 800;">

c. Masukkan jawaban yang ditemukan ke dalam netcat
<img src="/images/malw-1-c.png" alt="1" style="width: 800;">