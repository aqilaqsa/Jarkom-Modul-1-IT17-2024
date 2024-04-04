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
<img src="/images/malw-1-b.png" alt="2" style="width: 800;">

c. Masukkan jawaban yang ditemukan ke dalam netcat
<img src="/images/malw-1-c.png" alt="3" style="width: 800;">



### 2 - whoami

``` Flag: JARKOM2024{Duk3_0f_4rak!s_LISAN AL GHAIB!_IJC8XznHl1VHCrY} ```<br>
**Solved by: Mutiara Nurhaliza**

### Pengerjaan
a. Buka file di wireshark, lalu klik TCP Stream
<img src="/images/whoami-2-a.png" alt="4" style="width: 800;">

b. Melakukan screening untuk mencari string yang berisi nama orang, disini terdapat string yang mencurigakan 
<img src="/images/whoami-2-b.png" alt="5" style="width: 800;">

c. Decode string yang didapat menggunakan Base64
<img src="/images/whoami-2-c.png" alt="6" style="width: 800;">

d. Memasukkan jawaban pada netcat
<img src="/images/whoami-2-d.png" alt="7" style="width: 800;">



### 3 - secret

``` Flag: JARKOM2024{10_Blm_tW_MIO_MIRZA?_9T8kv09HyzFHl4B} ```<br>
**Solved by: Mutiara Nurhaliza**

### Pengerjaan
a. Buka file di wireshark, lalu klik Follow TCP Stream.
<img src="/images/secret-3-a.png" alt="8" style="width: 800;">

b. Melakukan screening untuk mencari user dan password, disini didapat bahwa usernya adalah h3ngk3rTzy dan password nya adalah S!l3ncE.
<img src="/images/secret-3-b.png" alt="9" style="width: 800;">

c. Menggunakan FileZilla dan memasukkan host, username, dan password yang telah ditemukan.
<img src="/images/secret-3-c.png" alt="10" style="width: 800;">

d. Mendownload mirza.jpg yang terdapat pada file h3ngk3rTzy.
<img src="/images/secret-3-d.png" alt="11" style="width: 800;">

e. Memasukkan jawaban pada netcat.
<img src="/images/secret-3-e.png" alt="12" style="width: 800;">



### 4 - fuzz

``` Flag: JJARKOM2024{s3m4ng4t_ya_<3_IJ8kRcxHgzFsk88} ```<br>
**Solved by: Mutiara Nurhaliza**

### Pengerjaan
a. Mencari ip address attacker. Dengan asumsi bahwa 10.33.1.154 adalah ip address attacker karena sering mengirim paket SYN.
<img src="/images/fuzz-4-a.png" alt="13" style="width: 800;">

b. Mencari port yang digunakan oleh korban. Berdasarkan network traffic tersebut, attacker melakukan koneksi ke port 80 dari korban
<img src="/images/fuzz-4-b.png" alt="14" style="width: 800;">

c. Mencari endpoint yang digunakan untuk login dengan mencoba untuk follow stream dari situ didapatkan ‘Post /’ yang menunjukkan bahwa endpoint nya adalah /.
<img src="/images/fuzz-4-c.png" alt="15" style="width: 800;">

d. Mencari tool yang digunakan oleh attcker untuk bruteforce login. Dari follow stream sebelumnya didapat bahwa tools yang digunakan untuk melakukan fuzzing yaitu Fuzz Faster U Fool v2.0.0-dev.
<img src="/images/fuzz-4-d.png" alt="16" style="width: 800;">

e. Melakukan follow stream dan screening lagi untuk mencari username dan password yang mungkin digunakan oleh attacker. disini terdapat username dan password dengan Content-Length paling panjang yaitu username=admin&password=sUp3rSecretp@ssw0rd.

f.  Memasukkan 5 jawaban yang telah ditemukan ke netcat.
<img src="/images/fuzz-4-e.png" alt="17" style="width: 800;">



### 5 - evidence
<img src="/images/evidence-5-a.png" alt="18" style="width: 800;">

``` Flag: JARKOM2024{m4innya_h3bat_IhfRXbnjgAdt84Y} ```<br>
**Solved by: Aqila Aqsa**

### Pengerjaan
a. Buka file pcap di wireshark, klik kanan TCP stream, follow, masukkan domain korban yang ditemukan ke netcat.
<img src="/images/evidence-5-b.png" alt="19" style="width: 800;">

