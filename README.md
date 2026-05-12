# LaTeX Thesis Repository — UGM

> **Institution:** Universitas Gadjah Mada (UGM)  
> **Author:** Argya Vityasy — 23/522547/PA/22475  
> **Program:** Informatika, Departemen Teknik Elektro dan Informatika, FMIPA UGM

This repository contains LaTeX source code for both the **thesis proposal** and the **full thesis (skripsi)** using the official UGM thesis class (`ugmskripsi.cls`).

---

## Repository Structure

```
skripsi/                          # Git repo root
│
├── AGENTS.md                     # Official UGM guide reference (READ THIS FIRST)
├── README.md                     # This file
├── .gitignore                    # Ignores LaTeX build artifacts
├── LICENSE
├── ugmskripsi.cls                # MASTER UGM class file
│
├── proposal/                     # 📝 THESIS PROPOSAL (current work)
│   ├── main.tex                  # Document: [proposal,indonesia]
│   ├── ugmskripsi.cls            # Copy of master (for compatibility)
│   ├── references.bib            # Bibliography
│   ├── figures/
│   │   └── logougm.pdf           # UGM logo
│   └── chapters/
│       ├── bab1-pendahuluan.tex
│       ├── bab2-penelitian-terkait.tex
│       ├── bab3-metodologi.tex
│       └── bab4-jadwal-penelitian.tex
│
└── skripsi/                      # 📚 FULL THESIS (future work)
    ├── main.tex                  # Document: [skripsi,indonesia]
    ├── ugmskripsi.cls            # Copy of master
    ├── references.bib            # Bibliography
    ├── figures/
    │   └── logougm.pdf           # UGM logo
    ├── chapters/
    │   ├── bab1-pendahuluan.tex
    │   ├── bab2-identifikasi-masalah.tex
    │   ├── bab3-kajian-ilmiah.tex
    │   ├── bab4-perancangan.tex
    │   ├── bab5-pembuatan.tex
    │   └── bab6-pengujian.tex
    └── lampiran/
        └── lampiran-a.tex
```

---

## How to Compile

### Prerequisites

Install a LaTeX distribution:
- **macOS:** [MacTeX](https://tug.org/mactex/) (`brew install --cask mactex`)
- **Windows:** [MiKTeX](https://miktex.org/) or [TeX Live](https://tug.org/texlive/)
- **Linux:** `sudo apt-get install texlive-full`

### Option 1: Local Compilation

```bash
# Navigate to proposal or skripsi directory
cd proposal/        # or cd skripsi/

# Full compile (with bibliography)
export PATH="/Library/TeX/texbin:$PATH"
pdflatex main.tex && bibtex main && pdflatex main.tex && pdflatex main.tex

# Or use latexmk (auto-handles everything)
latexmk -pdf main.tex
```

### Option 2: Overleaf (Cloud)

1. Go to [Overleaf](https://www.overleaf.com/)
2. Create new project → Upload Project
3. Upload **either** `proposal/` or `skripsi/` folder as a zip
4. Overleaf auto-compiles on save

> **Note:** Each folder (`proposal/` and `skripsi/`) is self-contained with its own copy of `ugmskripsi.cls`.

---

## Key Differences: Proposal vs Skripsi

| Feature | Proposal | Skripsi |
|---------|----------|---------|
| Document class | `[proposal,indonesia]` | `[skripsi,indonesia]` |
| Cover | "PROPOSAL TUGAS AKHIR" | "SKRIPSI" |
| Approval page | ✅ | ✅ |
| Declaration | ❌ | ✅ |
| Motto / Persembahan | ❌ | ✅ |
| Preface | ❌ | ✅ |
| Daftar Isi | ✅ | ✅ |
| Daftar Tabel / Gambar | ❌ | ✅ |
| Daftar Simbol | ❌ | ✅ |
| Intisari | ✅ (ID only) | ✅ (ID) |
| Abstract | ✅ (EN) | ✅ (EN) |
| Bab 1 | Rumusan **Masalah** | **Perumusan Produk** |
| Bab 2 | Penelitian Terkait | Identifikasi Masalah dan Ide Inovatif |
| Bab 3 | Metode dan Rancangan | Kajian Ilmiah |
| Bab 4 | Jadwal Penelitian | Perancangan Prototipe/Produk |
| Bab 5 | ❌ | Proses Pembuatan Produk |
| Bab 6 | ❌ | Pengujian dan Evaluasi Produk |
| Glosarium | ⚠️ Optional | ❌ |
| Lampiran | ❌ | ✅ |

---

## Before You Compile

1. **Fill in your metadata** in `main.tex`:
   ```latex
   \fullname{Your Full Name}
   \idnum{Your Student ID}
   \firstsupervisor{Your Advisor}
   % ... etc
   ```

2. **Replace `figures/logougm.pdf`** with the official UGM logo

3. **Add references** to `references.bib` and cite them with `\citep{key}`

---

## Troubleshooting

| Problem | Solution |
|---------|----------|
| `logougm` not found | Add `figures/logougm.pdf` |
| References show `[?]` | Run `bibtex main` then `pdflatex main.tex` twice |
| PDF not updating | Delete `.aux` files and recompile |

---

## Resources

- **Official Guide:** `examples/pedoman_ta.pdf`
- **Example Proposal:** `examples/contoh_proposal.pdf`
- **Example Skripsi:** `examples/contoh_skripsi.pdf`
- **Case Study:** [`invenio-rdm-gitops`](https://github.com/vityasyyy/invenio-rdm-gitops)

---

Happy writing! 🎓
