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


* Buka file config **www.super.franky.A10.com** di sites-available pada node Skypie

![image](https://user-images.githubusercontent.com/74232912/139309431-a2eb5cc5-5301-421e-80ea-9231eea33b3c.png)

![image](https://user-images.githubusercontent.com/74232912/139309513-2f35e81d-79a0-401d-87d1-a52e77d59123.png)


* Pada config ditambahkan

```
<Directory /var/www/jarkom2021.com/super.franky.a10.com/public/js>
           Options +Indexes
</Directory>

Alias "/js" "/var/www/super.franky.a10.com/public/js"
```

![h1](https://user-images.githubusercontent.com/74232912/139309619-ccd7f353-cd8a-4e6f-bd19-2d78bc37a6ed.png)


* Setelah itu di save dan jangan lupa ``` Service Apache2 Restart```


* Pada node client Loguetown dilakukan command lynx untuk melihat hasilnya

```lynx www.super.franky.A10.com/js```

![image](https://user-images.githubusercontent.com/74232912/139309069-33993e6d-e422-4c58-8a87-0f046ba834b9.png)

![image](https://user-images.githubusercontent.com/74232912/139309112-74703e99-4c69-45c9-8c9b-66445aafef76.png)


## Nomor 14
Pertanyaan: Dan Luffy meminta untuk web **www.general.mecha.franky.yyy.com** hanya bisa diakses dengan **port 15000** dan **port 15500**


* Buka file config **www.general.mecha.franky.A10.com** pada folder /sites-available/

``` nano /etc/apache2/sites-available/www.general.mecha.franky.yyy.com.conf```

![image](https://user-images.githubusercontent.com/74232912/139309786-c5f03650-1b55-4ad9-8427-f449b0a7897f.png)


* Kemudian, pada bagian atas yaitu bagian VirtualHost yang awalnya ```*:80``` diganti dengan ```*:15000 *:15500```

![image](https://user-images.githubusercontent.com/74232912/139309939-7dde0b53-6d9c-4494-8284-6f1cb0685520.png)


* Jangan lupa **Listen 15000** dan **Listen 15500 pada ports.conf**

```nano /etc/apache2/ports.conf```

![h2](https://user-images.githubusercontent.com/74232912/139310445-f6b113c7-17ea-4203-9e5d-457813dcb541.png)


* Setelah itu save dan jangan lupa untuk ``` service apache2 restart```


* Pada node client, buka command lynx

```lynx www.general.mecha.franky.yyy.com:15000```

![image](https://user-images.githubusercontent.com/74232912/139310549-5ba2fe1c-e073-4ca0-a16a-063cd389faab.png)


* atau

```lynx www.general.mecha.franky.yyy.com:15500```

![image](https://user-images.githubusercontent.com/74232912/139310593-706b4d28-b029-4147-af42-a51e0b030436.png)


* Maka akan keluar

![image](https://user-images.githubusercontent.com/74232912/139310733-6f679cef-3d6f-4ccb-ab8b-4a003242530a.png)


##### **Catatan : Jika pada akhir **www.general.mecha.franky.yyy.com** tidak diberi **:15000** atau **:15500** maka akan secara otomatis mengarah ke **www.franky.A10.com**

## Nomor 15
Pertanyaan: dengan authentikasi **username luffy** dan **password onepiece** dan file di **/var/www/general.mecha.franky.yyy**


* Pada file config **www.general.mecha.franky.A10.com** ditambahkan configurasi berikut

```
<Directory /var/www/general.mecha.franky.a10.com>
                AuthType Basic
                AuthName "Private"
                AuthUserFile /etc/apache2/.htpasswd
                Require valid-user
</Directory>
```

![h3](https://user-images.githubusercontent.com/74232912/139311445-7ebcc3b7-7e6b-4a58-af54-a0908d0c919b.png)


* Selanjutnya jangan lupa di save dan ```service apache2 restart```


* Kemudian lakukan command ini pada folder /etc/apache2/

```htpasswd -c /etc/apache2/ .htpasswd luffy``` --> Luffy disini sebagai Username


* Setelah mengetik enter, akan muncul untuk mengisi passwordnya dan Re-enter password

![image](https://user-images.githubusercontent.com/74232912/139312066-ce49ed51-154c-4c1c-9f3f-30631a750bed.png)


* Kemudian coba di client

```lynx www.general.mecha.franky.A10.com:15500```

![image](https://user-images.githubusercontent.com/74232912/139312205-48c4af1a-f6bd-4c5e-9a31-5d1b1cf7d67e.png)

![h4](https://user-images.githubusercontent.com/74232912/139312351-bd20459b-8f3b-4c3c-8de3-534e54c26509.png)

![h5](https://user-images.githubusercontent.com/74232912/139312523-eccbe71d-8ace-4ebe-89dc-654b62b2803e.png)


* Maka akan terbuka websitenya
 
![image](https://user-images.githubusercontent.com/74232912/139312618-48c7c9a0-c365-42c9-b252-d307094d7b4f.png)


## Nomor 16
Pertanyaan: Dan setiap kali mengakses IP Skypie akan diahlikan secara otomatis ke **www.franky.yyy.com**


* Masuk pada folder sites-available

``` cd /etc/apache2/sites-available```

![image](https://user-images.githubusercontent.com/74232912/139313133-513e0b6a-8050-49e5-82d5-96a9456b614e.png)


* kemudian buka file **000-default.conf**

![image](https://user-images.githubusercontent.com/74232912/139313303-2bfba272-9a7d-4ea2-a075-76cf8b9d0221.png)


* Kemudian ubahlah **DocumentRoot**-nya menjadi
 
![h6](https://user-images.githubusercontent.com/74232912/139313455-6985b620-d7f0-4258-bfda-c15883228954.png)


* Jangan lupa save dan ```service apache2 restart```


* Coba pada client untuk membuka IP Skypie, ```IP Skypie = 10.4.2.4```

```lynx 10.4.2.4```

![image](https://user-images.githubusercontent.com/74232912/139313659-13a54b6b-818e-4780-8b59-4e935c58e468.png)

![image](https://user-images.githubusercontent.com/74232912/139313678-1183d550-f09f-46d0-b9f5-392343e561da.png)


## Nomor 17
Pertanyaan: Dikarenakan Franky juga ingin mengajak temannya untuk dapat menghubunginya melalui website **www.super.franky.yyy.com**, dan dikarenakan pengunjung web server pasti akan bingung dengan randomnya images yang ada, maka Franky juga meminta untuk mengganti request gambar yang memiliki **substring “franky”** akan diarahkan menuju **franky.png**. Maka bantulah Luffy untuk membuat konfigurasi dns dan web server ini!



* Pada client Loguetown membuka website **www.super.franky.A10.com**

```lynx www.super.franky.A10.com```

![image](https://user-images.githubusercontent.com/74232912/139313915-d9c98043-7788-4112-8bb6-1c1789fc6f87.png)


* Kemudian, ketika sudah masuk kedalam website nya, buka folder public, setelah itu buka folder images

![image](https://user-images.githubusercontent.com/74232912/139314086-6e3b96c2-5771-4d5e-b443-200bb2eb2f12.png)

![image](https://user-images.githubusercontent.com/74232912/139314131-840d00ee-9503-4f67-a7da-12bece172a91.png)


* Kemudian pilih lah file gambar yang memiliki substring **"franky"** didalamnya, pada contoh ini saya menggunakan file **bukanfrankytapirandom.99689**

![image](https://user-images.githubusercontent.com/74232912/139314359-059e5c56-a59e-455c-8f27-b0620c7a0792.png)


* Nah maka yang akan keluar adalah file gambar **franky.png**

![image](https://user-images.githubusercontent.com/74232912/139314480-5485861b-0ffb-42d5-8627-5802e155f285.png)


* Jika yang dipilih bukan gambar yang mengandung substruing **"franky"** maka akan membuka file tersebut. Disini saya mengambil file **background-frank.jpg**

![image](https://user-images.githubusercontent.com/74232912/139314704-2449dc92-e847-4f90-8b72-e8013d11a238.png)


* Maka yang akan keluar adalah file **background-frank.jpg** itu sendiri

![image](https://user-images.githubusercontent.com/74232912/139314823-b2e6ddeb-e2e8-4311-a26d-080e31897225.png)


## Kendala