b. Masukkan web server korban ke netcat.
<img src="/images/evidence-5-c.png" alt="20" style="width: 800;">

c. Melakukan filter `http.request.command == "POST"` untuk menemukan endpoint yang digunakan untuk login sebagai user biasa.
<img src="/images/evidence-5-f.png" alt="21" style="width: 800;">

d. Masukkan endpoint ke netcat
<img src="/images/evidence-5-d.png" alt="22" style="width: 800;">

e. Kembali ke filter POST, temukan email dan password yang sukses digunakan untuk login, masukkan ke dalam netcat.
<img src="/images/evidence-5-e.png" alt="23" style="width: 800;">

**Kendala**
- Kesalahan screening TCP stream hingga akhir sehingga menyebabkan kesalahan credentials yang ditemukan untuk login.
<img src="/images/evidence-kendala.png" alt="24" style="width: 800;">



### 6 - ATM or ATP or FTP?
<img src="/images/atm-6-a.png" alt="25" style="width: 800;">

``` Flag: JARKOM2024{Brut3f0rce_FtP_IhrCXbAjizds8AB} ```<br>
**Solved by: Aqila Aqsa**

### Pengerjaan
a. Buka file pcap di wireshark, filter `ftp` karena bahasan dari soal adalah FTP. Selanjutnya, connect ke netcat, pertanyaannya adalah password yang didapatkan hacker.
<img src="/images/atm-6-b.png" alt="26" style="width: 800;">

b. klik kanan pada stream dengan teks *Login Successful*, masukkan jawaban ke netcat.
<img src="/images/atm-6-c.png" alt="27" style="width: 800;">



### 7 - How Many packets?
<img src="/images/packets-7-a.png" alt="28" style="width: 800;">

``` Flag: JARKOM2024{c0unT_uR_P4cket5_uhrCXcpjgRdt8r8} ```<br>
**Solved by: Aqila Aqsa**

### Pengerjaan
a. Buka file pcap di wireshark, karena ini merupakan bruteforce FTP, dan ketika connect netcat pertanyaannya adalah berapa kali attempt login, saya berpikir bahwa setiap attempt akan mengandung pass yang dikirimkan. Jadi, saya melakukan filter `ftp.request.command contains "PASS"`. Packets terdisplay di bagian kanan bawah (934).
<img src="/images/packets-7-b.png" alt="29" style="width: 800;">



### 8 - trace him
<img src="/images/tracehim-8-a.png" alt="30" style="width: 800;">

``` Flag: JARKOM2024{Wh3re’5_thE_S4uce_IhC8R7AygAkel8q} ```<br>
**Solved by: Aqila Aqsa**

### Pengerjaan
a. Masih berhubungan dengan soal How Many packets, dapat dilihat IP address attacker yang melakukan bruteforce.
<img src="/images/tracehim-8-b.png" alt="31" style="width: 800;">

b. Masukkan jawaban ke netcat.
<img src="/images/tracehim-8-c.png" alt="32" style="width: 800;">



### 9 - creds
<img src="/images/creds-9-a.png" alt="33" style="width: 800;">

``` Flag: JARKOM2024{s3curE_uR_FtP_I6fCv7Ajy1kHkAY} ```<br>
**Solved by: Aqila Aqsa**

### Pengerjaan
a. Buka file pcap di wireshark, filter `ftp` karena bahasan soal adalah ftp. akan terlihat creds attacker.
<img src="/images/creds-9-b.png" alt="34" style="width: 800;">

b. Masukkan jawaban ke netcat.
<img src="/images/creds-9-c.png" alt="35" style="width: 800;">


