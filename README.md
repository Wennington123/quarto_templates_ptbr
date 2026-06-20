# Quarto Templates — Periódicos e Universidades Brasileiras 🇧🇷

[![Quarto](https://img.shields.io/badge/Quarto-%3E%3D1.6.0-blue)](https://quarto.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

Formatos customizados do [Quarto](https://quarto.org) para trabalhos acadêmicos em periódicos e universidades brasileiras.

Atualmente disponível:

| Template | Programa | Instituição |
|----------|----------|-------------|
| Projeto de Pesquisa de Mestrado | PPGENS (Mestrado em Ensino) | UNIVASF |

---

## 📋 Instalação

### 1. Instalar o R

| SO | Como instalar |
|----|---------------|
| **Fedora** | `sudo dnf install R` |
| **Ubuntu / Debian** | `sudo apt install r-base` |
| **Windows** | Baixar o instalador em [cran.r-project.org/bin/windows/base](https://cran.r-project.org/bin/windows/base/) e executar. |
| **macOS** | Baixar o `.pkg` em [cran.r-project.org/bin/macosx](https://cran.r-project.org/bin/macosx/) e executar. |

> No Linux, algumas distribuições podem não ter a versão mais recente do R nos repositórios oficiais. Nesse caso, siga as instruções do [CRAN para Linux](https://cran.r-project.org/bin/linux/) para adicionar o repositório correto.

### 2. Instalar o RStudio

Baixe o instalador da sua plataforma em [posit.co/download/rstudio-desktop](https://posit.co/download/rstudio-desktop/):

| SO | Arquivo |
|----|---------|
| **Fedora** | `.rpm` (baixar e instalar com `sudo dnf install ./rstudio*.rpm`) |
| **Ubuntu / Debian** | `.deb` (baixar e instalar com `sudo dpkg -i rstudio*.deb`) |
| **Windows** | `.exe` (executar o instalador) |
| **macOS** | `.dmg` (arrastar para a pasta Applications) ou via Homebrew: `brew install --cask rstudio` |

### 3. Instalar os pacotes R

Abra o RStudio e, no **Console** (geralmente à esquerda ou embaixo), cole e execute:

```r
install.packages(c("knitr", "rmarkdown", "quarto"))
```

> Pode levar alguns minutos na primeira vez. Aguarde o prompt `>` aparecer de novo antes de prosseguir.

### 4. Instalar o Quarto CLI

O RStudio já vem com o Quarto empacotado, mas para usar o template pela linha de comando (ou garantir a versão mais recente), instale o Quarto CLI separadamente:

| SO | Como instalar |
|----|---------------|
| **Fedora** | Baixar o `.rpm` em [quarto.org/docs/get-started](https://quarto.org/docs/get-started/) e instalar com `sudo dnf install ./quarto*.rpm` |
| **Ubuntu / Debian** | Baixar o `.deb` e instalar com `sudo dpkg -i quarto*.deb` |
| **Windows** | Baixar o `.msi` e executar |
| **macOS** | `brew install --cask quarto` |

Para verificar se o Quarto foi instalado corretamente:

```bash
quarto --version
```

### 5. Instalar o LaTeX (para gerar PDF)

Sem o LaTeX não é possível compilar o PDF. A forma mais prática é instalar o TinyTeX direto do R:

No **Console** do RStudio:

```r
tinytex::install_tinytex()
```

> O TinyTeX é uma distribuição LaTeX leve que instala pacotes sob demanda. Se preferir uma instalação completa, veja as alternativas abaixo.

<details>
<summary>Alternativas ao TinyTeX (clique para expandir)</summary>

| SO | Alternativa |
|----|-------------|
| **Fedora** | `sudo dnf install texlive-scheme-medium texlive-abntex2` |
| **Ubuntu / Debian** | `sudo apt install texlive-latex-extra texlive-fonts-extra texlive-lang-portuguese` |
| **macOS** | `brew install --cask mactex-no-gui` <br> Depois: `sudo tlmgr install abntex2 libertinus` |
| **Windows** | Baixar [MiKTeX](https://miktex.org/download). Durante a instalação, marque **"Install missing packages on the fly"**. |

</details>

### Verificação rápida

No terminal do RStudio (`Tools → Terminal`) ou no seu terminal:

```bash
quarto --version          # ≥ 1.6.0
lualatex --version        # deve mostrar a versão
kpsewhich abntex2-alf.bst # deve retornar um caminho
```

---

## 🚀 Como usar

### Abrir o projeto

1. Abra o **RStudio**.
2. Vá em `File → Open Project...` e selecione o arquivo `main.Rproj` dentro da pasta do template desejado (ex.: `ppgens/projeto_mestrado_ppgens/main.Rproj`).
3. O RStudio vai abrir o projeto e configurar o diretório de trabalho automaticamente.

### Renderizar o PDF

1. No painel **Files** (no canto inferior direito do RStudio), clique no arquivo `main.qmd`.
2. Clique no botão **Render** (no topo do editor, com um ícone de engrenagem ou seta) — ou pressione `Ctrl+Shift+K` (`Cmd+Shift+K` no macOS).
3. A saída PDF será gerada na mesma pasta do projeto.

> Na primeira renderização o TinyTeX pode baixar pacotes LaTeX adicionais automaticamente. Pode levar alguns minutos.

### Personalizar o template

Edite o arquivo `main.qmd`:

- **Dados pessoais**: Altere nome, título, orientador(a), área de concentração no cabeçalho YAML (no topo do arquivo, entre `---`).
- **Conteúdo**: Escreva o texto do seu projeto nas seções existentes (Introdução, Objetivos, Metodologia, etc.).
- **Referências**: Edite o arquivo `references.bib` no formato BibTeX. As citações no texto usam `@chave`.

---

## 🤝 Contribuindo

Quer adicionar o template da sua universidade?

1. Faça um fork do repositório.
2. Crie uma pasta com o padrão `instituicao/programa-tipo/` (ex.: `ufabc/ppgh-dissertacao/`).
3. Coloque o template Quarto (`.qmd`), o projeto RStudio (`.Rproj`), o arquivo de referências (`.bib`), o CSL da ABNT e os logos.
4. Envie um Pull Request.

---

## 📄 Licença

MIT — veja [LICENSE](LICENSE).
