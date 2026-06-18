# PPGENS-UNIVASF — Projeto de Mestrado (Turma 2026)

Modelo oficial de **Projeto de Pesquisa** do **Programa de Pós-Graduação em Ensino (PPGENS)** da **Universidade Federal do Vale do São Francisco (UNIVASF)** — Campus Senhor do Bonfim (BA).

> **Última atualização:** 2026, conforme modelo da turma 2026.
> **Tipo de documento:** Projeto de Pesquisa para avaliação de componente curricular.

---

## Setup rápido por sistema operacional

### Fedora
```bash
sudo dnf install texlive-scheme-medium texlive-libertinus texlive-abntex2
```

### Ubuntu / Debian
```bash
sudo apt install texlive-latex-extra texlive-fonts-extra texlive-lang-portuguese fonts-libertinus
```

### macOS
```bash
brew install --cask mactex-no-gui
sudo tlmgr install libertinus abntex2
```

### Windows
Baixar [MiKTeX](https://miktex.org/download). Marcar "Install missing packages on the fly".

---

## Estrutura do documento

### Elementos pré-textuais (obrigatórios)

1. **Capa** — Nome da universidade, programa, autor, título, local e ano
2. **Folha de rosto** — Autor, título, natureza do trabalho, orientador, área de concentração
3. **Lista de ilustrações** (opcional)
4. **Lista de tabelas** (opcional)
5. **Lista de abreviaturas e siglas** (opcional)
6. **Lista de símbolos** (opcional)
7. **Resumo**
8. **Sumário**

### Elementos textuais (obrigatórios)

1. **Introdução** — contextualização, justificativa (acadêmica e social), problema de pesquisa
2. **Objetivos** — geral e específicos (3-4)
3. **Referencial teórico** — revisão da literatura, conceitos, lacunas
4. **Metodologia** — local, amostra, critérios, método, ética, análise, riscos/benefícios
5. **Cronograma** — 24 meses com etapas discriminadas
6. **Orçamento** — equipamentos, material de consumo, serviços, diárias, ressarcimento

### Elementos pós-textuais

1. **Referências** — ABNT NBR 6023/2018
2. **Glossário** (opcional)
3. **Apêndices** (opcional)
4. **Anexos** (opcional)

---

## Formatação

| Elemento              | Especificação                                 |
|-----------------------|-----------------------------------------------|
| Fonte                 | Times New Roman 12pt ou Arial 11pt            |
| Espaçamento           | 1,5                                           |
| Margens               | Superior 2cm, Esquerda 2cm, Inferior 2cm, Direita 2cm |
| Numeração de páginas  | Canto superior direito, a partir da Introdução |
| Tamanho               | Mínimo 15, máximo 25 páginas                  |

---

## Normas ABNT

- **Formatação geral**: NBR 14724/2023
- **Citações**: NBR 10520/2023
- **Referências**: NBR 6023/2018
- **Estilo bibliográfico**: `abntex2-alf`

### Regras de citação

- Até 3 linhas: entre aspas, no corpo do texto
- Acima de 3 linhas: recuo de 4cm, fonte 10, sem aspas

---

## Editores compatíveis

O formato é agnóstico ao editor. Você pode editar `.qmd` com:

- **RStudio** — preview integrado, chunks R nativos
- **VS Code** + [extensão Quarto](https://marketplace.visualstudio.com/items?itemName=quarto.quarto)
- **Positron** — preview integrado
- **Neovim** + [quarto-nvim](https://github.com/quarto-dev/quarto-nvim)
- **Terminal** — editar com qualquer editor, renderizar com `quarto render`

---

## Observações

- Redação em linguagem acadêmica, impessoal (evitar 1ª pessoa)
- Texto contínuo e articulado (exceto objetivos e cronograma)
- Problema de pesquisa em forma de **pergunta clara e objetiva**
- Referências em ordem alfabética, sem numeração
- A pesquisa somente terá início após aprovação do Comitê de Ética em Pesquisa (CEP)
- O projeto deve seguir o **Guia para Submissão de Projetos de Pesquisa Envolvendo Seres Humanos** do CEP/UNIVASF
