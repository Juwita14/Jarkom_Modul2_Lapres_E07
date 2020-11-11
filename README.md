# Jarkom_Modul2_Lapres_E07
Anggota Kelompok E07:

Juwita Kartika Rani		05111840000051</br>
Muhammad Rafi Yudhistira    05111840000115</br> 
Siti Munawaroh  		 05111840007004</br>


1. Men-setting alamat utama web semerue07.pw

   a.) Install bind9 di UML MALANG
   
   b.)Setting /etc/bind/named.conf.local

![Screenshot (491)](https://user-images.githubusercontent.com/58022238/98759829-7701ae00-2404-11eb-9d40-4e6aff875fe8.png)

  c.) Mkdir etc/bind/jarkom
  
  d.) cp /etc/bind/db.local /etc/bind/jarkom/semerue07.pw
  
  e.) Edit file semerue07.pw
  </br>![1 e](https://user-images.githubusercontent.com/56763570/98809113-edd18380-23d1-11eb-8af6-b85fd083a66c.png)</br>
  
  f.) Service bind9 restart
  g.) Setting pada client nano /etc/resolve.conf masukkan ip malang, coba ping
  
   ![Screenshot (495)](https://user-images.githubusercontent.com/58022238/98761276-ac5bcb00-2407-11eb-8338-889d5f03e8f0.png)

  
 2. embuat alias www.semerue07.pw
 
   a.) Nano /etc/bind/jarkom/semerue07.pw

![Screenshot (496)](https://user-images.githubusercontent.com/58022238/98761287-b251ac00-2407-11eb-8493-430b5ecb3fc8.png)
   b.)Service bind9 restart
   c.)Cek ping lewat client


  
