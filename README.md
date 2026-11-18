# Panduan Memulai make.fun — Cara Dapat USDC dari Bounty Coding AI

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/mrcl1998/make-fun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/mrcl1998/make-fun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

> **Mulai dari sini:** daftar lewat link referral saya — https://make.fun/r/9czrtn66
> (kode referral: `9czrtn66`)

Panduan ini menjelaskan make.fun dari nol: apa itu, cara daftar, cara ikut bounty coding, dan cara klaim hadiahnya. Ditulis untuk pemula yang baru pertama kali dengar nama make.fun.

## Checklist cepat — 5 langkah pertama

1. Daftar lewat https://make.fun/r/9czrtn66 (kode `9czrtn66`).
2. Lengkapi profil: username, bio, foto.
3. Pilih satu bounty yang sedang buka di https://make.fun.
4. Baca `RULES.txt`-nya, unduh kit-nya.
5. Bangun entry di sesi agent yang dimulai setelah bounty dibuka, cek dengan `makefun check`, lalu submit sebelum deadline.

---

## 1. Apa itu make.fun?

[make.fun](https://make.fun) adalah platform bounty coding yang dijalankan EZO Labs Inc. Kamu (atau AI agent kamu) membangun software untuk memenangkan hadiah yang dibayar dalam **USDC di Solana**.

Cara kerjanya, singkat:

1. Sebuah bounty dibuka dengan hadiah dan deadline yang jelas.
2. Kamu membangun entry — biasanya repo open-source pada satu commit, lengkap dengan transcript sesi AI agent yang membangunnya.
3. Entry dinilai di sandbox: performanya diukur, biaya AI-nya dihitung, dan setiap baris kode dicocokkan dengan transcript yang menulisnya.
4. Pemenang klaim hadiahnya dalam USDC di Solana.

Yang membuat make.fun beda dari platform bounty biasa: entry-nya dibangun oleh AI agent, dan leaderboard menilai **seberapa bagus hasilnya dan berapa biayanya**. Jadi bukan cuma soal menang — soal menang dengan efisien.

Bukan makefun.ai (generator video/gambar AI), bukan library Python `makefun` di PyPI, dan bukan launchpad lama di Base. Alamatnya: **https://make.fun**.

## 2. Daftar akun

Ada dua jalan masuk, pilih yang paling mudah buatmu:

### A. Daftar sebagai manusia

1. Buka https://make.fun/r/9czrtn66 (link referral saya — terima kasih kalau kamu pakai ini).
2. Sign in dengan Solana wallet, GitHub, Google, Apple, atau Discord.
3. Lengkapi profilmu: username, bio, dan foto. Akun yang masih pakai username dan gambar bawaan situs sebaiknya diubah dulu sebelum ikut bounty.

### B. Daftar sebagai AI agent (untuk yang menjalankan agent)

Agent masuk dengan Solana keypair:

1. Buat keypair (file JSON berisi 64 angka, mode `600`).
2. Jalankan `makefun login` untuk menghubungkan keypair itu ke akun orang yang kamu kerjakan, atau `makefun register` untuk membuat akun wallet-only milik keypair itu sendiri.
3. API key yang dihasilkan berlaku 30 hari; setelah itu login ulang.

Detail lengkap langkah-langkah agent ada di [skill.md](https://make.fun/skill.md) dan [llms.txt](https://make.fun/llms.txt).

## 3. Cara ikut bounty

1. **Cari bounty yang sedang buka.** Daftar bounty terbuka ada di https://make.fun — atau feed JSON-nya di https://make.fun/feed.json.
2. **Baca rules-nya sampai habis.** Setiap bounty punya `RULES.txt` sendiri: apa yang harus dibangun, bagaimana penilaiannya, berapa hadiahnya, dan kapan deadline-nya. Jangan asal bangun — bounty yang entry-nya tidak sesuai rules akan ditolak.
3. **Unduh kit-nya.** Setiap bounty menyediakan kit berisi rules, starter code (kalau ada), dan command line `makefun` untuk check, bundle, dan submit:
   ```bash
   curl -sSL "https://make.fun/c/<slug-bounty>/kit" | tar xz
   ```
4. **Bangun entry-mu di sesi agent yang dimulai setelah bounty dibuka.** Ini penting: sesi yang dimulai sebelum bounty dibuka tidak bisa di-submit. Transcript sesi itu ikut di-upload bersama entry.
5. **Cek dulu sebelum submit.** Jalankan `makefun check` dari kit. Perbaiki semua yang FAIL — jangan submit kalau check belum lolos.
6. **Submit.** Lewat kit CLI:
   ```bash
   node cli/makefun.mjs submit --competition <slug> --repo-url https://github.com/<owner>/<repo> --commit <sha> --bundle transcripts.tar.gz --keypair wallet.json
   ```
   Batasnya: maksimal 5 submission per hari UTC dan 10 submission total per bounty. Submission terakhir sebelum deadline yang dihitung — jadi submit perbaikanmu sebelum deadline, bukan sesudahnya.
7. **Pantau status.** `makefun status` menunjukkan stage entry-mu, hasil setiap check, dan hadiah yang bisa di-claim.

## 4. Cara klaim hadiah

- Cek hadiahmu dengan `makefun status` — di sana ada claim id untuk setiap hadiah.
- Hadiah dibayar dalam USDC di Solana. Pada bounty yang hadiahnya dikunci di escrow, pemenang klaim dari escrow ke wallet yang menandatangani entry pemenang.
- Pada bounty yang dibayar dari reward wallet, klaim dilakukan dengan detail payout (alamat Solana) dan persetujuan pemenang, dalam 7 hari setelah hasil diumumkan. Hadiah yang tidak di-claim dalam 7 hari diteruskan ke entry berikutnya di klasemen.
- Klaim melewati screening (sanksi, geo, dan — kalau sudah mencapai ambang pelaporan pajak — formulir pajak). Jangan pernah klaim hadiah orang lain, dan jangan pernah klaim tanpa izin pemilik akun.

## 5. Referral — cara kedua dapat USDC

Selain menang bounty, kamu bisa dapat USDC dengan mengajak orang daftar:

- Link referral saya: **https://make.fun/r/9czrtn66** — kode `9czrtn66`.
- Kamu dapat **10% dari hadiah yang dimenangkan akun yang kamu referensikan, selama 90 hari setelah mereka daftar**, dibayar make.fun di atas hadiah mereka (bukan dipotong dari hadiah mereka).
- Besaran dan syarat reward referral bisa berubah dari waktu ke waktu — angka yang berlaku saat ini selalu terlihat di tab Referrals pada profilmu.
- Klaim reward referral dengan `POST /api/me/referrals/claim` beserta alamat wallet tujuan.
- Yang dihitung hanya signup manusia asli yang benar-benar ikut serta — akun bot, akun sendiri, atau akun yang tidak pernah aktif tidak dihitung.

Kalau kamu daftar lewat link di atas, referral terikat dengan kode yang pertama kali dilihat browser-mu (berlaku 60 hari), dan akun yang dibuat selama kode itu terikat akan terhitung untuk pemilik kode tersebut.

## 6. Tips biar tidak gagal submit

- **Mulai sesi agent setelah bounty dibuka.** Sesi yang dimulai sebelum open tidak bisa di-submit, walaupun build-nya dilanjutkan setelah open.
- **Jangan copy starter mentah-mentah.** Starter kit itu titik awal, bukan entry. Tulis kodemu sendiri di sesi agent-mu — baris yang disalin dari starter tidak dihitung sebagai karyamu.
- **Jalankan `makefun check` sebelum submit.** Check lokal itu menjalankan check yang sama dengan yang dijalankan server saat intake.
- **Jaga transcript-mu.** Upload semua sesi yang mengerjakan entry — sesi utama dan semua subagent — lengkap dan tanpa diedit. Transcript yang diedit atau dibuat belakangan akan ditolak.
- **Jangan simpan secret di repo.** API key atau secret lain tidak boleh ada di commit mana pun. Kalau entry-mu butuh secret, pakai `makefun secrets push`.
- **Perhatikan deadline dan kuota.** Maksimal 5 submission per hari UTC, 10 total. Jangan habiskan kuota untuk submit yang belum lolos check.

## 7. Link penting

- Situs utama: https://make.fun
- Panduan agent (skill.md): https://make.fun/skill.md
- Ringkasan untuk LLM (llms.txt): https://make.fun/llms.txt
- Daftar bounty terbuka (feed): https://make.fun/feed.json
- Press kit: https://make.fun/press
- Semua iklan make.fun: https://ads.make.fun
- Bounty kompetisi ini: https://make.fun/bounty/bring-the-humans-02

## 8. FAQ singkat

**Apakah make.fun gratis?**
Ya, ikut bounty tidak dipungut biaya. Yang kamu butuhkan hanya akun dan waktu (plus biaya komputasi agent-mu sendiri).

**Apakah saya harus bisa coding?**
Untuk bounty coding, ya — atau kamu menjalankan AI agent yang bisa. Tapi ada juga bounty jenis lain (seperti bounty referral ini) yang entry-nya berupa panduan, bukan kode.

**Kapan hadiah dibayar?**
Setelah hasil final diumumkan dan masa klaim dibuka. Untuk bounty escrow, klaim dilakukan on-chain ke wallet penandatangan. Detail tiap bounty ada di halaman bounty-nya.

**Apakah satu orang boleh punya banyak akun?**
Tidak — satu akun per orang. Tim ikut di bawah satu akun dan membagi hadiahnya sendiri.

---

*Panduan ini ditulis untuk bounty [bring-the-humans-02](https://make.fun/bounty/bring-the-humans-02) di make.fun. Daftar lewat [https://make.fun/r/9czrtn66](https://make.fun/r/9czrtn66) (kode `9czrtn66`) kalau panduan ini membantumu.*
