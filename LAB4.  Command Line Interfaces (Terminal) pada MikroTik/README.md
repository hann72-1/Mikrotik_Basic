# LAB4.  Command Line Interfaces (Terminal) pada MikroTik

<img width="817" height="422" alt="image" src="https://github.com/user-attachments/assets/6fd46a45-9939-496b-927a-89ed022125e4" />

Assalamualaikum Wr. Wb

Kali ini saya akan menjelaskan CLI (Coman Line Interface) & sedikit mempraktikannya.

Kalian sering meremote mikrotik via WinBox? sudah tidak aneh dengan tampilannya bukan? tampilan pada WinBox teman-teman adalah GUi (Graphical User Interface) adalah metode dimana meremote mikrotik dengan tampilan grafik atau Kata saya mah "Jalur Mudah". Yang harus kalian tahu bahwa CLI ini digunakan untuk meremote device mikrotik untuk para sepuh atau tingkat lanjut/advanced, karna basic meremotenya hanya dengan teks. Tetapi jangan khawatir di sini saya akan membahas sedikit tentang CLi

<h1> Yang harus kalian Tahu</h1>

Struktur perintah (command) pada CLI mirip dengan sistem direktori menu pada WinBox

-Contoh: Cara menambahkan IP

/ip address add address=192.168.10.1/24 interface=ether22

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

   <h2> Cara menambahkan IP </h2>

   menambahkan ip: 192.168.10.1/24 di interface:ether 1

   1. ketikan /ip/address add address=192.168.10.1/24 interface=ether1
  
   2. Klik (enter)
  
      <img width="541" height="58" alt="Screenshot 2026-06-26 141427" src="https://github.com/user-attachments/assets/9b395d6c-72a0-46b7-a8d4-30d154ae1d2f" />

  
   3. Tanda kalau sukses tidak adanya tulisan invalid seperti ini:
  
      <img width="535" height="37" alt="Screenshot 2026-06-26 141534" src="https://github.com/user-attachments/assets/b5a67334-e05c-41cb-b9dc-077494c7f4b6" />


    <h2> Cara cek IP Address</h2>

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

   <h2> Cara Menambahkan paswword pada user admin </h2>

  
        

     

     



