**ARAHAN PROJEK — Sistem Pemantauan Belanjawan Madani Negeri Kedah**

**Nama Sistem:** Sistem Pemantauan Belanjawan Madani Negeri Kedah

**Tujuan:** Sistem pengisian dan pemantauan perancangan latihan guru sekolah rendah dan menengah negeri Kedah berdasarkan peruntukan Kementerian Pendidikan Malaysia.

**Pengguna & Akses:**
- Sekolah → log masuk kod unik sekolah → isi perancangan latihan
- PPD (10 daerah) → ID + kata laluan → pantau sekolah dalam daerah
- JPN (1 akaun) → ID + kata laluan → pantau semua sekolah Kedah

**Borang Pengisian Sekolah:**
- Tajuk latihan (teks bebas)
- Subjek fokus → dropdown: BM, BI, Matematik, Sejarah, Sains (wajib dahulu) → selepas 5 wajib selesai, guru boleh isi subjek lain sendiri (teks bebas, boleh berbilang)
- Tarikh latihan (pemilih tarikh, DD/MM/YYYY)
- Anggaran kos RM (angka, tolak dari baki bajet)
- Status → dropdown terus dalam jadual rekod: Dalam Pelaksanaan / Selesai
- Upload laporan (PDF/Word) → kotak upload nampak dari awal, aktif hanya bila status Selesai, terdapat arahan jika belum selesai
- Semua medan boleh diedit semula selepas simpan
- Bilangan guru — tetap dari sistem, papar sahaja, guru tidak perlu isi

**Paparan Sekolah:**
- Peruntukan diterima, jumlah digunakan, baki (dengan bar visual)
- Status 5 subjek wajib (visual chip: Selesai/Dalam Pelaksanaan/Belum Dirancang)
- Jadual rekod latihan (edit terus, status boleh tukar dalam jadual)

**Dashboard PPD:**
- Pantau sekolah dalam daerah sendiri sahaja
- Status subjek wajib setiap sekolah
- Senarai latihan, tarikh, tajuk, subjek, status
- Bilangan guru, bajet dan baki sekolah
- Graf perbelanjaan dan kemajuan

**Dashboard JPN:**
- Pantau semua 128 sekolah, 10 daerah negeri Kedah
- Graf perbelanjaan keseluruhan
- Status subjek wajib mengikut daerah
- Kemajuan perbelanjaan mengikut daerah
- Senarai tarikh cadangan latihan

**Pangkalan Data (Supabase):**
- `sekolah` → kod, nama_sekolah, daerah, bajet, bil_guru
- `pengguna` → id, nama, peranan (PPD/JPN), daerah
- `latihan` → id, sekolah_id, nama_latihan, subjek[], tarikh, status, kos
- `dokumen` → id, latihan_id, fail_url

**Data Sekolah:** 128 sekolah, 10 daerah Kedah (data lengkap disediakan — tampal CSV sekolah sekali)

**Platform:** Desktop-first, responsif untuk telefon

**Bahasa:** Bahasa Melayu Rasmi sepenuhnya

**Fasa Pembangunan:**
1. Skema DB Supabase + import 128 sekolah
2. Sistem log masuk (3 peranan)
3. Antaramuka sekolah (pengisian)
4. Dashboard PPD dan JPN
5. Graf dan laporan
6. Upload dokumen

---
