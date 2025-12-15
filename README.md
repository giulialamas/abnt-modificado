# ABNT NBR 6023:2025 (pt-BR) — CSL para Mendeley / Zotero

Este repositório disponibiliza um **estilo CSL (Citation Style Language)** adaptado às **atualizações da ABNT NBR 6023:2025**, com foco em referências bibliográficas e citações no sistema **autor-data**, compatível com **Mendeley** e **Zotero**.

⚠️ **Importante**: o **Mendeley não aceita mais upload direto de arquivos `.csl`**.  
O estilo deve ser carregado **via URL (raw GitHub)**.

---

## 📁 Arquivo do estilo

- **`abnt-6023-2025-adaptado.csl`**

URL RAW (uso obrigatório no Mendeley):

https://raw.githubusercontent.com/giulialamas/abnt-modificado/refs/heads/main/abnt-6023-2025-adaptado.csl


---

## ✅ Principais adequações à ABNT NBR 6023:2025

### 🔹 Autoria
- **Bibliografia**: lista **todos os autores** (configuração padrão do estilo).
- **Citação no texto**: usa *et al.* a partir de **4 autores**.

> A norma indica que “convém indicar todos”, mas permite abreviação — esta implementação privilegia conformidade acadêmica.

---

### 🔹 Ausência de local e/ou editora
Aplicação automática de:
- `[S. l.]` → sem local
- `[s. n.]` → sem editora
- `[S. l.: s. n.]` → ambos ausentes (**em itálico**)

---

### 🔹 Obras sem autoria
- O título **não é exibido em negrito**, conforme orientação do material-base da ABNT 6023:2025.

> Limitação técnica do CSL: a regra “primeira palavra do título em CAIXA ALTA” não pode ser aplicada com precisão automática.  
> Caso exigido, recomenda-se ajustar manualmente o campo **Title** no Mendeley/Zotero.

---

### 🔹 Artigos científicos
- Inclui automaticamente:
  - **DOI** (se existir)
  - **URL**
  - **Data de acesso**

---

### 🔹 Referência de IA / Software (ex.: ChatGPT)
Implementada via tipo CSL **`software`**, com os campos:
- Autor
- Título
- Versão
- Local
- Data
- `Genre` (ex.: modelo)
- URL
- Data de acesso

---

1. Copie a URL abaixo:
