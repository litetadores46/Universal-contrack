# TokenForge · GitHub App Pengembangan Token

[![HTML](https://img.shields.io/badge/HTML-5-orange)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind-CDN-38bdf8)](https://tailwindcss.com/)
[![ECharts](https://img.shields.io/badge/ECharts-5-aa00ff)](https://echarts.apache.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Bahasa](https://img.shields.io/badge/bahasa-Indonesia-red)]()

**TokenForge** adalah konsol web interaktif (GitHub App UI) untuk memandu pengembangan token dari tahap ide hingga listing. Aplikasi ini membantu tim proyek menyusun konfigurasi smart contract, merancang tokenomics, dan memantau checklist audit & kepatuhan — dalam satu dasbor.

> ⚠️ **Penting:** Alat ini bersifat **edukatif & simulasi**. Bukan saran investasi, bukan ajakan membeli token, dan tombol "Simulasi Deploy" **tidak** menerbitkan kontrak nyata di blockchain. Selalu audit smart contract oleh pihak ketiga dan konsultasikan penasihat hukum sebelum penawaran token publik.

---

## ✨ Fitur Utama

| Tab | Fungsi |
|-----|--------|
| **Ringkasan** | Timeline 7 tahap pengembangan token (ide → listing) dengan status *done / current / pending* |
| **Konfigurasi Token** | Form nama, simbol, desimal, total supply, dan pilihan jaringan (ERC-20, BEP-20, TRC-20, SPL, Polygon) + **preview token langsung** + simulasi deploy (alamat kontrak & tx hash dummy) |
| **Tokenomics** | 6 slider alokasi (Tim Inti, Investor, Komunitas & Airdrop, Likuiditas, Treasury, Ekosistem) dengan **pie chart donut interaktif** (ECharts) dan indikator total % (merah jika ≠ 100%) |
| **Audit & Kepatuhan** | Checklist 12 item (audit kontrak, KYC/AML, lapor Bappebti, dll.) dengan **progress bar otomatis** + catatan kepatuhan regulasi Indonesia |

- **Responsif** — tampil baik di desktop maupun mobile.
- **Self-contained** — satu file `tokenforge-dashboard.html`, tanpa build step.
- **Dark theme** — konsol bergaya developer-tool dengan aksen oranye.

---

## 🚀 Cara Pakai

### Opsi 1 — Buka langsung
1. Unduh `tokenforge-dashboard.html`.
2. Buka dengan browser apa pun (Chrome, Firefox, Edge).
3. Butuh koneksi internet (Tailwind, ECharts, dan Google Fonts dimuat via CDN).

### Opsi 2 — Host di GitHub Pages
1. Commit file ke repo, mis. ke folder `docs/` atau root sebagai `index.html`.
2. **Settings → Pages → Source:** pilih branch (`main`) dan folder (`/docs` atau `/root`).
3. Akses di `https://<username>.github.io/<repo>/`.

### Opsi 3 — Integrasi ke GitHub App
Sematkan halaman ini sebagai **UI landing/dashboard** setelah pengguna meng-install GitHub App Anda. Sesuaikan bagian header (badge `org/token-proyek`) dengan data instalasi dari API GitHub.

---

## 📁 Struktur Proyek

```
tokenforge/
├── tokenforge-dashboard.html   # Konsol UI utama (satu file, self-contained)
├── README.md                   # Dokumentasi ini
├── LICENSE                     # Lisensi MIT
└── docs/                       # (opsional) aset tambahan untuk GitHub Pages
```

---

## ⚙️ Konfigurasi

Semua data contoh dapat diubah langsung di dalam `<script>` pada file HTML:

| Variabel | Lokasi | Keterangan |
|----------|--------|------------|
| `defaults` (tokenomics) | blok `TOKENOMICS SLIDERS + PIE` | Nilai awal 6 alokasi (default: 15/20/25/15/15/10) |
| `labels` (tokenomics) |同上 | Nama keranjang alokasi |
| `items` (audit) | blok `AUDIT CHECKLIST` | Daftar 12 item checklist |
| `<option>` jaringan | elemen `<select id="cfg-network">` | Daftar standar/jaringan yang tersedia |
| `--accent`, `--bg`, dll. | `:root` di `<style>` | Palet warna tema |

---

## 🛠️ Tech Stack

- **Vanilla HTML + CSS + JavaScript** — tanpa framework, tanpa build step.
- **Tailwind CSS (Play CDN)** — utilitas styling.
- **Apache ECharts 5** — pie chart donut tokenomics.
- **Google Fonts** — Sora (UI) + JetBrains Mono (kode/alamat).
- **GitHub App UI pattern** — badge koneksi repo, alur tahapan.

### Standar Token yang Didukung (contoh)
- **ERC-20** — Ethereum, paling matang, gas tinggi.
- **BEP-20** — BNB Chain, biaya rendah & cepat.
- **TRC-20** — TRON, throughput tinggi.
- **SPL** — Solana, kecepatan tinggi & biaya mikro.
- **ERC-20 (L2)** — Polygon, biaya rendah.

---

## 🗺️ 7 Tahap Pengembangan Token

1. **Ide & Whitepaper** — dokumen visi, use case, model ekonomi.
2. **Desain Tokenomics** — alokasi, vesting, jadwal unlock.
3. **Pengembangan Smart Contract** — berbasis OpenZeppelin, unit test.
4. **Audit Keamanan** — auditor eksternal, perbaiki issue.
5. **Testnet & Bug Bounty** — uji jaringan tes, hadiah bug.
6. **Mainnet Launch** — deploy & verifikasi kontrak di explorer.
7. **Listing & Pasca-launch** — DEX/CEX listing, liquidity locking, komunitas.

---

## 📜 Kepatuhan Hukum (Indonesia)

Sebelum penawaran token ke publik:
- **Bappebti** — ketentuan perdagangan aset kripto (Perdagangan Aset Kripto di Bursa Berjangka).
- **OJK** — konsultasi status sekuritas jika token memiliki unsur investasi.
- **KYC/AML** — wajib bagi pelaku pasar aset kripto.
- **Audit smart contract** oleh auditor independen (mis. CertiK, SlowMist, OpenZeppelin).

---

## 🤝 Kontribusi

1. Fork repo ini.
2. Buat branch fitur: `git checkout -b fitur-baru`.
3. Commit perubahan: `git commit -m 'tambah fitur ...'`.
4. Push: `git push origin fitur-baru`.
5. Buka **Pull Request**.

---

## 📄 Lisensi

Didistribusikan di bawah lisensi **MIT**. Lihat `LICENSE` untuk detailnya.

---

<p align="center">
Dibuat untuk edukasi pengembangan token · Selalu DYOR (Do Your Own Research)
</p>
