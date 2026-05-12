# Contributing to UGM Thesis LaTeX Template

Thank you for your interest in contributing! This guide covers how to use, fork, and contribute to this template.

---

## Table of Contents

1. [For Students: Using the Template](#for-students-using-the-template)
2. [For Contributors: Submitting Changes](#for-contributors-submitting-changes)
3. [Versioning](#versioning)
4. [Code of Conduct](#code-of-conduct)

---

## For Students: Using the Template

### Quick Start

1. **Fork this repository** to your own GitHub account
2. **Clone your fork** locally:
   ```bash
   git clone https://github.com/YOUR_USERNAME/ugm-thesis-latex.git
   cd ugm-thesis-latex
   ```
3. **Customize the template**:
   - Edit `template/proposal/main.tex` and `template/skripsi/main.tex`
   - Replace all `{{PLACEHOLDER}}` with your actual data
   - Write your content in the chapter files under `template/*/chapters/`
4. **Compile**:
   ```bash
   make proposal    # or make proposal-docker
   make skripsi     # or make skripsi-docker
   ```

### What to Change

#### Metadata (`main.tex`)
Replace these placeholders:
```latex
\titleind{{{JUDUL_BAHASA_INDONESIA}}}
\titleeng{{{JUDUL_BAHASA_INGGRIS}}}
\fullname{{{NAMA_LENGKAP}}}
\idnum{{{NIM}}}
\degree{{{JENJANG}}}
\gelar{{{GELAR}}}
\yearsubmit{{{TAHUN}}}
\program{{{PROGRAM_STUDI}}}
\dept{{{DEPARTEMEN}}}
\firstsupervisor{{{NAMA_DOSEN_PEMBIMBING}}}
\firstexaminer{{{NAMA_DOSEN_PENGUJI_1}}}
\secondexaminer{{{NAMA_DOSEN_PENGUJI_2}}}
```

#### Content (`chapters/*.tex`)
- Replace all `TODO` comments with your actual content
- Replace lorem ipsum with your writing
- Add your references to `references.bib`
- Add your figures to `figures/`

#### Logo
Replace `template/*/figures/logougm.pdf` with the official UGM logo from your department.

### What NOT to Change
- `ugmskripsi.cls` — unless you know what you're doing
- `.github/` — unless contributing back upstream

---

## For Contributors: Submitting Changes

### Reporting Bugs

Before reporting a bug:
1. Check if the issue already exists
2. Try compiling with `make clean` first
3. Ensure you have the required LaTeX packages

When reporting, include:
- Your OS and LaTeX distribution
- The exact error message
- Steps to reproduce

### Requesting Template Updates

When UGM releases a new pedoman or changes requirements:
1. Open a **Template Update** issue
2. Attach the new pedoman PDF or relevant documentation
3. Describe exactly what changed
4. Propose a solution if you have one

### Submitting Pull Requests

1. **Fork** the repository
2. **Create a feature branch**: `git checkout -b feat/your-feature`
3. **Make your changes**
4. **Test compilation**:
   ```bash
   make proposal-docker
   make skripsi-docker
   ```
5. **Update documentation** if needed (README.md, AGENTS.md)
6. **Commit** with conventional commit messages:
   ```bash
   git commit -m "fix(cls): correct page numbering in proposal mode"
   ```
7. **Push** and open a Pull Request

#### PR Checklist
- [ ] Both `proposal` and `skripsi` compile successfully
- [ ] All 3 copies of `ugmskripsi.cls` are updated (root, template/proposal, template/skripsi)
- [ ] Documentation updated if needed
- [ ] Conventional commit format used

### Commit Message Format

We use [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>(<scope>): <description>

[optional body]

[optional footer]
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Formatting (no code change)
- `refactor`: Code refactoring
- `chore`: Maintenance tasks
- `ci`: CI/CD changes

**Scopes:**
- `cls`: Class file (`ugmskripsi.cls`)
- `proposal`: Proposal template
- `skripsi`: Skripsi template
- `build`: Makefile, Docker
- `docs`: README, AGENTS, CONTRIBUTING

---

## Versioning

We use git tags for versioning based on academic years:

```bash
# Tag format: vYYYY.N
# YYYY = Academic year start
# N    = Revision number within that year

git tag -a v2025.1 -m "Template for academic year 2024/2025"
git tag -a v2025.2 -m "Updated with pedoman fixes"
git tag -a v2026.1 -m "Template for academic year 2025/2026"
```

### Version Table

| Version | Academic Year | Notes |
|---------|--------------|-------|
| v2025.1 | 2024/2025 | Initial release |
| v2026.1 | 2025/2026 | Updated pedoman |

### Using Specific Versions

```bash
# Clone specific version
git clone --branch v2026.1 https://github.com/vityasyyy/ugm-thesis-latex.git

# Or checkout after clone
git checkout v2026.1
```

---

## Code of Conduct

- Be respectful and constructive
- Help others learn
- Give credit where due
- Follow UGM academic integrity guidelines

---

## Questions?

Open an issue with the **Question** label or contact the maintainers.

Happy writing! 🎓
