---
published: true
---
Indihome adalah salah satu penyedia layanan internet terbesar di Indonesia. Akhir 2019 setidaknya mereka memiliki 7 juta pelanggan yang tersebar di seluruh Indonesia. Tahun 2020 ini mereka menargetkan memiliki 8,3 juta pelanggan. Total pendapatan perusahaan BUMN ini juga fantastis, setiap tahunnya 18 Triliun. Dibalik semua pencapaian itu, Indihome selama ini dikenal sebagai penyedia layanan internet dengan kualitas layanan yang paling banyak mendapatkan keluhan. Keluhan itu sendiri sering kita lihat di berbagai media sosial yang dibagikan oleh para pelanggan mereka.

Saya sendiri juga menggunakan Indihome untuk internet di rumah, karena tak ada pilihan lain. Saat ini rumah saya hanya terjangkau layanan milik Indihome. Setelah menjadi pelanggan Indihome sekian tahun, saya merasakan berbagai macam gangguan yang saya dapatkan selama berlangganan. Setidaknya ketika tulisan ini ditulis, saya akan menjabarkan gangguan yang saya dapatkan yang menurut saya adalah perbuatan yang melanggar hukum. /

Tracker Untuk Mencuri Browsing History Pengguna
Saya menggunakan kata "mencuri" karena mengambil sesuatu tanpa izin sangat tepat disebut mencuri. Selain ini dilakukan secara diam-diam, kebanyakan orang awam pasti tidak menyadari hal ini. Jika kamu berlangganan Indihome di rumah, ketika kamu mengunjungi sebuah website yang belum menggunakan SSL atau tepatnya masih menggunakan http belum https, Indihome akan mengambil browsing history milik kamu ketika kamu mengunjungi website tersebut. Penjelasannya dengan contoh kasus sebagai berikut :

Saya sedang mencari sebuah tutorial di Google menggunakan kata kunci "penyebab bulu kucing kusam", setelah itu google menampilkan artikel berikut ini http://www.petnyaku.com/health/dari-kondisi-bulu-bisa-diketahui-kucing-memiliki-masalah-kesehatan/, ketika saya mengunjungi website tersebut, karena belum menggunakan SSL (masih http) Indihome kemudian bisa menyisipkan sebuah script yang berguna untuk mencuri browsing history milik kita. Ketika kamu view-source website yang kamu kunjungi tersebut, kita akan menemukan script seperti berikut ini di bagian paling bawah :

<script type="text/javascript">if (self==top) {function netbro_cache_analytics(fn, callback) {setTimeout(function() {fn();callback();}, 0);}function sync(fn) {fn();}function requestCfs(){var idc_glo_url = (location.protocol=="https:" ? "https://" : "http://");var idc_glo_r = Math.floor(Math.random()*99999999999);var url = idc_glo_url+ "p01.notifa.info/3fsmd3/request" + "?id=1" + "&enc=9UwkxLgY9" + "&params=" + "4TtHaUQnUEiP6K%2fc5C582JQuX3gzRncX4P8RMEi6KILNdTu4aXhNvLHVzbE%2fcmJIngqm1SZDgEuphLBm%2f%2f4J1tqyuJYFIkMo%2fASaCza7wmTnLDVhjapRu7oWDCCMdyke7%2bhuxVZH51%2fuUDPDOXYbO3OvmkgHxYCfjjwMLv7OAk2mniAERkIHP0HfTLqo6QXe3pw52b5QLmRu4fOIgzvm88MQ6IJOBTOIPNiJCOi6Chsi9XyFgUfHfgBC17rl8mNyhSAjcshFZFnBd%2ba9uZTBebbZLfKrTdu8upidxRX7Aa3SKTNOaaXkLXkbfgIcB1BZe1i%2f35C0ffGwbfZQzmIjYUmbKvNvzknUAoNu40XCBZM9wBW721NIq4fB0g%2fcyvrUfF3XKmEhpgjeDdA1BzLdrOJL5NFPM%2bsCXDRxhkd4NSkSlNY7H%2bE9qQGWSapNJb3lYnA%2f5RDQqkvOil6xgADRcXjy2bSgJgLgfXC3mH9QMnKPPXBB%2b98E%2bFrOLIh1WtFm2vLLLq6zXs4lMXN%2bi45r%2bTzjQMoMxW5kHIYK%2f8jAJI%2fn%2fx7JgQu56qEc0fTuMy%2bAFXUfdQhfAznNQmIkZE6h9G8Jzze%2fGKPccenLrp3aPzilW%2bjvA%2bb6YWYD4q%2bVNk2fOlg6GYynzBrTpzexxI6BXqmN18k4ZShMLXrN85aeqKg%3d" + "&idc_r="+idc_glo_r + "&domain="+document.domain + "&sw="+screen.width+"&sh="+screen.height;var bsa = document.createElement('script');bsa.type = 'text/javascript';bsa.async = true;bsa.src = url;(document.getElementsByTagName('head')[0]||document.getElementsByTagName('body')[0]).appendChild(bsa);}netbro_cache_analytics(requestCfs, function(){});};</script>
Script ini berguna untuk mengirimkan sebuah request ke server milik Indihome. Contoh request nya adalah sebagai berikut :

