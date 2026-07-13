# Team Manifesto
## Tim Konsultan IT — Proyek "Aplikasi Mobile Kantin Pintar Kampus"

> Dokumen ini adalah kebijakan resmi tim untuk memastikan konflik komunikasi yang membuat tim sebelumnya bubar **tidak terulang kembali**. Setiap anggota wajib membaca dan menyepakati dokumen ini sebelum Sprint dimulai.

**Tim:** 3 anggota — Backend Developer, Frontend Developer, Scrum Master & QA
**Sisa waktu proyek:** 2 minggu
**Status awal:** 50% progres, kode berantakan, tanpa dokumentasi API

---

## Daftar Isi

1. [Latar Belakang Masalah](#1-latar-belakang-masalah)
2. [SOP Code Review](#2-sop-code-review)
3. [Protokol Komunikasi](#3-protokol-komunikasi)
4. [Komitmen Bersama](#4-komitmen-bersama)

---

## 1. Latar Belakang Masalah

Tim sebelumnya bubar karena tiga masalah utama yang manifesto ini secara spesifik dirancang untuk mencegah:

| Masalah Tim Lama | Akar Penyebab | Solusi di Manifesto Ini |
|---|---|---|
| Backend & Frontend saling menyalahkan | Format JSON berubah tanpa pemberitahuan | [SOP Code Review](#2-sop-code-review) + dokumentasi API wajib |
| Kritik kode terasa menyerang secara personal | Tidak ada standar bahasa saat review | [Aturan Bahasa Code Review](#22-bahasa-yang-dilarang-vs-dianjurkan) |
| Anggota burnout, komunikasi tidak terkendali | Tidak ada jam kerja yang disepakati | [Protokol Jam Komunikasi](#32-jam-kerja-komunikasi) |

---

## 2. SOP Code Review

### 2.1 Aturan Dasar

1. **Setiap perubahan pada struktur data (termasuk format JSON) wajib didiskusikan dan disetujui di channel `#backend-frontend-sync` SEBELUM di-push**, bukan setelahnya. Ini adalah aturan paling kritis karena inilah yang membubarkan tim sebelumnya.
2. Setiap *Pull Request* (PR) wajib direview oleh minimal 1 anggota lain sebelum di-merge ke branch utama. Tidak ada PR yang merge sendiri (*self-merge*) tanpa review, kecuali untuk perbaikan typo dokumentasi.
3. Reviewer wajib memberi respons (approve / request changes / comment) dalam waktu maksimal **12 jam** pada hari kerja, agar tidak menghambat progres tim yang sudah kekurangan waktu.
4. Kritik ditujukan pada **kode**, bukan pada **orang**. Setiap komentar review harus bisa dijawab dengan perbaikan teknis, bukan pembelaan diri.

### 2.2 Bahasa yang Dilarang vs Dianjurkan

Tujuan aturan ini: memastikan kritik membangun, bukan menyerang — sumber konflik utama tim sebelumnya.

|  Dilarang |  Dianjurkan | Mengapa |
|---|---|---|
| "Kode ini berantakan banget." | "Bagian ini bisa lebih rapi kalau dipecah jadi fungsi terpisah, gimana menurutmu?" | Fokus ke solusi, bukan penilaian personal |
| "Kok bisa kepikiran begini sih?" | "Aku kurang paham alasan di balik pendekatan ini, bisa dijelaskan? Mungkin ada cara lain yang lebih sesuai konvensi kita." | Mengajukan pertanyaan, bukan menghakimi |
| "Ini salah, ganti." | "Menurutku ada edge case yang belum tercover di sini (misal: input kosong). Boleh ditambahkan validasinya?" | Spesifik dan memberi alasan teknis |
| "Lagi-lagi format JSON-nya beda dari yang disepakati." | "Format response endpoint ini berbeda dari skema yang kita sepakati di dokumentasi. Bisa disesuaikan, atau apakah skemanya yang perlu diupdate bersama?" | Mengarahkan ke proses, bukan menyalahkan individu |
| "Lambat banget ngerjain ini." | "Aku lihat task ini masih *in progress*, ada yang bisa aku bantu supaya nggak menghambat task berikutnya?" | Menawarkan bantuan, bukan menekan |

### 2.3 Format Komentar Review yang Disarankan

Setiap komentar review sebaiknya mengikuti struktur singkat:

```
[Observasi] Apa yang dilihat di kode
[Pertanyaan/Saran] Pertanyaan klarifikasi atau usulan perbaikan
[Alasan] Mengapa hal ini penting (performa, konsistensi, bug potensial, dll.)
```

**Contoh:**
> *Observasi:* Endpoint `/menu` mengembalikan field `harga` sebagai string.
> *Saran:* Bisa diubah jadi number sesuai skema yang sudah kita sepakati?
> *Alasan:* Supaya frontend tidak perlu melakukan parsing tambahan dan menghindari bug perhitungan total seperti yang terjadi di tim sebelumnya.

### 2.4 Eskalasi Jika Terjadi Perbedaan Pendapat

Jika Backend Dev dan Frontend Dev tidak sepakat setelah 2 kali bertukar komentar di PR:

1. Pindahkan diskusi ke *voice/video call* singkat (maks. 15 menit) — bukan lanjut berdebat lewat teks.
2. Jika masih belum sepakat, Scrum Master/QA menjadi penengah dan keputusan akhir diambil bersama dengan mempertimbangkan *Definition of Done* yang sudah ditulis di Product Backlog (lihat Deliverable A).
3. Keputusan apa pun yang diambil dicatat singkat di dokumentasi API agar tidak terjadi perubahan diam-diam (*silent change*) seperti masalah tim sebelumnya.

---

## 3. Protokol Komunikasi

### 3.1 Channel Komunikasi

| Channel | Fungsi |
|---|---|
| `#daily-scrum` (chat grup) | Update harian singkat (lihat 3.3) |
| `#backend-frontend-sync` | Diskusi teknis, terutama perubahan kontrak data/API |
| GitHub/Trello comments | Diskusi yang melekat pada task atau PR spesifik |
| Voice/video call | Diskusi yang butuh klarifikasi cepat atau ada perbedaan pendapat |

Prinsip: **diskusi teknis yang mengubah kesepakatan (misalnya format data) harus tercatat secara tertulis**, tidak hanya dibahas lisan lalu lupa didokumentasikan.

### 3.2 Jam Kerja Komunikasi

Untuk mencegah *burnout* yang menjadi salah satu faktor kegagalan tim sebelumnya:

- **Jam komunikasi normal:** 09.00–21.00 WIB.
- **Dilarang** mengirim chat yang menuntut respons cepat (koordinasi tugas, request review, dsb.) **di atas pukul 21.00 WIB**, kecuali untuk kondisi darurat (lihat di bawah).
- Pesan yang dikirim di luar jam kerja **tidak wajib dibalas** sampai jam kerja berikutnya dimulai. Tidak ada anggota yang dianggap lalai karena tidak membalas chat malam hari.
- Pengecualian (*"kecuali sistem down"*) hanya berlaku untuk:
  - Sistem/server production tidak bisa diakses
  - Deadline submission dalam hitungan jam dan ada blocker kritis
  - Hal lain yang disepakati bersama sebagai keadaan darurat

Untuk kondisi darurat di atas, gunakan kata kunci **`[URGENT]`** di awal pesan supaya jelas dibedakan dari chat koordinasi biasa.

### 3.3 Daily Scrum (Stand-up Harian)

- **Waktu:** maksimal 15 menit, dilakukan setiap hari kerja jam 19.00–19.15 WIB (di luar jam kuliah/kelas masing-masing anggota).
- **Format:** setiap anggota menjawab 3 pertanyaan saja:
  1. Apa yang sudah dikerjakan kemarin?
  2. Apa yang akan dikerjakan hari ini?
  3. Apakah ada *blocker* (penghambat)?
- Difasilitasi oleh **Scrum Master/QA**, yang juga mencatat *blocker* apa pun ke board (kolom To Do/In Progress) agar tidak hilang begitu saja.

### 3.4 Sprint Review & Retrospective

- **Sprint Review** dilakukan di akhir minggu ke-2, untuk mendemonstrasikan hasil ke Product Owner (klien).
- **Sprint Retrospective** dilakukan setelah Sprint Review, internal tim saja, membahas 3 hal singkat: apa yang berjalan baik, apa yang perlu diperbaiki, dan satu tindakan konkret untuk sprint berikutnya (jika ada).

### 3.5 Update ke Product Owner (Klien)

Agar klien tidak lagi merasa progres "stagnan" tanpa kabar seperti sebelumnya:

- Scrum Master/QA mengirim **update progres singkat setiap akhir minggu** (1-2 paragraf + status board) ke Product Owner, walau belum diminta.
- Jika ada risiko keterlambatan, komunikasikan **secepat mungkin** beserta rencana mitigasinya — bukan ditutupi sampai mendekati deadline.

---

## 4. Komitmen Bersama

Dengan menyepakati dokumen ini, seluruh anggota tim berkomitmen untuk:

- ✅ Mengomunikasikan setiap perubahan kontrak data (API/JSON) sebelum implementasi, tidak sesudahnya.
- ✅ Memberi dan menerima kritik kode secara konstruktif sesuai SOP di atas.
- ✅ Menghormati jam kerja komunikasi yang telah disepakati demi kesehatan mental tim.
- ✅ Bersikap transparan ke sesama anggota dan ke Product Owner mengenai progres maupun *blocker*.
- ✅ Memprioritaskan penyelesaian masalah di atas mencari siapa yang salah.

| Nama Anggota | Peran | Tanda Tangan / Persetujuan |
|---|---|---|
| Surya | Backend Developer | _______________ |
| Kaffa | Frontend Developer | _______________ |
| Deswa | Scrum Master & QA | _______________ |

---

*Dokumen ini adalah Deliverable B dari studi kasus penyelamatan proyek "Aplikasi Mobile Kantin Pintar Kampus", melengkapi Deliverable A (Manajemen Tim & Kerja Sama).*
