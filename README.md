# Jarkom-Modul-2-A10-2021

## Nomor 1
Pertanyaan: Semua node terhubung pada router Foosha, sehingga dapat mengakses internet

## Nomor 2
Pertanyaan: Luffy ingin menghubungi Franky yang berada di EniesLobby dengan denden mushi. Kalian diminta Luffy untuk membuat website utama dengan mengakses **franky.yyy.com** dengan alias **www.franky.yyy.com** pada folder **kaizoku**

## Nomor 3
Pertanyaan: Setelah itu buat subdomain **super.franky.yyy.com** dengan alias **www.super.franky.yyy.com** yang diatur DNS nya di EniesLobby dan mengarah ke Skypie

## Nomor 4
Pertanyaan: Buat juga reverse domain untuk domain utama

## Nomor 5
Pertanyaan: Supaya tetap bisa menghubungi Franky jika server EniesLobby rusak, maka buat Water7 sebagai DNS Slave untuk domain utama

## Nomor 6
Pertanyaan: Setelah itu terdapat subdomain **mecha.franky.yyy.com** dengan alias **www.mecha.franky.yyy.com** yang didelegasikan dari EniesLobby ke Water7 dengan IP menuju ke Skypie dalam folder **sunnygo**

## Nomor 7
Pertanyaan: Untuk memperlancar komunikasi Luffy dan rekannya, dibuatkan subdomain melalui Water7 dengan nama **general.mecha.franky.yyy.com** dengan alias **www.general.mecha.franky.yyy.com** yang mengarah ke Skypie

## Nomor 8
Pertanyaan: Setelah melakukan konfigurasi server, maka dilakukan konfigurasi Webserver. Pertama dengan webserver **www.franky.yyy.com**. Pertama, luffy membutuhkan webserver dengan DocumentRoot pada **/var/www/franky.yyy.com**.

* Pindah ke direktori /var/www. File zip franky akan diletakkan di direktori ini  
  ```cd /var/www```
* Download file zip franky  
  ```wget https://github.com/FeinardSlim/Praktikum-Modul-2-Jarkom/raw/main/franky.zip```  
* Unzip file franky  
  ```unzip franky.zip```  
* Pindah ke direktori sites-available  
  ```cd /etc/apache2/sites-available```  
* Copy 000-default.conf ke www.franky.A10.com.conf  
  ```cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/www.franky.A10.com.conf```  
* Buka file config www.franky.A10.com.conf  
  ```nano /etc/apache2/sites-available/www.franky.A10.com.conf```  
