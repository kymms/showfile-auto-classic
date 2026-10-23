# SHOWFILE AUTO Classic V0.1.0

Versi aplikasi lengkap dengan desain Classic Console, berdasarkan mesin scene V0.6.8.6. Dibuat untuk repository terpisah.

## Coba di ponsel

1. Ekstrak ZIP, lalu upload **isi folder** ke root repository GitHub baru. `index.html` dan `template.scn` harus berada berdampingan.
2. Salin `visitor-tracker.js` asli dari repository Anda ke direktori yang sama. ZIP sumber tidak menyertakan file tracker; tidak ada tracker pengganti yang dibuat.
3. Aktifkan GitHub Pages untuk repository tersebut.
4. Buka alamat GitHub Pages di Chrome Android atau Safari iPhone. Gunakan tampilan portrait.

Jangan hanya membuka HTML melalui aplikasi pratinjau file di ponsel. Unduhan scene dan validasi impor mengambil `template.scn` melalui HTTP(S), sehingga jalankan lewat alamat Pages.

## Tampilan dan kontrol

- Delapan channel dalam satu bank: CH 1–8, 9–16, 17–24, 25–32. Layar tetap portrait dengan lebar maksimum 480 px. Bank terakhir menampilkan slot kosong jika jumlah input bukan kelipatan delapan.
- Label nama channel mendatar dan berukuran ringkas seperti tombol processing. Nama panjang dapat terpotong di strip; ketuk nama atau SEL untuk melihat dan mengedit nama lengkap di panel detail.
- Tombol Gate, EQ dan Comp terhubung langsung ke switch processing scene.
- Pada Monitor / FOH + Monitor, fader mengatur level send ke Mixbus yang dipilih. Paling bawah adalah send OFF. Fader bukan channel master dan bukan meter audio.
- Panel detail menyediakan nama, warna/inverse, stereo link, HPF, Main LR, tap point, ON/OFF send dan level dB presisi.
- Dalam FOH, strip menampilkan Main LR. Bus berjenis Group memakai halaman Routing untuk assign; fader monitor tidak ditampilkan untuk Group.
- Enter pada nama menyimpan dan berpindah ke channel berikutnya, termasuk melewati batas bank.
- Tabel lengkap tetap tersedia di bagian yang dapat dibuka di bawah panel detail. Aux/FX Return, Mixbus, DCA, routing, FX rack, import dan export tetap tersedia.

Penyimpanan Classic memakai `showfile_classic_v01`, terpisah dari versi utama. Saat pertama dibuka konfigurasi Classic mulai baru. Gunakan Import Scene untuk membawa file sebelumnya. Pengaturan link tetap mengikuti L ke R sesuai versi utama.

## Scene

Import M32/X32 `.scn` dan ekspor M32 menggunakan mesin V0.6.8.6. Warna inverse, CMB/LEC2 dari scene impor, sumber INS/M/C/LR/OFF dan anggota DCA Aux/FX dipertahankan. Pilihan WING tetap Coming soon.

Aturan ekspor lama tetap berlaku: master Bus/Matrix −∞ dan pasangan stereo mengikuti L. Ini bukan koneksi remote/live mixer.

## Visitor tracker

Blok asli dipertahankan persis, termasuk baris berikut satu kali:

```html
<script src="./visitor-tracker.js"></script>
```

## Validasi

Pengujian otomatis JavaScript dan simulasi DOM lulus:

- Startup serta ekspor untuk Monitor, FOH dan FOH + Monitor.
- Delapan strip, empat bank, slot tidak aktif, Gate/EQ/Comp dan fader send nyata.
- OFF pada fader, level desimal pada panel, send stereo dan hasil SCN.
- Nama + Enter melewati batas bank dan penyimpanan terpisah.
- DCA Aux/FX, link/unlink, inverse colour dan routing FX.
- Impor file TIARA basic MON.scn asli, ekspor dan baca ulang; parameter FX asli dipertahankan.
- Blok tracker dan template.scn tidak berubah.

Pratinjau browser lokal tidak dapat diakses karena koneksi timeout. Tampilan serta interaksi sentuh belum diverifikasi langsung di ponsel/Telegram atau console fisik.
