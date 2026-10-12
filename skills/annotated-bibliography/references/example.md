# Contoh interaksi annotated-bibliography

Contoh ini menunjukkan urutan pilihan, overview, dan anotasi. Slot dalam tanda kurung siku diisi hanya setelah karya lengkap dibaca dan metadata diverifikasi. Tidak ada pilihan otomatis.

## Input pengguna

> Buat bibliografi beranotasi untuk paper agentic AI yang saya lampirkan. Topik riset saya ialah peran agen dalam digital twin klinis.

## Checkbox setelah inventaris awal

**Tipe anotasi, pilih satu atau gabungan**

- [ ] Deskriptif
- [ ] Sumatif
- [ ] Evaluatif
- [ ] Reflektif
- [ ] Gabungan, sebut dua sampai empat fungsi

**Isi tambahan, pilih beberapa**

- [ ] Kata kunci
- [ ] Metode dan data
- [ ] Hasil
- [ ] Keterbatasan
- [ ] Kegunaan bagi riset
- [ ] Pertanyaan lanjutan
- [ ] Status verifikasi

**Keluaran, pilih beberapa**

- [ ] Teks di respons
- [ ] Markdown di respons
- [ ] Berkas Markdown
- [ ] Tabel inventaris
- [ ] Diagram Mermaid
- [ ] Ekspor SVG atau PNG
- [ ] Infografis PNG

Tunggu jawaban pengguna untuk tipe dan keluaran. Baca dan verifikasi paper selama menunggu. Jangan menganggap pilihan pertama sebagai jawaban. Jika tabel dipilih, tanyakan apakah pengguna menginginkan tabel di respons atau XLSX ketika aturan workspace mewajibkannya. Jika infografis dipilih, tanyakan karya, audiens, bahasa, orientasi, gaya, detail, dan tool gambar.

## Contoh jawaban pengguna

> Gabungan deskriptif, evaluatif, dan reflektif. Tambahkan kata kunci, keterbatasan, dan status verifikasi. Tampilkan Markdown di respons.

Jawaban itu mengizinkan ketiga fungsi dan format yang disebut. Kotak lain tetap tidak dipilih. Lanjutkan setelah paper lengkap dibaca.

## Bentuk keluaran untuk setiap karya lengkap

**S1. Overview**

- **Sitasi:** [Sitasi lengkap terverifikasi dengan DOI atau tautan resmi].
- **Pendahuluan:** [Tema dan masalah yang dinyatakan penulis; bagian dan halaman].
- **Tujuan dan Metode:** [Tujuan, desain, sumber data atau korpus, analisis; tulis `tidak dilaporkan` untuk unsur yang absen].
- **Scope:** [Objek, domain, waktu, dan batas cakupan yang benar-benar diteliti].
- **Kegunaan:** [Kontribusi spesifik bagi pertanyaan pengguna].
- **Batasan:** [Batas yang dilaporkan penulis dan batas tambahan dari audit, dibedakan dengan jelas].
- **Kesimpulan:** [Simpulan penulis dengan tingkat kepastian yang sesuai bukti].
- **Refleksi:** [Peran karya sebagai landasan utama atau pendukung dan batas pemakaiannya dalam riset pengguna].

**Anotasi gabungan, deskriptif:** [Jenis, kata kunci, struktur, dan ciri karya yang paling relevan. Ringkas.]

**Anotasi gabungan, evaluatif:** [Kontribusi, kekuatan dan kelemahan metode atau bukti, serta pengaruhnya pada simpulan. Tunjukkan lokasi bagian dan halaman.]

**Anotasi gabungan, reflektif:** [Di mana dan bagaimana karya akan dipakai dalam rancangan riset pengguna, tanpa mengulang overview.]

Untuk sumber yang masih menunggu teks lengkap, tampilkan identitas dan status akses saja. Jangan tulis overview atau anotasi substantif. Untuk diagram atau infografis yang dipilih, setiap simpul penjelasan memakai `[ringkasan klaim] | S1 | [nomor dan judul bagian asli] | [halaman]`, disertai legenda sitasi.
