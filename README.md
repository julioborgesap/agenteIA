# Agente NL ↔ CPC - Lógica para Computação

> Trabalho da disciplina **Lógica para Computação**
> Uni-FACEF - Professor Márcio Funes

---

## 📝 Descrição

Este projeto é um **Agente de IA para Web** capaz de:

1. Traduzir frases em português (NL) para **Cálculo Proposicional Clássico (CPC)**.
2. Traduzir fórmulas CPC para frases em português compreensíveis.

O objetivo é auxiliar o estudo de **lógica proposicional**, tornando a transição entre **linguagem natural** e **notação formal** mais intuitiva.

---

## 🏗 Arquitetura do Sistema

```
+-------------------+        +------------------------+
|                   |        |                        |
|   Interface Web   | <----> |   Lógica de Tradução   |
|  (HTML, CSS, JS)  |        | (NL ↔ CPC, heurísticas |
|                   |        | +regras de mapeamento) |
+-------------------+        +------------------------+
         |
         v
+-------------------+
|    Base de        |
|  Proposições      |
|  (P, Q, R...)     |
+-------------------+
```

* **Interface Web:** Recebe frases ou fórmulas, exibe resultados e permite definir proposições.
* **Base de proposições:** Armazena nomes (P, Q, R...) e seus significados em português.
* **Lógica de tradução:**

  * **NL → CPC:** identifica conectivos, negações e cláusulas, mapeia fragmentos para proposições existentes ou cria novas.
  * **CPC → NL:** interpreta a árvore sintática da fórmula e monta frases em português com base nos significados das proposições.

> Observação: Todo processamento é **client-side** (no navegador), sem necessidade de servidor backend.

---

## ⚙️ Estratégia de Tradução

### 1️⃣ NL → CPC

* Baseada em **regras e heurísticas**:

  * `Se ... então ...` → `→`
  * `e` → `∧`, `ou` → `∨`
  * `não` → `¬`
  * `nem ... nem ...` → `¬P ∧ ¬Q`
* **Mapeamento de termos:** cada fragmento da frase é comparado com proposições definidas.
* **Proposições novas:** se não houver correspondência, o sistema cria P, Q, R automaticamente.

### 2️⃣ CPC → NL

* **Parsing da fórmula:** transforma string em **árvore sintática**.
* **Reconstrução de frase:** percorre árvore e substitui símbolos por conectivos em português usando os significados das proposições.

### 3️⃣ Uso de LLMs (opcional)

* É possível integrar **OpenAI API ou HuggingFace** para melhorar a interpretação de frases complexas.
* Não está ativo no código atual para facilitar execução offline.

---

## 🧩 Exemplos de Input/Output

| Tipo     | Entrada                                    | Saída Esperada                               | Observação                                |
| -------- | ------------------------------------------ | -------------------------------------------- | ----------------------------------------- |
| NL → CPC | "Se chover e ventar, então aula cancelada" | `(P ∧ Q) → R`                                | Frase simples, heurística funciona.       |
| NL → CPC | "Não está chovendo"                        | `¬P`                                         | Negação simples corretamente mapeada.     |
| CPC → NL | `(P ∧ Q) → R`                              | "Se (chover e ventar), então aula cancelada" | Tradução coerente com proposições.        |
| NL → CPC | "Se chover ou nevar, não vamos à praia"    | `(P ∨ Q) → ¬R`                               | Detecta "ou" e "não" corretamente.        |
| CPC → NL | `¬(P ∨ Q)`                                 | "Não chover ou não ventar"                   | Frases compostas podem gerar ambiguidade. |

---

## ⚠️ Análise de Acertos e Erros

**Acertos:**

* Frases simples com conectivos diretos (`e`, `ou`, `não`, `Se... então`) são traduzidas corretamente.
* Negação composta (`¬(P ∧ Q)`) gera resultado coerente: `Não P ou Não Q`.

**Erros / limitações:**

* Frases longas ou com conjunções complexas podem gerar fórmulas incompletas ou ambíguas.
* Pronomes e termos implícitos (`ela`, `isso`) nem sempre são reconhecidos.
* Ambiguidade na linguagem natural pode gerar múltiplas interpretações possíveis.

---

## 💡 Possibilidades de Melhoria

* Integrar **modelo de LLM** (ChatGPT API ou HuggingFace) para NL → CPC mais preciso.
* Suporte a **frases compostas complexas** com múltiplos conectivos.
* Interface mais interativa: cores diferentes para cada proposição.
* Exportar fórmulas CPC em **PDF ou imagem**.
* Criar **histórico de traduções**.

---

## 💻 Tecnologias

* **HTML / CSS / JavaScript** — interface e lógica principal.
* **Heurísticas e parsing** — manipulação de strings e árvore sintática.
* Frontend puro → fácil hospedagem online (GitHub Pages, Replit, Vercel, etc.).

---

## 📂 Estrutura do projeto

```
.
├── index.html          # Interface web e lógica principal
└── README.md           # Este arquivo
```

---

## 📖 Referências

* Disciplina **Lógica para Computação**, Uni-FACEF
* Introdução à **Lógica Proposicional**
* HTML/CSS/JS para desenvolvimento web