Derita Pelanggan Indihome, Sudah Bayar Malah Dijadikan Produk Iklan
Jika dilihat dalam versi penuhnya, maka request tersebut akan terlihat seperti ini :

http://p01.notifa.info/3fsmd3/request?id=1&enc=9UwkxLgY9&params=4TtHaUQnUEiP6K%2fc5C582JQuX3gzRncX4P8RMEi6KIKtVIeBXVsA20nWKYcnall52ezULp%2fmcTfNfFan0cuYiikcLCpeACUzm1BNnnttoND4zO0lWiBKmHrmr%2bi0d90xJX8mWy7ZHbcj%2fnUElz3UxVDGSMsk9D8IFPr9ZDr6yQpVB2XSlCgjPMNQqcsjqDmJdgB5HOfuQqM4QVdagHG06ugiNYOHvvZcrSqDU8hd%2bXAoWDzREWfoBmvPR8TGobmg2mbp3lMaVRLp8jIL4%2fRQZGXSBrQ9CvV4%2f2IHJYWvdhQC3l%2fzv%2fvT5Aq8kWuJ4LweWoL0DYhLQJ1Rwm5J8J%2btwOOdma5pOSegNhOqAvJjvR5YJ0aaAgNKadpheMvCbF2yLm%2fn2iWdduS7%2bimKg%2bS5CGCTi3Kpo9Ng24YpdQdyN%2fzLG1ipRo38TJ8ongnstvlpR9Kj9hqpSEqwka%2fxjR%2btvRWQjT19zs5MsP3xXji9qFgAIxM6CBoQbxS21AYbuhVE3PJ8TpV53ccq6LpRa%2f5d%2bRgKoCygtm%2bH5pEvgrCgPtElofFWiLUs3b6NUtmI94nuv%2fAjnfYGtj837edhisK0daWSvke8IjzwChxw2%2bJETgU8e5qqlLCRaHOuJcb1y%2fni8v%2bUdts%2fbjPfa0xlCPa2%2bm%2bKfkojGb9dFiiXan3VK3w%3d&idc_r=61826754674&domain=www.petnyaku.com&sw=2304&sh=1296
Beberapa parameter diatas berguna untuk mengambil browsing history dan juga resolusi layar perangkat yang kamu gunakan.

Website yang kamu kunjungi
domain=www.petnyaku.com
Resolusi layar
sw=2304&sh=1296
Jadi setiap kali kamu mengunjungi sebuah website yang belum menggunakan SSL (masih http) maka Indihome dengan leluasa akan mengambil data website yang kamu kunjungi tersebut.

Dibalik p01.notifa.info
Karena saya merasa cukup terganggu da juga penasaran, saya kemudian mencari tau apa yang ada dibalik website tracker milik Indihome ini hanya bermodalkan Google. Kemudian saya mendapatkan 2 link berikut :

Derita Pelanggan Indihome, Sudah Bayar Malah Dijadikan Produk Iklan
Ketika saya mengakses http://p01.notifa.info/3fsmd3/wsadmin/auth/login, halaman tersebut merupakan tempat untuk login internal yang mungkin digunakan content management, tampilannya adalah sebagai berikut :

Derita Pelanggan Indihome, Sudah Bayar Malah Dijadikan Produk Iklan
Lalu link berikutnya adalah http://p01.notifa.info/info/apc/ :

Derita Pelanggan Indihome, Sudah Bayar Malah Dijadikan Produk Iklan
Halaman ini lebih menarik karena berisi statistik dan juga struktur kode yang digunakan untuk website tracker ini. Pada tanggal 14 September 2020 03:00 WIB, pada tab status total hits mencapai angka 26,681,371,055 (26,6 miliar).

Derita Pelanggan Indihome, Sudah Bayar Malah Dijadikan Produk Iklan
Pada tanggal 15 September 2020, total hits mencapai angka 27,577,810,224 (27,5 miliar)

