# RAMALABS VMTS Studio v3.0

Aplikasi web **statis**, tanpa backend, untuk menyusun draf akademik yang dapat ditelaah: pemetaan VMTS PT dan UPPS, visi keilmuan Program Studi, kekhasan, CP/CPL/CPMK, contoh RPS 16 pertemuan, pembelajaran, kebijakan, roadmap 5 tahun, program kerja, serta 10 rekomendasi mata kuliah penciri dengan penelusuran literatur web opsional.

## Publikasikan melalui GitHub Pages

1. Buat repository baru di GitHub, misalnya `ramalabs-vmts-studio`.
2. **Unggah semua isi folder ini ke root repository** (pastikan `index.html` berada di root, bukan di dalam folder bertingkat).
3. Commit ke branch `main`.
4. Buka **Settings → Pages → Build and deployment → Deploy from a branch**, pilih `main` dan `/ (root)`, lalu **Save**.
5. Alamat publik biasanya `https://NAMA-AKUN.github.io/ramalabs-vmts-studio/` setelah publikasi selesai. Alternatif: untuk domain utama pengguna, gunakan nama repository `NAMA-AKUN.github.io`.

Tidak diperlukan `npm install`, Node.js, basis data, pustaka CDN, atau server backend. Fitur pencarian OpenAlex dapat dicoba tanpa API key menggunakan kuota anonim; kunci API gratis pengguna dapat dimasukkan secara opsional ketika dibutuhkan. Berkas Word dibuat langsung di browser sebagai dokumen Office Open XML (.docx). PDF menggunakan fitur cetak bawaan browser; tombol PDF tidak langsung mengunduh berkas tanpa dialog, karena implementasi ini tidak memakai pustaka PDF eksternal. Buka `index.html` langsung di browser untuk mencoba, walaupun beberapa tindakan clipboard mungkin memerlukan HTTPS.

## Cara penggunaan

1. Lengkapi identitas, fokus ilmu, keunggulan, kebutuhan mitra, dan mata kuliah contoh.
2. Salin VMTS resmi PT dan UPPS, dengan butir dipisah `;` atau baris baru.
3. Jalankan pemetaan keselarasan dan telaah indikatornya.
4. Buka halaman **Visi keilmuan PS**, baca definisi dan perbedaannya dengan visi kelembagaan, lalu klik **Hasilkan visi keilmuan** untuk menghasilkan 3 alternatif serta kriteria dan argumentasi akademik. Anda dapat menyunting rumusan secara langsung.
5. Jalankan **Generator keluaran** untuk membuat seluruh 13 draf akademik; revisi pada halaman **Telaah & sunting**.
6. Pada halaman **Visi keilmuan PS** klik **Unduh Word (.docx)** untuk mendapatkan dokumen khusus visi; atau **Cetak / Simpan PDF** untuk membuka dialog cetak browser.
7. Pada menu **10 MK penciri • riset web**, pilih **Susun 10 MK penciri**, lalu **Cari bukti web (OpenAlex)** ketika terhubung internet. Lihat status per mata kuliah; bukalah DOI yang ditemukan untuk menguji relevansinya. Seluruh judul, CPL, capaian, alasan dan strategi pembelajaran dapat disunting. Rekomendasi menyesuaikan rumpun PS (digital, pendidikan, bisnis, teknik, pertanian, kesehatan, hukum, atau umum). Tersedia ekspor Word dan cetak/PDF khusus 10 MK.
8. Pada **Ekspor & data**, unduh laporan lengkap dalam format **Word (.docx)**, **HTML**, **CSV**, dan **JSON**. Tombol **Cetak / Simpan PDF** akan membuka dialog pencetakan browser; pilih tujuan **Save as PDF / Simpan sebagai PDF** (atau printer fisik).

**Privasi:** Data proyek disimpan di `localStorage` browser pengguna dan tidak diunggah ke GitHub. Fitur riset web mengirimkan frasa pencarian topik (bahasa Inggris) ke OpenAlex (`api.openalex.org`) sebagai layanan eksternal; bukan VMTS lengkap, identitas institusi, atau isian lain. API key opsional tidak disimpan di proyek. Jangan menganggap penyimpanan browser sebagai arsip permanen. Ekspor JSON secara berkala.

