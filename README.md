# Agente NL ↔ CPC - Lógica para Computação

> Trabalho da disciplina **Lógica para Computação**
> Uni-FACEF - Professor Márcio Funes

---

## 📝 Descrição

Este projeto é um **Agente de IA simples para Web**, capaz de:

1. **Traduzir sentenças em linguagem natural (NL) em português para fórmulas do Cálculo Proposicional Clássico (CPC)**.
2. **Traduzir fórmulas do CPC para frases em português compreensíveis**.

O objetivo é auxiliar o aprendizado de **lógica proposicional**, tornando a transição entre **linguagem natural** e **notação formal** mais intuitiva.

---

## 🎯 Funcionalidades

### 1️⃣ Definir proposições
- Defina proposições (`P`, `Q`, `R`, etc.) e seus significados em português.
- Proposições podem ser adicionadas, editadas ou removidas.
- O sistema sugere proposições automaticamente se detectar termos desconhecidos.

### 2️⃣ NL → CPC
- Tradução de frases simples em português para fórmulas proposicionais.
- Reconhece conectivos: **e**, **ou**, **não**, **Se… então**, **nem… nem**.

### 3️⃣ CPC → NL
- Tradução de fórmulas proposicionais para frases em português usando os significados definidos.
- Suporta conectivos: ∧, ∨, ¬, →, ↔.

### 4️⃣ Extras
- Normalização de fórmulas: converte símbolos alternativos (->, =>, ~, &&, ||) para padrões ∧, ∨, ¬, →, ↔.
- Sugestão automática de proposições a partir de frases.

---

## 📌 Como usar

1. Abra `index.html` no navegador.
2. **Defina proposições** (P, Q, R...) e seus significados.
3. **NL → CPC**
   - Digite uma frase em português.
   - Clique **Converter NL → CPC**.
   - Fórmula gerada será exibida.
4. **CPC → NL**
   - Digite uma fórmula CPC usando proposições definidas.
   - Clique **Converter CPC → NL**.
   - Frase em português será exibida.
5. **Dicas**
   - Use frases simples e claras.
   - Ajuste proposições para sentido correto.
   - Teste com os exemplos fornecidos.

---

## 🧩 Exemplos de uso

### 1️⃣ NL → CPC

**Frase:**  
*"Se chover, então a grama ficará molhada."*

**Fórmula gerada:**  
`P → Q`

---

### 2️⃣ CPC → NL

**Fórmula:**  
`(P ∧ Q) → R`

**Frase gerada:**  
*"Se (chover e fizer frio), então a aula será cancelada."*

---

## 💻 Tecnologias

- **HTML / CSS / JavaScript** — interface e lógica.
- **Heurísticas de NLP simples** — sem bibliotecas externas.
- Frontend puro → fácil hospedagem online.

---

## ⚠️ Observações

- Tradutor é **educacional** e baseado em regras simples.
- Frases complexas podem gerar sugestões imperfeitas.
- Para maior precisão, integrar **OpenAI API ou HuggingFace** é possível, mas **não inclua chaves no código público**.

---

## 📂 Estrutura do projeto

├── index.html # Interface web e lógica principal
├── README.md # Este arquivo
└── (opcional) assets/ # Imagens ou GIFs explicativos

---

## 🌐 Hospedagem

- [GitHub Pages](https://pages.github.com/)

Basta subir o `index.html` e abrir no navegador.

---

## 📖 Referências

- Disciplina **Lógica para Computação**, Uni-FACEF  
- Introdução à **Lógica Proposicional**  
- HTML/CSS/JS para desenvolvimento web