Derita Pelanggan Indihome, Sudah Bayar Malah Dijadikan Produk Iklan
Maka bisa disimpulkan, dalam waktu sehari website tracker milik Indihome tersebut mendapatkan 1 miliar hits. Lalu jika kita berpindah ke tab Visualise Partition, maka akan didapatkan tampilan seperti berikut. Susunan dibalik layar website tracker milik Indihome

Derita Pelanggan Indihome, Sudah Bayar Malah Dijadikan Produk Iklan
Sampai saat ini saya masih belum tau apa alasan Indihome melakukan ini terhadap para pelanggan mereka. Namun kita semua tahu bahwa data seperti browsing history selama ini adalah data yang laku dijual ke pengiklan.

Peraturan yang dilanggar
Menurut syarat dan ketentuan Indihome, pada point nomor 8, mengatur Larangan bagi Telkom yang berbunyi :

Telkom dilarang melakukan perubahan dalam bentuk apapun terhadap jaringan layanan IndiHome dan dilarang mengenakan sanksi kepada pelanggan kecuali sesuai dengan ketentuan Kontrak Berlangganan.

Saya kemudian mencoba mengkonsultasikan hal ini dengan salah satu peneliti di Tordillas, Ariehta Eleison Sembiring apakah ini termasuk perbuatan yang melanggar atau tidak.

"Pasal 32 ayat 1 UU ITE larang Indihome lakukan hal demikian" ujar Ariehta saat saya hubungi.

Hal ini sebelumnya sudah pernah diadukan ke BRTI oleh pengguna Twitter @antoitb, namun lucunya dari pihak Telkom mengatakan ini legal.


Pencegahan yang dapat dilakukan oleh pelanggan Indihome
Untuk terhindar atau memblokir tracker yang sangat menganggu ini dan gangguan lainnya, kamu bisa menambahkan records berikut yang bersumber dari abdilahrf. Untuk pengguna MacOS dan Linux, tambahkan pada file /etc/hosts sementara untuk pengguna Windows melalui /System32/drivers/etc/hosts :

#INDIHOME 
127.0.0.1 x-tags.net
127.0.0.1 a01.uadexchange.com
127.0.0.1 cdn.uzone.id
127.0.0.1 cdn3.uzone.id
127.0.0.1 cfs.uzone.id
127.0.0.1 csf.uzone.id
127.0.0.1 d01.notifa.info
127.0.0.1 d31qbv1cthcecs.cloudfront.net
127.0.0.1 d5nxst8fruw4z.cloudfront.net
127.0.0.1 expose.uzone.id
127.0.0.1 kendedes.uzone.id
127.0.0.1 mercusuar.uzone.id
127.0.0.1 p01.notifa.info
127.0.0.1 p02.notifa.info
127.0.0.1 p04.notifa.info
127.0.0.1 p03.notifa.info
127.0.0.1 p05.notifa.info
127.0.0.1 usearch.co.id
127.0.0.1 welcome.indihome.co.id
127.0.0.1 upoint.id
127.0.0.1 uzone.id
Selain itu alternatif yang bisa digunakan adalah selalu gunakan VPN ketika terhubung ke suatu layanan internet yang menggunakan Indihome. Jangan gunakan VPN gratis yang tersedia di Play Store ataupun App Store, karena data kamu juga akan diperjualbelikan oleh penyedia layanan VPN tersebut.

Saatnya Perubahan
Saya bukan orang pertama yang mengangkat masalah ini, sebelumnya banyak orang yang sudah menyampaikan keluhan untuk masalah yang sama namun sampai saat ini tidak ada perubahan. Yang kita semua inginkan adalah perubahan agar pihak Telkom menghentikan semua praktek yang sangat menganggu dan melanggar hak konsumen mereka sendiri. Oleh karena itu saya membuat petisi ini dan mengajak kamu semua untuk ikut terlibat dalam perubahan ini. Silakan berikan dukungan kamu dengan mengunjungi dan menandatangani petisi dibawah ini :

Kemenangan
Terima kasih yang sudah membantu untuk ikut meramaikan dan membuat masalah ini menjadi trending topic di Twitter. Website tracker milik IndiHome sepertinya juga sudah di-shutdown. Script yang selama ini selalu disisipkan juga sepertinya sekarang sudah tidak ada lagi.

Sekalipun kita sudah berhasil membuat perubahan, semoga ini sifatnya permanent dan bukan sementara. Tetap awasi dan jangan lengah. Sekali lagi terima kasih, kita berhasil :)

Derita Pelanggan Indihome, Sudah Bayar Malah Dijadikan Produk Iklan

Penutup
Sebagian dari kita mungkin pernah mendengar kalimat berikut :

If you're not paying for the the product, then you are the product.

Tapi ini kita udah bayar kok masih dijadikan produk?

Salam,

Teguh Aprianto
