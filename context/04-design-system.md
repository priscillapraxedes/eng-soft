# Design system — identidade "A Planta do Software" (blueprint)

## Conceito
Engenharia = **planta baixa**. O material inteiro joga com a metáfora do blueprint:
antes de construir, desenha-se. O `bg-grid` que os irmãos já usam como fundo vira aqui
**papel milimetrado de planta**, e a cor-tema é o **azul-ciano blueprint**.

## Paleta (deltas sobre a base dos irmãos)
Copiar a base dark de `programacao-iniciantes-v2`/`novo-material-fullstack`
(`--bg:#0a0a12`, surfaces `#12121e/#1a1a2e/#222240`, código `#0d0d1a`, texto `#eef0f8`,
dim `#8892b0`, os 7 acentos) e definir por cima:

- `--blueprint: #38bdf8` — cor-tema primária (azul-ciano de planta técnica)
- `--blueprint-deep: #0ea5e9` — variação para gradientes
- `--amber: #f7b731` — contraste quente (destaques, selos) — já existe na família
- Cores temáticas por bloco: U1 pode gravitar para o blueprint; bloco ágil pode usar o
  verde-menta `#06d6a0` (post-its/quadros); testes o coral `#ff6b6b`. Definir gradientes
  `.grad-*` por capítulo como nos irmãos.
- Fundo: bg-grid um pouco mais presente que nos irmãos (papel milimetrado), orbs em tons
  de azul.

## Tipografia
Idêntica aos irmãos: **Nunito** (corpo), **Caveat** (títulos manuscritos — aqui vira
"anotação de engenheiro sobre a planta"), **JetBrains Mono** (raro — pouquíssimo código).

⚠️ **Ligatures OFF obrigatório** (CLAUDE.md raiz): `font-variant-ligatures:none` +
`font-feature-settings "liga" 0,"clig" 0,"calt" 0` em `pre, code` e TODA classe mono
custom de widget (a regra global não pega `.sim-*`, `.board-*` etc. — repetir localmente).
Mesmo sendo material teórico, setas `->` e `>=` aparecem em diagramas/pseudocódigo.
Escapar `<>&` dentro de `<pre>` sempre.

## O que copiar dos irmãos (shared/)
- `styles.css` (tokens) + `components.css` + `animations.css` + `scripts.js` — trazer e
  adaptar: barra de progresso, sidebar off-canvas, quiz com confete (`checkQuiz`/`confettiAt`),
  motor `data-seq` (sequências animadas com quadros que "voltam" — perfeito para ciclos
  iterativos!), `.flow-container.autoplay`, scroll-reveal, hub cards com `.em-breve`.
- `motion-fx.js` — Motion (motion.dev) v11 via CDN jsdelivr em `try/catch` com fallback
  CSS (offline-first para sala de aula), `prefers-reduced-motion` respeitado.
- Caixas semânticas: `.concept`, `.analogy`, `.tip`, `.warning`, `.quiz`, `.exercise`.
- NÃO trazer: playground de código, vendor React/Babel, tag-forge, padrão olhinho/VSCode.

## Componentes NOVOS deste material
- **Caixa "Mito × Realidade"** (recorrente, 1/cap) — substitui o BugZilla: visual de
  carimbo "MITO" caindo sobre a frase, realidade revelada embaixo.
- **Caixa "🤖 E a IA nisso?"** — pincelada curta por capítulo (decisão 2026-08-07).
- **Caixa "🎲 Dinâmica em sala"** — instruções da atividade presencial para a professora
  (tempo, material, passos). Estilo distinto (borda tracejada tipo "cartão de jogo").
- **Simuladores de processo** (a "máquina didática" desta disciplina): sprint, WIP/Kanban,
  dívida técnica, go/no-go, entrevista, dilemas éticos, escolha de ciclo de vida.
  Receita herdada: input escolhido pelo aluno, caso de ERRO visível, 1º disparo automático
  na viewport, botão só para repetir, fallback sem Motion.
- **Diagramas SVG que se desenham** (casos de uso, classes, fluxos de processo) —
  stroke-dashoffset animado, estética blueprint (traço ciano sobre grid).

