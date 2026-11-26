# Paintball Arena

Game tembak-tembakan cat dari atas (top-down) yang jalan langsung di browser.

**Main sekarang:** https://wabelocs-max.github.io/paintball-arena/

## Mode

- **Main lokal**: 2–4 pemain di satu keyboard/gamepad, slot kosong bisa diisi bot.
- **Main online**: buat room, lalu teman memilihnya dari daftar **Pilih room yang sedang main**, atau masuk lewat kode 4 huruf / tautan undangan. Centang **Room privat** kalau room tidak ingin tampil di daftar. Semua pemain tersambung lewat server relay publik (MQTT over WebSocket di `broker.emqx.io`, cadangan `broker.hivemq.com`), jadi bisa main dari data seluler maupun wifi. Room tetap ada selama masih ada pemain di dalamnya.
- **Tim**: Bebas (sendiri-sendiri), 2, 3, atau 4 tim. Tiap tim punya warna sendiri, peluru teman setim tidak melukai, skor dihitung per tim.

## Power-up

Muncul acak di arena (maksimal 3 sekaligus). Jalan ke atasnya untuk mengambil.

| Power-up | Efek | Lama |
|---|---|---|
| Lari kencang (biru muda) | Gerak 1,5× lebih cepat | 6 detik |
| Tembak cepat (oranye) | Tembakan 2,5× lebih cepat, peluru tidak habis | 6 detik |
| Perisai (putih) | Menahan 1 tembakan | 12 detik |
| Tembak sebar (ungu) | 3 peluru sekaligus | 7 detik |

Semua efek hilang kalau kamu tertembak.

## Kontrol

| Pemain | Jalan | Tembak |
|---|---|---|
| 1 | W A S D | Spasi / F |
| 2 | Panah | Enter / `/` |
| 3 | I J K L | U / O |
| 4 | Numpad 8 4 5 6 | Numpad 0 |

Gamepad: stik kiri jalan, stik kanan bidik, RT atau A tembak. `Esc` / `P` untuk menu.

Saat online, pemain memakai WASD atau panah.

**HP/tablet:** centang "Tampilkan tombol layar sentuh" di lobi (otomatis menyala di layar sentuh). Joystick kiri untuk jalan dan membidik, tombol Tembak di kanan. Saat main, game mengisi seluruh layar; dengan HP dimiringkan (landscape) tombol menumpang di atas arena. Di Android, game otomatis masuk layar penuh.

## Catatan online

- Hemat data: sekitar 1 KB/s kirim dan 3 KB/s terima per pemain untuk room 4 orang (kira-kira 15 MB per jam). Kalau tulisan **sinyal lemah** muncul di pojok atas, ada pemain yang koneksinya tersendat.

- Kena atau tidaknya tembakan ditentukan di layar **penembak**: kalau peluru terlihat mengenai lawan di layarmu, lawan kalah. Lawan yang baru muncul kembali kebal 1,5 detik (berkedip), dan perisai menahan satu tembakan; keduanya ditandai tulisan di atas pemain.

- Pembuat room menentukan **maks pemain**: 2, 4, 6, atau 8 (selalu genap, dan habis dibagi jumlah tim). Pemain yang datang setelah room penuh akan diberi tahu dan kembali ke lobi.
- Pemain yang bergabung otomatis masuk ke tim yang anggotanya paling sedikit. Tim dan warna **terkunci selama ronde berjalan**; tombol **Ganti tim** (juga ada di Menu) hanya aktif di jeda 5 detik antar-ronde, dan hanya ke tim yang belum penuh.
- Kalau tidak bisa tersambung: cek internet, matikan VPN atau pemblokir iklan yang memblokir WebSocket, lalu muat ulang halaman.
- Server relay yang dipakai adalah server publik gratis: siapa pun yang tahu kode room bisa ikut masuk, dan datanya (posisi, tembakan, skor) tidak dienkripsi end-to-end. Jangan kirim data pribadi lewat game ini.

Semua kode ada di satu file: `index.html`.
