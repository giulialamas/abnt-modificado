# ABNT NBR 6023:2025 (pt-BR) — Estilo CSL para Mendeley e Zotero

Este repositório disponibiliza um **estilo CSL (Citation Style Language)** adaptado às **atualizações da ABNT NBR 6023:2025**, com foco em **referências bibliográficas** e **citações no sistema autor-data**, compatível com **Mendeley Cite (Word)** e **Zotero**.

> ⚠️ Observação importante: o **Mendeley não aceita mais upload direto de arquivos `.csl`**.  
> O estilo deve ser carregado **exclusivamente via URL (raw GitHub)**.

---

## 📁 Arquivo do estilo

- **`abnt-6023-2025-adaptado.csl`**

URL RAW para uso no Mendeley:

https://raw.githubusercontent.com/giulialamas/abnt-modificado/refs/heads/main/abnt-6023-2025-adaptado.csl


---

## 📌 Escopo e conformidade normativa

Este estilo foi desenvolvido a partir do estilo ABNT clássico (Zotero) e **adaptado com base no material de referência da ABNT NBR 6023:2025**, incluindo:

- forma de apresentação de autoria
- tratamento de ausência de local e/ou editora
- apresentação de artigos eletrônicos
- referências de software e inteligência artificial
- manutenção do padrão **autor-data** nas citações

> Recomenda-se sempre conferir exigências específicas de periódicos, programas de pós-graduação ou bancas avaliadoras.

---

## ✅ Principais características implementadas

### 🔹 Autoria
- **Bibliografia**: lista **todos os autores** por padrão (conforme recomendação da norma).
- **Citações no texto**: utiliza *et al.* a partir de **4 autores**.

---

### 🔹 Ausência de local e/ou editora
O estilo aplica automaticamente:
- `[S. l.]` → sem local
- `[s. n.]` → sem editora
- `[S. l.: s. n.]` → ambos ausentes (**em itálico**)

---

### 🔹 Obras sem autoria
- O título **não recebe destaque tipográfico (negrito)**.
- O tratamento segue a orientação apresentada no material-base da ABNT 6023:2025.

> Limitação técnica do CSL: a regra “colocar apenas a primeira palavra do título em CAIXA ALTA” não pode ser aplicada com total precisão automática.  
> Caso isso seja exigido, recomenda-se ajustar manualmente o campo **Title** no gerenciador de referências.

---

### 🔹 Artigos científicos
Para artigos de periódicos, revistas e jornais:
- inclusão automática de **DOI**, quando disponível
- inclusão de **URL** e **data de acesso**, quando aplicável

---

### 🔹 Referência de Inteligência Artificial / Software
Implementada via tipo CSL **`software`**, permitindo referenciar, por exemplo, ChatGPT e outros modelos computacionais, com os seguintes campos:
- Autor
- Título
- Versão
- Local
- Data
- `Genre` (ex.: modelo)
- URL
- Data de acesso

---

## 🚀 Como usar no **Mendeley Cite (suplemento do Word)**

Este é o método **atualmente recomendado**, pois o Mendeley funciona como **add-in do Microsoft Word**.

### Passo 1 — Abrir o Mendeley Cite
1. Abra o **Microsoft Word**.
2. Vá até a aba **Referências**.
3. Clique em **Mendeley Cite** para abrir o painel lateral.
4. Faça login na sua conta Mendeley, se solicitado.

---

### Passo 2 — Acessar as configurações de citação
No painel lateral do Mendeley Cite:
1. Clique em **Citation settings** (ícone de engrenagem ⚙️).
2. Em **Citation style**, clique em **Change citation style**.

---

### Passo 3 — Adicionar um estilo personalizado via URL
1. Role a lista de estilos até o final.
2. Clique em **Add a custom style**.
3. Selecione a opção **Add style using a URL**.
4. Cole a URL abaixo:

---

## 🛠 Opção complementar — Macro do Word para itálico em *et al.* (Mendeley Cite)

### Contexto
Embora o estilo CSL esteja corretamente configurado para aplicar itálico em *et al.* (conforme ABNT NBR 10520 / 6023), o **Mendeley Cite (suplemento do Word)** apresenta limitações conhecidas na renderização tipográfica de citações no texto, podendo ignorar a formatação definida no CSL.

Como alternativa **opcional**, **segura** e amplamente aceita em ambiente acadêmico, pode-se utilizar uma **macro do Microsoft Word** para aplicar itálico em *et al.* **após a finalização do texto**.

> ✔️ Não altera campos do Mendeley  
> ✔️ Não interfere na lógica das citações  
> ✔️ Aceita em dissertações, teses e artigos científicos  

---

### Como instalar a macro

1. No **Microsoft Word**, pressione:
   - **Windows**: `Alt + F11`
   - **macOS**: `Option + Fn + F11`

2. No **Editor VBA**:
   - Clique em **Insert → Module**
   - Um novo módulo em branco será criado

3. Cole o código da macro (abaixo) dentro do módulo

4. Feche o editor VBA e retorne ao Word

---

### Macro Word — aplicar itálico em *et al.*

```vba
Sub ItalicizeEtAl()
    Dim rng As Range

    Set rng = ActiveDocument.Content

    With rng.Find
        .ClearFormatting
        .Text = "et al."
        .Replacement.ClearFormatting
        .Replacement.Font.Italic = True
        .Replacement.Text = "et al."
        .Forward = True
        .Wrap = wdFindContinue
        .Format = True
        .MatchCase = False
        .MatchWholeWord = True
        .MatchWildcards = False
        .Execute Replace:=wdReplaceAll
    End With
End Sub

