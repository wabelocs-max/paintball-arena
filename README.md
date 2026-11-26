# Paintball Arena

Game tembak-tembakan cat dari atas (top-down) yang jalan langsung di browser.

**Main sekarang:** https://wabelocs-max.github.io/paintball-arena/

## Mode

- **Main lokal**: 2–4 pemain di satu keyboard/gamepad, slot kosong bisa diisi bot.
- **Main online**: buat room, kirim kode 4 huruf atau tautan undangan ke teman. Browser para pemain tersambung langsung (WebRTC lewat [PeerJS](https://peerjs.com)); pembuat room jadi host.
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

**HP/tablet:** centang "Tampilkan tombol layar sentuh" di lobi (otomatis menyala di layar sentuh). Joystick kiri untuk jalan dan membidik, tombol Tembak di kanan. Paling nyaman dimainkan dengan HP dimiringkan (landscape).

## Catatan online

- Room tetap ada selama pembuatnya tidak keluar atau menutup tab.
- Maksimal 8 pemain per room.
- Sebagian jaringan kantor/sekolah atau operator seluler memblokir koneksi langsung antar-browser; kalau tidak bisa tersambung, coba jaringan lain.

Semua kode ada di satu file: `index.html`.
