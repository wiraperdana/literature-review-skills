---
name: literature-review
description: Menyusun tinjauan literatur yang menilai dan menyintesis karya lengkap lintas sumber. Pakai untuk pertanyaan riset, peta literatur, perbandingan temuan, atau identifikasi celah bukti; gunakan annotated-bibliography untuk catatan yang berdiri sendiri per referensi.
---

# Literature review

Jawab pertanyaan riset melalui sintesis lintas karya. Jika hanya satu karya lengkap tersedia, nyatakan batas perbandingan lintas sumber dan cari tambahan hanya bila pengguna mengizinkan. Contoh paper dan angka dari bahan ajar atau sumber sekunder harus diperiksa pada karya aslinya sebelum dipakai sebagai bukti riset.

## Penggunaan model dan subtugas paralel

Untuk pencarian karya, pengambilan metadata, dan verifikasi DOI, gunakan tool deterministik lebih dulu, terutama resolusi `https://doi.org/<DOI>` dan halaman resmi penerbit. Jika subtugas itu memerlukan agent dan lingkungan mendukung pemilihan model, berikan kepada model termurah yang mampu memenuhi syarat bukti, dengan reasoning effort `medium` atau padanannya. Contohnya GPT-6 Luna, GPT-5.6 Terra, atau Claude Sonnet bila tersedia dan biayanya sesuai di lingkungan aktif. Jangan menganggap urutan harga, ketersediaan, atau nama model berlaku di semua harness.

Bagi kumpulan referensi atau basis data pencarian yang independen kepada beberapa agent agar pencarian dan verifikasi dapat berjalan paralel, selama biaya koordinasi tetap masuk akal. Berikan cakupan, kueri, dan ID sumber yang tidak tumpang tindih. Minta setiap agent mengembalikan DOI, hasil resolusi, URL resmi, metadata yang cocok, status teks lengkap, catatan penyaringan, dan ketidakpastian. Agent yang juga membaca karya wajib mengakses versi lengkap dan mencatat lokasi bukti. Agent utama memeriksa hasil sebelum memakai sitasi atau klaim dalam sintesis. Jika pemilihan model atau agent paralel tidak tersedia, jalankan langkah yang sama dengan tool dan model aktif. Berkas skill ini sendiri tidak mengubah model sesi yang sedang berjalan.

## 1. Tetapkan masukan dan pilihan

Terima satu atau lebih URL, path file atau folder, atau attachment. Inventaris karya yang diberikan, versi, duplikat, dan status akses teks lengkapnya. Ambil pertanyaan riset, konteks atau populasi, batas waktu, bahasa, serta sumber tambahan yang boleh dicari. Jika pertanyaan belum ada, bantu rumuskan dari tujuan pengguna. Jangan memilih periode atau menyebut seorang penulis penting hanya berdasarkan ingatan.

Sebelum analisis substantif, tampilkan kelompok checkbox berikut. Tandai pilihan yang sudah dinyatakan pengguna. Tanyakan pilihan yang benar-benar diperlukan; lanjutkan inventaris dan pemeriksaan akses sambil menunggu. Pengguna dapat memilih beberapa teknik dan format. Tampilkan `- [ ]` bila antarmuka tidak menyediakan checkbox interaktif.

- **Jenis review, pilih satu:** naratif; kritis; pemetaan literatur; scoping; sistematis.
- **Teknik, pilih sesuai tujuan:** membandingkan; mengontraskan; mengkritik; menyintesis; meringkas.
- **Peta, pilih beberapa:** tema dan subtema; hubungan konsep; metode dan hasil; kronologi; penulis atau karya yang berpengaruh; perbedaan dan celah bukti.
- **Keluaran, pilih beberapa:** teks di respons; Markdown di respons; berkas Markdown; daftar kata kunci dan kueri; tabel; diagram Mermaid; ekspor SVG atau PNG; infografis PNG.
- **Jika infografis dipilih:** pilih karya yang digambarkan, audiens, bahasa, orientasi, gaya visual, tingkat detail, dan GPT Image atau Nano Banana bila tool-nya tersedia. Tawarkan pilihan ini, jangan langsung membuat gambar.

Jika pengguna memilih tabel, tanyakan apakah tabel cukup di respons atau perlu XLSX ketika aturan workspace mengharuskannya. Jika berkas dipilih, ikuti aturan lokasi dan otorisasi workspace. Lihat [contoh penggunaan](references/example.md) hanya bila perlu memperlihatkan input, checkbox, atau bentuk hasil.

## 2. Tentukan jenis review secara jujur

- **Naratif:** sintesis terarah, jelaskan cara memilih sumber dan batas cakupan.
- **Kritis:** sintesis ditambah pengujian asumsi, metode, bukti, dan penjelasan alternatif.
- **Pemetaan literatur:** petakan kelompok topik, pendekatan, dan celah; jelaskan dasar pengelompokan.
- **Scoping:** tetapkan cakupan dan kriteria seleksi, lalu laporkan proses penelusuran dan pemetaan secara transparan.
- **Sistematis:** perlu protokol pertanyaan, sumber pencarian, kueri, tanggal, kriteria masuk dan keluar, proses penyaringan, penilaian studi, dan metode sintesis yang dapat diaudit. Bila elemen ini belum ada, sebut hasil sebagai rancangan atau review pendahuluan.

## 3. Dapatkan, baca, dan verifikasi karya lengkap

1. Untuk URL, buka publikasi lengkap dari penerbit atau repositori yang sah. Untuk folder dan attachment, identifikasi karya yang benar. Daftar pustaka, abstrak, landing page, dan ringkasan pihak lain hanya petunjuk pencarian. Jika karya lengkap tak tersedia, laporkan ID-nya dan minta file atau akses dari pengguna. Jangan memasukkan klaim substantifnya ke sintesis.
2. Baca setiap karya terpilih dari awal sampai akhir. Cakup definisi, kerangka teori, metode, data, hasil, tabel dan gambar, pembahasan, kesimpulan, serta lampiran yang memengaruhi interpretasi. Periksa halaman pindai dan elemen visual secara langsung; koreksi OCR yang meragukan. Baca konteks sebelum dan sesudah bagian yang akan dikutip.
3. Catat ID sumber, versi, judul, penulis, tahun, venue, DOI bila ada, jenis publikasi, serta status pembacaan. Verifikasi DOI dengan resolusi DOI dan cocokkan metadata dengan publikasinya bila DOI tersedia. Periksa koreksi atau retraksi yang relevan. Ikuti aturan sitasi workspace yang lebih ketat. Tandai `[UNVERIFIED]` jika verifikasi gagal; jangan mengisi metadata dari ingatan.
4. Petakan urutan bab, section, dan subsection dengan nomor serta judul asli. Catat halaman cetak dan nomor halaman PDF jika berbeda. Untuk setiap klaim penting, catat lokasi, kondisi berlakunya, kekuatan bukti, dan batas interpretasinya. Pisahkan pernyataan penulis, data yang ditampilkan, dan inferensi agent.

Nilai pertanyaan dan kontribusi karya, desain, sampel atau korpus, pengukuran, pembanding, analisis, ketidakpastian, keterbatasan, serta kecocokan hasil dengan klaim. Sesuaikan penilaian dengan studi empiris, karya teoretis, atau review. Jangan menyamakan reputasi venue dengan mutu setiap hasil.

## 4. Cari dan sintesis bila diperlukan

Jika pencarian tambahan diminta, turunkan kata kunci dari pertanyaan dan istilah yang dipakai karya lengkap. Catat sinonim, istilah lebih luas atau sempit, variasi ejaan, dan kueri Boolean. Catat basis data atau situs, kueri, tanggal, jumlah hasil, penyaringan, alasan pengecualian, dan penelusuran daftar pustaka. Jangan menggambarkan korpus kecil yang diberikan pengguna sebagai cakupan seluruh bidang.

Kelompokkan hasil menurut konsep dan pertanyaan, bukan urutan paper. Bandingkan temuan yang sejalan dan berlawanan beserta perbedaan desain atau konteksnya. Jelaskan perubahan metode dan konsep menurut tahun. Identifikasi penulis atau karya yang berpengaruh hanya dengan dasar yang bisa ditunjukkan, misalnya kontribusi awal atau hubungan sitasi yang terverifikasi. Sebut celah bukti bersama batas pencarian yang mendasarinya. Untuk setiap klaim penting, tautkan sumber dan lokasi bagian, lalu beri tingkat keyakinan yang sepadan.

## 5. Buat peta dan infografis

Gunakan Mermaid `flowchart` sebagai sumber peta yang dapat dibaca dalam Markdown dan diolah programmatically. Susun dari pertanyaan atau topik ke subtema, lalu ke simpul bukti. Labeli hubungan sesuai maknanya, seperti mendukung, berbeda konteks, atau bertentangan. Hubungan bibliometrik atau kausal hanya boleh dinyatakan bila datanya ada. Untuk rentang tahun, perlihatkan tahun publikasi karya yang benar-benar tercakup dan jelaskan kriteria periodisasinya. Ekspor SVG atau PNG hanya bila dipilih dan renderer tersedia.

**Setiap simpul yang menjelaskan isi literatur wajib memuat ringkasan klaim, ID sumber, dan nomor serta judul bab, section, atau subsection persis seperti dokumen.** Tambahkan halaman bila tersedia. Pisahkan klaim dari karya berbeda ke simpul berbeda agar lokasi bukti tidak kabur. Simpul kategori buatan agent diberi tanda `Sintesis`. Sertakan legenda ID ke sitasi lengkap dan lokasi bukti. Jangan mengarang heading. Jika karya tak memiliki pembagian bagian yang memenuhi syarat ini, minta keputusan pengguna sebelum karya itu masuk visual.

Untuk infografis, buat daftar teks simpul dan hubungan dari catatan bukti sebelum memanggil GPT Image atau Nano Banana yang tersedia. Sertakan label bagian asli di setiap simpul penjelasan. Periksa hasil secara visual terhadap daftar teks, sitasi, nomor bagian, dan hubungan. Perbaiki atau buat ulang kesalahan. Jika label tetap keliru, jangan serahkan gambar sebagai hasil terverifikasi; berikan peta Mermaid yang dapat diperiksa dan jelaskan keterbatasannya. Simpan berkas akhir sesuai aturan workspace.

## 6. Periksa hasil

Sajikan jawaban atau peta tematik, metode pemilihan sumber, daftar sumber yang dibaca lengkap, klaim beserta lokasi bukti, perbedaan hasil, batas sintesis, dan sumber yang tertahan. Periksa bahwa semua node dan klaim dapat ditelusuri ke karya yang benar, tidak ada sitasi rekaan, dan jenis review sesuai proses yang benar-benar dilakukan.
