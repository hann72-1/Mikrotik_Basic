# LAB2. Default Configuration

<br>
<br>
<br>

<img width="817" height="422" alt="image" src="https://github.com/user-attachments/assets/8c88a7ae-586b-4a27-b3f3-a373206d9acb" />

Assalamualium Wr.Wb

kali ini saya akan menjelaskan Default Configuration pada mikrotik, pada dasarnya perangkat mikrotik yang baru kalian beli pasti sudah dalam keadaan default configuration, atau konfigurasi yang di tetapkan oleh pabrik agar kita tinggal menyalakan perangkat dan menggunakannya. Untuk pemula, default configuration ini sangat berguna, jadi kita akan membahas apa saja sih yang sudah di konfig oleh pabrik agar mikrotik ini tinggal menggunakannya??

sebelum itu cek device mikrotik masing-masing, apakah mikrotik dalam keadaan default configuration atau tidak. Cara mengetahuinya coba teman-teman koneksikan mikrotiknya sesuai topologi, dan login menggunakan

user: admin

password: (kosong)

NOTE: tidak semua user dan passwordnya sama, mikrotik yang baru biasanya password defaultnya berbeda-beda,biasanya terletak di belakang dus box mikrotiknya. Tetapi mikrotik keluaran lama default passwordnya (kosong).

<img width="667" height="483" alt="default config" src="https://github.com/user-attachments/assets/751ab479-e962-416d-bf33-62f2b2916cbe" />

Tanda bahwa device kalian sudah default configuration.

<br>
<br>

"Kang device saya gada tampilan seperti itu, tadi juga login ipnya 0.0.0.0, kalo ini kenapa?"

Biasanya device seperti itu berada di blank configuartion (konfig kosongan)

<h1> Cara membuat default configuartion mikrotik </h1>

1. Kalian remote dulu menggunakan winbox

2. Klik bagian system

   <img width="304" height="720" alt="Screenshot 2026-06-26 093253" src="https://github.com/user-attachments/assets/add60cca-0475-4203-a71a-6fabb8039cbd" />

3. Klik reset configuartion

   <img width="371" height="721" alt="Screenshot 2026-06-26 093440" src="https://github.com/user-attachments/assets/c2d9ffd3-6006-4947-a0a0-56b82b60b795" />

4. klik do not backup, karna kita hanya ingin membuat default configuration mikrotik, JANGAN CENTANG NO DEFAULT CONFIGURATION, lalu klik reset configuartion

   <img width="452" height="223" alt="Screenshot 2026-06-26 093541" src="https://github.com/user-attachments/assets/399a5f7e-6ea4-4127-850c-5a93cce7c632" />

5. JANGAN PANIK!!! Kalian akan keluar dari winbox secara otomatis, tunggu mikrotik beberapa saat, sampai kembali pada tampilan awal. Karna setiap mereset konfigurasi, mikrotik akan me-reboot secara otomatis.

6. Setelah Mikrotik menyala kembali mikrotik dalam keadaan default configuration 

<br>
<br>

<h1> Isi dari default configuration </h1>

1. Interface

   <img width="671" height="374" alt="interface" src="https://github.com/user-attachments/assets/dd23bb74-33e4-4bff-bfbb-0d15aa34358a" />

   Coba teman-teman cek interface masing-masing, device saya ada 5 port dan 1 WLAN. Coba perhatikan flag di kiri setiap interface

   Flag Setiap Interface

   a. R (running)

   b. S (slave)

   ini berarti interface tersebut tidak berdiri sendiri,melainkan sudah menyatu di 1 bridge, perhatikan kembali flag s ini berada ether 2-5, dan wlan. Itu berarti port tersebut dalam 1 bridge yang sama. Dan juga interface yang berstatus slave tidak dapat di beri ip terpisah

2. Bridge

   <img width="367" height="92" alt="bridge" src="https://github.com/user-attachments/assets/cfa0cee9-d27c-44d6-839b-0d6d5854eeef" />

   Coba Teman-teman cek bagian bridge, kita memiliki 1 bridge yang bernama "bridge", coba teman-teman cek bagian bridge port.

   <img width="375" height="199" alt="bridge port" src="https://github.com/user-attachments/assets/a41f556f-1d66-406e-b9ed-407606de36c5" />

   seperti yang saya katakan tadi "bridge" berisikan ether 2-5 dan wlan. Jadi mereka tu seperti di satu jalur yang sama.




   



