---
name: backlink-pass
description: Routine quinzenal de backlinks editoriais inversos — adiciona links contextuais em posts antigos apontando pros posts novos publicados na quinzena. Use a cada 2 semanas (2ª e 4ª quinta-feira do mês) ou quando o usuário pedir explicitamente "rodar backlink-pass".
---

# Routine de backlink-pass

Você é um agente dedicado a fechar o gap de backlinks editoriais inversos no blog da Kliente 360. Posts novos sempre entram com forward links (pros posts anteriores), mas posts antigos não recebem links pros novos automaticamente. Sua função é executar esse pass inverso a cada lote de ~4 posts novos.

## Fontes da verdade (leia antes de agir)

1. **`blog/posts/README.md`** §"Routine de backlink-pass" — fluxo operacional completo, guardrails, edge cases. Em caso de conflito entre este prompt e o README, **o README vence**.
2. **`blog/posts/README.md`** §"Estratégia de links internos" — regras de texto-âncora, formato técnico de link, fallback de idioma.
3. **`EDITORIAL.md`** — tabela viva de posts. Coluna `Backlink pass` é o state tracker.

## Procedimento

### 1. Identificar o lote

Ler `EDITORIAL.md`. Listar os **4 posts mais recentes** (por ordem da coluna `#`) com:
- `Status = [x]` (publicado)
- `Backlink pass = [ ]` (ainda não processado)

Se houver menos de 4 nessa condição:
- Se 1–3: processa o que tiver (lote parcial é válido).
- Se 0: encerrar a execução, reportar "nenhum lote pendente" e parar.

### 2. Para cada post novo do lote

Identificar **2–5 posts antigos** onde o tema cruza naturalmente.

**Como identificar cruzamento**:
- Grep os arquivos `.md` em `blog/posts/` pelos conceitos-chave do post novo (palavra-chave primária, termos do TL;DR, keywords do frontmatter).
- Critério: o post antigo já **menciona o conceito específico** do post novo, não apenas tem assunto correlato. Exemplo bom: post novo "FinOps de IA" → post antigo "custos reais de inferência" (ambos discutem custos/orçamento). Exemplo ruim: mesmo post novo → post antigo "Sales Cloud antipadrões" (só liga em "empresarial", insuficiente).
- Pular qualquer post antigo com **5+ backlinks já acumulados** (saturado). Conte heuristicamente os `<a href="/blog/` no corpo.
- Pular posts com `no-backlink: true` no frontmatter.

Se nenhum post antigo cruzar naturalmente, **pular o post novo** — marcar `Backlink pass = [x]` mesmo assim e seguir. Forçar link sem cruzamento é spam.

### 3. Para cada post antigo identificado

Adicionar **exatamente 1 link inline** na prosa pro post novo:

- **Onde**: dentro de um parágrafo da argumentação, no ponto onde o conceito é mencionado. Nunca num bullet "veja também".
- **Texto-âncora**: descritivo, 3–8 palavras, diz o que o leitor encontra. Nunca "leia mais", "saiba sobre", "clique aqui".
- **Formato técnico**: ver `blog/posts/README.md` §"Estratégia de links internos" item 4. Resumo:
  - PT antigo → PT novo: `/blog/<slug-novo>.html`
  - EN antigo → EN novo: `/blog/en/<slug-novo>.html` (só se EN existir, senão linkar PT)
  - ES antigo → ES novo: análogo
- **Aplicar nas 3 variantes** do post antigo (`.md`, `.en.md`, `.es.md`). Se alguma variante não existe, pular ela.

### 4. Commitar

**Um commit por post antigo modificado**:

```
git add blog/posts/<slug-antigo>.md blog/posts/<slug-antigo>.en.md blog/posts/<slug-antigo>.es.md
git commit -m "blog: backlink <slug-antigo> → <slug-novo>"
```

Não agrupar múltiplos posts antigos no mesmo commit — granularidade é o ponto, pra reverter limpo se um link envelhecer mal.

### 5. Fechar o lote

Depois de processar os 4 posts novos, atualizar `EDITORIAL.md` marcando `Backlink pass = [x]` em cada um. Commit final:

```
git add EDITORIAL.md
git commit -m "editorial: backlink-pass lote <YYYY-MM-DD>"
git push origin main
```

## Guardrails críticos (não viole)

- **Cruzamento natural obrigatório** — sem MENÇÃO específica do conceito no antigo, sem link.
- **Cap 1 link por post antigo por execução** — não enche post antigo de novos links.
- **Cap 3 backlinks abertos por post novo** — se só 1–2 cruzam, fica em 1–2.
- **Não regere HTML** — não rode `npm run build`. Netlify cuida no deploy.
- **Não toque em outros arquivos** — só `blog/posts/*.md` e `EDITORIAL.md`.
- **Não invente posts** — só linkar pra posts já publicados (existem como `.md` em `blog/posts/`).
- **Não mexa em forward links existentes** — você só adiciona links pro post novo em posts antigos. Não reescreve nem reorganiza links pré-existentes.

## Output esperado por execução típica

- 4 posts novos processados (estado: `Backlink pass = [x]`)
- ~8–12 posts antigos editados (média 2–3 por post novo × 4 posts novos)
- ~8–12 commits `blog: backlink ...` + 1 commit `editorial: backlink-pass lote ...`
- Total: ~10–13 commits empurrados pra `main`
- Netlify redeploya 1x ao final (push único)

## Quando reportar e parar

Reporte ao final em 2–4 bullets:
- Quantos posts novos processados / quantos pulados (e por quê)
- Quantos posts antigos editados
- Quantos backlinks abertos no total
- Se houver post novo sem cruzamento, dizer qual e por quê (decisão editorial — usuário pode querer ângulo manual)

Não rodar build, não abrir PR. `main` push direto é o fluxo.
