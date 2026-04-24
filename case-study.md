# Diego Tattoo Studio — Landing Page
### Posicionamento premium, conversão via WhatsApp, identidade visual autoral

---

## Visão Geral

| | |
|---|---|
| **Cliente** | Diego Tattoo Studio — Campo Formoso, BA |
| **Tipo** | Landing page de conversão (one-page) |
| **Função** | Design de UI · Front-end · Estratégia de CRO |
| **Stack** | HTML · CSS · JavaScript vanilla |
| **Status** | Entregue e publicado |

---

## Contexto

Diego é tatuador com mais de 12 anos de experiência, especializado em Realismo, Blackwork e Fine Line. Apesar do portfólio de alto nível, a presença digital era inexistente — indicações aconteciam pelo Instagram e boca a boca.

O objetivo era criar uma landing page que posicionasse o estúdio no segmento premium, gerasse confiança rapidamente e convertesse visitantes em agendamentos via WhatsApp.

---

## O Problema

Estúdios de tatuagem geralmente erram em uma das duas direções: **visual genérico** (templates Wix/Squarespace que não comunicam identidade) ou **portfólio sem CTA** (Instagram bonito, mas sem funil de conversão).

O desafio aqui era duplo:

1. Criar uma identidade visual forte o suficiente para comunicar **arte premium** — não serviço commodity
2. Construir um **fluxo de página que vende**: autoridade → confiança → ação

---

## Sistema de Design

Antes de qualquer componente, defini um sistema de design completo em CSS custom properties — o "The Noir Gallery".

**Paleta:**
- Background base: `#000000` (preto puro — máximo contraste com o dourado e profundidade cinematográfica)
- Superfícies em camadas: 5 níveis de `--surface-*` para profundidade sem bordas
- Acento dourado: `#e9c176` — único ponto de cor quente, máxima atenção quando usado

**Tipografia — 3 fontes com papéis distintos:**
- **Epilogue** (headline) — condensada, 900 weight, italic para emoção
- **Manrope** (body) — humanista, legível, 300 weight para sofisticação
- **Space Grotesk** (label/UI) — técnica, para botões e tags

**Grid:** container fixo de 1120px com padding responsivo via `max(24px, calc((100% - 1120px) / 2))` — alinha perfeitamente do mobile ao ultrawide sem media queries extras.

**Espaçamento:** baseline 8pt com escala `clamp()` em seções — ritmo consistente em qualquer viewport.

---

## Seções e Decisões

### Hero
Headline em dois registros: linha 1 em branco (declaração), linha 2 em dourado itálico (impacto emocional). CTA imediato para WhatsApp. Background com glow radial sutil para criar profundidade sem imagem.

**Detalhe:** cursor customizado como agulha de tatuagem (ponta dourada, haste rotacionada 45°) — reforço da identidade sem ser literal.

### Portfólio — Galeria
Grid assimétrico de 3 colunas com célula central em `span 2` (tall). O Blackwork (leão) domina o centro — hierarquia visual intencional que guia o olhar e demonstra a peça mais técnica primeiro.

Cada imagem com `object-fit: cover` e `object-position` calibrado manualmente por foto:
- Realismo (retrato de criança): `center top` — foco no rosto, não no relógio
- Realismo Colorido: `center 20%` — composição do leão no quadrante superior
- Artístico (águia): `filter: saturate(0.82) contrast(0.92)` — reduz peso visual para não competir com o centro

### Expertise (Estilos)
Cards com ícone circular em `outline` dourado, texto hierarquizado em três níveis (tag · título · descrição). Hover com `translateY(-6px)` + `box-shadow` profundo + `border-color` dourado no ícone — feedback visual premium sem JavaScript.

Copy estratégico: cada estilo tem uma promessa única, sem repetição de palavras entre os 4 cards.

### Sobre o Artista
Grid `1.25fr 1fr` com texto à esquerda e foto à direita — proporção deliberada: o texto leva, a foto confirma. Stats (12 anos, número de clientes) como prova social quantitativa.

### Biossegurança
Seção dedicada que poucos estúdios têm online. Sinal de confiança direto: o cliente sabe que a escolha é segura antes mesmo de perguntar.

### Depoimentos
Cards com estrelas, citação real, localidade do cliente. Sem carrossel — os três depoimentos aparecem juntos, o que transmite mais credibilidade do que um por vez.

### Localização
Dado real: Praça do Farias, Campo Formoso — BA. Google Maps embed com overlay CSS para integrar o iframe ao tema escuro sem workarounds.

### Modais de Suporte ao Cliente
Dois modais acessíveis pelo footer — **Guia de Pós-cuidado** e **Política de Cancelamento** — respondem as objeções silenciosas que impedem o agendamento.

