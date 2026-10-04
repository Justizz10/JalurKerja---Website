# Jalurkerja

Landing page pencarian kerja berbasis **HTML dan CSS murni** (tanpa JavaScript, tanpa framework). Pengguna dapat mencari lowongan, mengecek kecocokan profil dengan syarat pekerjaan, menyimpan lowongan, dan mensimulasikan alur melamar dari awal sampai akhir.

> Proyek ini dibuat sebagai prototipe untuk tugas UX/UI. Semua data lowongan, perusahaan, dan gaji adalah contoh.

![Tampilan Jalurkerja](screenshot.png)

**Demo:** `https://USERNAME.github.io/NAMA-REPO/` *(ganti setelah GitHub Pages aktif)*

---

## Fitur

| Fitur | Keterangan |
|---|---|
| Pencarian lowongan | Saring berdasarkan posisi dan lokasi dari bagian hero. |
| Kategori pekerjaan | Saring daftar lowongan berdasarkan bidang (Bisnis, Operasional, Design, Finance, Marketing). |
| Profil kamu | Pilih keahlian dan pengalaman sebelumnya. Pengalaman dihitung sebagai keahlian setara (transferable skills). |
| Indikator kecocokan | Setiap lowongan menampilkan jumlah syarat yang cocok dengan profil, dalam bentuk bar dan teks. |
| Penjelasan syarat | Di detail lowongan, tiap syarat diberi arti singkat dan status "Cocok" atau "Belum ada". |
| Simpan lowongan | Ikon hati pada kartu lowongan, dengan filter "Tersimpan". |
| Alur lamaran | Detail lowongan, unggah CV, konfirmasi, lalu layar berhasil. |
| Responsif | Tata letak menyesuaikan desktop, tablet, dan ponsel. |

## Alur pengguna

```
Landing page → Lihat layanan → Daftar lowongan → Cari / filter
→ Detail lowongan → Sesuai? ──Tidak──► kembali ke daftar
                        │
                       Ya
                        ▼
        Lamar sekarang → Unggah CV → Konfirmasi → Lamaran berhasil
```

## Dasar perancangan

Fitur kecocokan profil, pencarian, dan penyimpanan disusun dari hasil *gap analysis* terhadap tiga persona pengguna.

| Persona | Kebutuhan utama | Jawaban di prototipe |
|---|---|---|
| Kevin (fresh graduate) | Tahu apakah memenuhi syarat dan apa artinya | Penjelasan tiap syarat dan indikator kecocokan |
| Maya (transisi karier) | Pengalaman lama dinilai relevan | Pilihan pengalaman sebelumnya sebagai keahlian setara |
| Arif (freelance) | Tahu apakah portofolio cocok dengan posisi | Portofolio sebagai salah satu syarat yang bisa dicocokkan |
| Semua | Mencari dan menyimpan lowongan relevan | Filter posisi, lokasi, kategori, dan fitur simpan |

## Teknologi

- HTML5
- CSS3: variabel CSS, grid, flexbox, `:has()`, `:target`, `:checked`, dan CSS counter
- Font [Inter](https://fonts.google.com/specimen/Inter) lewat Google Fonts

Interaksi (modal, filter, kecocokan profil, simpan) memakai trik CSS, bukan JavaScript:

- **Modal dan alur lamaran** memakai `:target` pada anchor `#id`.
- **Filter kategori, posisi, dan lokasi** memakai input tersembunyi dan selektor `:has()`.
- **Hitungan kecocokan dan jumlah tersimpan** memakai `counter-increment`.

## Struktur proyek

```
.
├── index.html     # struktur halaman dan data lowongan
├── style.css      # seluruh gaya, filter, dan animasi
├── logo.png       # logo dan favicon
└── README.md
```

## Cara menjalankan

Tidak perlu instalasi.

```bash
git clone https://github.com/USERNAME/NAMA-REPO.git
cd NAMA-REPO
```

Lalu buka `index.html` langsung di browser, atau jalankan server lokal:

```bash
python3 -m http.server 8000
# buka http://localhost:8000
```

### Deploy dengan GitHub Pages

1. Buka **Settings → Pages** di repo.
2. Pada *Build and deployment*, pilih **Deploy from a branch**.
3. Pilih branch `main` dan folder `/ (root)`, lalu simpan.
4. Tunggu beberapa menit, situs tersedia di URL Pages repo Anda.

## Kompatibilitas browser

Butuh browser modern yang mendukung `:has()`: Chrome, Edge, Safari, dan Firefox versi terbaru. Di browser lama, filter dan indikator kecocokan tidak akan berfungsi.

## Keterbatasan

Karena tanpa JavaScript dan tanpa backend:

- Pencarian memakai pilihan posisi dan lokasi, bukan kolom ketik bebas.
- Kombinasi filter yang tidak menghasilkan lowongan menampilkan area kosong tanpa pesan.
- Profil, lowongan tersimpan, dan CV yang diunggah tidak disimpan. Semuanya hilang saat halaman dimuat ulang.
- Layar konfirmasi lamaran bersifat umum dan tidak menampilkan data yang diisi.
- Kecocokan profil hanya perkiraan sederhana (syarat terpenuhi dari 4), bukan penilaian perekrut.

## Rencana pengembangan

- [ ] Kolom pencarian kata kunci dengan JavaScript
- [ ] Penyimpanan profil dan lowongan tersimpan (`localStorage` atau backend)
- [ ] Ringkasan data pada layar konfirmasi lamaran
- [ ] Pesan "tidak ada hasil" untuk kombinasi filter kosong
- [ ] Mode terang

## Lisensi

Tentukan lisensi proyek Anda, misalnya [MIT](https://choosealicense.com/licenses/mit/), lalu tambahkan file `LICENSE`.

## Kontak

Dibuat oleh **NAMA ANDA** · [GitHub](https://github.com/USERNAME)
