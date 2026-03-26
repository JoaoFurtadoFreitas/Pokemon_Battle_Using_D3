# D3 Pokémon Battle

## 🖼️ Nome da Obra
**Batalha pokemon**

---
## Contribuidores
**Implementação do Vine Whip** - João Furtado 
## 📌 Descrição

Esta visualização interativa simula uma batalha no estilo clássico de Pokémon utilizando **D3.js** e **SVG**. O foco principal da implementação é o ataque **Vine Whip**, que combina animação fluida, feedback visual e interação do usuário para criar uma experiência lúdica e envolvente.

Diferente do uso tradicional do D3 voltado para gráficos de dados, este projeto explora a biblioteca como uma ferramenta de **animação e narrativa visual**, priorizando estética, dinamismo e interatividade.

---

## 🎮 Como Interagir

> **Instrução:** Passe o mouse sobre os golpes e clique em **“VINE WHIP”**

- Ao passar o mouse sobre um golpe:
  - Uma seta aparece indicando a seleção
- Ao clicar em **VINE WHIP**:
  - Um cipó é animado do jogador até o oponente
  - O oponente recebe dano
  - A barra de HP é atualizada
  - Um efeito de impacto é exibido
  - A câmera aplica um leve zoom na ação

---

## ✨ Funcionalidades

### 🌱 Animação do Ataque

- O ataque é desenhado dinamicamente usando `SVG path`
- Utiliza curvas de Bézier para simular o movimento natural de um cipó
- A animação ocorre em duas fases:
  - **Extensão** (ataque)
  - **Retração** (retorno)

---

### 💥 Sistema de Dano

- Dano aleatório entre **15 e 24**
- Aplicado exatamente no momento do impacto
- O HP nunca fica negativo

```js
const damage = Math.floor(Math.random() * 10) + 15;
```

---

### ❤️ Barra de Vida Dinâmica

- Escala proporcional com `d3.scaleLinear`
- Transição suave na redução de HP
- Mudança de cor baseada na vida restante:
  - 🟢 Verde: acima de 50%
  - 🟡 Amarelo: entre 20% e 50%
  - 🔴 Vermelho: abaixo de 20%

---

### 🔴 Feedback Visual (Impacto)

- O oponente pisca em vermelho ao ser atingido
- Uso de `filter` e `brightness` para reforçar o feedback visual

---

### 🔍 Zoom Cinemático

- Zoom-in durante o ataque
- Zoom-out ao final da animação
- Direciona o foco do usuário para o momento da ação

---

### 🔒 Controle de Estado

- Uso da variável `isBattling` para impedir múltiplos ataques simultâneos
- Evita sobreposição de animações e inconsistências no estado do jogo

---

### 🎯 Camada de Animação

- Criação de um `attackLayer` separado
- Garante que os efeitos visuais apareçam acima dos sprites

---

## 🎯 Objetivo

A implementação do **Vine Whip** busca:

- Criar uma experiência interativa e divertida
- Explorar o uso do D3.js além de gráficos tradicionais
- Demonstrar animações complexas com SVG
- Melhorar o feedback visual para o usuário
