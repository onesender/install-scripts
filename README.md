# Install Scripts
OneSender install scripts

Repository ini berisi kumpulan script untuk install OneSender secara otomatis.

Ada beberapa teknik install yang bisa digunakan

## Teknik Symlink
Gunakan teknik ini jika ingin menginstall beberapa aplikasi OneSender di satu VPS server.

Teknik sysmlink ini dapat memudahkan maintenace. Ketika update kita cukup mengubah file master saja. Semua instance OneSender akan otomatis berubah ke versi terbaru.

Struktur akhir folder seperti ini:
```
|-- /opt/onesender-master
    |-- resource
    |-- onesender-x86_64   -> file binary utama / aplikasi OneSender

|-- /opt/onesender-01      -> aplikasi pertama
    |-- resource
    |-- onesender-1        -> symlink ke path /opt/onesender-master/onesender-x86_64
    |-- config_1.yaml      -> file config instance pertama

|-- /opt/onesender-02      -> aplikasi kedua
    |-- resource
    |-- onesender-2        -> symlink ke path /opt/onesender-master/onesender-x86_64
    |-- config_2.yaml      -> file config instance kedua
```

### Langkah install

Pastikan Anda menggunakan versi terbaru. Kami melakukan update secara berkala. Pastikan Anda mengunduh lagi versi terbaru dari dashboard sebelum  menggunakan tutorial ini.

Tahap install meliputi 3 bagian:
1. Menyiapkan folder instalasi
2. Install master OneSender
3. Install instance OneSender

#### 1. Menyiapkan folder install
1. Unduh file installer `onesender-latest.zip` dari dashboard [https://onesender.net/my-account](https://onesender.net/my-account). 
2. Upload file installer ke VPS. Letakkan di path `/root/onesender-latest.zip`
3. extract file zip tersebut 
```
cd /root/
unzip -q onesender-latest.zip
```
Keterangan:
- Folder instalasi berada di path `/root/onesender-2.1.3`.
- Nama folder dapat berbeda-beda, menyesuikan versi terbaru OneSender.

#### 2. Install master OneSender
Langkah ini bertujuan untuk memindahkan file-file master yang diperlukan untuk install OneSender.

Lokasi folder master berada di path `/opt/onesender-master`.

1. Masuk ke folder instalasi
```
cd /root/onesender-2.1.3
```
*PS: Sesuikan folder instalasi dengan versi yang digunakan*

2. Masuk ke folder install
```
cd /root/onesender-2.1.3/installer/symlink-technique/
```

3. Jalankan script install
``` 
sudo bash ./install-master.sh
```
