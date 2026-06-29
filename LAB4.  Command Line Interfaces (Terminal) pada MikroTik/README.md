# LAB4.  Command Line Interfaces (Terminal) pada MikroTik

<img width="817" height="422" alt="image" src="https://github.com/user-attachments/assets/6fd46a45-9939-496b-927a-89ed022125e4" />

Assalamualaikum Wr. Wb

Kali ini saya akan menjelaskan CLI (Coman Line Interface) & sedikit mempraktikannya.

Kalian sering meremote mikrotik via WinBox? sudah tidak aneh dengan tampilannya bukan? tampilan pada WinBox teman-teman adalah GUi (Graphical User Interface) adalah metode dimana meremote mikrotik dengan tampilan grafik atau Kata saya mah "Jalur Mudah". Yang harus kalian tahu bahwa CLI ini digunakan untuk meremote device mikrotik untuk para sepuh atau tingkat lanjut/advanced, karna basic meremotenya hanya dengan teks. Tetapi jangan khawatir di sini saya akan membahas sedikit tentang CLi

<h1> Yang harus kalian Tahu</h1>

Struktur perintah (command) pada CLI mirip dengan sistem direktori menu pada WinBox

-Contoh: Cara menambahkan IP

/ip address add address=192.168.10.1/24 interface=ether2

/ip >> adalah (folder utama), address >> adalah (folder di dalam folder utama), add >> command menambahkan rule

Pusing?? hehehe bentar ini baru teori mari kita praktek

<img width="542" height="352" alt="general comand" src="https://github.com/user-attachments/assets/e3ef57d3-5542-41f7-a57d-59f54336696b" />


<img width="594" height="336" alt="WhatsApp Image 2026-06-26 at 13 52 52" src="https://github.com/user-attachments/assets/46646ae4-a261-4984-a3bb-35b2d033fb6a" /> 

Tips:

-[TAB] untuk melengkapi perintah tertentu

  contoh: /system shut[TAB] = /system shutdown

-Bisa juga menggunakan singkatan 

  contoh: /sys shut        = /system shutdown


<h1> Praktek Cli </h1>

1. Remote terlebih dahulu meggunakan WinBox

2. Klik Bagian Terminal sampai tampilan seperti ini:

   <img width="605" height="406" alt="Screenshot 2026-06-26 140257" src="https://github.com/user-attachments/assets/610c1576-84b1-4618-b3a6-d63afdbff0b3" />

3. klik n (enter), (enter lagi), klik ctrl + c,

4. Masukan User & Password

