# Jarkom_Modul2_Lapres_C03

- Brananda Denta WP - 05111840000143
- R. Dafa Berlian Denmar - 05111840000149

## Outline

+ [Soal 1](#soal-1)
+ [Soal 2](#soal-2)
+ [Soal 3](#soal-3)
+ [Soal 4](#soal-4)
+ [Soal 5](#soal-5)
+ [Soal 6](#soal-6)
+ [Soal 7](#soal-7)
+ [Soal 8](#soal-8)
+ [Soal 9](#soal-9)
+ [Soal 10](#soal-10)
+ [Soal 11](#soal-11)
+ [Soal 12](#soal-12)
+ [Soal 13](#soal-13)
+ [Soal 14](#soal-14)
+ [Soal 15](#soal-15)
+ [Soal 16](#soal-16)
+ [Soal 17](#soal-17)

## Soal 1

### Langkah Pengerjaan

- Install bind9 pada UML Malang
- Setting /etc/bind/named.conf.local seperti dibawah ini

### Screenshot

![no 1](/img/namedConfLocalMalang.jpg)

- mkdir /etc/bind/semeru
- copy file db.local menjadi semeruc03.pw 

```sh
cp /etc/bind/db.local /etc/bind/semeru/semeruc03.pw
```

- edit file semeruc03.pw

### Screenshot

![no 1](/img/semeruc03.pw.jpg)

- `service bind9 restart` pada UML Malang
- setting pada client ***GRESIK*** dengan perintah

```sh
nano /etc/resolve.conf
```

- masukkan ip malang, dan coba ping

### Screenshot

![no 1](/img/resolvGresik.jpg)
![no 1](/img/pingSemeru.jpg)


## Soal 2
### Langkah Pengerjaan

- jalankan perintah `nano /etc/bind/semeru/semeruc03.pw` pada UML Malang dan ditambahkan beberapa konfigurasi dibawah

### Screenshot

![no 2](/img/semeruc03.pw.jpg)

- service bind9 restart pada UML Malang
- lalu cek ping pada UML Client

### Screenshot

![no 2](/img/wwwsemeru.jpg)

## Soal 3

### Langkah Pengerjaan

- Jalankan perintah `nano /etc/bind/semeru/semeruc03.pw` dan setting seperti dibawah

### Screenshot
![no 3](/img/semeruc03.pw.jpg)

- Jalankan perintah `service bind9 restart` pada UML Malang
- tes ping penanjakan.semeruc03.pw pada UML client

### Screenshot
![no 3](/img/pingpenanjakan.jpg)

## Soal 4

### Langkah Pengerjaan

- Edit file **/etc/bind/named.conf.local** pada *MALANG* dan tambahkan konfigurasi untuk zone 77.151.10.in-addr.arpa.

### Screenshot
![no 4](/img/namedConfLocalMalang.jpg)

- lalu copy file db.local dengan perintah `cp /etc/bind/db.local /etc/bind/semeru/77.151.10.in-addr.arpa` lalu kita edit seperti dibawah

### Screenshot
![no 4](/img/77.jpg)

- restart bind9 pada *MALANG*

```sh
service bind9 restart
```

- tes pada UML client host -t PTR 10.151.77.34

### Screenshot
![no 4](/img/host-TGresik.jpg)

## Soal 5
### Langkah Pengerjaan

- Setting pada UML MALANG, Edit file `/etc/bind/named.conf.local` dan tambahkan type, notify, dan also-notify seperti gambar berikut

### Screenshot

![no 5](/img/namedConfLocalMalang.jpg)

- Lakukan restart bind9

```sh
service bind9 restart
```

- Pada UML MOJOKERTO, lakukan update dan install bind9

```sh
apt-get update
apt-get install bind9 -y
```

- lalu ubah file **/etc/bind/named.conf.local** seperti dibawah

### Screenshot

![no 5.1](/img/namedConfLocalMojo.jpg)

- Lakukan restart bind9

```sh
service bind9 restart
```

- Untuk testing, Pada server MALANG silahkan matikan service bind9

```sh
service bind9 stop
```

- Pada client GRESIK pastikan pengaturan nameserver mengarah ke IP MALANG dan IP MOJOKERTO

### Screenshot

![no 5](/img/resolvGresik.jpg)

- tes ping pada UML Client (GRESIK)
### Screenshot

![no 5](/img/pingSemeru.jpg)

## Soal 6

### Langkah Pengerjaan

- Setting pada UML Malang pada file /etc/bind/semeru/semeruc03.pw, tambahkan subdomain gunung

### Screenshot
![no 6](/img/semeruc03.pw.jpg)

- Kemudian edit file /etc/bind/named.conf.local menjadi seperti gambar di bawah:

### Screenshot

![no 6.1](/img/namedConfLocalMalang.jpg)

- Restart service bind

```sh
service bind9 restart
```

- Setting pada UML Mojokerto pada file /etc/bind/named.conf.local

### Screenshot
![no 6](/img/namedConfLocalMojo.jpg)

- Kemudian buat direktori dengan nama delegasi

- Copy db.local ke direktori pucang dan edit namanya menjadi gunung.semeruc03.pw, lalu ubah menjadi seperti berikut.

### Screenshot
![no 6](/img/gunungSemeru.jpg)

- Restart service bind

```sh
service bind9 restart
```

- Untuk testing, ping gunung.semeruc03.pw pada UML client

### Screenshot
![no 6](/img/pingGunung.jpg)

## Soal 7
### Langkah Pengerjaan

- Buat subdomain naik.gunung.semeruc03.pw dengan mengatur file /etc/bind/delegasi/gunung.semeruc03.pw pada UML Mojokerto

### Screenshot
![no 7](/img/gunungSemeru.jpg)

- Restart service bind

```sh
service bind9 restart
```

- Cek ping naik.gunung.semeruc03.pw pada UML client

### Screenshot
![no 7.1](/img/pingNaik.jpg)

## Soal 8

### Langkah Pengerjaan

- Install php dan apache2
- copy file default menjadi semeruc03.pw.conf pada directory /etc/apache2/sites-available
- Tambahkan ServerAlias dan ServerName, serta atur DocumentRoot

### Screenshot
![no 8](/img/semeruConf.jpg)

- wget 10.151.36.202/semeru.pw.zip pada directory /var/www/ lalu di unzip dan rename menjadi semeruc03.pw
- a2ensite semeruc03.pw untuk enable site dan service apache2 restart
- akses website semeruc03.pw pada browser
### Screenshot
![no 8](/img/webUtama.jpg)

## Soal 9
### Langkah Pengerjaan

- Pindah ke directory /var/www/semeruc03.pw dan buat file .htaccess dengan isi file
### Screenshot

![no 9](/img/homehtaccess.jpg)

- Menjalankan perintah a2enmod rewrite untuk mengaktifkan module rewrite.

- Pindah ke directory /etc/apache2/sites-available kemudian buka file semeruc03.pw.conf dan tambahkan
```
<Directory /var/www/semeruc03.pw>
     Options +FollowSymLinks -Multiviews
     AllowOverride All
 </Directory>
```

### Screenshot

![no 9](/img/semeruConf.jpg)

- Restart apache dengan perintah " service apache2 restart "

### Screenshot

![no 9](/img/indexHome.jpg)
![no 9](/img/homeShow.jpg)


## Soal 10
### Langkah Pengerjaan
- Buat directory website dengan perintah " mkdir /var/www/penanjakan.semeruc03.pw "
- Pindah ke direktori /etc/apache2/sites-available dan copy file default ke file penanjakan.semeruc03.pw.conf
- Edit file penanjakan.semeruc03.pw.conf

### Screenshot

![no 10](/img/penanjakanAtas.jpg)

- Aktifkan konfigurasi dengan perintah " a2ensite penanjakan.semeruc03.pw "
- Download file pendukung dengan wget 10.151.36.202/penanjakan.semeruc03.pw.zip lalu unzip ke directory /var/www/penanjakan.semeruc03.pw

### Screenshot

![no 10](/img/lsPenanjakan.jpg)

## Soal 11
### Langkah Pengerjaan

- tambahkan konfigurasi pada file /etc/apache2/sites-available/penanjakan.semeruc03.pw.conf sesuai dengan gambar :

### Screenshot

![no 11](/img/penanjakanAllAtas.jpg)

- Sehingga menjadi seperti ini pada tampilan website:

### Screenshot

![no 11](/img/penanjakanShowAll.jpg)

![no 11](/img/penanjakanShowError.jpg)

![no 11](/img/penanjakanShowPub.jpg)

![no 11](/img/cssforb.jpg)

![no 11](/img/imagesforb.jpg)

![no 11](/img/jsforb.jpg)

## Soal 12
### Langkah Pengerjaan

- Tambahkan ErrorDocument dan pemeriksaan redirect status pada file /etc/apache2/sites-enabled/penanjakan.semeruc03.pw.conf

### Screenshot

![no 12](/img/404conf.jpg)

Hasil:

![no 12](/img/404page.jpg)

## Soal 13
### Langkah Pengerjaan

- Edit file konfigurasi yang berada di folder /etc/apache2/sites-available
- Buka file penanjakan.semeruc03.pw.conf
- Tambahkan konfirgurasi seperti pada gambar dibawah
```
<Directory /var/www/penanjakan.semeruc03.pw/public/javascripts>
     Options -Indexes
 </Directory>
 Alias "/js" "var/www/penanjakan.semeruc03.pw/public/javascripts"
```

### Screenshot

![no 13](/img/aliasJs.jpg)

- Restart apache dengan perintah service apache2 restart

### Screenshot

![no 13](/img/aliasJs.jpg)

![no 13](/img/aliasJsShow.jpg)

- Menunjukkan halaman forbidden karena folder /public/javascripts sudah diatur menjadi forbidden

## Soal 14

### Langkah Pengerjaan

- Pindah ke directory /etc/apache2/sites-available

```sh
cd /etc/apache2/sites-available
```

- Copy file 000-default.conf menjadi file naik.gunung.semeruc03.pw.conf
- Buka file naik.gunung.semeruc03.pw.conf lalu ubah port yang digunakan. Dimana awalnya port 80 menjadi port 8888.
- Ubah juga DocumentRoot yang awalnya /var/www/html menjadi /var/www/naik.gunung.semeruc03.pw.

### Screenshot

![no 13](/img/naikGunung.jpg)

- Tambahkan port 8888 pada file ports.conf pada directory /etc/apache2

### Screenshot

![no 13](/img/8888.jpg)

- wget 10.151.36.202/naik.gunung.semeru.pw.zip pada directory /var/www/ lalu di unzip dan rename menjadi naik.gunung.semeruc03.pw

### Hasil

![no 14](/img/isiNaik.jpg)

## Soal 15
### Langkah Pengerjaan

- Pada UML Probolinggo ketikkan `htpasswd -c /etc/apache2/.htpasswd semeru` 
- Lalu isi password dengan "kuynaikgunung"
- lakukan `cat` pada `/etc/apache2/.htpasswd` untuk memeriksa username dan password

### Screenshot

![no 15](/img/cat.jpg)

- Buka file /etc/apache2/sites-available/naik.gunung.semeruc03.pw.conf dan tambahkan syntax  berikut.

```sh
<Directory "/var/www/naik.gunung.semeruc03.pw">
    AuthType Basic
    AuthName "Restricted Content"
    AuthUserFile /etc/apache2/.htpasswd
    Require valid-user
</Directory>
```

### Screenshot

![no 15](/img/naikGunung.jpg)

- cek pada website naik.gunung.semeruc03.pw:8888 akan keluar pop-up sign in

### Screenshot

![no 15](/img/signin.jpg)

## Soal 16
### Langkah Pengerjaan

- Buka file 000-default.conf di /etc/apache2/sites-available/default
- Kemudian tambahkan `Redirect permanent / http://semeruc03.pw`

### Screenshot

![no 16](/img/00.jpg)

- Restart apache

```sh
service apache2 restart
```

### Screenshot

![no 16](/img/inputIP.jpg)
![no 16](/img/setelahInput.jpg)

## Soal 17
### Langkah Pengerjaan

- Setting pada file /var/www/penanjakan.semeruc03.pw/.htaccess seperti dibawah

### Screenshot

![no 17](/img/htaccess.jpg)

- RewriteEngine On dan RewriteRule yang ada akan mengakibatkan semua request url yang mengandung string "semeru" akan di redirect ke /public/images/semeru.jpg
- Karena /public/images/semeru.jpg sendiri mengandung kata "semeru", tentu akan terjadi infinite loop melakukan redirect (umumnya maximum 10 kali). Untuk menghindari loop tersebut ditambahkan RewriteCond yang akan memeriksa apabila nama file /public/images/semeru.jpg benar-benar ada (sesuai), proses redirect tidak akan dilakukan kembali

- Coba buka pada website penanjakan.semeruc03.pw/public/images/bukansemeruaja.jpg atau penanjakan.semeruc03.pw/public/images/asdasdasdsemeruasdasdasd.jpg maka akan ter-redirect ke url penanjakan.semeruc03.pw/public/images/semeru.jpg

### Screenshot

![no 17](/img/bukansemeruaja.jpg)
![no 17](/img/aja.jpg)
![no 17](/img/asd.jpg)
![no 17](/img/semeru.jpg)