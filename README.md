# DevClub /> — Landing Page

Landing page de uma formação de programação (estilo bootcamp). O site conta o "problema" de quem tenta aprender sozinho, mostra a solução da trilha, faixas salariais, depoimentos, formações disponíveis e termina com um CTA (botão de matrícula) que leva pro WhatsApp.

---

## 1. Como abrir o projeto

Não tem nenhuma instalação ou servidor. É **um único arquivo `.html`** com tudo dentro dele: HTML, CSS e JavaScript.

Pra rodar:

1. Baixe o arquivo `index.html`.
2. Clique duas vezes nele (ou arraste pra dentro do navegador).
3. Pronto — ele abre igual a um site normal.


---

## 2. Por que é um arquivo só?

Normalmente um site profissional separa tudo em vários arquivos (`.html`, `.css`, `.js`, pastas de imagem etc.) e usa ferramentas de build (Webpack, Vite...). Aqui não — é tudo num arquivo só, de propósito, pra ficar fácil de:
- Abrir e testar sem precisar instalar nada;
- Compartilhar (é só mandar um arquivo);
- Hospedar em qualquer lugar que aceite HTML puro (GitHub Pages, Netlify, até um servidor bem simples).

A desvantagem é que o arquivo fica grande e um pouco mais difícil de navegar — por isso ele tem **bastante comentário explicando as decisões**, então vale a pena ler os comentários enquanto mexe em algo.

---

## 3. Estrutura geral do arquivo

Abrindo o `index-v4.html`, você vai ver três partes bem grandes, nessa ordem:

```
<head>
  <style> ... TODO O CSS FICA AQUI ... </style>
</head>
<body>
  ... TODO O HTML DAS SEÇÕES DA PÁGINA ...
  <script> ... TODO O JAVASCRIPT FICA AQUI ... </script>
</body>
```

Ou seja: primeiro vem o estilo (cor, tamanho, layout), depois o conteúdo (textos, imagens, botões), e no final o comportamento (o que acontece quando você rola a página, clica em algo, etc.).

### As seções da página (na ordem que aparecem)

| Seção (`id`)     | O que é |
|---|---|
| `#hero`          | Título principal + contadores animados |
| `#salario`       | A "espiral" com as faixas salariais (Júnior/Pleno/Sênior) |
| `#problema`       | Bloco "problema vs solução" + comparação + 3 vantagens |
| `#stats`          | 4 cards de estatística (nota, número de aulas, horas, projetos) |
| `#paraquem`        | "Pra quem é o curso" |
| `#reviews`        | Carrossel de depoimentos |
| `#mindmap`        | Linha do tempo "como o DevClub funciona" |
| `#formacoes`      | Escolha de trilha (Front-end / Back-end / Full Stack) |
| `#vantagens`       | Cards de vantagens (suporte, mentoria, etc.) |
| `#founder`        | Sobre o fundador |
| `#destaques`       | Cards das formações em destaque |
| `#trust`          | Empresas onde ex-alunos foram contratados |
| `#fit`            | "Isso é / não é pra você" |
| `#faq`            | Perguntas frequentes |
| `#closing`         | Chamada final pro CTA |
| `<footer>`        | Rodapé |

---


## 4. Como o JavaScript funciona (resumo simples)

O `<script>` no final do arquivo é dividido em blocos, cada um cuidando de uma coisa. Os principais, em ordem de "o que fazem":

- **Cursor customizado** — troca a setinha do mouse por uma bolinha (só em telas com mouse de verdade).
- **Barra de progresso de leitura** — a linha fininha no topo que enche conforme você rola a página.
- **Reveal ao rolar** — os elementos que têm a classe `.reveal` aparecem com um efeito de "sobe e aparece" quando entram na tela. Usa uma ferramenta do navegador chamada `IntersectionObserver`, que avisa o JavaScript quando um elemento fica visível.
- **Contadores animados** — os números que sobem de 0 até o valor final (tipo "1.000 alunos"). Uma função só (`setupCounter`) cuida de todos eles, lendo configurações escritas direto no HTML (`data-target`, `data-prefix` etc.).
- **Chuva de código no fundo** — o efeito visual estilo Matrix, desenhado num `<canvas>` (não são milhares de elementos HTML, é só desenho de tela).
- **Espiral de salário** — o círculo que você arrasta pra ver Júnior/Pleno/Sênior usa um pouco de trigonometria (seno e cosseno) pra calcular a posição de cada card.
- **Accordions** — FAQ e a timeline do fundador abrem/fecham clicando, sempre fechando o anterior antes de abrir o novo.
- **Menu lateral (drawer)** e **modal de privacidade** — só ligam/desligam uma classe CSS (`.open`) pra mostrar/esconder.

---

## 5. Responsividade

O site já é responsivo (se adapta pra celular, tablet e desktop) usando `@media` no CSS

---

## 6. Dependências externas

O único recurso externo que o site carrega é a fonte do Google Fonts, declarada lá no `<head>`:

```html
<link href="https://fonts.googleapis.com/css2?family=Orbitron..." rel="stylesheet">
```

Fora isso, **zero bibliotecas, zero frameworks**. Nenhum React, jQuery, Bootstrap, nada. Só HTML, CSS e JavaScript puro.

---
