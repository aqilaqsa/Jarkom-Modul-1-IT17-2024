# Write Up Modul 1 Praktikum Jaringan Komputer Wireshark through CTFd
## Kelompok IT17
1. Aqila Aqsa (5027211032)
2. Mutiara Nurhaliza (5027221010)

### 1 - Malwleowleo

``` Flag: JARKOM2024{beC4refUl_0f_m4lwAr3_cJw8XzAti6Jo88Y} ```<br>
**Solved by: Mutiara Nurhaliza**

### Pengerjaan
a. Buka file pcap di wireshark, lalu klik di TCP stream
<img src="/images/malw-1-a.png" alt="1" style="width: 800;">

b. Lakukan screening untuk mencari string yang berisi nama **`malware`**
<img src="/images/malw-1-b.png" alt="1" style="width: 800;">

c. Masukkan jawaban yang ditemukan ke dalam netcat
<img src="/images/malw-1-c.png" alt="1" style="width: 800;">

### 2 - whoami

``` Flag: JARKOM2024{Duk3_0f_4rak!s_LISAN AL GHAIB!_IJC8XznHl1VHCrY} ```<br>
**Solved by: Mutiara Nurhaliza**

### Pengerjaan
a. Buka file di wireshark, lalu klik TCP Stream
<img src="/images/whoami-2-a.png" alt="1" style="width: 800;">

b. Melakukan screening untuk mencari string yang berisi nama orang, disini terdapat string yang mencurigakan 
<img src="/images/whoami-2-b.png" alt="1" style="width: 800;">

c. Decode string yang didapat menggunakan Base64
<img src="/images/whoami-2-c.png" alt="1" style="width: 800;">

d. Memasukkan jawaban pada netcat
<img src="/images/whoami-2-d.png" alt="1" style="width: 800;">


### 3 - secret

``` Flag: JARKOM2024{10_Blm_tW_MIO_MIRZA?_9T8kv09HyzFHl4B} ```<br>
**Solved by: Mutiara Nurhaliza**

### Pengerjaan
a. Buka file di wireshark, lalu klik Follow TCP Stream
<img src="/images/secret-3-a.png" alt="1" style="width: 800;">

b. Melakukan screening untuk mencari user dan password, disini didapat bahwa usernya adalah h3ngk3rTzy dan password nya adalah S!l3ncE
<img src="/images/secret-3-b.png" alt="1" style="width: 800;">

c. Menggunakan FileZilla dan memasukkan host, username, dan password yang telah ditemukan
<img src="/images/secret-3-c.png" alt="1" style="width: 800;">

d. Mendownload mirza.jpg yang terdapat pada file h3ngk3rTzy
<img src="/images/secret-3-d.png" alt="1" style="width: 800;">

e. Memasukkan jawaban pada netcat
<img src="/images/secret-3-e.png" alt="1" style="width: 800;">


