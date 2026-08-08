# Engenharia de Software — material interativo

Material didático da disciplina **Engenharia de Software** (Sistemas para Internet, 4º período,
Centro Universitário UNIESP) — **Profa. Priscilla Praxedes**.

Site estático, sem build: é só abrir o `index.html` no navegador (ou servir a pasta).

## A proposta

Engenharia de Software tem fama de disciplina de slide com bullet point. Aqui a teoria vira
coisa que se mexe: o aluno **roda uma sprint**, **entope um quadro Kanban** até o gargalo
aparecer, **acumula dívida técnica** e vê a velocidade do time cair, **entrevista um cliente**
que não sabe explicar o que quer.

Cada capítulo traz:

| Elemento | O que é |
|---|---|
| 🎮 **Simulador** | o conceito abstrato virando mecanismo manipulável |
| 🧨 **Mito × Realidade** | derruba um mito clássico que o aluno vai ouvir por aí |
| 🤖 **E a IA nisso?** | o que muda naquele tema com IA — sem promessa mágica |
| 🎲 **Dinâmica em sala** | atividade presencial pronta, com tempo e passos, para a professora conduzir |
| ❓ **Quiz** | com feedback explicativo |

Não há exercício de programação: a disciplina é teórica e a condução é da professora.

## Conteúdo

**Unidade 1 — Como nasce um software**
1. O mundo movido a software · 2. Ética do engenheiro · 3. Processos e ciclos de vida ·
4. O Manifesto Ágil · 5. Scrum: o time e o backlog · 6. Scrum: a sprint · 7. Kanban e XP

**Unidade 2 — Do papel ao produto**
8. Requisitos: entender o problema · 9. Requisitos: escrever bem · 10. Modelagem visual ·
11. Viabilidade e MVP · 12. Qualidade e testes · 13. Evolução e dívida técnica

\+ guia de seminários.

## Rodando

```bash
python3 -m http.server 8000
```

Depois abra <http://localhost:8000>. Também funciona com o Live Server do VS Code.

## Estrutura

```
index.html              hub com os capítulos
capitulos/NN-slug/      um capítulo por pasta, HTML auto-contido
shared/                 design system (CSS + JS compartilhados)
context/                memória viva do projeto — leia antes de editar
tools/checar.py         checagem das regras da casa
```

## Antes de commitar qualquer HTML

```bash
python3 tools/checar.py
```

Verifica ligaduras de fonte mono, símbolos unicode proibidos, escape dentro de `<pre>`,
datas de semestre, classes sem CSS, âncoras quebradas e colisão de nomes de classe.

## Stack

HTML/CSS/JS puro, sem build e sem framework. Única dependência externa é o
[Motion](https://motion.dev) via CDN, carregado dentro de `try/catch` — se a CDN cair
(ou a sala estiver sem internet), o site continua funcionando com animações CSS.
<!-- test commit & push -->
