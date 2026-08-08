# Plano de capítulos — arco completo

13 capítulos + guia de seminários. **1 capítulo ≈ 1 aula de 2h.** Duas unidades
institucionais (U1: caps 1–7, U2: caps 8–13), sem datas no material.

Cobre a ementa institucional: conceituação de ES · métodos para especificação ·
processos de software · ciclos de vida · desenvolvimento ágil · estudos de viabilidade.

## Estrutura padrão de capítulo

Hero temático → **Aquecimento** (quiz provocativo) → Conceitos (analogia → máquina/visual →
síntese) → caixa **"Mito × Realidade"** (derruba 1 mito clássico) → caixa **"🤖 E a IA nisso?"**
(pincelada) → caixa **"🎲 Dinâmica em sala"** (atividade presencial para a professora) →
Quiz final → Resumo + gancho do próximo.

---

## UNIDADE 1 — "Como nasce um software"

### Cap 01 — O mundo movido a software
- ES ≠ programação: a disciplina do COMO se constrói, não do código em si.
- Definição (Sommerville), por que existe: a crise do software.
- **Linha do tempo animada de desastres**: Therac-25, Ariane 5, Knight Capital
  (US$ 440 mi em 45 min), caso BR (apagão de app bancário / filas do gov.br).
- **Máquina "Anatomia de um fracasso"**: aluno escolhe um desastre e vê o fluxo do erro
  (onde o processo falhou — nunca é "só um bug").
- Mito × Realidade: "engenharia de software é coisa de quem programa".
- Dinâmica: "pense num app que te deixou na mão — a falha foi técnica ou de entendimento?"
- IA: se a IA escreve código, a engenharia importa mais ou menos? (provocação, sem resposta pronta)

### Cap 02 — Ética do engenheiro de software
- Código ACM/IEEE: 8 princípios como cards navegáveis.
- LGPD essencial (o que o dev precisa saber; dados pessoais/sensíveis).
- **Máquina de dilemas**: cenários reais (vigilância × privacidade; prazo × qualidade em
  software médico; viés de algoritmo em crédito) — o aluno decide, vê consequências,
  compara com estatística local das escolhas.
- Mito × Realidade: "ética é problema do jurídico".
- Dinâmica: mesa redonda com um dilema da máquina.
- IA: deepfakes, viés, quem responde pelo código gerado por IA.

### Cap 03 — Processos e ciclos de vida
- As 4 atividades fundamentais (especificação → desenvolvimento → validação → evolução)
  como fluxo animado.
- **Cascata** (Royce 1970 — e a ironia: o próprio Royce já apontava os limites),
  **prototipação**, **incremental**, **espiral** (Boehm) — cada modelo é um fluxo animado
  lado a lado, com prós/contras. (Corrigir o erro herdado dos slides da Carolina: rótulos
  problemas/vantagens do espiral trocados.)
- **Jogo "Escolha o modelo"**: cenários (app de startup com requisitos voláteis; sistema
  bancário regulado; site institucional simples) → aluno escolhe o ciclo de vida → animação
  mostra as consequências da escolha (boas e ruins).
- Mito × Realidade: "cascata está morto" (regulados/contratos ainda usam variações).
- Dinâmica: turma dividida defende modelos diferentes para um mesmo cenário.
- IA: protótipos de tela gerados por prompt mudaram o custo da prototipação.

### Cap 04 — O Manifesto Ágil
- A história: 2001, Snowbird, 17 pessoas — narrativa visual (candidato a vídeo
  HyperFrames/Remotion).
- **4 valores como balanças animadas** (X *mais que* Y — a balança pende, mas os dois
  pratos têm peso).
- 12 princípios agrupados em 4 temas navegáveis (entrega, mudança, pessoas, excelência).
- "Ser ágil ≠ fazer ágil": anti-padrões (fake agile, daily de 1h, "scrumfall").
- Mito × Realidade: "ágil = sem documentação".
- Dinâmica: debate "documentação abrangente morreu?"
- IA: iterar em horas — o manifesto envelheceu bem ou mal?

### Cap 05 — Scrum: o time e o backlog
- Papéis (PO, SM, Devs) como cards; **máquina "De quem é essa decisão?"** (situações →
  aluno aponta o papel responsável).
- Product Backlog: **montar e priorizar o backlog do produto fio-condutor** (arrastar
  itens, ver valor × esforço).
- Sprint Backlog vs Product Backlog (o "tudo" vs o "agora").
- Mito × Realidade: "Scrum Master é chefe do time".
- Dinâmica: eleger um PO da turma e priorizar um backlog no telão.
- IA: IA rascunhando backlog a partir de uma conversa com o cliente — e por que o PO revisa.

### Cap 06 — Scrum: a sprint
- Eventos (Planning, Daily, Review, Retro) na ordem certa, com time-boxes — ciclo animado.
- **Simulador de sprint**: 2 semanas comprimidas em 1 minuto — cartões andam no quadro,
  imprevistos acontecem (dev doente, requisito mudou no meio), **burndown se desenhando**.
- **Planning Poker jogável no navegador** (cada aluno no celular, professora no telão;
  100% local, sem backend).
- Mito × Realidade: "daily é reunião de status para o chefe".
- Dinâmica: o próprio Planning Poker, com um item do backlog da turma.
- IA: bots de standup e resumos automáticos de sprint.

### Cap 07 — Kanban e XP
- Kanban: origem (Toyota), fluxo contínuo vs sprints; **simulador de WIP** — o aluno abre
  tarefas demais e VÊ o gargalo entupir; limitar WIP destrava o fluxo. Lead time como métrica.
- XP: test-first, programação em pares, integração contínua — como conceitos (sem código).
- Scrum × Kanban: quando usar cada um (tabela viva).
- Mito × Realidade: "quanto mais tarefas em andamento, mais produtivo".
- Dinâmica: **penny game** (jogo da moeda) presencial para sentir WIP/lotes.
- IA: previsão de lead time e detecção de gargalo por IA.

*(Fecho da U1 — avaliação a critério da professora; material pode ganhar uma página
"Revisão U1" futuramente.)*

---

## UNIDADE 2 — "Do papel ao produto"

### Cap 08 — Requisitos: entender o problema
- **O abismo da comunicação**: recriar animado o cartoon clássico do balanço
  ("o que o cliente pediu / o que o analista entendeu / ... / o que ele precisava").
- "A falha mais cara não é de código, é de entendimento."
- Técnicas de elicitação com prós/contras: entrevista, observação/etnografia, workshop
  (JAD/brainstorm), questionário, análise de documentos.
- **Jogo da entrevista**: cliente fictício com necessidades escondidas — o aluno escolhe
  perguntas; perguntas ruins geram requisitos falsos, a pergunta certa desenterra o
  requisito real.
- Mito × Realidade: "o cliente sabe exatamente o que quer".
- Dinâmica: entrevista em duplas (um recebe uma "carta secreta de necessidades").
- IA: IA transcrevendo e minerando entrevistas — e o risco de alucinar requisito.

### Cap 09 — Requisitos: escrever bem (user stories, RF × RNF)
- RF × RNF; a sequência "qual importa mais?" terminando em **=** (herdada da Carolina —
  a melhor construção dela, refeita animada).
- RNF mensurável: "rápido" não é requisito; "responde em 2s com 1.000 usuários" é.
  Classificações (produto/organizacional/externo) de leve.
- **Máquina de montar user story**: peças que encaixam (Como/Quero/Para) + critérios de
  aceitação + **detector de ambiguidade** (palavras-alerta: "rápido", "fácil", "etc.").
- Mito × Realidade: "requisito bom é requisito comprido".
- Dinâmica: caça à ambiguidade num requisito real projetado no telão.
- IA: IA escrevendo stories a partir do backlog — quem garante o critério de aceitação?

### Cap 10 — Modelagem visual
- Por que desenhar antes de construir (**a planta da casa** — analogia-mãe do material,
  casa com a identidade blueprint).
- **Casos de uso**: atores, elipses, include/extend — diagrama SVG que **se desenha
  sozinho** sobre o produto fio-condutor.
- **Diagrama de classes light**: caixinhas (nome/atributos/métodos) e relações — clicável,
  sem mergulhar em UML formal.
- Ferramentas de hoje: draw.io, Miro, **Mermaid** (mostrar texto virando diagrama — ponte
  com IA).
- Mito × Realidade: "UML morreu" (morreu o culto; o desenho continua).
- Dinâmica: modelar no papel um sistema simples e comparar entre grupos.
- IA: descrever o sistema em português e ganhar o diagrama Mermaid pronto.

### Cap 11 — Viabilidade e MVP
- Estudo de viabilidade (item explícito da ementa): dimensões **técnica, econômica,
  operacional, legal, de cronograma** — checklist interativo.
- Custo × valor; matriz de priorização.
- **MVP**: a animação clássica esqueite → patinete → bicicleta → carro; casos reais BR
  (como grandes apps começaram pequenos).
- **Simulador go/no-go**: 3 propostas de projeto com orçamento, prazo e riscos — o aluno
  decide qual aprovar e vê o desfecho.
- Mito × Realidade: "MVP é produto malfeito".
- Dinâmica: pitch de viabilidade em grupos (5 min por grupo).
- IA: IA barateou construir — viabilidade agora é mais sobre "devemos?" que "conseguimos?".

### Cap 12 — Qualidade e testes
- Por que testar: Dijkstra ("teste mostra a presença de defeitos, não a ausência").
- Terminologia como **dominó animado**: engano → defeito → erro → falha.
- Caixa preta × caixa branca (analogia médica: sintomas × exames).
- **Pirâmide de testes interativa**: unidade/integração/E2E — custo e velocidade visíveis.
- **Caça ao bug conceitual**: dada uma especificação, o aluno projeta casos de teste;
  classes de equivalência gamificadas ("quantos testes você precisa MESMO?").
- Mito × Realidade: "testar é a última etapa".
- Dinâmica: "quebre o formulário" — turma projeta entradas maliciosas para um cadastro.
- IA: geração de testes e testes de regressão com IA (aprofunda no Cap 13).

### Cap 13 — Evolução, dívida técnica e o futuro
- Software nunca fica pronto (leis de Lehman, de leve; Heráclito).
- Tipos de manutenção (corretiva/adaptativa/perfectiva/preventiva) — quiz de classificação.
- **Simulador de dívida técnica**: cada atalho acelera a entrega AGORA e desacelera as
  próximas — gráfico de velocidade caindo; refatorar = pagar a dívida.
- Legado: substituir × transformar × manter.
- **Fecho de IA** (amarra todas as pinceladas): copilots, agentes, vibe coding, IA em
  testes — o que muda e o que NÃO muda no papel do engenheiro (entender o problema,
  decidir trade-offs, garantir qualidade).
- Mito × Realidade: "manutenção é consertar bug" (é a minoria do trabalho).
- Dinâmica: debate estruturado "IA substitui o dev?"

---

## Guia de seminários (página extra, não é capítulo)
- Temas sugeridos: UX, garantia de qualidade, gestão de configuração (Git/versionamento),
  gestão de riscos, DevOps/CI-CD, tendências emergentes.
- Formato, critérios e **rubrica de avaliação** clara (a professora ajusta pesos).

## Ordem de produção sugerida
1. Fundação: `shared/` + hub + identidade blueprint
2. Caps 01–03 (abrem a disciplina)
3. Caps 04–07 (bloco ágil — coração do curso)
4. Caps 08–10 (requisitos + modelagem)
5. Caps 11–13 + guia de seminários
