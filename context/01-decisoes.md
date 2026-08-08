# Log de decisões (append-only — marcar "superseded", nunca apagar)

## 2026-08-07 — Fundação do projeto

**Contexto:** Prof. Kelson está montando o material da disciplina Engenharia de Software para
a **Profa. Priscilla Praxedes** (a disciplina será dela; ela tem liberdade total sobre o
conteúdo). O material da profa. Ana Carolina (mesma disciplina, outro horário) foi analisado
apenas como referência do currículo padrão — não é para ser seguido.

**Decisões travadas (respostas do prof. Kelson):**

1. **Fio condutor: MISTO.** Um produto fictício leve atravessa os SIMULADORES
   (proposta: **UniFood**, app de delivery do campus — validar nome com o prof antes de usar),
   mas exemplos, quizzes e estudos de caso variam por capítulo (banco, jogo, hospital,
   e-commerce...). Não é um "projeto da disciplina" formal.
2. **IA na ES: pinceladas + fecho.** Cada capítulo ganha uma caixa curta
   "🤖 E a IA nisso?" mostrando como IA muda aquele tema hoje; o Cap 13 amarra tudo
   num panorama (copilots, agentes, vibe coding, IA em testes).
3. **Identidade visual: família dark + cor-tema própria.** Mesma base dos irmãos
   (Nunito/Caveat/JetBrains Mono, dark, Motion via CDN com fallback), mas com paleta de
   destaque exclusiva. Conceito proposto: **"A Planta do Software"** (blueprint/planta baixa —
   ver `04-design-system.md`).
4. **SEM semestre/datas no material.** Será reaproveitado nos próximos semestres.
   Nada de "2026.2", cronograma com datas, nomes de feriados etc. O ritmo (1 capítulo ≈
   1 aula de 2h) fica implícito.

**Outras convenções herdadas do workspace (CLAUDE.md raiz):**
- PT-BR em tudo; ligatures OFF em toda fonte mono; escapar `<>&` em `<pre>`;
  repo git independente (init na primeira entrega de código).
- Padrões dos irmãos que valem aqui: autoplay por IntersectionObserver, quiz com confete,
  caixas semânticas (.concept/.analogy/.tip/.warning), hub com cards + "em breve",
  barra de progresso, sidebar off-canvas, pasta context/ como memória viva.
- Padrões que NÃO se aplicam: olhinho 👀 de código, "digite no VSCode", playground de
  código, BugZilla (vilão de bugs de código). Substitutos: simuladores de processo e a
  caixa recorrente **"Mito × Realidade"** (cada capítulo derruba 1 mito clássico da ES).

**Estado:** planejamento aprovado em conversa; nenhuma linha de HTML produzida ainda.
Próximo passo: fundação (shared/ + hub) e Cap 01.

## Entrega 1 — fundação + hub + Cap 01

**Construído:**
- `shared/` derivado de `novo-material-fullstack`, podado (saíram BugZilla, playground,
  mini-browser, forja de tags, visualizadores, paredes de logo, seção de carreira);
  `components.css` de 1810 → ~900 linhas. Identidade blueprint aplicada.
- Componentes novos: `.mito-real`, `.ia-box`, `.dinamica`, `.sim` (casca de simulador),
  `.blueprint` (planta técnica), `.timeline`, `.checklist`, `.cap-nav`.
- `index.html` (hub) com "a planta animada" do ciclo de vida e os 14 cards.
- `capitulos/01-mundo-movido-a-software/` — Therac-25, Ariane 5, Mars Climate Orbiter,
  Knight Capital e o caso brasileiro C&M/Pix, cada um com fonte primária e ressalva de
  número disputado. Simulador "Anatomia de um fracasso" (3 casos × 5 estágios).
- `tools/checar.py` — validador das regras da casa.

**Bug de design pego na revisão:** `.blueprint` era ao mesmo tempo componente e modificador
de `.stack-chip`; o `padding` do componente vencia e deformava os chips. Modificador
renomeado para `.stack-chip.processo`. Nome reservado documentado no `04-design-system.md`.

**Rodada de auditoria adversarial (3 lentes: regras / técnica / factual-didática).**
Aplicado da lente "regras":
- Ariane 5 dizia "37 segundos" na linha do tempo e "39" no simulador. São eventos
  diferentes: inerciais desligam aos ~37 s, ruptura aos ~39 s. Os três pontos foram
  reescritos para narrar a sequência.
- Regra global de ligaduras ampliada para `.mr-carimbo`, `.sim-tag`, `.tl-ano`,
  `.code-header .filename`, `.code-header .lang-badge`, `.code-block .line-numbers`,
  `.hub-card .num` — todas usam mono e estavam descobertas.
- Acentuação faltando em texto visível de SVG (documentação, manutenção, código,
  triângulo de restrições, três).
- `&` cru no `<link>` das fontes (hub e capítulo).
- Frase sobre a C&M que envelhecia sozinha ("depois das novas regras, várias delas
  pediram descredenciamento") trocada por relato datado e fechado.
- Bug de lógica do simulador: no Therac-25 o 5º elo (pós-desastre) contava como barreira,
  fazendo o veredito dizer "5 de 5 pontos antes de virar notícia" — contradição. A lição
  sobre ouvir o operador migrou para o elo de TESTE; o elo `boom` agora é `barreira:null`,
  igual aos outros dois casos.
- **Dois pontos cegos do próprio `checar.py`**: (a) só inspecionava `<style>` inline,
  nunca o `shared/`; (b) a regex de data só pegava "2026.1"/"semestre" — ano nu passava.
  Ambos corrigidos, mais o parser que grudava comentário CSS no seletor.

**Convenção de setas (nova):** `←` e `»` são permitidos (navegação decorativa);
`→ ⇒ ≠ ≥ ≤ ↘` são proibidos e barrados pelo checador.

**Repositório:** https://github.com/kelsonvictr/eng-soft.git (`main`).