## Estrutura de arquivos
Igual aos irmãos: `index.html` (hub) · `capitulos/NN-slug/index.html` (auto-contido,
CSS/JS do capítulo inline) · `shared/` · `assets/` · `context/` · futuramente `tooling/`
(HyperFrames/Remotion para vídeos pré-renderizados, ex.: história do Manifesto Ágil).
Repo git independente (init na primeira entrega).

## Tom
PT-BR leve, "você", frases curtas, emojis com parcimônia. A professora conduz teoria +
discussão; o site anima e simula. Sem memes por ora (exigiriam aprovação prévia).

---

# ✅ FUNDAÇÃO CONSTRUÍDA — inventário do `shared/`

Base derivada de `novo-material-fullstack` e podada: saíram BugZilla, playground, mini-browser,
forja de tags, visualizadores de lista/dict, paredes de logos e a seção de carreira.
`components.css` foi de 1810 para ~900 linhas.

## Arquivos
| Arquivo | O que traz |
|---|---|
| `styles.css` | tokens (paleta blueprint), reset, **regra de ligaduras**, fundo de papel milimetrado, barra de progresso, sidebar, hero, chapter-divider, step-section, footer |
| `components.css` | cards, `.concept`, `.analogy`, `.tip/.warning/.bug`, `.code-block`, `.toggler`, `.exercise`, `.quiz`, `.flow-container`, `.terminal`, `.keyword-chip`, `.hub-card` (+`.em-breve`), `.about-*` **+ os componentes próprios (abaixo)** |
| `animations.css` | keyframes vivos apenas (mortos removidos) |
| `scripts.js` | `toggleSection`, sidebar, `updateProgress`, `checkQuiz`+`confettiAt`, terminais, `data-seq`, **`onView(el, fn)`** (helper global para os simuladores), `revealOnView`, linha do tempo em cascata |
| `motion-fx.js` | Motion v11 via CDN em `try/catch`, `data-motion="rise|pop|float"`, respeita `prefers-reduced-motion` |

## Componentes próprios (fim do `components.css`)
- `.mito-real` → `.mr-mito` (`.mr-carimbo` = carimbo "MITO" que cai) + `.mr-real` (`.mr-tag`)
- `.ia-box` → `.ia-title` + `.ia-emoji`
- `.dinamica` → `.din-head` (`.din-ic`, h4, `.din-meta`) + `.din-body` + `.din-nota`
- `.sim` (casca dos simuladores) → `.sim-head`/`.sim-ic`/`.sim-tag`, `.sim-body`, `.sim-hint`,
  `.sim-chips`/`.sim-chip.on`, `.sim-btn`(`.ghost`), `.sim-actions`, `.sim-out` (`.ok/.bad/.warn/.muted/.ln.on`)
- `.blueprint` (moldura de planta técnica p/ SVG) → `.draw` (com `--len`), `.fade`, `.blueprint-label`,
  legenda via `data-legenda`
- `.timeline` → `.tl-item`(`.grave`, `.on`), `.tl-ano`, `.tl-titulo`, `.tl-custo`
- `.checklist`, `.cap-nav` (`.nav-voltar`, `.nav-proximo`)

## ⚠️ Nomes reservados / armadilhas
- **`.blueprint` é componente, não modificador.** O chip do hero é `.stack-chip.processo`
  (usar `.stack-chip.blueprint` faz o `padding:20px` do componente vencer e deformar o chip).
  Modificadores válidos de chip: `.processo .agil .requisito .teste .etica`.
- Classes mono criadas em widget de capítulo precisam **repetir** a regra de ligaduras localmente —
  a global cobre só `pre, code, .code-block pre, .terminal, .terminal-body, textarea, .mono, .blueprint-label`.
- `.hub-card` usa `.c01`…`.c13` e `.csem` para a faixa colorida; `.em-breve` trava e acinzenta.

## Hub (`index.html`)
Hero + **"a planta animada"** (SVG do ciclo Entender→Planejar→Construir→Validar→Evoluir com a
volta em arco "e aí volta tudo de novo") + boas-vindas + grade da Unidade 1 (7 caps) +
Unidade 2 (6 caps) + seminários + 6 cartões de diferencial. CSS local com prefixo `.pl-*`/`.planta`.
