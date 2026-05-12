# UGM Thesis LaTeX Template

> **Template LaTeX resmi untuk Tugas Akhir Fakultas FMIPA Universitas Gadjah Mada (UGM)**

Template ini menyediakan struktur LaTeX lengkap untuk penulisan **Proposal Tugas Akhir** dan **Skripsi** sesuai dengan pedoman resmi FMIPA UGM.

---

## Quick Start

### 1. Fork Repository Ini

Klik tombol **Fork** di pojok kanan atas untuk menyalin repository ke akun GitHub Anda.

### 2. Clone ke Lokal

```bash
git clone https://github.com/YOUR_USERNAME/ugm-thesis-latex.git
cd ugm-thesis-latex
```

### 3. Ganti Metadata

Edit file `template/proposal/main.tex` dan `template/skripsi/main.tex`, ganti semua placeholder:

```latex
\titleind{Judul Penelitian Anda dalam Bahasa Indonesia}
\titleeng{Your Research Title in English}
\fullname{Nama Lengkap Anda}
\idnum{XX/XXXXXX/PA/XXXXX}
\program{Informatika}
\dept{Teknik Elektro dan Informatika}
\firstsupervisor{Nama Dosen Pembimbing, S.T., M.T.}
```

### 4. Tulis Konten

Edit file-file di `template/*/chapters/` dan ganti konten lorem ipsum dengan tulisan Anda.

### 5. Compile

```bash
# Opsi 1: Makefile (membutuhkan texlive terinstall)
make proposal
make skripsi

# Opsi 2: Docker (tidak perlu texlive)
make proposal-docker
make skripsi-docker
```

---

## Features

- **Struktur lengkap** sesuai pedoman UGM (Proposal + Skripsi)
- **Class file resmi** UGM (`ugmskripsi.cls`) dengan dukungan `[proposal]` dan `[skripsi]`
- **Placeholder yang jelas** dengan format `{{PLACEHOLDER}}` dan komentar `TODO`
- **3 cara kompilasi**: vimtex, Makefile, atau Docker
- **CI/CD otomatis** dengan GitHub Actions
- **Lorem ipsum** sebagai placeholder konten
- **Bilingual**: Bahasa Indonesia + English abstract

---

## Repository Structure

```
ugm-thesis-latex/
├── .github/
│   ├── workflows/
│   │   └── compile-latex.yml      # CI: Kompilasi otomatis
│   ├── ISSUE_TEMPLATE/            # Template laporan issue
│   └── PULL_REQUEST_TEMPLATE.md   # Template PR
│
├── docker/
│   └── Dockerfile                 # Image LaTeX untuk Docker
│
├── template/                      # Template utama (fork ini!)
│   ├── proposal/
│   │   ├── main.tex               # Metadata + struktur proposal
│   │   ├── ugmskripsi.cls         # Class file UGM
│   │   ├── chapters/              # 4 BAB
│   │   ├── figures/
│   │   │   └── logougm.pdf        # Ganti dengan logo UGM resmi
│   │   └── references.bib         # Database referensi
│   │
│   └── skripsi/
│       ├── main.tex               # Metadata + struktur skripsi
│       ├── ugmskripsi.cls
│       ├── chapters/              # 6 BAB (Inovasi Produk)
│       ├── figures/
│       ├── lampiran/              # Lampiran
│       └── references.bib
│
├── Makefile                       # Build automation
├── CONTRIBUTING.md                # Panduan kontribusi
├── AGENTS.md                      # Referensi pedoman UGM
├── README.md                      # File ini
└── examples/                      # Dokumen resmi UGM
    ├── pedoman_ta.pdf
    ├── contoh_proposal.pdf
    └── contoh_skripsi.pdf
```

---

## Cara Kompilasi

### Prerequisites

**Opsi A: Local (texlive terinstall)**
- macOS: `brew install --cask mactex`
- Windows: [MiKTeX](https://miktex.org/) atau [TeX Live](https://tug.org/texlive/)
- Linux: `sudo apt-get install texlive-full`

**Opsi B: Docker (tanpa texlive)**
- [Docker Desktop](https://www.docker.com/products/docker-desktop)

### Makefile Commands

```bash
# Lokal (membutuhkan texlive)
make proposal          # Kompilasi proposal
make skripsi           # Kompilasi skripsi
make clean             # Bersihkan file bantu
make all               # Kompilasi keduanya

# Docker (tidak perlu texlive)
make proposal-docker   # Kompilasi proposal dalam container
make skripsi-docker    # Kompilasi skripsi dalam container
make all-docker        # Kompilasi keduanya dalam container
make shell             # Shell interaktif dalam container
```

### vimtex (Neovim/Vim)

Jika menggunakan Neovim dengan [vimtex](https://github.com/lervag/vimtex):

```vim
:VimtexCompile    " Mulai live preview
:VimtexView       " Buka PDF viewer
:VimtexStop       " Hentikan kompilasi
```

---

## Versi Template

Gunakan tag untuk mengambil versi sesuai tahun akademik:

```bash
# Clone versi spesifik
git clone --branch v2026.1 https://github.com/vityasyyy/ugm-thesis-latex.git

# Atau checkout setelah clone
git checkout v2026.1
```

| Versi | Tahun Akademik | Catatan |
|-------|---------------|---------|
| v2025.1 | 2024/2025 | Rilis awal |

---

## Troubleshooting

| Masalah | Solusi |
|---------|--------|
| `logougm` not found | Ganti `template/*/figures/logougm.pdf` dengan logo UGM resmi |
| References `[?]` | Jalankan `bibtex main` lalu `pdflatex main.tex` 2x |
| `natbib` error | Pastikan texlive-full atau package `natbib` terinstall |
| PDF tidak update | Jalankan `make clean` lalu kompilasi ulang |
| Docker tidak jalan | Pastikan Docker Desktop berjalan |

---

## Contributing

Ingin berkontribusi? Lihat [CONTRIBUTING.md](CONTRIBUTING.md) untuk panduan lengkap.

**Cara cepat berkontribusi:**
1. Fork repository
2. Buat branch: `git checkout -b fitur-anda`
3. Commit perubahan
4. Push dan buat Pull Request

---

## License

[MIT License](LICENSE)

> **Catatan:** Logo UGM dan dokumen pedoman adalah hak milik Universitas Gadjah Mada. Template ini hanya menyediakan struktur LaTeX dan tidak berafiliasi resmi dengan UGM.

---

## Resources

- **Pedoman Resmi:** `examples/pedoman_ta.pdf`
- **Contoh Proposal:** `examples/contoh_proposal.pdf`
- **Contoh Skripsi:** `examples/contoh_skripsi.pdf`
- **AGENTS.md:** Referensi cepat struktur dan aturan UGM

---

Selamat menulis! 🎓
