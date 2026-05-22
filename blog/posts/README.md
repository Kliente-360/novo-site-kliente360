# Blog Kliente 360 — guia para autores (humanos e agentes)

Este diretório guarda **os posts do blog em Markdown**. O build os converte em HTML estilizado automaticamente.

> Para começar do zero: copie `_template.md`, renomeie para `<seu-slug>.md`, preencha o frontmatter e escreva o corpo.

## Pipeline

```
blog/posts/<slug>.md   →   npm run build   →   blog/<slug>.html
                                            +   blog/index.html (listagem)
                                            +   sitemap.xml
```

O build é executado automaticamente pela Netlify em cada deploy. Para testar local: `npm install && npm run build`.

## Estrutura de um post

Todo post é um arquivo `.md` com duas partes:

### 1. Frontmatter YAML (obrigatório)

```yaml
---
title:       "Título declarativo, 50–80 caracteres"
slug:        "kebab-case-sem-acento"        # = nome do arquivo
pillar:      "ai"                            # sf | data | ai
date:        "2026-05-22"                    # ISO YYYY-MM-DD
readMinutes: 6                               # opcional (calcula sozinho)
excerpt:     "Resumo de uma linha (≤160 chars)."
tldr:        "Resumo de 2–3 frases. Pensa em LLM lendo (GEO)."
keywords:    ["termo1", "termo2", "termo3"]  # opcional
---
```

### 2. Corpo em Markdown

Padrão CommonMark + GFM. Suportado:
- Headings `##`, `###`
- Listas `-` e `1.`
- Blockquote `>`
- Ênfase `**negrito**`, `*itálico*`
- Inline code `` `código` ``
- Links `[texto](url)`

Tabelas, código em blocos e imagens não estão integrados ao tema visual ainda. Evitar até habilitarmos.

## Pilares

Cada post pertence a **um pilar primário**. O pilar define:
- Cor temática (pílula, drop-cap, barra lateral, marcadores)
- Eyebrow do header
- Recomendações automáticas no final

| Valor    | Pilar               | Cor       |
|----------|---------------------|-----------|
| `sf`     | Salesforce          | `#0B5394` |
| `data`   | Data & Analytics    | `#C9A227` |
| `ai`     | IA & Aplicações     | `#6D28D9` |

## Arquivos especiais

- `_template.md` — esqueleto. Ignorado pelo build.
- `README.md` — esta documentação. Ignorada pelo build.
- Qualquer arquivo iniciado por `_` é ignorado (use para rascunhos: `_draft-meu-post.md`).

## Traduções (multi-idioma)

Cada post pode ter variantes por idioma:

```
quando-agente-e-resposta.md       → PT (padrão, obrigatório)
quando-agente-e-resposta.en.md    → EN (opcional)
quando-agente-e-resposta.es.md    → ES (opcional)
```

Todos os arquivos do mesmo post compartilham o **mesmo `slug`** no frontmatter. Os campos a traduzir são `title`, `excerpt`, `tldr`, `keywords` e o corpo. O `pillar` e o `date` ficam no arquivo PT e valem para todas as variantes.

URLs geradas:
- `/blog/<slug>.html` (PT, sempre presente)
- `/blog/en/<slug>.html` (somente se `<slug>.en.md` existir)
- `/blog/es/<slug>.html` (somente se `<slug>.es.md` existir)

A listagem `/blog/`, `/blog/en/` e `/blog/es/` mostra apenas posts com tradução para o idioma da página.

## Tom de voz

Boutique informada falando com decisor informado. Direto, técnico, sem clichês.

**Usar**: "uma prática única", "agentes onde já existe dado", "conversa direta com quem entrega", nomes próprios (Salesforce, Tableau, Agentforce, Data Cloud).

**Evitar**: "transformação digital", "jornada", "experiência fluida", "soluções inovadoras", "costurar", "ladainha", "no fim do dia", "alavancar", auto-elogio.

## Checklist antes de publicar

- [ ] Frontmatter completo, com todos os campos obrigatórios.
- [ ] Slug em kebab-case, sem acentos.
- [ ] Pilar correto (sf | data | ai).
- [ ] Title declarativo, sem ponto final.
- [ ] Excerpt em uma linha, ≤160 caracteres.
- [ ] TL;DR em 2–3 frases (cabeça, não chamada para ação).
- [ ] Primeiro parágrafo abre direto na tese, sem "neste post".
- [ ] H2 em forma de sentença declarativa ou pergunta, nunca "Introdução"/"Conclusão".
- [ ] Pelo menos um blockquote forte para sintetizar um ponto.
- [ ] Sem palavras da lista de evitar.
- [ ] 5–8 minutos de leitura, salvo justificativa.

## Para agentes de redação

Se você é um agente automatizado escrevendo um post:

1. Leia `_template.md` integralmente — ele tem regras editoriais que vão além do schema.
2. Verifique 3 posts publicados nesta pasta como referência de tom.
3. Use os pilares conforme tabela acima — não invente cor ou label.
4. Datas devem ser realistas (não futuras além de alguns dias).
5. Slug = nome do arquivo (sem `.md`). Devem ser idênticos.
6. **Não** crie HTML por conta própria. **Não** edite `assets/` ou `scripts/`. **Não** suba dependências.
7. Após criar o arquivo, abra um PR ou commit em `main` com a mensagem: `blog: <slug> — <pilar>`.

## Para agentes de revisão

- Cheque o checklist acima.
- Marque sugestões inline no PR.
- Aprove apenas se o tom estiver fiel ao guia.
