<img width="890" height="492" alt="image" src="https://github.com/user-attachments/assets/3ef630de-1aa0-43bc-adad-1116acab5cfd" />

<br>

Assalamualaikum Wr. Wb

Kali ini saya akan membagikan materi "Cara Mengkoneksikan Mikrotik Ke Internet", tentu saja sampai laptop teman-teman dapat mengakses internet. Langsung saja kita Lab, sebelum itu koneksikan mikrotik teman-teman menggunakan kabel lan/RJ45 sesuai topologi di atas.

<h1> Koneksikan Mikrotik Ke Internet DHCP (otomatis) </h1>

1. Remote mikrotik teman-teman menggunakan WinBox

2. Buka IP >> DHCP Client

<img width="308" height="336" alt="Screenshot 2026-06-27 090705" src="https://github.com/user-attachments/assets/dafcdf0e-ecad-44ed-8d29-3d6209e04ad5" />


3. Klik (+)

   -Arahkan interfacenya ke ether1

   -Centang Use Peer DNS
   
   Ini berfungsi agar kita mendapatkan DNS secara otomatis dari ISP (sumber internet)

   -Centang Use Peer NTP

    Ini berfungsi agar perangkat router atau komputer secara otomatis menerima dan menyinkronkan pengaturan waktu dari server NTP (Network Time Protocol) yang diberikan oleh ISP

   -Klik Aplly, lalu Ok

   <img width="673" height="340" alt="Screenshot 2026-06-27 090855" src="https://github.com/user-attachments/assets/8b0ef82d-279a-455b-9136-36d077269418" />

   -Pastikan statusnya sudah bound

   <img width="494" height="404" alt="Screenshot 2026-06-27 091824" src="https://github.com/user-attachments/assets/1f20cc09-a176-4e1e-ae89-d6ff455a6d81" />

4. Teman-teman boleh mecatat terlebih dahulu Ip yang keluar

   <img width="531" height="353" alt="image" src="https://github.com/user-attachments/assets/aa218753-d37e-4b66-91b1-5c720de67131" />

5. Selanjutnya kita buat ip gateway (UNTUK LAPTOP KITA)

   -Klik Ip >> Address

   <img width="267" height="280" alt="Screenshot 2026-06-27 092415" src="https://github.com/user-attachments/assets/43a2991d-21ef-4409-a75a-ab55017e8421" />


   -Klik tanda (+)

   -Tambahkan Ipnya 192.168.10.1/24

   -Arahkan Interfacenya ke ether2

   -Klik Aplly lalu Ok

   <img width="466" height="166" alt="Screenshot 2026-06-27 092539" src="https://github.com/user-attachments/assets/0402bdf5-e577-4cfb-bd0d-29f7f6d15b15" />

   Kita sudah punya ip gateway (UNTUK LAPOP KITA) yakni 192.168.10.1

6. Kita setting firewall NAT

     -Klik Ip >> Firewall >> NAT

     <img width="533" height="216" alt="Screenshot 2026-06-27 093028" src="https://github.com/user-attachments/assets/e0fc3195-af87-476f-939b-413fdf3e1c98" />

     -Klik (+) lalu chain=srcnat out-interfaceny=ether1

     <img width="426" height="349" alt="Screenshot 2026-06-27 093145" src="https://github.com/user-attachments/assets/f31f53c9-52cd-44e9-bb37-d66ce9534037" />

     -Klik bagian action lalu pilih masquerade, klik Aplly dan Ok

     <img width="407" height="168" alt="Screenshot 2026-06-27 093229" src="https://github.com/user-attachments/assets/7ebd7948-5fbd-4e99-8272-ba9dc3d53f69" />

7. Setting Ip teman-teman menggunakan Control Panel

   -Klik Ctrl + R mengeluarkan tab run lalu ketikan control panel & klik Ok

   -Klik bagian Network And Internet

   <img width="1150" height="679" alt="Screenshot 2026-06-27 093936" src="https://github.com/user-attachments/assets/e4156314-6066-49f7-8917-054a426b3ab1" />

   -Klik Network And Sharing Center

   <img width="509" height="131" alt="Screenshot 2026-06-27 094251" src="https://github.com/user-attachments/assets/74f6a6b9-b0ee-4432-9aaf-78ce995687a8" />

   -Klik Change Adapter Setting

   <img width="247" height="149" alt="Screenshot 2026-06-27 094739" src="https://github.com/user-attachments/assets/9303ca0e-ebff-4a33-b8c3-8203e7e83ada" />

   -Doble klik Adapter Kabel LAN teman-teman, pilih properties, pilih internet protocol version 4

   <img width="741" height="491" alt="Screenshot 2026-06-27 094504" src="https://github.com/user-attachments/assets/61cf3eb4-2236-425f-ad5b-8fd8fdddf23c" />

   -Isikan sesuai dengan foto lalu klik Ok

   <img width="406" height="459" alt="Screenshot 2026-06-27 095150" src="https://github.com/user-attachments/assets/be3e0135-9fda-4311-b9d6-ebdc7cef08d6" />

8. Cek koneksi internet dengan ping google.com lewat cmd teman-teman, bila sudah replay berarti laptop dan mikrotik teman-teman sudah mendaptakan internet, teman-teman juga bisa coba ping lewat mikrotik teman-teman, dengan cara buka Winbox >> New Terminal >> ping google.com

   <img width="569" height="297" alt="Screenshot 2026-06-27 095544" src="https://github.com/user-attachments/assets/a26074c9-b26d-4a69-b241-0e8e160cacad" />

   PIng lewat CMD

   <img width="598" height="195" alt="Screenshot 2026-06-27 095902" src="https://github.com/user-attachments/assets/59533ca6-8985-410d-b5eb-913aef681295" />

   Ping lewat Mikrotik

<br>

<h1> Koneksikan Mikrotik ke Internet Static (manual) </h1>

<img width="400" height="323" alt="Screenshot 2026-06-27 103450" src="https://github.com/user-attachments/assets/c55bef48-7677-4009-add6-515b7ad81f3e" />

<br>

Sebelum mencoba topologi di atas, saya harap teman-teman reset konfigurasi mikrotik teman-teman menjadi blank configuration, setelah itu remote kembali mikrotik teman-teman menggunakan WinBox dan ingat kembali catatan tadi yang telah di tulis

<img width="531" height="353" alt="Screenshot 2026-06-27 092110" src="https://github.com/user-attachments/assets/dd2b5b7c-40ee-4616-b484-52c41047d2bd" />

1. Setting ip address

   -Masuk ke Ip >> Address

   -Klik (+) masukan ip yang telah teman-teman catat, ip saya 192.168.0.109/24, lalu pilih interfacenya sesuai topologi yakni ether2, klik apply lalu Ok

   <img width="376" height="372" alt="Screenshot 2026-06-27 104554" src="https://github.com/user-attachments/assets/b3ecc53c-0c26-46f0-af2b-934490af2fd8" />

2. Setting Ip Gateway (UNTUK LAPTOP KITA)

   -Masuk ke Ip >> Address

   -Klik (+) masukan ipnya 192.168.10.1/24, pilih interfacenyanya sesuai topologi yakni ether1, klik apply lalu Ok

   <img width="360" height="373" alt="Screenshot 2026-06-27 104954" src="https://github.com/user-attachments/assets/c07f2249-101c-4d0b-903a-65eed0ea935f" />

3. Setting Ip Gateway (UNTUK MIKROTIK)

   -Klik Ip >> Routes Klik tanda (+)

      -masukan dst address: 0.0.0.0/0

      kenapa harus 0.0.0.0/0? karna ini adalah default route yang berarti semua tujuan dari ip bisa di tuju menggunakan 0.0.0.0/0

      -masukan gatewaynya sesuai catatan yang teman-teman catat, punya saya 192.168.0.1

   <img width="703" height="303" alt="Screenshot 2026-06-27 105610" src="https://github.com/user-attachments/assets/da5148ea-105c-4010-a43f-667112870b7e" />

4. Setting DNS mikrotik teman

   -Klik Ip >> DNS

      -masukan Ip Serversnya 8.8.8.8 dan 8.8.4.4, jika teman-teman hanya bisa masukan 1 ip, bisa klik tanda seperti di foto

   <img width="457" height="248" alt="Screenshot 2026-06-27 110206" src="https://github.com/user-attachments/assets/71d2ca9a-4646-4f8d-8149-276338b45924" />

5. Setting Firewall NAT

   -Masuk ke Ip >> Firewall >> NAT, klik (+) chain:srcnat out-interfacenya:ether2

   <img width="513" height="329" alt="Screenshot 2026-06-27 112536" src="https://github.com/user-attachments/assets/54b102f0-1e3d-41df-b9f1-6c2e67da8ee4" />


   -Masuk bagian action:masquerade lalu aplly, Ok

   <img width="407" height="168" alt="Screenshot 2026-06-27 093229" src="https://github.com/user-attachments/assets/66b49562-bba7-4fe9-8714-b5d5ec43820f" />


6. Setting Kembali Ip Laptop kita di control panel

   -Setting sesuaikan dengan ip yang teman-teman pasang tadi, lalu klik Ok

   <img width="406" height="459" alt="Screenshot 2026-06-27 095150" src="https://github.com/user-attachments/assets/e1f1ee8b-5a69-4fe7-9a0c-7163791f86f7" />

7. Silahkan tes ping google.com lewat CMD atau Terminal Winbox

   <img width="545" height="270" alt="Screenshot 2026-06-27 110838" src="https://github.com/user-attachments/assets/d32e1bb8-26fa-4438-b2cb-5e034434cb6a" />

   Tes Ping google.com CMD

   <img width="542" height="118" alt="Screenshot 2026-06-27 111106" src="https://github.com/user-attachments/assets/5f413864-0c80-47c7-ac04-69a632b32365" />

   Tes Ping google.com Terminal WinBox


<hr>

Kesimpulan: Ini adalah cara untuk mengkoneksikan mikrotik teman-teman ke Internet, perhatikan kemabli apa saja yang di butuhkan untuk mengkoneksikan ke Internet, seperti Ip Gateway untuk laptop, Ip Gateway untuk mikrotik, DNS, dan ip default route yakni 0.0.0.0/0. Biasakan teman-teman membaca topologi dengan telilti

Akhir Kata

Wassalamualaikum Wr. Wb








   



   


