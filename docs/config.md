File pengaturan

## app

| Key        | Deskripsi           | status  |
| ------------- |-------------| -----|
| installed      | bool: `true` / `false`. Setting ini disi otomatis oleh aplikasi | opsional |
| sync_contacts      | bool: `true` / `false`. Izinkan aplikasi OneSender akses kontak. Default: `false` | opsional |
| wamd_session_path      | string. Lokasi file session. Contoh: `/opt/onesender/whatsapp.session`. Jika settinga ini tidak ada, otomatis akan membuat file `whatsapp.session`| opsional |

## database
| Key        | Deskripsi           | status  |
| ------------- |-------------| -----|
| connection | string. Contoh: `mysql` | wajib |
| host | string. Contoh: `localhost`  | wajib |
| log | string. Pilihan: `silent`, `info`  | opsional |
| name | string. Nama database | wajib |
| password | string. Password database  | wajib |
| port | integer. Port database. Default `3306`  | wajib |
| user | string. Nama user | wajib |

## server
| Key        | Deskripsi           | status  |
| ------------- |-------------| -----|
| port | integer. Setting default `3000` | opsional |