**Metodologi dan batasan:** Algoritme keselarasan menghitung irisan kata bermakna setiap butir UPPS terhadap butir PT yang paling dekat. Angkanya bukan nilai kesesuaian semantik/akreditasi. Generator berbasis aturan deterministik, **bukan** AI/LLM; hasil merupakan draf awal, bukan dokumen yang otomatis patuh hukum atau siap disahkan. Contoh CPMK, RPS, kurikulum, dan program kerja harus divalidasi pakar, pemangku kepentingan dan pejabat berwenang. Acuan hukum perlu diperiksa terhadap Permendiktisaintek 39/2025 dan perubahannya 10/2026, serta aturan lembaga/akreditasi terkait.

## Struktur

- `index.html`: aplikasi lengkap, HTML + CSS + JavaScript mandiri.
- `.nojekyll`: memastikan GitHub Pages tidak memproses situs dengan Jekyll.
- `README.md`: panduan ini.

## Hak cipta

Copyright © 2026 ramalabs. All rights reserved. Tidak ada lisensi open-source yang diberikan secara tersirat. Bila repository dipublikasikan, perhatikan pengaturan visibilitas repo dan status kepemilikan konten.

## Pembaruan v3.0

- Menu tersendiri **Visi Keilmuan Program Studi** berisi definisi, perbedaan visi kelembagaan, enam kriteria perumusan, dan alternatif rumusan yang dapat diedit.
- Ekspor **DOCX asli** untuk rumusan visi atau laporan lengkap tanpa dependensi pihak ketiga.
- **Cetak / Simpan PDF** untuk rumusan visi dan laporan lengkap melalui dialog cetak browser (pilih simpan PDF). Untuk pencetakan, pastikan browser mengizinkan jendela baru/pop-up.
- Dokumen unduhan tetap merupakan **draf akademik** yang perlu review dan pengesahan.

## Pembaruan v3.0 — Rekomendasi 10 mata kuliah penciri

- Menu khusus dengan **10 usulan mata kuliah** mengikuti bidang PS, CPL usulan, alasan, contoh capaian dan strategi pembelajaran. Semua dapat disunting.
- **Penelusuran daring on-demand** pada publikasi ilmiah terindeks OpenAlex sejak 2021; maksimal dua rekaman per mata kuliah, tanpa server perantara. Proses ini butuh internet dan dibatasi kebijakan CORS, kuota API, serta ketersediaan layanan. Indikator keberhasilan tiap MK transparan.
- **Catatan metodologis:** Artikel ilmiah OpenAlex mendukung penilaian tren topik, tetapi **bukan bukti bahwa mata kuliah tersebut ada di universitas pembanding atau otomatis kompetitif**. Untuk benchmarking kurikulum perlu menelaah silabus nyata dari [MIT OpenCourseWare](https://ocw.mit.edu/search/), [OpenLearn](https://www.open.edu/openlearn/free-courses/full-catalogue), institusi sejenis, serta standar asosiasi profesi. Tautan tersebut merupakan rujukan katalog untuk verifikasi manual, bukan hasil pembandingan otomatis.
- Berkas DOCX dan cetak/PDF khusus **10 MK penciri**; laporan lengkap DOCX/HTML/PDF kini menyertakan 10 rekomendasi dan referensi ilmiah jika tersedia. JSON proyek mencakup daftar MK serta hasil penelusuran dan dapat diimpor ulang.
- Saat offline, atau jika OpenAlex tidak tersedia, aplikasi tetap menghasilkan rekomendasi awal, **berlabel belum terverifikasi dari web**.

### Risiko teknis / batasan

GitHub Pages hanya meng-host aset statis; karena itu pencarian web langsung dilakukan oleh browser pengguna melalui API OpenAlex yang menyediakan endpoint publik. Aplikasi **tidak** dapat melakukan crawling sembarang situs (CORS dan persyaratan akses berlaku), tidak menggantikan penilaian reviewer akademik, dan tidak menjamin setiap topik didukung hasil pencarian. Bila tombol *Cari bukti web* gagal, pemeriksaan status pada masing-masing MK menunjukkan kegagalan dan rekomendasi tetap tersedia untuk direvisi. Perubahan nama MK tidak otomatis mengubah kata kunci pencarian yang berasal dari rancangan topik awal; untuk memakai kata kunci baru buat kembali 10 rekomendasi setelah memperbarui konteks PS.

**Sumber API:** https://help.openalex.org/api/ dan https://help.openalex.org/api/authentication/.
