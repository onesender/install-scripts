# Template Pesan WooCommerce

Template pesan plugin integrasi WooCommerce menggunakan template engine [twig](https://twig.symfony.com/doc/3.x/). Sehingga tag dan fungsi-fungsi templating di twig dapat digunakan di plugin.

Berikut ini beberapa contoh penggunaan template

### Simple message

<table><tr><td>Template</td><td>Preview</td></tr><tr><td>
<pre>
Hello, *{{nama}}*!

Berikut ini informasi order Anda:

Order ID: *{{order_id}}*

Produk:
{{ringkasan_pembelian}}

Pembayaran sebagai berikut:
{{ringkasan_pembayaran}}
Terima kasih
</pre>

</td><td>

Hello, <b>John</b>!<br><br>Berikut ini informasi order Anda:<br><br>Order ID: <b>1775</b><br><br>Produk:<br>OneSender Paket Starter<br>1 x Rp150.000 = Rp150.000<br><br><br>Pembayaran sebagai berikut:<br>Transfer Bank<br><b>BRI (Bank Rakyat Indonesia)</b><br>Nomor rekening: <b>123-456-789</b><br>Atas nama: <b>John</b><br><br><br>Terima kasih

</td></tr></table>

Keterangan:
- Pada keyword nama ditambahkan filter `trim`. Fungsinya untuk menghapus karakter spasi di awal dan di akhir text.

### Listing product
WooCommerce menyimpan data produk (item pembelian) dalam format Array. Diperlukan tag looping/perulangan untuk memunculkan nama produk.


<table><tr><td>Template</td><td>Preview</td></tr><tr><td>
<pre>
Hello, *{{nama|trim}}*!

Berikut ini informasi order Anda:

Order ID: *{{order_id}}*

Produk:
{% for item in items %}

*{{item.nama_produk}}*
Qty:{{item.qty}} 
Harga: {{item.harga}}
{% endfor %}

Total fee: {{total_fee}}
Total invoice: {{jumlah_tagihan}}

Pembayaran sebagai berikut:
{{ringkasan_pembayaran}}

Terima kasih
</pre>

</td><td>

Hello, <b>John</b>!<br><br>Berikut ini informasi order Anda:<br><br>Order ID: <b>1775</b><br><br>Produk:<br><br><b>OneSender Paket Starter</b><br>Qty:1 <br>Harga: Rp150.000<br><br>Total fee: -Rp487<br>Total invoice: <b>Rp149.513</b><br><br>Pembayaran sebagai berikut:<br>Transfer Bank<br><b>BRI (Bank Rakyat Indonesia)</b><br>Nomor rekening: <b>123-456-789</b><br>Atas nama: <b>John</b><br><br><br>Terima kasih

</td></tr></table>

