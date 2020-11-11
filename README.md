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

  
 2. Membuat alias www.semerue07.pw
 
   a.) Nano /etc/bind/jarkom/semerue07.pw

   ![Screenshot (496)](https://user-images.githubusercontent.com/58022238/98761287-b251ac00-2407-11eb-8493-430b5ecb3fc8.png)</br>
   b.)Service bind9 restart</br>
   c.)Cek ping lewat client</br>
   ![2c](https://user-images.githubusercontent.com/56763570/98809428-60426380-23d2-11eb-895d-000270af912f.png)</br>
   
 3. Membuat sub domain www.penanjakan.semerue07.pw</br>
   a.)Nano /etc/bind/jarkom/semerue07.pw </br>
   ![3a](https://user-images.githubusercontent.com/56763570/98809718-e3fc5000-23d2-11eb-8a95-8add45a6fb94.png)</br>
   b.)Service bind9 restart</br>
   c.)Test ping penanjakan.semerue07.pw</br>
   ![3c](https://user-images.githubusercontent.com/56763570/98809734-eced2180-23d2-11eb-85ad-fcd4de62b934.png)</br>
   
4. Membuat reverse domain untuk domain utama</br>
   a.)Nano /etc/bind/named.conf.local</br>
   ![4a](https://user-images.githubusercontent.com/56763570/98810453-22463f00-23d4-11eb-8617-1d4b982af0d2.png)</br>
   b.)cp /etc/bind/db.local /etc/bind/jarkom/71.151.10.in-addr.arpa lalu edit</br>
   ![4b](https://user-images.githubusercontent.com/56763570/98810477-2b371080-23d4-11eb-98f0-219f1868b849.png)</br>
   c.)Service bind9 restart</br>
   d.)Test memakai host -t PTR 10.151.71.68 di client</br>
   ![4d](https://user-images.githubusercontent.com/56763570/98810633-5cafdc00-23d4-11eb-8cfb-043665ff4126.png)</br>
   
5. Membuat dns server-slave  pada malang-mojokerto</br>
   a.)Konfigurasikan server MALANG DAN MOJOKERTO nano /etc/bind/named.conf.local</br>
      i. Malang</br>
      ![5a i](https://user-images.githubusercontent.com/56763570/98810832-a4366800-23d4-11eb-89a2-0724d4b37ac9.png)</br>
      ii. Mojokerto</br>
      ![5a ii](https://user-images.githubusercontent.com/56763570/98810965-e495e600-23d4-11eb-8b1e-2fc0f260311a.png)</br>
   b.)service bind9 restart</br>
   c.)Testing di client</br>
   ![5c](https://user-images.githubusercontent.com/56763570/98811204-4c4c3100-23d5-11eb-89b9-0e1bc8b400a0.png)</br>
   
6. Buat subdomain dengan alamat http://gunung.semerue07.pw yang didelegasikan pada server MOJOKERTO dan mengarah ke IP Server PROBOLINGGO. </br>
   a.)Konfigurasi MALANG nano /etc/bind/jarkom/semerue07.pw</br>
   ![6a 1](https://user-images.githubusercontent.com/56763570/98811531-dbf1df80-23d5-11eb-943d-c72b18fe3ced.png)</br>
   ![6a 2](https://user-images.githubusercontent.com/56763570/98811545-de543980-23d5-11eb-86a8-4ee055a5781a.png)</br>
   ![6a 3](https://user-images.githubusercontent.com/56763570/98811551-e01dfd00-23d5-11eb-9a55-03d0c96b204c.png)</br>
   ![6a 4](https://user-images.githubusercontent.com/56763570/98811556-e2805700-23d5-11eb-9871-757b81bf17a8.png)</br>
   ![6a 5](https://user-images.githubusercontent.com/56763570/98811562-e44a1a80-23d5-11eb-819c-f6886e117093.png)</br>
   
7. Buat subdomain dengan nama http://naik.gunung.semerue07.pw, domain ini diarahkan ke IP Server PROBOLINGGO.</br>
   ![7 1](https://user-images.githubusercontent.com/56763570/98812198-e82a6c80-23d6-11eb-9962-feab3e170091.png)</br>
   ![7 2](https://user-images.githubusercontent.com/56763570/98812183-df399b00-23d6-11eb-8fcd-7ea77d32a1ba.png)</br>
   
8. Domain http://semeruyyy.pw memiliki DocumentRoot pada /var/www/semeruyyy.pw.</br>
   a.)Install php</br>
   b.)Install apache2</br>
   c.)Cp 000-default.conf menjadi semerue07.pw.conf dan konfigurasikan seperti ini</br>
   ![8c](https://user-images.githubusercontent.com/56763570/98812639-b49c1200-23d7-11eb-9058-a6af17c48ada.png)</br>
   d.)wget 10.151.36.202/semeru.pw.zip pada /var/www/, unzip</br>
   e.)A2ensite semerue07.pw dan service apache2 restart</br>
   f.)Coba akses melalui browser</br>
   ![8f](https://user-images.githubusercontent.com/56763570/98812665-bcf44d00-23d7-11eb-8511-19719849a741.png)</br>
   
9. diaktifkan mod rewrite agar urlnya menjadi http://semeruyyy.pw/home.]</br>
   ![9 1](https://user-images.githubusercontent.com/56763570/98812873-27a58880-23d8-11eb-80ea-5a3b4c22339f.png)</br>
   ![9 2](https://user-images.githubusercontent.com/56763570/98812875-28d6b580-23d8-11eb-8c89-7e2abd666a84.png)</br>
   ![9 3](https://user-images.githubusercontent.com/56763570/98812881-2a07e280-23d8-11eb-8996-beb940776181.png)</br>
   .htaccess di var www semeru</br>







   
   
   




  
