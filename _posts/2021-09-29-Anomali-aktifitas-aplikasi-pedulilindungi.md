---
published: true
---
![pl.png]({{ site.baseurl }}/images/pl/pl.png)

### apakah aplikasi peduli lindungi itu benar-benar melindungi kita? atau aplikasi tersebut menjadi sebuah bisnis yg menguntungkan?

pada tanggal 27 september 2021, seseorang analis  cyber security [@BukanYahya](https://twitter.com/BukanYahya/status/1442355427627335684) membagikan sebuah thread yg cukup menarik yaitu anomali aktifitas aplikasi peduli lindungi. anomali yg baru ditemukan itu ada dua:

- aplikasi menyimpan data device secara manual
- data dikirimkan ke website aneh diluar indonesia


1. mengirimkan data nama, terakhir login, cpu, ram dan storage secara manual ke database analytic pedulilindungi pada saat melakukan aktifitas verifikasi login, verifikasi register dan register.

![pl1]({{ site.baseurl }}/images/pl/pl1.png)

kenapa ini jadi anomali ? soalnya kalau hubungannya sama aktifitas user, pedulilindungi udah punya analytic dari vendor http://app-measurement.com sama crashlytic, jadi buat apa kirim manual pada aktifitas tersebut ?

2. aplikasi akan mengirimkan data nama operator seluler, cpu, storage, ram, device, platform dll ke domain `http://track.analytic.rocks` berikut pada saat melakukan aktifitas apapun, biarpun itu belum login

![pl2.png]({{ site.baseurl }}/images/pl/pl2.png)

nah yang menarik itu poin ke dua, kira kira kalau digambarkan seperti ini, ada trusted network yang jelas itu punya vendor pedulilindungi, dan ada http://track.analytic.rocks yang ini ga jelas punya siapa.

![pl3.png]({{ site.baseurl }}/images/pl/pl3.png)

dr hasil analisa http://track.analytic.rocks itu berujung punya telkom kalau di trace lebih dalam, apa buktinya ? ada dua kalau buka link ini http://track.analytic.rocks/static/collect.js akan ada keyword "blanja", salah satu kata bahasa indonesia dalam source code ini, dan tau sendiri blanja punya siapa?

![pl4.png]({{ site.baseurl }}/images/pl/pl4.png)

dan satu lagi, saya analisa lebih dalam pada hostnya, `http://track.analytic.rocks` alamat IP nya adalah "52.221.60.108" kalau di cek history SSL nya host ini nempel dengan domain http://cfs.uzone.id dan domain http://smarteye.id yang berujung ke anak perusahaan telkom.

![pl5.png]({{ site.baseurl }}/images/pl/pl5.png)

![pl6.png]({{ site.baseurl }}/images/pl/pl6.png)

sebenernya yang lebih parah itu adalah alamat IP tersebut, di alamat IP "52.221.60.108" dan "52.77.99.172" itu tersimpan apa ? dan sempet di scan ternyata ada "kemungkinan" lubang keamanan nya, kek gini ma calon calon bocor lagi, oh iya servernya di singapura, bukan di indonesia

![pl7.png]({{ site.baseurl }}/images/pl/pl7.png)

![pl8.png]({{ site.baseurl }}/images/pl/pl8.png)

![pl9.png]({{ site.baseurl }}/images/pl/pl9.png)

ngiseng cek di virus total juga ada yang nyebut anomali, jadi vendornya itu `http://Bfore.Ai` dia pengawas internet buat cek aktifitas domain yang terbilang "anomali" dan `http://track.analytic.rocks` itu termasuk.

![pl10.png]({{ site.baseurl }}/images/pl/pl10.png)

[Teguh Aprianto](https://twitter.com/secgron/status/1442142118554660867)

Buat yang ga paham, jadi aplikasi PL itu mengirimkan data pengguna ke sebuah server yang menggunakan domain http://analytic.rocks.

Informasi tentang http://analytic.rocks ini sedikit sekali. Tapi setelah saya melakukan pencarian, muncul "blanja". Blanja punya siapa? Telkom.

Walaupun kita tau Telkom terlibat sebagai pihak pengelola aplikasi PL, tapi atas kepentingan apa data tersebut dikirimkan langsung ke aset milik Telkom yg anonim ini? Seharusnya data ini hanya berada di dalam environment PL yang dikelola oleh Kemenkes dan Telkom.

Masyarakat menggunakan aplikasi tersebut "dipaksa" dan yang mereka tau data itu hanya digunakan untuk PL. Ketika terjadi perpindahan data ke aset milik Telkom yang tak dikenal dan berada di luar lingkungan PL, wajar jika kemudian masyarakat bertanya, kenapa dan untuk apa?

informasi keterkaitan http://analytic.rocks dengan Telkom juga bisa ditemukan melalui http://store.indihome.co.id. Selain itu juga ada di https://track.analytic.rocks/static/.

Bayangin data kamu di aplikasi PL digunakan untuk kepentingan bisnis Telkom. Tanpa consent dan tanpa penjelasan.

Jadi bisa dikatakan http://analytic.rocks ini adalah web app analytics milik Telkom yg selama ini digunakan utk menampung data dr berbagai unit bisnis Telkom. 

Selain itu http://analytic.rocks ini linked dengan http://cfs.uzone.id dan juga SmartEye, keduanya milik Metranet, anak usaha Telkom.

Jadi data pengguna PL dialihkan utk kepentingan bisnis metranet yg salah satu produknya adalah digital advertising. 

jujur saya juga menggunakan aplikasi PL ini tetapi hanya untuk keperluan yg dibutuhkan menggunakan aplikasi tersebut, jika sudah selesai pasti akan saya uninstal lagi aplikasinya.

cuma di INDONESIA hal seperti ini dibiarkan, di negara2 lain jika ada kasus seperti ini sudah pasti akan  di jatuhi hukuman atau dikenakan denda, sekelas Facebook aja pernah kena kasus jual beli data pengguna [https://www.liputan6.com/news/read/3447123/mark-zukerberg-akui-jual-data-facebook-ke-pihak-ketiga](https://www.liputan6.com/news/read/3447123/mark-zukerberg-akui-jual-data-facebook-ke-pihak-ketiga)


terima kasih untuk [@BukanYahya](https://twitter.com/BukanYahya/status/1442355427627335684) dan [Teguh Aprianto](https://twitter.com/secgron/status/1442142118554660867) atas informasinya.
