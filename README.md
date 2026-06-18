# Quarto Templates — Universidades Brasileiras 🇧🇷

[![Quarto](https://img.shields.io/badge/Quarto-%3E%3D1.6.0-blue)](https://quarto.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

Formatos customizados do [Quarto](https://quarto.org) para trabalhos acadêmicos em universidades brasileiras, seguindo as normas ABNT e os requisitos de cada programa de pós-graduação.

---

## 📦 Extensões disponíveis

| Extensão | Instituição | Programa | Documento | Ano |
|----------|-------------|----------|-----------|-----|
| [`ppgens-univasf-projeto`](./_extensions/ppgens-univasf-projeto/) | UNIVASF | PPGENS | Projeto de Mestrado | 2026 |

> Consulte o README de cada template em `templates-universitarios/` para instruções específicas.

---

## 📋 Instalação

Antes de usar qualquer template, instale as dependências uma única vez.

### Passo 1 — Quarto CLI

Baixe o instalador em [quarto.org/docs/get-started](https://quarto.org/docs/get-started/):

| SO | Arquivo |
|----|---------|
| Fedora | `.rpm` |
| Ubuntu / Debian | `.deb` |
| macOS | `brew install --cask quarto` |
| Windows | `.msi` |

### Passo 2 — LaTeX + fontes

| SO | Comando |
|----|---------|
| **Fedora** | `sudo dnf install texlive-scheme-medium texlive-libertinus texlive-abntex2` |
| **Ubuntu / Debian** | `sudo apt install texlive-latex-extra texlive-fonts-extra texlive-lang-portuguese fonts-libertinus` |
| **macOS** | `brew install --cask mactex-no-gui`<br>`sudo tlmgr install libertinus abntex2` |
| **Windows** | Baixar [MiKTeX](https://miktex.org/download). Marcar "Install missing packages on the fly". |

### Passo 3 — R e RStudio

| SO | R | RStudio |
|----|---|---------|
| **Fedora** | `sudo dnf install R` | [Download .rpm](https://posit.co/download/rstudio-desktop/) |
| **Ubuntu** | `sudo apt install r-base` | [Download .deb](https://posit.co/download/rstudio-desktop/) |
| **macOS** | [CRAN .pkg](https://cran.r-project.org/bin/macosx/) | `brew install --cask rstudio` |
| **Windows** | [CRAN .exe](https://cran.r-project.org/bin/windows/base/) | [Download .exe](https://posit.co/download/rstudio-desktop/) |

### Passo 4 — Pacotes R

No console do RStudio:

```r
install.packages(c("knitr", "rmarkdown"))
```

### Verificação rápida

No terminal do RStudio (`Tools → Terminal`):

```bash
quarto --version          # ≥ 1.6.0
lualatex --version        # funciona
kpsewhich abntex2-alf.bst # retorna caminho
fc-list | grep -i libertinus  # fontes instaladas
```

---

## 🚀 Como usar

Tudo é feito de dentro do RStudio.

> Usamos o RStudio por ser o ambiente mais eficiente para documentos Quarto — preview integrado, suporte nativo a chunks R e renderização unificada.
> *colocar o passo a passo
---

## 🤝 Contribuindo

Quer adicionar o template da sua universidade?

1. Fork do repositório
2. Crie `_extensions/sua-universidade-tipo/`
3. Documente em `templates-universitarios/sua-universidade/tipo/`
4. Pull Request

---

## 📄 Licença

MIT — veja [LICENSE](LICENSE).
