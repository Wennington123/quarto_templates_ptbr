# Quarto Templates — Universidades Brasileiras 🇧🇷

[![Quarto](https://img.shields.io/badge/Quarto-%3E%3D1.6.0-blue)](https://quarto.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

Repositório de formatos customizados do [Quarto](https://quarto.org) para trabalhos acadêmicos em universidades brasileiras. Cada extensão implementa as regras de formatação ABNT e os requisitos específicos de cada programa de pós-graduação.

---

## 📦 Extensões disponíveis

| Extensão | Instituição | Programa | Documento | Ano |
|----------|-------------|----------|-----------|-----|
| [`ppgens-univasf-projeto`](./_extensions/ppgens-univasf-projeto/) | UNIVASF | PPGENS | **Projeto de Mestrado** | 2026 |

**Legenda dos tipos de documento:**
- **Projeto** — Projeto de pesquisa submetido como avaliação de componente curricular
- **Qualificação** — Texto para exame de qualificação (em breve)
- **Dissertação** — Texto final de defesa (em breve)

---

## 🚀 Instalação

### Como template (recomendado para começar um novo projeto)

Cria uma pasta com o template pronto para editar:

```bash
quarto use template Wennington123/quarto_templates_ptbr
```

### Como extensão (adiciona o formato a um projeto existente)

```bash
quarto add Wennington123/quarto_templates_ptbr
```

---

## ✍️ Uso

Após instalar, use o formato no YAML do seu documento `.qmd`:

```yaml
---
title: "TÍTULO DO PROJETO DE PESQUISA"
author: "Seu Nome"
date: "2026"
format: ppgens-univasf-projeto
projeto-type: "Fundamentos Teóricos e Metodológicos da Pesquisa"
orientador: "Prof. Dr. Nome do Orientador"
area-concentracao: "Ensino e Práticas de Formação Docente no Semiárido"
abstract: "Resumo do trabalho..."
---
```

### Campos YAML específicos do PPGENS-UNIVASF

| Campo | Descrição |
|-------|-----------|
| `projeto-type` | Nome do componente curricular |
| `orientador` | Nome do(a) orientador(a) |
| `area-concentracao` | Área de concentração do programa |
| `doc-type` | Tipo de documento: `Dissertação` (para qualificação/defesa) |
| `dedicatoria` | Texto da dedicatória |
| `agradecimentos` | Texto dos agradecimentos |
| `epigrafe` | Texto da epígrafe |
| `folha-aprovacao` | Caminho para PDF da folha de aprovação |

### Renderizar

```bash
quarto render documento.qmd --to ppgens-univasf-projeto
```

---

## 📋 Requisitos e Setup por Sistema Operacional

### ① Quarto CLI

O Quarto pode ser usado com **qualquer editor** — RStudio, VS Code, Positron, Neovim, ou até no terminal. O `quarto render` é só uma linha de comando.

| SO | Instalação |
|----|-----------|
| **Fedora** | Baixar `.rpm` em [quarto.org/docs/get-started](https://quarto.org/docs/get-started/) |
| **Ubuntu/Debian** | Baixar `.deb` na mesma página |
| **macOS** | `brew install --cask quarto` |
| **Windows** | Baixar `.msi` na mesma página |

Verifique:
```bash
quarto --version  # deve ser ≥ 1.6.0
```

### ② LaTeX (LuaLaTeX)

Necessário para gerar PDF. O Quarto usa Pandoc + LuaLaTeX por trás.

#### Fedora
```bash
sudo dnf install texlive-scheme-medium texlive-libertinus texlive-abntex2
```

#### Ubuntu / Debian
```bash
sudo apt install texlive-latex-extra texlive-fonts-extra texlive-lang-portuguese
sudo apt install fonts-libertinus
```

#### macOS
```bash
brew install --cask mactex-no-gui
# Depois: sudo tlmgr install libertinus abntex2
```

#### Windows
Baixar [MiKTeX](https://miktex.org/download) ou [TeX Live](https://tug.org/texlive/windows.html). Durante a instalação, marcar "Install missing packages on the fly".

### ③ R e RStudio (opcional — para análise de dados)

Se seu projeto envolve análises estatísticas com `.qmd`, instale o R:

| SO | Instalação |
|----|-----------|
| **Fedora** | `sudo dnf install R` |
| **Ubuntu** | `sudo apt install r-base` |
| **macOS** | Baixar [CRAN .pkg](https://cran.r-project.org/bin/macosx/) |
| **Windows** | Baixar [CRAN .exe](https://cran.r-project.org/bin/windows/base/) |

RStudio é opcional — você pode editar `.qmd` com o editor que preferir:
- [RStudio Desktop](https://posit.co/download/rstudio-desktop/) (mais amigável pra R)
- [VS Code](https://code.visualstudio.com/) + extensão [Quarto](https://marketplace.visualstudio.com/items?itemName=quarto.quarto)
- [Positron](https://github.com/posit-dev/positron)
- Neovim + [quarto-nvim](https://github.com/quarto-dev/quarto-nvim)

### ④ Pacotes R necessários (se usar chunks R)

```r
install.packages(c("knitr", "rmarkdown"))
```

### ⑤ Estilo bibliográfico ABNT

O formato usa `abntex2-alf` como estilo bibliográfico. Ele já vem com:

- **Fedora:** `sudo dnf install texlive-abntex2`
- **Ubuntu:** incluso no `texlive-latex-extra`
- **macOS:** `sudo tlmgr install abntex2`
- **Windows:** MiKTeX baixa automaticamente sob demanda

### Checklist rápido

```bash
quarto --version        # ≥ 1.6.0
lualatex --version      # deve funcionar sem erro
kpsewhich abntex2-alf.bst  # deve retornar um caminho
fc-list | grep -i libertinus  # deve listar as fontes
```

---

## 📁 Estrutura do repositório

```
quarto_templates_ptbr/
├── _extensions/
│   └── ppgens-univasf-projeto/    # Extensão para Projeto de Mestrado
│       ├── _extension.yml         # Definição do formato PDF
│       └── partials/              # Templates LaTeX
│           ├── title.tex          # Capa e folha de rosto
│           └── before-body.tex     # Elementos pré-textuais
├── templates-universitarios/      # Documentação das regras de cada template
│   └── ppgens-univasf/
│       └── projeto/
│           └── README.md          # Especificações ABNT e estrutura
├── template.qmd                   # Template de exemplo
├── LICENSE
└── README.md
```

---

## 🤝 Contribuindo

Quer adicionar o template da sua universidade?

1. Faça um fork do repositório
2. Crie a extensão em `_extensions/universidade-tipo/`
3. Documente as regras em `templates-universitarios/universidade/tipo/`
4. Abra um Pull Request

---

## 📄 Licença

MIT — veja o arquivo [LICENSE](LICENSE).
