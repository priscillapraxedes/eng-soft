# Engenharia de Software — Profa. Priscilla Praxedes

Material didático HTML da disciplina Engenharia de Software (UNIESP, Sistemas para
Internet, 4º período). **Teórico-interativo, sem código para digitar** — a professora
não é programadora; os "playgrounds" são simuladores de processo.

**A memória viva mora em `context/`** — leia `context/00-overview.md` primeiro.
Plano completo dos capítulos em `context/02-plano-capitulos.md`; decisões em
`context/01-decisoes.md` (append-only); identidade visual em `context/04-design-system.md`.

Regras do workspace (CLAUDE.md raiz) valem integralmente: ligatures OFF em fontes mono,
escapar `<>&` em `<pre>`, PT-BR, um conceito por vez. Este diretório é (será) um repo
git independente — não commitar na raiz do workspace.

Restrição específica: **nenhuma menção a semestre/ano/datas** no conteúdo — o material
é reaproveitado a cada semestre.

## Depois de editar qualquer HTML, rode

```bash
python3 tools/checar.py
```

Ele pega: ligaduras faltando em classe mono, símbolos unicode proibidos (`→ ⇒ ≠ ≥ ≤`),
`< > &` cru dentro de `<pre>`, datas de semestre, classes usadas e nunca definidas em CSS,
âncoras `goTo()`/`href="#..."` quebradas, e **colisão de nome** (usar um componente como
`.blueprint` na posição de modificador — o CSS do componente vaza e deforma o elemento).
