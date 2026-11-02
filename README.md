# TokenForge Â· GitHub App Pengembangan Token

[![HTML](https://img.shields.io/badge/HTML-5-orange)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind-CDN-38bdf8)](https://tailwindcss.com/)
[![ECharts](https://img.shields.io/badge/ECharts-5-aa00ff)](https://echarts.apache.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Bahasa](https://img.shields.io/badge/bahasa-Indonesia-red)]()

**TokenForge** adalah konsol web interaktif (GitHub App UI) untuk memandu pengembangan token dari tahap ide hingga listing. Aplikasi ini membantu tim proyek menyusun konfigurasi smart contract, merancang tokenomics, dan memantau checklist audit & kepatuhan â€” dalam satu dasbor.

> âš ï¸ **Penting:** Alat ini bersifat **edukatif & simulasi**. Bukan saran investasi, bukan ajakan membeli token, dan tombol "Simulasi Deploy" **tidak** menerbitkan kontrak nyata di blockchain. Selalu audit smart contract oleh pihak ketiga dan konsultasikan penasihat hukum sebelum penawaran token publik.

---

## âœ¨ Fitur Utama

| Tab | Fungsi |
|-----|--------|
| **Ringkasan** | Timeline 7 tahap pengembangan token (ide â†’ listing) dengan status *done / current / pending* |
| **Konfigurasi Token** | Form nama, simbol, desimal, total supply, dan pilihan jaringan (ERC-20, BEP-20, TRC-20, SPL, Polygon) + **preview token langsung** + simulasi deploy (alamat kontrak & tx hash dummy) |
| **Tokenomics** | 6 slider alokasi (Tim Inti, Investor, Komunitas & Airdrop, Likuiditas, Treasury, Ekosistem) dengan **pie chart donut interaktif** (ECharts) dan indikator total % (merah jika â‰  100%) |
| **Audit & Kepatuhan** | Checklist 12 item (audit kontrak, KYC/AML, lapor Bappebti, dll.) dengan **progress bar otomatis** + catatan kepatuhan regulasi Indonesia |

- **Responsif** â€” tampil baik di desktop maupun mobile.
- **Self-contained** â€” satu file `tokenforge-dashboard.html`, tanpa build step.
- **Dark theme** â€” konsol bergaya developer-tool dengan aksen oranye.

---

## ðŸš€ Cara Pakai

### Opsi 1 â€” Buka langsung
1. Unduh `tokenforge-dashboard.html`.
2. Buka dengan browser apa pun (Chrome, Firefox, Edge).
3. Butuh koneksi internet (Tailwind, ECharts, dan Google Fonts dimuat via CDN).

### Opsi 2 â€” Host di GitHub Pages
1. Commit file ke repo, mis. ke folder `docs/` atau root sebagai `index.html`.
2. **Settings â†’ Pages â†’ Source:** pilih branch (`main`) dan folder (`/docs` atau `/root`).
3. Akses di `https://<username>.github.io/<repo>/`.

### Opsi 3 â€” Integrasi ke GitHub App
Sematkan halaman ini sebagai **UI landing/dashboard** setelah pengguna meng-install GitHub App Anda. Sesuaikan bagian header (badge `org/token-proyek`) dengan data instalasi dari API GitHub.

---

## ðŸ“ Struktur Proyek

```
tokenforge/
â”œâ”€â”€ tokenforge-dashboard.html   # Konsol UI utama (satu file, self-contained)
â”œâ”€â”€ README.md                   # Dokumentasi ini
â”œâ”€â”€ LICENSE                     # Lisensi MIT
â””â”€â”€ docs/                       # (opsional) aset tambahan untuk GitHub Pages
```

---

## âš™ï¸ Konfigurasi

Semua data contoh dapat diubah langsung di dalam `<script>` pada file HTML:

| Variabel | Lokasi | Keterangan |
|----------|--------|------------|
| `defaults` (tokenomics) | blok `TOKENOMICS SLIDERS + PIE` | Nilai awal 6 alokasi (default: 15/20/25/15/15/10) |
| `labels` (tokenomics) |åŒä¸Š | Nama keranjang alokasi |
| `items` (audit) | blok `AUDIT CHECKLIST` | Daftar 12 item checklist |
| `<option>` jaringan | elemen `<select id="cfg-network">` | Daftar standar/jaringan yang tersedia |
| `--accent`, `--bg`, dll. | `:root` di `<style>` | Palet warna tema |

---

## ðŸ› ï¸ Tech Stack

- **Vanilla HTML + CSS + JavaScript** â€” tanpa framework, tanpa build step.
- **Tailwind CSS (Play CDN)** â€” utilitas styling.
- **Apache ECharts 5** â€” pie chart donut tokenomics.
- **Google Fonts** â€” Sora (UI) + JetBrains Mono (kode/alamat).
- **GitHub App UI pattern** â€” badge koneksi repo, alur tahapan.

### Standar Token yang Didukung (contoh)
- **ERC-20** â€” Ethereum, paling matang, gas tinggi.
- **BEP-20** â€” BNB Chain, biaya rendah & cepat.
- **TRC-20** â€” TRON, throughput tinggi.
- **SPL** â€” Solana, kecepatan tinggi & biaya mikro.
- **ERC-20 (L2)** â€” Polygon, biaya rendah.

---

## ðŸ—ºï¸ 7 Tahap Pengembangan Token

1. **Ide & Whitepaper** â€” dokumen visi, use case, model ekonomi.
2. **Desain Tokenomics** â€” alokasi, vesting, jadwal unlock.
3. **Pengembangan Smart Contract** â€” berbasis OpenZeppelin, unit test.
4. **Audit Keamanan** â€” auditor eksternal, perbaiki issue.
5. **Testnet & Bug Bounty** â€” uji jaringan tes, hadiah bug.
6. **Mainnet Launch** â€” deploy & verifikasi kontrak di explorer.
7. **Listing & Pasca-launch** â€” DEX/CEX listing, liquidity locking, komunitas.

---

## ðŸ“œ Kepatuhan Hukum (Indonesia)

Sebelum penawaran token ke publik:
- **Bappebti** â€” ketentuan perdagangan aset kripto (Perdagangan Aset Kripto di Bursa Berjangka).
- **OJK** â€” konsultasi status sekuritas jika token memiliki unsur investasi.
- **KYC/AML** â€” wajib bagi pelaku pasar aset kripto.
- **Audit smart contract** oleh auditor independen (mis. CertiK, SlowMist, OpenZeppelin).

---

## ðŸ¤ Kontribusi

1. Fork repo ini.
2. Buat branch fitur: `git checkout -b fitur-baru`.
3. Commit perubahan: `git commit -m 'tambah fitur ...'`.
4. Push: `git push origin fitur-baru`.
5. Buka **Pull Request**.

---

## ðŸ“„ Lisensi

Didistribusikan di bawah lisensi **MIT**. Lihat `LICENSE` untuk detailnya.

---

<p align="center">
Dibuat untuk edukasi pengembangan token Â· Selalu DYOR (Do Your Own Research)
</p>
