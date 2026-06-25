# LAB.1 Logging in Mikrotik

<img width="817" height="422" alt="image" src="https://github.com/user-attachments/assets/b24835fe-460a-463f-9c41-82d11c6c33dd" />

<br>
<br>
<br>

 Assalamualikum Wr. Wb.
 Di sini saya akan membagikan cara-cara untuk meremote/logging ke mikrotik, ada banyak caranya & perhatikan juga dengan port-portnya. sebelum itu hubungkan mikrotik dengan kabel misalnya kabel Rj45, seperti di topologi atas


 
 1.	Winbox
   <img width="117" height="114" alt="image" src="https://github.com/user-attachments/assets/27a2878b-92e2-4e8a-b542-a43eda14b4b8" />

  Aplikasi paling sering digunakan dengan **port 8291 TCP** 
  
  a. Unduh aplikasi winbox https://mikrotik.com/download/winbox atau di file yang saya upload
  
  b.	Install lalu klik bagian neighbors, lalu refresh
  
  c.	Setelah muncul , saya sarankan pilih Mac address, MAc address = 08:00:27:3A:83:01
  <img width="670" height="565" alt="Screenshot 2026-06-25 194921" src="https://github.com/user-attachments/assets/3b748594-e071-4fdb-aa86-f9e9c15ac9b2" />

  d.	Login: admin
  
     Password: (kosong)
  e.	Klik Connect
  
  <img width="1366" height="768" alt="Screenshot 2026-06-25 195131" src="https://github.com/user-attachments/assets/5ec66e56-ba79-4c0d-8530-e4fae9b8975b" />
  
 Ini adalah tampilan dari winbox
 
 Mudah bukan?

 <br>
 <br>
 <br>
 


2.	WebFig
   <img width="86" height="127" alt="image" src="https://github.com/user-attachments/assets/2c78c6fb-8b8b-4614-9f19-85cde80b6a51" />

webfig berada di **port 80 TCP** dan bisa di akses menggunakan browser, saya contohkan dengan chrome
NOTE: Pastikan mikrotik berada di default configuration

   a.	Buka chrome
   <img width="86" height="127" alt="image" src="https://github.com/user-attachments/assets/544e8cb4-5f5b-4064-9880-c02df824f35a" />

   b.	Pada pencarian ketikan 192.168.88.1 (ip default mikrotik)
   c.	Login: admin
      Password: (kosong)
d.	Klik Login atau Tekan Enter
 

e.	Setelah berhasil login, maka akan muncul tampilan mikrotik dalam mode GUI pada web browser
 


3.	Telnet/SSH
   Ini berada di **port**
  	**-Telnet (23 TCP)**
  	   protokol lama yang sudah lama, jarangan digunakan karena alasan keamanannya yang kurang
  	**-SSH (22 TCP)**
  	   Yang paling di sarankan karna keamanannya lebih aman dibandingkan telnet

   a.	Buka putty
<img width="95" height="116" alt="image" src="https://github.com/user-attachments/assets/9f6a27f5-cf48-4302-9b74-2f1e82eb063c" />

 
b.	Klik Tab Telnet 
c.	Ketik IP Address: 192.168.88.1 (ip default mikrotik)
d.	Ketik Port: 23 (port default telnet)
e.	Klik Open atau Tekan Enter
 

f.	Login: admin
Password:
Tekan Enter
 

g.	Setelah berhasil login, maka akan muncul tampilan mikrotik dalam mode CLI
 


4.	SSH
Cara keempat menggunakan SSH pada  aplikasi putty, berikut ini langkah nya
a.	Buka putty
 
b.	Klik Tab SSH 
c.	Ketik IP Address: 192.168.88.1 (ip default mikrotik)
d.	Ketik Port: 23 (port default telnet)
e.	Klik Open atau Tekan Enter
 

f.	Login: admin
Tekan Enter  

g.	Setelah berhasil login, maka akan muncul tampilan mikrotik dalam mode CLI
 


5.	FTP (filezilla)
Akses mikrotik via FTP (filezilla) bermanfaat untuk upload dan download file ke router mikrotik.
a.	Buka filezilla
 
b.	Isi Host: 192.168.88.1 (ip default mikrotik)
c.	Login: admin
d.	Password:
e.	Ketik Port: 21 (port default ftp)
f.	Klik Quickconnect
 

g.	Setelah berhasil login, maka akan muncul tampilan mikrotik dalam mode CLI
 

6.	Console
Akses mikrotik via console belum penulis lab kan, sambil menanti perangkat mikrotik yang ada port console nya.

7.	Tik App
Akses mikrotik via console belum penulis lab kan, sambil menanti perangkat smartphone android, karena Tik App yang rilis 2015 baru support OS Android.


Buat  kesimpulan : 

Ada 7 cara koneksi / akses/ remote / logging in ke dalam mikrotik, dengan berbagai manfaat dan karakteristik yang berbeda,
Hal ini sangat memudahkan admin untuk mengakses mikrotik, dengan pilihan yang bervariasi.
Kita dapat memilih akses mikrotik sesuaikan dengan kebutuhan.
