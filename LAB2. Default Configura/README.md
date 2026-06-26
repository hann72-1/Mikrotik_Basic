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

3. WAN (Wide Area Network)

   MIkrotik default sudah membuat konfig WAN otomatis agar kita dapat langsung menggunakan. WAN terdiri dari apa saja sih?

    -Port Khusus Internet

      Coba kalian perhatikan kembali interface ether 1 berstatus R saja, berarti dia berdiri sendiri sebagai interface. default mikrotik membuat ether 1 di khususkan sebagai jalur masuknya internet (WAN)

   -DHCP Client Otomatis

      Interface ether 1 sudah di konfig otomatis sebagai DHCP Client, coba teman-teman cek di bagian ip >> ip DHCp Client. artinya jika teman-teman menyambungkan kabel dari ISP ke port 1, Mikrotik akan langsung meminta dan menerima IP Address, Gateway, serta DNS secara otomatis dari ISP

   <img width="464" height="159" alt="dhcp client" src="https://github.com/user-attachments/assets/25c45174-07b9-45d0-9667-d87cb1ff561e" />

   Perhatikan juga statusnya bertulisan bound, berarti mikrotik ether 1 sukses mendaptkan ip,gateway, dan DNS otomatis

   -Firewall NAT

   <img width="518" height="150" alt="firewall" src="https://github.com/user-attachments/assets/174595ec-2d96-4d78-b36c-dc52402d5b2e" />

   Jalur WAN ini sudah terhubung dengan firewall NAT. Tugasnya adalah meneruskan internet dari ISP agar bisa dibagikan dan dinikmati oleh semua interface dari ether2-5 dan WLAN mikrotik teman-teman

   chain: srcnat

   action: Masqurade

   Ini adalah default mikrotik agar client yang nantinya terhubung ke router dapat menikmati internet

4. Ip Address

      <img width="338" height="348" alt="ip address" src="https://github.com/user-attachments/assets/cda6290f-ff0a-4bfb-9f2a-e339ce2f4d24" />

      Pada bagian ip >> address, terlihat 2 ip, yang 192.168.70.64 saya dapat dari DHCP Client, perhatikan juga flags di kiri terdapat tulisan D yang berarti dynamic, kurang lebih artinya saya mendapatkan ipnya secara otomatis.

      pada default mikrotik ip 192.168.88.1 di letakan di interface bridge, jadi semua interface/port yang masuk di bridge memiliki ip 192.168.88.x

5. DHCP Server

      <img width="278" height="398" alt="dhcp server" src="https://github.com/user-attachments/assets/a19d0ae8-5fd1-4677-a41b-bc8adce959c7" />

      Coba teman-teman cek IP >> DHCP Server, di situ terdapat 1 dhcp server dengan nama defconf, dan di arahkan ke interface bridge, seperti yang pernah saya katakan bridge ini adalah kumpulan interface yang sudah di kumpulkan dalam 1 segmen

6. Wireless

      <img width="402" height="368" alt="wirelless" src="https://github.com/user-attachments/assets/e7b05fcf-477a-476e-a835-b878f4b57f01" />

      Default Mikrotik sudah mengatur

      -Mode AP-Bridge: Artinya mikrotik otomais bertindak sebagai pemancar (access Point) yang bisa di tangkap oleh hp atau laptop

      -SSID Bawaan: Nama WI-FI (SSID) default biasanya berformat Mikrotik-XXXXXX (X adalah kombinasi dari mac address perangkat)

      -WI-FI tanpa password secara default mikrotik

      -Band & Frekuensi di atur otomatis: agar mikrotik memilih saluran yang paling bersih secara otomatis, dengan standar band universal (seperti 2.4GHz b/g/n)

7. Firewall Filter Rule

   <img width="901" height="374" alt="firewall filter rule" src="https://github.com/user-attachments/assets/de7f2f44-c937-43cd-90af-13c7dfb391a9" />

   Pada Default configuration di bagian Firewall >> Filter Rule, ether 1 dibuat khusus sebagai internet dan siapa saja yang mencoba meremote lewat ether 1 di buat drop atau tidak dapat meremotenya

   <hr>

   Kesimpulan: Default Configuration adalah cara paling mudah agar mikrotik dapat digunakan untuk client sampai client bisa menikmati internet.

   Akhir Kata Assalamualikum Wr. Wb




      

   




   



