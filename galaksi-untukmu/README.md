# Galaksi Untukmu 💫

Web galaksi 3D: hati partikel berdetak di tengah, cincin cahaya, lengan spiral,
kalimat + emoji + **foto** yang mengorbit. Ketuk tulisan/emoji/foto untuk membuka kartu pesan.

## Isi folder
- `index.html`  → seluruh web (semua pengaturan ada di bagian `CONFIG` paling bawah)
- `foto1.jpg`, `foto2.jpg`, `foto3.jpg` → foto contoh (ganti dengan fotomu)
- `musik.mp3` → **belum ada**, taruh lagumu dengan nama ini (atau ubah namanya di CONFIG)

## 1. Mengganti musik
1. Siapkan file lagu berformat `.mp3`.
2. Taruh di folder yang sama dengan `index.html`, lalu beri nama `musik.mp3` (menimpa yang lama).
3. Atau pakai nama lain, lalu ubah di `CONFIG`:
   ```js
   musik: { url: 'lagu-kita.mp3', volume: 0.7 },
   ```
4. Bisa juga memakai link langsung ke file mp3 (`https://.../lagu.mp3`). Kosongkan (`url: ''`) kalau tidak mau musik.

Catatan: musik baru bisa bunyi setelah pengunjung mengetuk tombol "Sentuh di sini" (aturan browser).
Hindari nama file dengan spasi. Pakai huruf kecil dan tanda minus, contoh `lagu-kita.mp3`.

## 2. Menambahkan foto
1. Taruh foto di folder yang sama dengan `index.html` (disarankan JPG/WEBP, lebar maksimal ±1200px, tiap file di bawah 500 KB biar ringan di HP).
2. Tambahkan barisnya di `CONFIG`:
   ```js
   foto: {
       daftar: [
           { src: 'foto1.jpg', teks: 'Kenangan pertama kita' },
           { src: 'foto-liburan.jpg', teks: 'Liburan bareng' },   // <- baris baru
       ],
       ulang: 3,
   ```
3. `ulang` = berapa kali tiap foto muncul mengorbit. Kalau fotomu banyak, kecilkan (1–2) supaya tidak berat.
4. Foto yang namanya salah/tidak ada akan dilewati (cek lewat Console browser).

## 3. Mengubah tulisan
Di `CONFIG`: `judul`, `frasa` (kalimat yang mengorbit), `pesanKartu` (pesan di kartu), `emoji`, dan warna.

## 4. Mempublish lewat GitHub Pages (gratis)

### Cara paling mudah (tanpa install apa pun)
1. Buat akun di https://github.com lalu klik **+** → **New repository**.
2. Nama repo bebas, misal `galaksi-untukmu`. Pilih **Public**. Klik **Create repository**.
3. Klik **uploading an existing file** (atau **Add file → Upload files**).
4. Pilih/seret **semua file** (`index.html`, foto, musik) lalu klik **Commit changes**.
   `index.html` harus berada di halaman paling depan repo, bukan di dalam folder lain.
5. Buka **Settings → Pages**. Di *Build and deployment*, pilih **Source: Deploy from a branch**,
   **Branch: main**, folder **/ (root)**, klik **Save**.
6. Tunggu 1–3 menit. Linkmu: `https://USERNAME.github.io/galaksi-untukmu/`
   (USERNAME = nama akun GitHub-mu). Kirim link itu ke orangnya.

### Lewat Git (kalau sudah terpasang)
```bash
cd galaksi-untukmu
git init
git add .
git commit -m "galaksi pertama"
git branch -M main
git remote add origin https://github.com/USERNAME/galaksi-untukmu.git
git push -u origin main
```
Lalu aktifkan Pages seperti langkah 5 di atas.

### Mengubah setelah publish
Buka file di repo → ikon pensil (edit) atau **Add file → Upload files** untuk menimpa → **Commit changes**.
Tunggu sebentar lalu refresh (kalau masih versi lama, buka dengan Ctrl+F5 atau tab penyamaran).

## Mencoba di komputer sebelum upload
Membuka `index.html` dengan klik dua kali bisa membuat foto tidak tampil (aturan keamanan browser).
Jalankan server lokal:
```bash
python3 -m http.server 8000
```
lalu buka http://localhost:8000