* Ubah DocumentRoot nya ke /var/www/franky.a10.com  
  ```
     ServerName franky.A10.com
     ServerAlias www.franky.A10.com
     ServerAdmin webmaster@localhost
     DocumentRoot /var/www/franky.a10.com
     ```
     ![configno8](https://imgur.com/JsaWo4O.png)
* Aktifkan config website yang telah dibuat  
  ```a2ensite www.franky.A10.com.conf```  
* Restart apache  
  ```service apache2 restart```  
* Buat direktori franky.a10.com  
  ```mkdir /var/www/franky.a10.com```  
* Copy file unzip franky ke direktori yang baru dibuat  
  ```cp -RT /var/www/franky /var/www/franky.a10.com```  
* Akses franky.A10.com  
  ```lynx franky.A10.com```  
  ![lynx8]()


## Nomor 9
Pertanyaan: Setelah itu, Luffy juga membutuhkan agar url **www.franky.yyy.com/index.php/home** dapat menjadi menjadi **www.franky.yyy.com/home**.  

* Pindah ke direktori sites-available  
  ```cd /etc/apache2/sites-available```  
* Buka file config www.franky.A10.com.conf  
  ```nano /etc/apache2/sites-available/www.franky.A10.com.conf```  
* Tambahkan alias  
  ```
  <Directory /var/www/franky.a10.com/index.php/home>
          Options +Indexes
  </Directory>
  Alias "/home" "/var/www/franky.a10.com/index.php/home"
  ```
  ![configno9]()
* Restart apache  
  ```service apache2 restart```  
* Akses franky.A10.com/home  
  ```lynx franky.A10.com/home```  
  ![lynx9]()


## Nomor 10
Pertanyaan: Setelah itu, pada subdomain **www.super.franky.yyy.com**, Luffy membutuhkan penyimpanan aset yang memiliki DocumentRoot pada **/var/www/super.franky.yyy.com**

* Pindah ke direktori /var/www. File zip super.franky akan diletakkan di direktori ini  
  ```cd /var/www```
* Download file zip super.franky  
  ```wget https://github.com/FeinardSlim/Praktikum-Modul-2-Jarkom/raw/main/super.franky.zip```  
* Unzip file super.franky  
  ```unzip super.franky.zip```  
* Pindah ke direktori sites-available  
  ```cd /etc/apache2/sites-available```  
* Copy 000-default.conf ke www.super.franky.A10.com.conf  
  ```cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/www.super.franky.A10.com.conf```  
* Buka file config www.super.franky.A10.com.conf  
  ```nano /etc/apache2/sites-available/www.super.franky.A10.com.conf```  
* Ubah DocumentRoot nya ke /var/www/super.franky.a10.com  
  ```
     ServerName super.franky.A10.com
     ServerAlias www.super.franky.A10.com
     ServerAdmin webmaster@localhost
     DocumentRoot /var/www/super.franky.a10.com
     ```
     ![configno10]()
* Aktifkan config website yang telah dibuat  
  ```a2ensite www.super.franky.A10.com.conf```  
* Restart apache  
  ```service apache2 restart```  
* Buat direktori super.franky.a10.com  
  ```mkdir /var/www/super.franky.a10.com```  
* Copy file unzip super.franky ke direktori yang baru dibuat  
  ```cp -RT /var/www/super.franky /var/www/super.franky.a10.com```  
* Akses super.franky.A10.com  
  ```lynx super.franky.A10.com```  
  ![lynx10]()


## Nomor 11
Pertanyaan: Akan tetapi, pada folder **/public**, Luffy ingin hanya dapat melakukan directory listing saja

* Pindah ke direktori sites-available  
  ```cd /etc/apache2/sites-available```  
* Buka file config www.super.franky.A10.com.conf  
  ```nano /etc/apache2/sites-available/www.super.franky.A10.com.conf```  
* Tambahkan options +indexes pada folder public  
  ```
  <Directory /var/www/super.franky.a10.com/public>
          Options +Indexes
  </Directory>
  ```
  ![configno11]()
* Restart apache  
  ```service apache2 restart```  
* Akses super.franky.A10.com/public  
  ```lynx super.franky.A10.com/public```  
  ![lynx11]()


## Nomor 12
Pertanyaan: Tidak hanya itu, Luffy juga menyiapkan **error file 404.html** pada folder /errors untuk mengganti error kode pada apache

* Pindah ke direktori sites-available  
  ```cd /etc/apache2/sites-available```  
* Buka file config www.super.franky.A10.com.conf  
  ```nano /etc/apache2/sites-available/www.super.franky.A10.com.conf```  
* Tambahkan error document
  ```
  ErrorDocument 404 /error/404.html
  ```
  ![configno12]()
* Restart apache  
  ```service apache2 restart```  
* Akses super.franky.A10.com/publikkk  
  ```lynx super.franky.A10.com/publikkk```  
  ![lynx11]()


## Nomor 13
Pertanyaan: Luffy juga meminta Nami untuk dibuatkan konfigurasi virtual host. Virtual host ini bertujuan untuk dapat mengakses file asset **www.super.franky.yyy.com/public/js** menjadi **www.super.franky.yyy.com/js**

## Nomor 14
Pertanyaan: Dan Luffy meminta untuk web **www.general.mecha.franky.yyy.com** hanya bisa diakses dengan **port 15000** dan **port 15500**

## Nomor 15
Pertanyaan: dengan authentikasi **username luffy** dan **password onepiece** dan file di **/var/www/general.mecha.franky.yyy**

## Nomor 16
Pertanyaan: Dan setiap kali mengakses IP Skypie akan diahlikan secara otomatis ke **www.franky.yyy.com**

## Nomor 17
Pertanyaan: Dikarenakan Franky juga ingin mengajak temannya untuk dapat menghubunginya melalui website **www.super.franky.yyy.com**, dan dikarenakan pengunjung web server pasti akan bingung dengan randomnya images yang ada, maka Franky juga meminta untuk mengganti request gambar yang memiliki **substring “franky”** akan diarahkan menuju **franky.png**. Maka bantulah Luffy untuk membuat konfigurasi dns dan web server ini!


## Kendala
