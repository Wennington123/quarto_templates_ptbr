# Quarto Templates — Universidades Brasileiras 🇧🇷

[![Quarto](https://img.shields.io/badge/Quarto-%3E%3D1.6.0-blue)](https://quarto.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

Formatos customizados do [Quarto](https://quarto.org) para trabalhos acadêmicos em universidades brasileiras, seguindo as normas ABNT e os requisitos de cada programa de pós-graduação.

---

## 📦 Extensões disponíveis

| Extensão | Instituição | Programa | Documento | Ano |
|----------|-------------|----------|-----------|-----|
| [`ppgens-univasf-projeto`](./_extensions/ppgens-univasf-projeto/) | UNIVASF | PPGENS | Projeto de Mestrado | 2026 |

---

## 🚀 Como usar

Você pode usar este formato de duas maneiras.

### Opção A: template (recomendado para começar um trabalho novo)

Cria uma pasta limpa com tudo pronto para editar e renderizar:

1. Abra o terminal no diretório onde quer criar o projeto
2. Execute:

```bash
quarto use template Wennington123/quarto_templates_ptbr
```

3. O Quarto vai pedir um nome para a pasta. Digite e pressione Enter
4. Abra a pasta no RStudio:

```
File → Open Project → selecione o arquivo .Rproj
```

5. Edite o `.qmd` — o arquivo já vem com o esqueleto completo do template

### Opção B: extensão (para adicionar a um projeto que já existe)

Se você já tem um projeto Quarto em andamento:

1. No terminal, dentro da pasta do seu projeto:

```bash
quarto add Wennington123/quarto_templates_ptbr
```

2. No YAML do seu `.qmd`, defina o formato:

```yaml
format: ppgens-univasf-projeto
```

3. Abra no RStudio, edite e clique em **Render**

> A extensão instala apenas o formato em `_extensions/`. Ela não inclui o template de exemplo (`template.qmd`). Para começar do zero, use a **Opção A**.

> **Dica:** Usamos o RStudio por ser o ambiente mais eficiente para documentos Quarto — preview integrado, suporte nativo a chunks R e renderização unificada.

### Exemplo de cabeçalho YAML

```yaml
---
title: "TÍTULO DO TRABALHO"
author: "Seu Nome"
date: "2026"
format: ppgens-univasf-projeto
orientador: "Prof. Dr. Nome do Orientador"
area-concentracao: "Sua área de concentração"
abstract: "Resumo do trabalho..."
---
```

### Renderizar

No RStudio, clique em **Render**. Ou no terminal:

```bash
quarto render documento.qmd --to ppgens-univasf-projeto
```

---

## 📋 Setup inicial (faça uma vez)

### Passo 1 — Quarto CLI

Baixe o instalador em [quarto.org/docs/get-started](https://quarto.org/docs/get-started/):

| SO | Arquivo |
|----|---------|
| Fedora | `.rpm` |
| Ubuntu / Debian | `.deb` |
| macOS | `brew install --cask quarto` |
| Windows | `.msi` |

```bash
quarto --version   # precisa ser ≥ 1.6.0
```

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

```bash
quarto --version          # ≥ 1.6.0
lualatex --version        # funciona
kpsewhich abntex2-alf.bst # retorna caminho
fc-list | grep -i libertinus  # fontes instaladas
```

---

## 📁 Estrutura do repositório

```
quarto_templates_ptbr/
├── _extensions/
│   └── ppgens-univasf-projeto/    # Extensão Quarto
│       ├── _extension.yml
│       ├── abnt.csl               # Estilo ABNT
│       └── partials/
│           ├── title.tex
│           └── before-body.tex
├── templates-universitarios/      # Documentação dos templates
│   └── ppgens-univasf/
│       └── projeto/
│           └── README.md
├── template.qmd                   # Template de exemplo
├── LICENSE
└── README.md
```

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
