# Quarto Templates — Universidades Brasileiras 🇧🇷

[![Quarto](https://img.shields.io/badge/Quarto-%3E%3D1.6.0-blue)](https://quarto.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

Repositório de formatos customizados do [Quarto](https://quarto.org) para trabalhos acadêmicos em universidades brasileiras. Cada extensão implementa as regras de formatação ABNT e os requisitos específicos de cada programa de pós-graduação.

---

## 📦 Extensões disponíveis

| Extensão | Instituição | Programa | Documento |
|----------|-------------|----------|-----------|
| [`ppgens-univasf`](./_extensions/ppgens-univasf/) | UNIVASF | PPGENS | Projeto de Pesquisa / Qualificação / Dissertação |

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
title: "TÍTULO DO TRABALHO"
author: "Seu Nome"
date: "2026"
format: ppgens-univasf
projeto-type: "Fundamentos Teóricos e Metodológicos da Pesquisa"
orientador: "Prof. Dr. Nome do Orientador"
area-concentracao: "Ensino e Práticas de Formação Docente no Semiárido"
abstract: "Resumo do trabalho..."
---
```

### Campos YAML específicos do PPGENS-UNIVASF

| Campo | Descrição |
|-------|-----------|
| `projeto-type` | Nome do componente curricular (projetos) |
| `orientador` | Nome do(a) orientador(a) |
| `area-concentracao` | Área de concentração do programa |
| `doc-type` | Tipo de documento: "Dissertação" ou "Tese" (qualificação/defesa) |
| `dedicatoria` | Texto da dedicatória |
| `agradecimentos` | Texto dos agradecimentos |
| `epigrafe` | Texto da epígrafe |
| `folha-aprovacao` | Caminho para PDF da folha de aprovação |

### Renderizar

```bash
quarto render documento.qmd --to ppgens-univasf
```

---

## 📋 Requisitos

- [Quarto](https://quarto.org/docs/get-started/) ≥ 1.6.0
- [LuaLaTeX](https://www.latex-project.org/get/) (necessário para output PDF)
- Fontes Libertinus instaladas no sistema

```bash
# Fedora
sudo dnf install texlive-libertinus

# Ubuntu/Debian
sudo apt install fonts-libertinus
```

---

## 📁 Estrutura do repositório

```
quarto_templates_ptbr/
├── _extensions/
│   └── ppgens-univasf/        # Extensão Quarto do PPGENS
│       ├── _extension.yml     # Definição do formato
│       └── partials/          # Templates LaTeX
│           ├── title.tex      # Capa e folha de rosto
│           └── before-body.tex # Elementos pré-textuais
├── templates-universitarios/  # Documentação das regras de cada template
│   └── ppgens-univasf/
│       └── README.md          # Especificações ABNT e estrutura
├── template.qmd               # Template de exemplo
├── LICENSE
└── README.md
```

---

## 🤝 Contribuindo

Quer adicionar o template da sua universidade?

1. Faça um fork do repositório
2. Crie a extensão em `_extensions/sua-universidade/`
3. Documente as regras em `templates-universitarios/sua-universidade/`
4. Abra um Pull Request

---

## 📄 Licença

MIT — veja o arquivo [LICENSE](LICENSE).