O Guia de Pós-cuidado estrutura o cuidado em 4 fases (primeiras 24h, dias 2–7, semanas 2–4 e sinais de alerta), comunicando que o relacionamento com o estúdio não termina na sessão — um diferencial raro no segmento.

A Política de Cancelamento documenta regras de sinal, prazo e reagendamento com linguagem direta, eliminando a insegurança de "e se eu precisar cancelar?" antes que ela impeça o clique.

Ambos compartilham o mesmo sistema visual do site (dark, dourado, tipografia hierarquizada) e fecham com um CTA direto para o WhatsApp do Diego. Implementação: HTML/CSS/JS vanilla, sem biblioteca — abertura por `classList`, fechamento por X, backdrop e tecla ESC.

### CTA Final
Seção de fechamento com glow radial dourado no background. Estrutura de conversão em 4 camadas:
1. **Headline** — ação direta ("Sua próxima tatuagem começa agora.")
2. **Subtítulo** — promessa concreta ("Do conceito ao resultado final...")
3. **Botão** — primeira pessoa, orientado a desejo ("Quero Minha Tatuagem")
4. **Trust signals** — remove última objeção ("Sem compromisso inicial · Atendimento direto com o tatuador")

---

## Destaques Técnicos

**Scroll reveal sem biblioteca:**  
`IntersectionObserver` com threshold e delay via classes CSS (`delay-2`, `delay-3`) — animações de entrada suaves sem depender de GSAP ou AOS.

**Cursor customizado em CSS puro:**  
A agulha de tatuagem usa apenas `::before` e `::after` no elemento `#cursor`, sem SVG externo. A haste e o corpo da máquina são retângulos rotacionados 45° com `transform-origin` na ponta.

**Responsividade sem framework:**  
Zero Bootstrap ou Tailwind. Grid nativo, `clamp()` para tipografia fluida, media queries cirúrgicas apenas onde necessário.

**Performance:**  
Nenhuma dependência JavaScript externa além das fontes Google. Bundle total < 50kb (excluindo imagens). Tempo de carregamento imperceptível em conexão média.

---

## Fluxo de Conversão

```
Hero (proposta)
  ↓
Portfólio (prova de qualidade)
  ↓
Expertise (autoridade técnica)
  ↓
Biossegurança (confiança)
  ↓
Depoimentos (prova social)
  ↓
Localização (acesso)
  ↓
CTA Final (ação)
```

Cada seção responde uma objeção implícita antes que o usuário a articule.

---

## Direção de Imagem

O material fotográfico entregue pelo cliente não estava compatível com o posicionamento premium da marca — fotos com qualidade baixa, iluminação plana e cenários genéricos.

**Foto principal (Diego no estúdio):**  
A imagem original mostrava um ambiente com paredes brancas, iluminação fria e sem identidade visual. Usei IA generativa para reconstruir completamente o background — substituindo a cena por um estúdio dark com o logo "Diego Tattoo" na parede, ring light visível, obras em exposição e equipamentos profissionais em cena. A pessoa, a pose e a máquina de tatuar foram preservadas; o ambiente foi recriado do zero para refletir o posicionamento da marca. Finalização no Figma.

**Galeria de portfólio:**  
As fotos das tatuagens chegaram com qualidade variável — algumas comprimidas, outras com iluminação incompatível com o tema escuro do site. Em cada imagem: upscale de resolução via IA e ajuste de exposição/cor para escurecer o ambiente e manter coerência visual com a paleta `#0c0c0c` do site. O resultado é uma galeria onde todas as peças parecem fotografadas no mesmo estúdio, mesmo vindo de sessões e contextos diferentes.

---

## Aprendizados

**Copy é produto.** As maiores melhorias de percepção vieram de ajustes de texto — não de redesigns visuais. O subtítulo do CTA passou por 3 versões até comunicar concreteza e emoção ao mesmo tempo.

**Hierarquia visual é estratégia.** A decisão de saturar menos a águia e deixar o leão central dominar não é estética — é guia de atenção deliberado.

**Trust signals no lugar certo.** Colocar "Sem compromisso inicial" abaixo do CTA (e não no topo) funciona porque chega quando o usuário já quer clicar, mas ainda hesita.

---

## Stack

```
HTML5 · CSS3 (Custom Properties, Grid, Clamp) · JavaScript ES6+
Google Fonts · Google Maps Embed · WhatsApp API
Git · GitHub · Figma · IA Generativa (tratamento e reconstrução de imagens)
```

---

*Design e desenvolvimento: [seu nome]*  
*Repositório disponível mediante solicitação*
