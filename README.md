# ABNT NBR 6023:2025 (pt-BR) — CSL para Mendeley/Zotero

Este repositório contém um arquivo **CSL (Citation Style Language)** adaptado para refletir as **regras da ABNT NBR 6023:2025** (referências) e manter o padrão **autor-data** para citações no texto.

> Baseado no estilo ABNT tradicional (Zotero) e ajustado para as atualizações destacadas no PDF `ABNT_referencias_maio_2025_2`.

---

## 📁 Arquivo principal

- `abnt-6023-2025-adaptado.csl`  
  Estilo CSL para usar em **Mendeley** (Desktop/Reference Manager) e **Zotero**.

---

## ✅ O que este estilo implementa (principais ajustes)

### 1) Autoria com muitos autores
- **Bibliografia:** por padrão **lista todos os autores** (configurado para não usar *et al.*).
- **Citação no texto:** usa *et al.* a partir de **4 autores** (padrão comum em autor-data).

> Observação: a ABNT 6023:2025 diz que “convém indicar todos”, mas permite abreviação (ex.: primeiro autor + *et al.*).  
> Se você quiser que a bibliografia use *et al.* também, veja a seção “Como personalizar”.

### 2) Local/Editora ausentes
O estilo aplica automaticamente:
- `[S. l.]` quando **falta local**
- `[s. n.]` quando **falta editora**
- `[S. l.: s. n.]` **em itálico** quando faltam **ambos**

### 3) Obras sem autoria
- Se não houver `author/editor/translator`, o estilo **não aplica negrito no título** (conforme a orientação do material-base).

> Limitação CSL: a regra “colocar a primeira palavra do título em CAIXA ALTA” não é implementável de forma perfeita no CSL.  
> Se isso for exigência rígida, a forma mais confiável é **editar o campo Título** já com a 1ª palavra em maiúsculas.

### 4) Artigos com DOI/URL/Acesso
Para artigos (`article-journal`, `article-magazine`, `article-newspaper`):
- adiciona **DOI** (se existir)
- adiciona **URL + data de acesso** (se existir)

### 5) Referência de IA / Software
Para o tipo CSL `software`, o estilo imprime:
- Autor
- Título
- Versão (`version`)
- Local
- Data (dia/mês/ano, quando disponível)
- `genre` (ex.: modelo)
- URL + Acesso

---

## 🚀 Como usar no Zotero

1. Baixe o arquivo `.csl` deste repositório.
2. No Zotero: **Preferences** → **Cite** → **Styles** → **+** (Add Style).
3. Selecione o arquivo `.csl`.

---

## 🚀 Como usar no Mendeley

### Mendeley Desktop (legado)
1. Baixe o arquivo `.csl`.
2. Abra o Mendeley Desktop.
3. Vá em: **View → Citation Style → More Styles…**
4. Aba **Get More Styles** (ou **Installed**) → **Add** / **Install CSL**
5. Selecione o arquivo `.csl`.

### Mendeley Reference Manager (novo)
O suporte a estilos CSL pode variar por versão. Se não aparecer a opção de instalar:
- use via **Zotero** para gerar as referências, ou  
- exporte a bibliografia em formato intermediário e formate no processador de texto.

---

## 🧾 Campos recomendados para preencher (Mendeley/Zotero)

Para obter o resultado correto, confira se os seguintes campos estão preenchidos:

### Artigos
- **Author**
- **Title**
- **Journal / Container title**
- **Year (Issued)**
- **Volume / Issue**
- **Pages**
- **DOI** (se houver)
- **URL** + **Accessed** (se for online)

### Livros
- **Author**
- **Title**
- **Edition** (se houver)
- **Place** (cidade)
- **Publisher**
- **Year**

### Webpages
- **Author** (se houver)
- **Title**
- **URL**
- **Accessed**

### IA / Software (tipo: Software)
- **Author** (ex.: OpenAI)
- **Title** (ex.: ChatGPT)
- **Version** (ex.: 5.2)
- **Place** (ex.: San Francisco, CA) — se você quiser seguir um modelo mais formal
- **Issued** (data)
- **Genre** (ex.: “Modelo: GPT-5.2”)
- **URL**
- **Accessed**

---

## 🔧 Como personalizar (rápido)

### A) Quer *et al.* na bibliografia a partir de 4 autores?
No bloco `<bibliography ...>` altere para:

```xml
<bibliography hanging-indent="false" et-al-min="4" et-al-use-first="1" entry-spacing="1">