## Kendala keseluruhan pengerjaan
1. VPN sering terdisconnect di tengah pengerjaan
2. laptop issue wireshark sering force close... <br>
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⣠⣤⡶⠶⠿⠿⠶⢶⣤⣄⠀⠀⠀⠀⢀⣀⣠⣤⣤⣤⣀⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⣤⣾⠟⠉⠀⠀⠀⠀⠀⠀⠀⠈⠛⢿⣦⣶⠿⠛⠉⠉⠁⠀⠈⠙⠻⣦⡀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣰⡿⠋⠀⠀⠀⣀⣠⣤⣤⣤⣤⣤⣤⣀⡀⠹⣧⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⢿⡄⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣰⡿⠁⠀⠀⣶⡿⠛⠉⠀⠀⠀⠀⠀⠈⠉⠻⢷⣿⣧⣶⣶⠶⠿⠿⠿⠿⠷⣶⣾⣷⣄⡀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣰⡿⠀⠀⠀⠀⠁⠀⠀⠀⠀⢀⣠⣤⣶⠶⢾⣿⣿⡿⠿⣶⣄⠀⠀⢴⡶⠶⡶⣷⣾⢿⠿⠿⠷⣦⣄⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⣀⣴⡟⠀⠀⠀⠀⠀⠀⣀⣤⣶⠾⣻⣭⣷⠾⠛⠛⠋⠛⠛⠛⠻⢿⣷⣤⣶⣷⠶⠿⡛⣛⢛⠛⠛⠿⣶⣿⡆⠀
⠀⠀⠀⠀⠀⢀⣴⡾⠛⠁⠀⠀⠀⠀⠀⢠⣴⣿⣭⡶⠟⠋⠉⠀⣀⣠⣤⣶⣶⠾⠿⠛⠻⢿⣧⣤⣴⡶⠿⢿⣿⣿⣿⣟⠛⠷⠿⣿⡆
⠀⠀⠀⠀⠀⣼⠟⠀⠀⠀⠀⠀⠀⠀⠀⠙⠷⠾⣷⣶⣶⡶⠾⠛⢻⣿⣏⣻⡿⠻⣦⡀⢀⣼⠏⠁⠀⠀⢠⣿⣧⣼⠛⣿⣷⠀⢀⣼⡇
⠀⠀⠀⢀⣾⠏⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠸⣯⣛⡷⣦⣤⣾⣿⣯⣽⣷⣴⣿⡷⣟⣿⠷⠶⣶⣤⣾⣿⣦⣿⣶⣿⣿⣿⣿⠏⠀
⠀⠀⣠⣿⠃⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠉⠛⠻⠶⠿⠿⠿⠷⢾⣿⣿⠟⠋⠁⣤⡀⠀⠀⠀⠀⠀⠀⢀⣠⣼⠟⠀⠀⠀
⠀⢠⡿⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣀⣠⣤⡶⠿⠋⠁⠀⠀⠀⠛⠻⢶⣶⡶⠶⠶⠿⣿⡏⠁⠀⠀⠀⠀
⢠⣿⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠛⠉⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠙⠿⠀⠀⠀⠈⢿⣦⠀⠀⠀⠀
⢸⡇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢹⣧⠀⠀⠀
⠸⣷⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣠⣶⠶⡿⠛⠛⠻⠿⠶⢶⣦⣤⣤⣀⣀⡀⠀⠀⠀⠀⠀⣀⣀⣀⣀⣤⣤⣶⠶⠟⠻⣧⠀⠀
⠀⢻⣇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢼⡟⠀⠰⡶⢶⣶⣶⣤⣤⣤⣀⣀⠉⠙⠛⠛⠛⠛⠛⠛⠛⠛⠛⠛⠉⠉⠀⠀⢀⣀⣴⡟⠀⠀
⠀⠈⢿⣆⠀⠀⠀⠀⠀⠀⠀⠀⠀⣴⠘⢿⣤⣀⣥⣤⣴⣦⣤⣬⣉⣉⣛⠛⠛⠿⠷⠶⠶⠶⠶⠶⠶⠶⠶⠶⠾⠟⠛⢻⣿⠁⠀⠀⠀
⠀⠀⠈⠻⣧⣄⠀⠀⠀⠀⠀⠀⠀⠻⣷⣤⣉⡉⠁⠀⠀⠀⠀⠈⠉⠛⠛⠻⠿⠿⠶⢶⣶⣶⣶⣦⣤⣤⣤⣄⣠⣤⣴⡾⠋⠀⠀⠀⠀
⠀⠀⠀⠀⠘⢿⣷⣦⣤⣀⡀⠀⠀⠀⠀⠉⠉⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣈⣽⠟⠋⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠉⠛⠿⣿⣿⣿⡷⣶⣦⣤⣄⣀⣀⣀⣀⣀⣀⣀⣀⣀⣀⣀⣀⣀⣀⣠⣤⣴⣶⡾⠿⠋⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠉⠙⠛⠷⠾⢯⣭⣭⣭⣭⣉⣉⣉⣉⣉⣉⣉⣩⣭⣽⡿⠟⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠉⠉⠉⠉⠉⠉⠉⠉⠉⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