5. Selamat masuk tampilan CLI

   <h2> Cara Menambahkan IP </h2>

   menambahkan ip: 192.168.10.1/24 di interface:ether 1

   1. ketikan /ip/address add address=192.168.10.1/24 interface=ether1
  
   2. Klik (enter)
  
      <img width="541" height="58" alt="Screenshot 2026-06-26 141427" src="https://github.com/user-attachments/assets/9b395d6c-72a0-46b7-a8d4-30d154ae1d2f" />

  
   3. Tanda kalau sukses tidak adanya tulisan invalid seperti ini:
  
      <img width="535" height="37" alt="Screenshot 2026-06-26 141534" src="https://github.com/user-attachments/assets/b5a67334-e05c-41cb-b9dc-077494c7f4b6" />


    <h2> Cara Cek IP Address</h2>

    cek ip yang sudah kita tambahkan tadi

    1. ketikan /ip/address/print

    2. Klik (enter)

     <img width="288" height="39" alt="Screenshot 2026-06-26 141757" src="https://github.com/user-attachments/assets/1306de0c-0057-450f-a1f6-94bb3ae4b18a" />

    3. Tanda kalau sukses tidak adanya tulisan invalid seperti ini:

     <img width="325" height="96" alt="Screenshot 2026-06-26 141812" src="https://github.com/user-attachments/assets/9ca59325-b4ee-4e9a-a676-483f69744d3d" />

     <h2> Cara Menganti Identity </h2>

     1. Ketikan /system/identity/set name=nama-teman-teman
  
     2. Klik (enter)
  
        <img width="388" height="39" alt="Screenshot 2026-06-26 143424" src="https://github.com/user-attachments/assets/1aabcdf4-9e0d-4a95-9ba2-fd8bc7e04c21" />
     
     3. Tanda kalau sukses rubahnya mikrotik menjadi nama teman-teman:
  
        <img width="384" height="50" alt="Screenshot 2026-06-26 143445" src="https://github.com/user-attachments/assets/7162f4c8-42f8-4657-968a-37329dbce307" />

   <h2> Cara Menambahkan Paswword Pada User Admin </h2>

     1. ketikan /password
  
     2. klik (enter)
  
        <img width="214" height="125" alt="Screenshot 2026-06-26 144127" src="https://github.com/user-attachments/assets/992b9ddf-ac2a-42b0-af29-042b9549db93" />

     3. -Masukan password lama= (kosongkan)

        -Masukan password baru= 123

        -Masukan ulang password baru=123

     4. Sekarang teman-teman login menggunakan admin & Password baru

   <h2> Cara Menambahkan User Baru, Password & Group Full</h2>

     1. Ketikan /user/add name=nama_teman-teman group=full password=nama_teman-teman123
  
     2. Klik (enter)
  
      <img width="497" height="44" alt="Screenshot 2026-06-26 144746" src="https://github.com/user-attachments/assets/0cc4d7bc-ed4b-4e82-97b3-985fa6a18b4a" />

      <h2> Cara Cek User </h2>

      1. Ketikan /user/print
  
      2. Klik (enter)
  
         <img width="392" height="124" alt="Screenshot 2026-06-26 144912" src="https://github.com/user-attachments/assets/aeaed979-d295-452c-a860-508139624e34" />

     <h2> Cara Menambahkan Firewall NAT</h2>

     1. Ketikan /ip/firewall/nat/add chain=srcnat out-interface=ether1 action=masquerade
  
     2. klik (enter)
  
     3. Tanda kalau sukses tidak adanya tulisan invalid:
  
        <img width="580" height="67" alt="Screenshot 2026-06-26 150443" src="https://github.com/user-attachments/assets/62690132-ebcf-4fff-b9f4-622c3ecd141e" />

     <h2> Cara Cek Firewall NAT</h2>

     1. ketikan /ip/firewall/nat/print
  
     2. Klik (enter)
  
     3. Tanda kalau berhasil tidak adanya tuiisan invalid:

        <img width="436" height="82" alt="Screenshot 2026-06-26 150627" src="https://github.com/user-attachments/assets/4354555e-564c-4ca3-b345-d1cc6c6a32d6" />


     <h2> Cara Menambahkan IP Gateway </h2>

     1. Ketikan /ip/route/add gateway=192.168.1.1
  
     2. Klik (enter)
  
     3. Tanda kalau berhasil tidak adanya tulisan invalid:
  
        <img width="372" height="48" alt="Screenshot 2026-06-26 151007" src="https://github.com/user-attachments/assets/36d99669-aad2-408c-a667-2f1033a5cf9d" />

     <h2> Cara Cek Ip Gateway</h2>

     1. Ketikan /ip/route/print
  
     2. klik (enter)
  
     3. Tanda kalau berhasil tidak adanya tulisan invalid:\
  
        <img width="507" height="128" alt="Screenshot 2026-06-26 151104" src="https://github.com/user-attachments/assets/d3f04206-44dc-44f0-8504-709f153b250e" />

     <h2> Menambahkan DNS & Melihat DNS </h2>

     1. ketikan /ip/dns/set servers= 8.8.8.8 allow-remote-requests=yes (untuk menambahkan DNS 8.8.8.8)
  
     2. Ketikan /ip/dns/print (untuk cek DNS)
  
        <img width="505" height="368" alt="Screenshot 2026-06-26 151849" src="https://github.com/user-attachments/assets/c7a4bbf2-b2c0-4626-aef4-ab67894095f8" />


     <h2> Fungsi Double [TAB] </h2>

     <img width="549" height="290" alt="Screenshot 2026-06-26 152130" src="https://github.com/user-attachments/assets/fe5f5574-a3af-4a3f-a8a5-79e488c5590a" />

     <hr>

Kesimpulan: Mode CLI ini digunakan oleh para sepuh/advanced/expert untuk meremote mikrotik dengan berbasis teks, kenapa masih beruguna? karena menurut orang mode CLI cukup simple dan enak dilihat, karna bentuknya yang sederhana. Juga bisa meremote jarak jauh dengan ringan karna basicnya adalah teks.

Tips: Pastikan teman-teman menggunakan [TAB] untuk membantu mengkoreksi tulisan dan mempermudah, double [TAB] untuk mengetahui comand selanjutnya atau ketika teman-teman lupa akan comamnd selanjutnya

Akhir Kata

Wassalamualaikum Wr.Wb



        




     

     



