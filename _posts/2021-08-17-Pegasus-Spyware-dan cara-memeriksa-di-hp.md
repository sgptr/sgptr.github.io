---
published: true
---
![pg1.png]({{ site.baseurl }}/images/pg/pg1.png)

**Cara mandiri memeriksa apakah hp kamu terinfeksi pegasus spyware**

-Refrensi : [Teguh Aprianto](https://tegoh.co)

Setahun belakangan Indonesia sedang ramai dengan bahasan seputar Pegasus, spyware milik NSO Group asal Israel. Pegasus selama ini dikenal digunakan untuk melakukan penyadapan terhadap aktivis, jurnalis, pengusaha dan juga para politikus. Kasus yang melibatkan Pegasus yang paling terkenal adalah [kasus pembunuhan Jamal Khashoggi](https://www.theguardian.com/world/2021/jul/18/nso-spyware-used-to-target-family-of-jamal-khashoggi-leaked-data-shows-saudis-pegasus) dan juga penyadapan terhadap [Jeff Bezos](https://www.vice.com/en/article/v74v34/saudi-arabia-hacked-jeff-bezos-phone-technical-report), pendiri Amazon. Berdasarkan [investigasi](https://www.theguardian.com/world/2021/jul/18/revealed-leak-uncovers-global-abuse-of-cyber-surveillance-weapon-nso-group-pegasus) yang dilaporkan oleh the Guardian dan 15 media lainnya, sebanyak 50.000 nomor telepon di seluruh dunia, dipantau oleh pemerintah lewat spyware buatan Israel ini.

Indonesia juga disebut turut menggunakan spyware asal Israel tersebut, Anggota Komisi I DPR dari PDI Perjuangan Effendi Muara Sakti Simbolon dan politikus Partai Demokrat Sjarifuddin Hasan membenarkan kabar adanya [penggunaan Pegasus](https://nasional.tempo.co/read/1358995/akun-aktivis-diretas-indonesia-disebut-punya-pegasus-dari-israel) oleh Pemerintah Indonesia. Selama ini ketika aktivis dan jurnalis yang mengalami serangan digital di Indonesia juga selalu dikaitkan dengan spyware asal Israel tersebut. Namun klaim tersebut tidak dapat dibuktikan, hanya bisa dibuktikan jika dilakukan digital forensik terhadap perangkat yang digunakan.

Namun sekarang kita bisa mengucapkan terima kasih kepada Amnesty International, berkat sebuah [riset tentang Pegasus](https://www.amnesty.org/en/latest/research/2021/07/forensic-methodology-report-how-to-catch-nso-groups-pegasus/) yang dilakukan oleh [Amnesty International Security Lab](https://www.amnesty.org/en/tech/), mulai sekarang kamu bisa melakukan pemeriksaan secara mandiri apakah HP yang kamu gunakan sudah terinfeksi Pegasus atau tidak. Jika kedepannya serangan digital masih terjadi dan dicurigai melibatkan Pegasus, jangan berharap banyak kepada Polisi untuk urusan digital forensik 😋

Mulai dari sekarang kamu bisa melakukan pemeriksaan secara mandiri menggunakan [MVT (Mobile Verification Toolkit](https://github.com/mvt-project/mvt). Berikut panduan untuk pengguna iOS dan juga Android.

**Pengguna iOS (iPhone dan iPad)**###

Sebelum memulai, ada beberapa depedencies yang harus kamu install. Perlu diketahui ketika menulis panduan ini saya menggunakan MacOS.

**Install Dependencies**

```brew install python3 libusb```

```pip3 install mvt```

**Install libimobiledevice**

```brew install --HEAD libimobiledevice```

Jika sudah, coba hubungkan perangkat iPhone atau iPad yang kamu gunakan ke komputer menggunakan kabel USB lalu jalankan perintah berikut :

```ideviceinfo```

**Backup Perangkat Menggunakan libimobiledevice**

Ketika sedang backup perangkat yang kamu gunakan, pastikan opsi encryption dalam keadaan aktif. Karena menurut panduan dari MVT, backup yang terenkripsi memiliki lebih banyak data ketimbang backup yang tidak terenkripsi.

```idevicebackup2 backup encryption on```

Jika sebelumnya backup sudah pernah dilakukan melalui aplikasi iTunes dan kamu sudah menerapkan password untuk backup, jalankan perintah berikut :

```idevicebackup2 backup encryption on --p passwordbackupkamu```

Setelah itu kamu bisa mulai melakukan backup menggunakan perintah berikut:

```idevicebackup2 backup --full /path/to/backup/```

Jika berhasil maka tampilannya sebagai berikut :

![pg2.gif]({{ site.baseurl }}/images/pg/pg2.gif)

Tampilan di terminal jika proses backup telah selesai :

![pg3.png]({{ site.baseurl }}/images/pg/pg3.png)

Proses backup akan memakan cukup banyak waktu dan dibutuhkan waktu sekitar beberapa jam, jadi tunggu saja sampai proses backup tersebut selesai. Jika sudah selesai, kamu bisa melanjutkan ke proses decrypting backup tersebut.

**Decrypting Backup**

```mvt-ios decrypt-backup -p password -d /path/to/decrypted /path/to/backup```

Jika proses decrypting berjalan normal, maka tampilannya akan seperti berikut ini :

![pg4.gif]({{ site.baseurl }}/images/pg/pg4.gif)

**Jalankan Pemeriksaan Backup**

Download indicators of compromise file dari Amnesty International Github repo.

```wget https://raw.githubusercontent.com/AmnestyTech/investigations/master/2021-07-18_nso/pegasus.stix2```

Buat folder untuk hasil dari pemeriksaan.

```mkdir hasil```

Mulai jalankan pemeriksaan.

```mvt-ios check-backup --output /path/to/hasil /path/to/backup/udid/ --iocs pegasus.stix2```

![pg5.png]({{ site.baseurl }}/images/pg/pg5.png)

Jika pemeriksaan berhasil, maka kamu akan menemukan beberapa file di direktori mvt/hasil. Jika ditemukan file yang berakhir dengan _detected.json, **maka ada indikasi jejak Pegasus ditemukan di perangkat yang kamu gunakan**. Untuk file JSON lainnya, file tersebut berisi data hasil pemindaian perangkat yang kamu gunakan. Jika file _detected.json tidak ditemukan, **maka bisa dikatakan bahwa perangkat yang kamu gunakan tidak terinfeksi oleh Pegasus.**

![pg6.png]({{ site.baseurl }}/images/pg/pg6.png)

**Pengguna Android**###

Untuk mulai melakukan pemeriksaan terhadap perangkat Android yang kamu gunakan, kamu harus menghubungkan perangkat Android milik kamu ke komputer dan juga harus mengaktifkan USB Debugging.

![pg7.png]({{ site.baseurl }}/images/pg/pg7.png)

**Install Dependencies**

```brew install android-platform-tools```

**Downloading APKs**

```mvt-android download-apks --output /path/to/folder```

Jika kamu ingin mengaktifkan opsi pemeriksaan menggunakan VirusTotal, jalankan perintah berikut :

```mvt-android download-apks --output /path/to/folder --virustotal```

**Pemeriksaan Melalui Backup SMS Android**

Beberapa serangan terhadap Android dilakukan dengan mengirimkan link berbahaya melalui SMS. Fitur backup Android tidak memungkinkan untuk mengumpulkan banyak informasi yang menarik untuk analisis forensik, tetapi dapat digunakan untuk mengekstrak SMS dan kemudian bisa kita periksa menggunakan MVT.

Kamu bisa menggunakan adb untuk mengekstrak backup hanya untuk SMS.

```adb backup com.android.providers.telephony```

![pg8.png]({{ site.baseurl }}/images/pg/pg8.png)

![pg9.png]({{ site.baseurl }}/images/pg/pg9.png)


Kamu harus menyetujui backup di layar HP yang kamu gunakan dan akan diminta untuk memasukkan kata sandi untuk mengenkripsi backup tersebut. Backup tersebut kemudian akan disimpan ke dalam file bernama backup.ab.

Selanjutnya kamu harus menggunakan Android Backup Extractor untuk mengubahnya menjadi format file yang dapat dibaca. Pastikan kamu sudah menginstall Java dan jalankan perintah berikut:

```java -jar ~/Download/abe.jar unpack backup.ab backup.tar```

```tar xvf backup.tar```

Jika backup dienkripsi, kamu akan diminta untuk memasukkan password oleh Android Backup Extractor.

**Ekstrak SMS yang Berisi Link Menggunakan MVT**

```mvt-android check-backup --output . . --iocs pegasus.stix2```

Untuk Android, hasil pemeriksaan nantinya akan ditampilkan di output terminal.

![pg10.png]({{ site.baseurl }}/images/pg/pg10.png)
