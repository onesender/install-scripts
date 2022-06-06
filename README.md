# Install Scripts
OneSender install scripts

Repository ini berisi kumpulan script untuk install OneSender secara otomatis.

Ada beberapa teknik install yang bisa digunakan

## Teknik Symlink
Gunakan teknik ini jika ingin menginstall beberapa aplikasi OneSender di satu VPS server.

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

**Langkah install*
1. Unduh file installer `onesender-latest.zip`. 
2. Upload file installer ke VPS. Letakkan di path `/root/onesender-latest.zip`
3. extract file zip tersebut 
```
cd /root/
unzip -q onesender-latest.zip
```
