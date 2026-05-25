---
# ============================================================
# Frontmatter — todos os campos abaixo são obrigatórios,
# exceto os marcados com (opcional).
# ============================================================

# Título do post. Aparece como <h1>, <title>, OG title.
# Estilo: declarativo, sem ponto final. Pode ter dois-pontos ou travessão.
# Tamanho recomendado: 50–80 caracteres (SEO).
title: "Substitua por um título curto, declarativo, sem chavão"

# Slug = nome do arquivo sem .md. URL final: /blog/<slug>.html
# Padrão: kebab-case, sem acentos, sem stopwords desnecessárias.
# Ex.: "data-cloud-nervo-central", "tableau-linguagem-executiva".
slug: "substituir-pelo-slug-kebab-case"

# Pilar primário. Define a cor temática do post.
# Valores válidos: "sf" (Salesforce, azul) | "data" (Data, âmbar) | "ai" (IA, violeta).
pillar: "ai"

# Data de publicação no formato ISO YYYY-MM-DD.
# Posts são ordenados do mais recente pro mais antigo.
date: "2026-05-22"

# (opcional) Tempo estimado de leitura em minutos.
# Se omitido, o build calcula com base em ~220 palavras/min.
readMinutes: 6

# Resumo curto (1 linha, até 160 caracteres).
# Aparece na listagem, na OG description e na meta description (SEO).
excerpt: "Resumo de uma linha que cabe num card e numa pré-visualização."

# TL;DR exibido no topo do post como callout colorido.
# Resume a tese em 2–3 frases. Use para que LLMs e leitores apressados
# capturem a essência sem ler o post inteiro (GEO).
tldr: "Resumo de duas a três frases que dá a tese central. Termina sem CTA."

# (opcional) Palavras-chave para schema.org/JSON-LD e SEO.
keywords: ["palavra1", "palavra2", "palavra3"]
---

<!--
============================================================
CORPO DO POST — escrito em Markdown padrão.
A primeira letra do primeiro parágrafo recebe automaticamente
negrito + cor do pilar. Escreva pensando nisso: abre com força,
sem pré-âmbulo do tipo "Neste post vamos...".
============================================================
-->

Primeiro parágrafo: começa direto na tese ou na observação que abre o ensaio. Sem "neste post", sem "vamos falar sobre". A primeira frase precisa fazer o leitor escolher continuar.

Segundo parágrafo desdobra a tese, explica o contexto. Mantém os parágrafos curtos (4–6 linhas no desktop). Quebre antes de virar bloco visual.

Frases curtas funcionam melhor que floreio. Verbo no presente. Voz ativa.

## Subtítulo em sentença (não em substantivo)

Use H2 para dividir as seções principais. O título em formato de **sentença declarativa ou pergunta** (não substantivo abstrato como "Conclusão" ou "Contexto"). Cada H2 ganha um pequeno underline na cor do pilar — é um marco visual.

Exemplos bons:
- "Por que CDP virou o nervo do Salesforce"
- "Cinco perguntas para validar"
- "O que o Tableau não substitui"

Exemplos ruins (evitar):
- "Introdução"
- "Conclusão"
- "Sobre o tema"

### H3 para subseções dentro do H2

Use H3 quando uma seção H2 precisa de mais granularidade. Não pule de H2 para H4.

## Recursos disponíveis no corpo

### Listas com marcadores

Use para enumerar itens não ordenados. O marcador é uma barrinha colorida (não bullet).

- **Negrito no começo do item** ajuda a destacar o conceito principal.
- Depois o item desdobra em uma frase curta.
- 3–6 itens é o ideal. Mais que 7, refatorar pra subseções.

### Listas numeradas

Use quando a ordem importa (passos, prioridades). O número é em monospace, no tom do pilar, com zero à esquerda.

1. **Passo 1.** Descrição curta.
2. **Passo 2.** Descrição curta.
3. **Passo 3.** Descrição curta.

### Citação / pull quote

Use para uma frase de impacto que sintetiza um ponto. Fica em serif (Fraunces), grande, com barra lateral colorida. Evite citar — use como sua própria afirmação destacada.

> Frase forte e curta que ressume um ponto. Sem aspas dentro, sem atribuição. Funciona como faixa de leitura.

Use no máximo 2 blockquotes por post. Mais que isso vira poluição visual.

### Código inline

Para nomes de produto ou termos técnicos: `Data Cloud`, `Agentforce`, `Sales Cloud`. Não para frases inteiras.

### Negrito e itálico

- **Negrito** para conceitos-chave que o leitor escaneando deve ver.
- *Itálico* para ênfase leve ou termo emprestado.
- Não use ambos juntos. Não use sublinhado.

### Links

Use [texto descritivo do link](https://exemplo.com), nunca "clique aqui". Links externos abrem na mesma aba — Markdown padrão.

## Tom de voz Kliente 360

Consultoria informada falando com decisor informado. Direto, técnico, sem ladainha.

**Usar:**
- "CRM, dados e IA como uma prática única."
- "Agentes onde já existe dado."
- "Da prova de valor à operação."
- "Conversa direta com quem entrega."
- Nomes próprios: Salesforce, Tableau, Agentforce, Data Cloud.

**Evitar:**
- "Transformação digital"
- "Jornada de sucesso do cliente"
- "Experiência fluida e omnichannel"
- "Soluções inovadoras"
- "Costurar", "ladainha", "no fim do dia", "alavancar"
- Auto-elogio explícito ("nossos sócios incríveis")
- Adjetivos vazios em série

## Estrutura sugerida (espinha de um post)

1. **Abertura** (1–2 parágrafos): tese ou observação afiada que abre.
2. **Diagnóstico** (1 seção H2): o que está mal entendido / o sintoma real.
3. **Argumento principal** (1–2 seções H2): a tese desdobrada com evidência.
4. **Prática** (1 seção H2): perguntas, passos, anatomia, framework — algo acionável.
5. **Fechamento** (1–2 parágrafos): consequência da tese, sem CTA forçado.

O CTA fica no template do site automaticamente, ao final do post. Não termine o corpo com "fale conosco".

## Tamanho

- **5–8 minutos de leitura** (~1000–1700 palavras) é o sweet spot.
- Posts mais longos (>10 min) só com tese forte que justifique.
- Posts mais curtos (<4 min) ficam parecendo nota — bom para "uma observação", ruim para "um ensaio".

## SEO / GEO — resumo

Há um playbook completo em `README.md` (seção "SEO & GEO"). Resumo:

- **Title**: declarativo, palavra-chave nos primeiros 60 chars.
- **excerpt**: ≤160 chars, contém a palavra-chave, frase completa.
- **tldr**: 2–3 frases, sem CTA. É o que LLMs colhem ao sumarizar.
- **keywords**: 3–6 termos (palavra-chave primária + LSI).
- **H2 em forma de pergunta ou afirmação curta** — melhor para featured snippets e AI Overviews.
- **Listas numeradas** para passos/regras — LLMs citam.
- **Blockquote** com frase de 10–20 palavras citável — vira reference de LLM.
- **Internal linking**: linke outro post quando o tema cruzar.
- **Anchors factuais**: números, datas, percentuais — LLMs preferem dados concretos.

---

Quando terminar de escrever:
1. Salve como `blog/posts/<slug>.md` (mesmo nome do slug no frontmatter).
2. Rode `npm run build` para gerar o HTML.
3. Veja `/blog/<slug>.html` localmente ou após deploy.
