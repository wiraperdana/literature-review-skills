# Literature Review

Repo ini memuat dua skill agent untuk bekerja dengan literatur akademik:

- [`literature-review`](skills/literature-review/SKILL.md) untuk menelusuri dan menyintesis bukti lintas sumber.
- [`annotated-bibliography`](skills/annotated-bibliography/SKILL.md) untuk membuat catatan terverifikasi per sumber dan inventaris referensi.

Skill ini dapat dibaca oleh Claude Code, Codex, atau agent lain yang mendukung berkas `SKILL.md`. Ia memakai kemampuan pencarian dan pembacaan sumber yang tersedia pada agent. Tidak ada layanan atau kredensial yang dibundel. Setiap folder skill berdiri sendiri; berkas dalam `references/` dibaca saat contohnya diperlukan.

## Pemakaian

Di dalam checkout repo, minta agent membaca `SKILL.md` yang sesuai dan mengerjakan pertanyaan riset Anda. Contoh:

> Pakai skill `literature-review` untuk [pertanyaan riset]. Sumber awal: [URL, path berkas atau folder, atau attachment]. Tampilkan pilihan jenis review, teknik, peta, dan format keluaran sebelum menyusun hasil.

> Pakai skill `annotated-bibliography` untuk menganotasi sumber dalam [URL, path berkas atau folder, atau attachment] terhadap pertanyaan riset [pertanyaan]. Tampilkan checkbox tipe anotasi dan format keluaran tanpa pilihan otomatis, lalu tunggu jawaban saya. Untuk setiap sumber, tulis overview sebelum anotasi menurut tipe pilihan saya.

Untuk pemasangan sebagai skill pengguna, salin folder skill yang diinginkan dari `skills/` ke direktori skill milik agent yang dipakai. Repo ini menyimpan sumber aslinya; perubahan dilakukan di sini sebelum disalin lagi.

Contoh input, checkbox, dan bentuk output ada di [contoh literature review](skills/literature-review/references/example.md) dan [contoh annotated bibliography](skills/annotated-bibliography/references/example.md). Keduanya memakai topik agentic AI dan digital twin sebagai ilustrasi, dengan slot untuk sitasi dan heading yang harus diisi dari literatur lengkap.

Kedua skill memerlukan pembacaan setiap literatur lengkap dari awal sampai akhir, termasuk bagian yang memengaruhi tafsir hasil. Jika URL hanya membuka abstrak atau metadata dan teks lengkap tidak tersedia, agent meminta pengguna menyediakan versi lengkapnya. Pilihan disajikan sebagai checkbox. Pada `annotated-bibliography`, pilihan yang belum dinyatakan tetap kosong dan anotasi menunggu jawaban pengguna. Setiap entri diawali overview berisi sitasi, pendahuluan, tujuan dan metode, scope, kegunaan, batasan, kesimpulan, dan refleksi. Diagram memakai Mermaid `flowchart` sebagai sumber yang dapat diperiksa, dengan SVG atau PNG sebagai ekspor bila dipilih.

Pengguna juga dapat memilih infografis dari literatur tertentu. Agent menyiapkan teks simpul dari sumber yang telah dibaca utuh, lalu membuat gambar dengan GPT Image jika tool tersedia. Setiap simpul yang menjelaskan isi sumber mencantumkan judul bab atau bagian asli, ID sumber, dan halaman bila tersedia. Teks serta hubungan pada gambar diperiksa terhadap sumber sebelum diserahkan. Jika hasil gambar tetap keliru, diagram Mermaid menjadi keluaran yang dapat diperiksa. Infografis baru dibuat setelah pengguna memilih sumber dan preferensi visualnya.

## Materi rujukan

Folder `sources/` berisi empat PDF perkuliahan MPPI Pekan 2 yang diberikan Wira. Seluruh halamannya dibaca saat menyusun skill, termasuk gambar contoh peta literatur. Materi menjelaskan pencarian kata kunci dan penyesuaiannya, lima teknik review, peta topik ke subtopik dan referensi, lima tipe anotasi, serta perbedaan anotasi per sumber dari sintesis lintas sumber. Contoh nama paper dan angka pada slide adalah bahan ajar; identitas serta hasil paper harus diverifikasi dari publikasi aslinya sebelum dikutip sebagai bukti riset.

## Batas saat ini

Skill berisi prosedur umum. Materi kuliah di `sources/` bukan korpus paper yang sudah lolos seleksi. Repo ini belum menyertakan protokol tinjauan untuk topik tertentu, otomasi basis data, atau uji pada paper riset nyata. Setiap tinjauan tetap memerlukan pertanyaan riset dan akses ke sumber yang relevan.

## Versi publik

Repo ini private dan menyimpan semuanya, termasuk slide MPPI di `sources/`. Versi publiknya ada di `github.com/wiraperdana/literature-review-skills`, tanpa folder `sources/`, karena slide itu karya dosen pengampu. Daftar pengecualiannya ada di `.publik-kecuali`.

```sh
scripts/terbitkan_publik.sh --cek   # lihat berkas yang akan terbit
scripts/terbitkan_publik.sh         # bangun commit publik lalu push ke remote "publik"
```
