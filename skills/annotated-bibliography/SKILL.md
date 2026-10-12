---
name: annotated-bibliography
description: Membuat sitasi dan anotasi yang dapat ditelusuri untuk setiap karya lengkap, serta inventaris seluruh referensi riset. Pakai untuk catatan deskriptif, sumatif, evaluatif, reflektif, atau gabungan; gunakan literature-review bila pengguna memerlukan sintesis argumen lintas sumber.
---

# Annotated bibliography

Hasil pokok adalah satu sitasi dan satu anotasi per karya yang telah dibaca lengkap. Inventaris dapat mencakup semua referensi yang ditemukan, termasuk yang teks lengkapnya masih tertahan, dengan status yang jelas. Contoh paper dan angka dari bahan ajar atau sumber sekunder harus diperiksa pada karya aslinya sebelum dipakai sebagai bukti riset.

## Penggunaan model dan subtugas paralel

Untuk pencarian teks lengkap, pengambilan metadata, dan verifikasi DOI, gunakan tool deterministik lebih dulu, terutama resolusi `https://doi.org/<DOI>` dan halaman resmi penerbit. Jika subtugas itu memerlukan agent dan lingkungan mendukung pemilihan model, berikan kepada model termurah yang mampu memenuhi syarat bukti, dengan reasoning effort `medium` atau padanannya. Contohnya GPT-6 Luna, GPT-5.6 Terra, atau Claude Sonnet bila tersedia dan biayanya sesuai di lingkungan aktif. Jangan menganggap urutan harga, ketersediaan, atau nama model berlaku di semua harness.

Bagi kumpulan referensi yang independen kepada beberapa agent agar pencarian dan verifikasi dapat berjalan paralel, selama biaya koordinasi tetap masuk akal. Berikan ID dan cakupan yang tidak tumpang tindih. Minta setiap agent mengembalikan DOI, hasil resolusi, URL resmi, metadata yang cocok, status teks lengkap, dan ketidakpastian. Agent yang juga membaca karya wajib mengakses versi lengkap dan mencatat lokasi bukti. Agent utama memeriksa hasil sebelum memasukkan sitasi atau klaim ke keluaran. Jika pemilihan model atau agent paralel tidak tersedia, jalankan langkah yang sama dengan tool dan model aktif. Berkas skill ini sendiri tidak mengubah model sesi yang sedang berjalan.

## 1. Tetapkan masukan dan pilihan

Terima satu atau lebih URL, path file atau folder, atau attachment. Ambil tujuan riset, pertanyaan yang dibantu bibliografi, gaya sitasi, bahasa, dan cakupan referensi. Jika pengguna meminta semua referensi dalam suatu riset, periksa naskah, daftar pustaka, dan berkas rujukan dalam scope untuk membedakan karya yang disitasi, terdaftar, tersedia lengkap, dan belum tersedia.

Setelah inventaris awal, tampilkan kelompok checkbox dan minta pengguna memilih hal yang belum ditetapkan. Kotak hanya boleh dicentang setelah pengguna memilihnya secara eksplisit, termasuk melalui permintaan awal. Jangan mencentang berdasarkan tebakan, rekomendasi, pilihan pertama antarmuka, atau format yang biasa dipakai. Permintaan awal yang sudah eksplisit adalah jawaban; jangan meminta konfirmasi ulang untuk pilihan itu. Gunakan `- [ ]` bila antarmuka tidak menyediakan checkbox interaktif. Hindari antarmuka yang otomatis memilih opsi pertama; gunakan daftar checkbox teks dan minta balasan nomor atau nama opsi bila perlu.

- **Tipe anotasi, pilih satu atau gabungan:** deskriptif; sumatif; evaluatif; reflektif; gabungan. Untuk gabungan, minta pengguna memilih dua sampai empat fungsi.
- **Isi tambahan, pilih beberapa:** kata kunci; metode dan data; hasil; keterbatasan; kegunaan bagi riset; pertanyaan lanjutan; status verifikasi. Pilihan ini mengatur kedalaman rincian setelah overview wajib, bukan menghapus unsur overview.
- **Keluaran, pilih beberapa:** teks di respons; Markdown di respons; berkas Markdown; tabel inventaris; diagram Mermaid; ekspor SVG atau PNG; infografis PNG.
- **Jika infografis dipilih:** pilih karya yang digambarkan, audiens, bahasa, orientasi, gaya visual, tingkat detail, dan GPT Image atau Nano Banana bila tool-nya tersedia. Tawarkan pilihan ini sebelum membuat gambar.

Tunggu jawaban pengguna untuk tipe dan format keluaran yang belum dipilih sebelum menulis overview maupun anotasi. Tidak ada jawaban berarti belum ada pilihan; jangan menerapkan default diam-diam. Sambil menunggu, lanjutkan inventaris, pencarian teks lengkap, pembacaan, dan verifikasi. Jika tujuan atau pertanyaan riset diperlukan untuk menilai kegunaan dan refleksi, tanyakan bersama checkbox. Jika tabel dipilih dan aturan workspace mengharuskannya, tanyakan tabel di respons atau XLSX, lalu tunggu jawaban. Ikuti aturan lokasi dan otorisasi sebelum membuat berkas. Lihat [contoh penggunaan](references/example.md) bila perlu menunjukkan alur pilihan dan bentuk hasil.

## 2. Baca dan verifikasi setiap karya

1. Beri ID stabil untuk setiap karya. Cocokkan versi dan duplikat. Untuk URL, cari teks lengkap dari penerbit atau repositori yang sah. Abstrak, landing page, metadata, dan anotasi orang lain tidak memenuhi syarat pembacaan.
2. Baca setiap karya yang akan dianotasi dari awal sampai akhir. Periksa pendahuluan, definisi, argumen, metode, data, hasil, tabel dan gambar, pembahasan, kesimpulan, serta lampiran yang memengaruhi tafsir. Periksa hasil pindai secara visual dan koreksi OCR yang tidak pasti. Baca bagian sebelum dan sesudah bukti yang dikutip.
3. Catat judul dan nomor bab, section, serta subsection persis seperti sumber; bedakan halaman cetak dari nomor halaman PDF. Kaitkan temuan, angka, penilaian, dan batasan dengan bagian dan halaman yang tepat. Pisahkan hasil yang ditampilkan, tafsir penulis, dan penilaian agent.
4. Verifikasi identitas dan metadata. Jika DOI ada, resolusi DOI harus cocok dengan judul, penulis, tahun, dan venue. Periksa koreksi atau retraksi yang relevan. Ikuti kebijakan sitasi workspace yang lebih ketat. Jika verifikasi gagal, tandai `[UNVERIFIED]` dan jangan isi celah dari ingatan.

Jika teks lengkap tak dapat diperoleh, minta berkas atau aksesnya dari pengguna. Tetap tampilkan karya itu dalam inventaris dengan status `menunggu teks lengkap`, tanpa anotasi substantif. Jika publikasi tak memiliki heading bab atau bagian yang memenuhi kebutuhan visual, minta keputusan pengguna sebelum memasukkannya ke diagram atau infografis.

## 3. Tulis overview tiap sumber sebelum anotasi tipe

Setelah pilihan dijawab, mulai setiap entri dengan overview berlabel seperti contoh MPPI. Urutannya: **Sitasi; Pendahuluan; Tujuan dan Metode; Scope; Kegunaan; Batasan; Kesimpulan; Refleksi.** Sitasi formal menjadi bagian pertama overview, cukup ditulis sekali. Overview wajib untuk setiap karya lengkap, apa pun tipe anotasi yang dipilih. Tulis setiap unsur secara singkat, sesuai tujuan riset pengguna, dan sertakan judul bagian asli serta halaman untuk klaim penting. Jangan meminjam angka atau contoh paper dari slide MPPI tanpa memeriksa karya aslinya.

- **Sitasi:** penulis, tahun, judul, venue atau penerbit, dan DOI atau tautan resmi dalam gaya yang dipilih.
- **Pendahuluan:** tema, latar masalah, dan masalah atau pertanyaan yang dinyatakan penulis.
- **Tujuan dan Metode:** tujuan karya, desain atau cara penulis menelitinya, sumber data atau korpus, dan analisis. Untuk survei, jelaskan cara memilih studi bila dilaporkan. Bila data, protokol, atau metode tidak dilaporkan, tulis `tidak dilaporkan` pada unsur itu.
- **Scope:** objek, populasi atau domain, periode, dan batas cakupan yang benar-benar digunakan. Bedakan lingkup yang diteliti dari contoh aplikasi yang hanya disebut.
- **Kegunaan:** sumbangan spesifik karya bagi pertanyaan riset pengguna. Jangan menyamakan potensi penerapan dengan hasil yang sudah diuji.
- **Batasan:** batas data, desain, generalisasi, atau akses bukti. Bedakan batasan yang diakui penulis dari temuan kritik pembaca.
- **Kesimpulan:** hasil dan simpulan penulis dengan kekuatan klaim yang sesuai bukti. Bedakan hasil terukur, sintesis literatur, dan usulan.
- **Refleksi:** penilaian agent tentang bagian riset pengguna yang dapat memakai karya ini, apakah ia landasan utama atau pendukung, serta batas pemakaiannya. Jangan mengarang tujuan riset bila belum diberikan.

Untuk karya nonempiris, sesuaikan `Tujuan dan Metode`, `Scope`, dan `Batasan` dengan jenis karya; jangan mengisi sampel atau angka yang tidak ada. Overview memberi orientasi yang sama bagi semua entri. Anotasi tipe di bawahnya memperdalam fungsi yang dipilih tanpa mengulang overview.

## 4. Tulis anotasi menurut tipe dan tips MPPI

- **Deskriptif:** mulai dari penulis, judul, dan jenis sumber yang sudah tercantum dalam sitasi. Jelaskan fitur, isi, susunan bagian, dan kata kunci sumber. Pilih ciri lain yang penting bagi konteks riset pengguna. Ringkas dan efisien. Baca sumber lengkap sebelum memilih ciri yang ditonjolkan.
- **Sumatif:** pilih argumen, pendekatan, data, dan hasil utama yang menjawab kebutuhan riset pengguna. Putuskan informasi yang perlu dihilangkan agar ringkas. Nyatakan kata kunci serta argumen dengan kata sendiri, tanpa menyalin atau mengaburkan makna penulis. Pisahkan hasil yang ditunjukkan dari kemungkinan manfaat yang hanya diusulkan.
- **Evaluatif:** nilai kontribusi, kelengkapan, keterpercayaan, keandalan, dan nilai sumber bagi konteks riset pengguna. Periksa hubungan masalah, tujuan, metode, data, analisis, dan kesimpulan. Uji kekuatan dan kelemahan dengan bukti spesifik serta lokasi bagian. Kritik yang kreatif tetap harus setia pada fakta; reputasi venue saja tidak cukup.
- **Reflektif:** jelaskan secara spesifik di mana dan bagaimana sumber akan dipakai dalam rancangan atau argumen riset pengguna. Tentukan perannya sebagai landasan utama atau pendukung, batas penerapan, dan langkah lanjut yang masuk akal. Nyatakan ini sebagai penilaian untuk riset pengguna. Tulis ringkas tanpa mengulang ringkasan isi.
- **Gabungan:** pilih dua sampai empat fungsi yang dikonfirmasi pengguna. Mulai dari deskripsi singkat bila deskriptif dipilih, lalu susun fungsi lain sesuai kebutuhan. Tetapkan dahulu hal yang ingin dicari dan kaitannya dengan riset pengguna. Satukan tanpa pengulangan serta beri label fungsi bila membantu pembaca.

Tips ini berasal dari `MPPI 2 - Annotated Bibliography.pdf`, terutama slide 9, 11, 13, 15, dan 17, serta unsur overview pada `MPPI 2 - Literature Review  Annotated Bibliography.pdf`, slide 15 sampai 19. Gunakan gaya sitasi yang diminta. Urutkan entri secara alfabetis kecuali pengguna memilih urutan tematik atau kronologis. Cantumkan lokasi bagian untuk klaim penting.

## 5. Buat tabel seluruh referensi bila diminta

Beri satu baris untuk setiap referensi dalam cakupan, termasuk yang belum dapat dianotasi. Kolom inti: ID; sitasi singkat; tahun; DOI atau tautan resmi; status hubungan dengan naskah; status akses dan pembacaan; tipe sumber; topik atau kata kunci; metode dan data; hasil yang relevan; keterbatasan; kegunaan bagi riset; judul bagian dan halaman bukti; status verifikasi. Sesuaikan kolom dengan pertanyaan riset dan format yang dipilih. Jangan menempatkan isi hasil atau kritik pada baris sumber yang belum dibaca lengkap.

## 6. Buat visual bila dipilih

Untuk hubungan sumber dan tema, gunakan Mermaid `flowchart`. Setiap simpul yang menjelaskan isi literatur wajib menyertakan ringkasan klaim, ID, serta nomor dan judul bab, section, atau subsection asli, ditambah halaman bila tersedia. Pisahkan klaim dari karya berbeda ke simpul berbeda. Tandai tema yang dirumuskan agent sebagai `Sintesis`. Hubungan kesamaan, perbedaan, dan pengaruh hanya boleh dinyatakan bila tercatat dalam karya. Sertakan legenda ID ke sitasi dan lokasi bukti.

Untuk infografis, susun teks tiap simpul dan hubungan dari catatan bukti sebelum memakai GPT Image atau Nano Banana yang tersedia. Periksa seluruh teks, angka, nomor bagian, dan relasi pada gambar. Perbaiki atau buat ulang kesalahan. Jika label tetap keliru, jangan serahkan gambar sebagai hasil terverifikasi; berikan diagram Mermaid dan jelaskan keterbatasannya. Simpan berkas akhir sesuai aturan workspace.

## 7. Periksa hasil

Jumlah entri substantif harus sama dengan jumlah karya lengkap yang diterima, atau setiap pengecualian harus dijelaskan. Pastikan setiap entri menampilkan overview sebelum anotasi tipe dan seluruh fungsi pilihan mengikuti tipsnya. Periksa bahwa tidak ada kotak yang dicentang tanpa pilihan eksplisit dan penulisan menunggu jawaban yang diperlukan. Periksa sitasi, DOI, lokasi bukti, konsistensi gaya, perbedaan isi sumber dari tafsir agent, serta kesesuaian refleksi dengan tujuan pengguna. Tampilkan daftar karya yang masih memerlukan teks lengkap.
