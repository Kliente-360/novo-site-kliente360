# Competitive SEO Brief v2 — Kliente 360
Data: 2026-05-25
Autor: agente de pesquisa (Claude Code + claude-chrome)
Escopo: segunda passada do `seo-competitive-brief.md` (2026-05-24). Fecha gaps que ficaram em aberto na v1: schemas, hreflang, sitemaps reais, sample profundo, e re-validação dos quick wins com info nova.

> **Metodologia v2.** Crawl real via Chrome (extensão MCP), passando dos 403 que travaram a v1. Para cada concorrente: pegamos `robots.txt` + `sitemap.xml`, contagem real de posts, hreflang declarado nas variantes, presença de JSON-LD (Article, BreadcrumbList, FAQPage, Organization), OG metadata por post, word count e estrutura de headings de pelo menos um post âncora, e — quando exposto — sinais de engagement (views, datas reais). Tudo coletado em 2026-05-25.

---

## TL;DR — o que mudou da v1

| Tópico | v1 dizia | v2 corrige / amplia |
|---|---|---|
| **Indicium PT-BR** | "abandonado / migrado meia-boca" | **121 posts em `/pt-br/content-hub/`** — full coverage PT. Sitemap exposto, hreflang correto. v1 estava errada. |
| **Volume Indicium** | "40–80 posts no hub + back-catálogo legado" | **243 URLs editoriais** no sitemap único (121 PT + 122 EN, pareados). Catálogo bem maior do que estimado. |
| **Indicium schemas** | "Não verificado (403). Sugere markup decente" | **ZERO JSON-LD.** Nenhum Article, BreadcrumbList, FAQ, Organization. Mesmo em posts com FAQ explícita ("Perguntas frequentes…"). |
| **Indicium internal linking** | não avaliado | **Zero internal/external links no corpo** do post âncora (1694 palavras). Sem estratégia de cluster. |
| **Everymind blog** | "20–40 itens em /insights/, mistura de release + cultura" | **Marca Everymind absorvida pelo AI/R.** `everymind.com.br` 301 → `aircompany.ai/en/salesforce/`. "Insights" virou form-gate de Industry Reports. **Não existe mais blog editorial público.** |
| **Sottelli volume** | "20–40 posts visíveis" | **32 posts confirmados** no sitemap. Latest 2026-02-24, depois silêncio. 7 posts em jul-ago/2025 + 1 em fev/2026 + 24 antigos. **~1 post/trimestre em 2026.** |
| **Sottelli schemas** | "Não verificado (403). Estrutura básica" | **ZERO JSON-LD.** OG genérico "Publicações \| Sottelli" em todos os posts (sem por-post OG). |
| **Sottelli engagement** | inferido | **Exposto na UI**: flagship Agentforce+Data Cloud = **19 views em 3 meses**; segundo melhor = **49 views em 9 meses**. Catálogo sem audiência real. |
| **Sottelli hreflang** | não verificado | Presente, mas **quebrado**: `en-us` aponta pra `/en/blog/{slug-PT}` (URL não existe versionada em EN). |
| **Sottelli link rot** | não verificado | **Múltiplos posts listados no sitemap retornam 404** (encoding de acento inconsistente entre sitemap e routing Wix). |

### Conclusão executiva v2

**A Kliente está em posição muito mais confortável do que a v1 sugeria — mas o ranking de prioridades muda.**

1. **Indicium é o único concorrente real em data PT-BR**, e em volume e DA. A v1 errou ao dizer que estava abandonado. Eles publicam, são bons em copy 101 (data mesh, Databricks, BI), e cobrem cases nomeados. **Mas** a tech SEO deles é fraca: zero schemas, zero internal linking. Kliente ganha em tech SEO mesmo perdendo em volume.
2. **Everymind morreu como marca editorial.** A absorção pelo AI/R esvaziou todo conteúdo. Quem buscava "everymind blog" agora cai num form de Industry Reports. **O território de "Salesforce especializada premium em PT-BR com produção editorial" ficou ainda mais vazio do que a v1 indicava.**
3. **Sottelli é fantasma operacional.** 19 views em 3 meses no flagship; sitemap quebrado; OG genérico; zero schema. Não é ameaça competitiva em SEO — é apenas um site institucional com blog dormente. v1 superestimou o risco.
4. **Pilar IA Aplicada continua deserto** em PT-BR — Indicium não cobre RAG/vector/fine-tuning/multi-agent em nenhum idioma; Sottelli tem 1 post; AI/R tem só páginas de produto. Kliente domina com 12+ posts.

**Implicação tática:** os quick wins #5–#9 da v1 ainda fazem sentido, mas a ordem muda e **3 ângulos novos aparecem** (data mesh em PT-BR, Power BI 2026, GEO).

---

## Indicium v2 — dados crawl

### Inventário

| Campo | Valor real |
|---|---|
| Robots | `Sitemap: https://indicium.ai/sitemap.xml` — sem disallows |
| Sitemap URLs totais | **285** |
| Posts editoriais (PT) | **121** em `/pt-br/content-hub/` |
| Posts editoriais (EN) | **122** em `/content-hub/` |
| Páginas institucionais | ~40 (parceiros, indústrias, sobre, careers, etc.) |
| Stack | **Webflow** (`cdn.prod.website-files.com`) |
| Hreflang | ✅ presente e correto: `x-default → /content-hub/...`, `en → /content-hub/...`, `pt-BR → /pt-br/content-hub/...` |
| Canonical | ✅ self-canonical por variante |
| OG por post | ✅ título + descrição + imagem próprias |
| **JSON-LD** | ❌ **zero schemas** (sem Article, BreadcrumbList, FAQ, Organization) |
| Lastmod no sitemap | ❌ ausente — não dá pra inferir cadência via sitemap |

### Sample profundo — "Data Mesh na prática: por que a governança federada impulsiona a inovação" (pt-br)

- **1.694 palavras**
- **5 H2s + 4 H3s** — estrutura limpa
- **Seção "Perguntas frequentes…"** explícita com 4 perguntas em H3 — **ideal pra FAQPage schema, mas não injetada**
- **0 links internos** no corpo. **0 links externos** no corpo. Sem cluster, sem outbound authority.
- Tom: didático-conceitual, primeira pessoa do plural, sem opinião dura.

### Cobertura temática real (filtrando `/pt-br/content-hub/`)

| Tema | Volume | Notas |
|---|---|---|
| Databricks | **6+ posts** | Treinamento, otimização Edenred, migração Aura, Unity Catalog, Lakebase, Data+AI Summit 2025 |
| Data mesh | **3 posts** | "Na prática", "Serviços financeiros", "Implementação" |
| IA setorial (FSI, varejo, energia) | ~10 posts | Banking digital, motor de crédito, manutenção preditiva, IA p/ rede de benefícios |
| Power BI | **3 posts** | Aumento de preço 2025, migração pra Microsoft Fabric (2x), transição |
| BI tools comparison | **0 posts em PT** (1 em EN) | "BI Tools Comparison: Power BI vs Tableau, Sigma, Omni, Metabase" só existe em `/content-hub/`, não tem versão `/pt-br/` |
| Modern Data Stack | **0 posts em PT** (1 em EN) | "What does the modern data stack actually mean" só em EN |
| Customer 360 / CDP | 1 post | "Customer 360 for enterprise retail" |
| RAG / vector DB / fine-tuning / agentes / multi-agent | **0 posts** | Pilar inteiro vazio. |
| Salesforce / Marketing Cloud / Service Cloud / Pardot / Agentforce | **0 posts** | Pilar inteiro fora de escopo. |
| FinOps de IA | 0 posts | — |
| Lakehouse | 1 post | "Lakebase Databricks" (anúncio Databricks, não tese) |

### O que isso muda

1. **Data mesh em PT-BR não é mais terreno vazio.** Indicium tem 3 posts ranqueando. Kliente entra com tese (não 101) ou não entra.
2. **Databricks em PT-BR é território Indicium.** Cases nomeados (Edenred, Aura, Copa Energia). Kliente não compete em volume — compete por agnosticismo (post #3 já publicado: "Databricks vs Snowflake vs BigQuery: o comparativo que um parceiro oficial não pode fazer" — perfeito).
3. **Modern Data Stack em PT-BR continua livre.** Kliente já publicou (#1) — aproveitar a janela de indexação antes que Indicium traduza.
4. **Power BI 2026** — Indicium tem 3 posts sobre aumento de preço/migração pra Fabric, mas TODOS de 2025. **Janela aberta pra "Power BI em 2026: 3 caminhos pra reduzir lock-in pós-Fabric"**.
5. **Tech SEO é vantagem permanente da Kliente.** Indicium não tem Article/BreadcrumbList/FAQ schemas, nem internal linking. Mesmo que cresçam em volume, vão perder rich results e cluster authority.

---

## Everymind / AI/R v2 — confirmação de morte editorial

### Estado real

- **`everymind.com.br` → 301 → `aircompany.ai/en/salesforce/`.** A marca virou sub-página institucional do grupo AI/R.
- **`/insights`** do AI/R = página gated com formulário pra "Industry Reports" (não é blog).
- Nav do AI/R lista 30+ produtos/serviços (AI/COCKPIT, LLIA, DORA, AI/AGENTSBUILDER, COMPOUND AGENTIC AI SYSTEMS, GEO etc.) — **zero link pra blog editorial**.
- Robots.txt: 404. Sitemap.xml: 404. Não existe descoberta de conteúdo indexável editorial.
- Estratégia clara: **deixaram de competir em SEO orgânico de blog**; investem em (a) parcerias certificadas (Salesforce #1 BR, ISG Provider Lens), (b) eventos/webcasts ("Transform AI"), (c) industry reports gated.

### Implicação

- O risco "Everymind pode entrar em conteúdo via AI/R" (v1 Risco #3) **caiu de Média pra Baixa**: AI/R está apostando em frameworks proprietários e relatórios gated, não em SEO editorial.
- O território "Salesforce especializada premium com produção editorial em PT-BR" está **mais vazio do que a v1 indicava**. Sottelli ocupa nominalmente mas com volume e qualidade decrescentes (próxima seção). **A Kliente é o único player com produção editorial real, técnica, em PT-BR, no nicho.**
- Apareceu termo novo na nav do AI/R: **"GEO (Generative Engine Optimization)"**. Vale Kliente publicar tese em PT-BR antes que vire commodity.

---

## Sottelli v2 — esqueleto operacional

### Inventário

| Campo | Valor real |
|---|---|
| Sitemap | `/sitemap.xml` indexa 3 sub-sitemaps: pages, blog-categories, blog-posts |
| Posts no `blog-posts-sitemap.xml` | **32** |
| Stack | **Wix** (`static.wixstatic.com`) |
| Hreflang | ⚠️ presente mas quebrado: `en-us → /en/blog/{slug-PT}` (URL inexistente versionada em EN) |
| OG por post | ❌ **OG title = "Publicações \| Sottelli" em todos** (genérico, sem por-post) |
| **JSON-LD** | ❌ zero schemas |
| Link rot | ⚠️ múltiplos posts no sitemap retornam 404 (encoding inconsistente de acento entre sitemap e routing) |

### Cadência real

| Período | Posts |
|---|---|
| 2026 | **1** (24/fev — "Abismo Hype/ROI") |
| Jul-ago 2025 | 7 posts em ~1 mês |
| Out 2024 | 1 post |
| Anteriores | ~23 posts dispersos |

**Padrão: silêncio + bursts curtos.** Não tem cadência editorial.

### Sinais de engagement expostos na UI (Wix)

| Post | Data | Views | Notas |
|---|---|---|---|
| O Abismo entre o Hype e o ROI (Agentforce + Data Cloud) | 24-fev-2026 | **19 visualizações** | 3 min de leitura. ~3 meses no ar. |
| Migração de dados pro Salesforce: boas práticas e armadilhas | 11-ago-2025 | **49 visualizações** | 4 min de leitura. ~9 meses no ar. |

**Tradução**: o flagship de SEO do Sottelli faz ~6 views/mês. Não há audiência. O risco "Sottelli pode escalar no mesmo tom" (v1 Risco #2) **cai de Média pra Baixa-Média**: eles têm a voz pra escrever, não a operação pra publicar.

### Estrutura do post âncora (não-acessível por bug Wix)

Tentativa de leitura profunda do flagship + segundo melhor retornou "Não foi possível encontrar esta página" mesmo seguindo o canonical declarado. Bug de encoding no routing Wix vs. sitemap. **A própria descoberta orgânica do Sottelli está parcialmente quebrada.** Listing do `/blog` index funciona; deep linking direto falha pra slugs com acento.

---

## Comparação de tech SEO — quadro consolidado

| Sinal | Indicium (PT-BR) | Sottelli | AI/R / Everymind | **Kliente** |
|---|---|---|---|---|
| Sitemap.xml | ✅ 285 URLs | ✅ multi-sitemap | ❌ 404 | ✅ |
| Robots.txt | ✅ aponta sitemap | ✅ | ❌ 404 | ✅ |
| Hreflang | ✅ correto | ⚠️ quebrado em EN | ❌ ausente | ✅ PT/EN/ES + x-default |
| Canonical | ✅ self-canonical | ✅ | n/a | ✅ |
| OG por post | ✅ próprio | ❌ genérico | n/a | ✅ + imagem dinâmica per-post |
| Article schema (JSON-LD) | ❌ | ❌ | n/a | ✅ |
| BreadcrumbList schema | ❌ | ❌ | n/a | ✅ Blog › Pilar › Post |
| FAQPage schema | ❌ (mesmo com FAQ no corpo) | ❌ | n/a | ✅ auto-injetado se ≥2 H2? |
| Internal linking no corpo | ❌ 0 | ⚠️ não verificado (404) | n/a | ✅ "Continue explorando" + inline |
| Cadência | desconhecida (sem lastmod) | ~1/trimestre | 0 | 2/sem × 3 idiomas |
| Engagement exposto | n/a | flagship = 19 views/3mo | n/a | n/a |

**Leitura**: a Kliente é a única na vizinhança com **tech SEO completo** (schemas + hreflang + OG dinâmico + internal linking). Esse é um moat permanente que não some com novos posts dos concorrentes.

---

## Re-validação dos quick wins v1

### Status atual dos 10 originais

| # | Pilar | Título | v1 status | v2 leitura |
|---|---|---|---|---|
| 1 | data | Modern Data Stack em 2026 | ✅ publicado | **Janela ainda aberta** — Indicium só tem em EN. Aproveitar. |
| 2 | sf | Quando NÃO usar Salesforce | ✅ publicado | Diferenciação confirmada — nenhum concorrente vai fazer "anti-Salesforce". |
| 3 | data | Databricks vs Snowflake vs BigQuery | ✅ publicado | **Mais valioso do que v1 estimou**: Indicium tem 6+ posts Databricks (viés total). Kliente é o agnóstico em PT-BR. |
| 4 | ai | FinOps de IA | ✅ publicado | Sem competição confirmada — segue ranqueando livre. |
| 5 | sf | Implementação Salesforce em 6 semanas | 🟡 fila | **Mantém prioridade**: Sottelli tem "Sales Boost 14 dias" (programa), AI/R não tem editorial. Frontal sem competição. |
| 6 | ai | RAG não é a resposta | 🟡 fila | **Sobe prioridade**: pilar AI Aplicada é 100% Kliente em PT-BR. Reforço de moat. |
| 7 | data | Tendências data 2026 | 🟡 fila | **Janela fecha em ~3 meses** — Indicium publicou trends 2026 em EN; provável que traduzam. Priorizar. |
| 8 | sf | Migração Pardot → MC Engagement | 🟡 fila | **Sem competição direta** — manter. |
| 9 | data | Power BI vs Tableau vs Looker vs Metabase | 🟡 fila | **Cuidado**: Indicium tem 3 posts Power BI em PT, mas zero comparativo multi-tool em PT. Janela ainda aberta. |
| 10 | ai | Multi-agent em produção | ✅ publicado | Sem competição PT-BR confirmada. |

### Quick wins NOVOS descobertos no crawl (3 ângulos)

| # | Pilar | Título proposto | Ângulo | Por que agora |
|---|---|---|---|---|
| **11** | data | **Data mesh em PT-BR: 3 perguntas que a federação não responde** | Crítica posicional ao formato 101 do Indicium | Indicium tem 3 posts "Na prática / Serviços financeiros / Implementação" — todos didáticos. Kliente entra com **tese** e leva o termo de cauda longa "data mesh erros" / "data mesh quando não usar". |
| **12** | data | **Power BI em 2026: 3 caminhos pra reduzir lock-in pós-Fabric** | Sequela ao aumento de preço — janela 2026 | Indicium tem 3 posts sobre aumento de preço **2025** e migração pra Fabric. Tudo do ano passado. "2026" abre nova SERP. Bate FinOps + lock-in (tema já forte da Kliente). |
| **13** | ai | **GEO (Generative Engine Optimization): como aparecer na resposta do LLM, não só no Google** | Termo emergente, sem cobertura PT-BR | AI/R lista "GEO" como serviço, mas zero conteúdo editorial. Indicium não cobre. Kliente publica primeiro e fica como referência em PT-BR. Encaixa com a tese "consultoria que diz como o mercado vai mudar". |

### Quick wins descartados ou rebaixados

- Nenhum descartado. **#9 BI tools** ficou um pouco mais arriscado (Indicium ativa em Power BI), mas o ângulo "matriz por porte de empresa Brasil" segue diferenciado.

### Nova ordem sugerida da fila (8 itens — 5 originais + 3 novos)

Critério: alternar pilar; abrir com janela-fechando-rápido; intercalar tese × comparativo × diário.

| Ordem | # | Título |
|---|---|---|
| 1 | 7 | Tendências data 2026 (**janela fecha em ~3 meses**) |
| 2 | 5 | Implementação Salesforce em 6 semanas |
| 3 | 13 | **GEO: como aparecer na resposta do LLM** (novo) |
| 4 | 9 | Power BI vs Tableau vs Looker vs Metabase (matriz por porte) |
| 5 | 6 | RAG não é a resposta: 6 padrões em que fine-tuning ganha |
| 6 | 11 | **Data mesh em PT-BR: 3 perguntas que a federação não responde** (novo) |
| 7 | 8 | Migração Pardot → Marketing Cloud Engagement |
| 8 | 12 | **Power BI em 2026: 3 caminhos pra reduzir lock-in pós-Fabric** (novo) |

---

## Diferenciação editorial — atualizações sobre a v1

Os 5 ângulos da v1 ("Consultoria que diz NÃO", "Métricas que ninguém publica", "Lado obscuro de X", "Decisões irreversíveis", "Diário de campo") **continuam válidos**. A v2 acrescenta dois ângulos defensivos descobertos no crawl:

6. **"Tech SEO como produto"** — publicar 1 post curto explicando que cada post tem JSON-LD, BreadcrumbList, FAQPage, OG dinâmico, hreflang completo. Não é content marketing — é positioning. Mostra que a Kliente trata o próprio site como produto de engenharia. Sottelli e Indicium não fazem nada disso. Útil pra leads técnicos.

7. **"Anti-101"** — todo post que o Indicium escreve em PT-BR começa por "O que é X". A Kliente pode reservar um formato fixo: "X não é o que dizem por aí" / "3 perguntas que X não responde" / "Quando X é desperdício". Não competir em 101 (Indicium ganha em volume); competir em tese.

---

## Riscos / observações — diff v1 → v2

| # | Risco v1 | Severidade v1 | Severidade v2 | Por que mudou |
|---|---|---|---|---|
| 1 | Indicium DA superior global em data/AI | Alta | **Alta** | confirmado e ampliado — 121 posts PT-BR ativos |
| 2 | Sottelli pode escalar no mesmo tom | Média | **Baixa-Média** | engagement exposto = 19 views/3mo; sem operação editorial |
| 3 | Everymind pode entrar via AI/R | Média | **Baixa** | AI/R não publica editorial; aposta em gated reports + frameworks |
| 4 | Inglês Indicium vaza pra buscas BR | Média | **Média** | mantém; mas Indicium agora cobre PT-BR — risco se desloca |
| 5 | Saturação Agentforce / Data Cloud | Média | **Baixa-Média** | Sottelli é único PT-BR ativo (1 post, baixíssimo engagement). Kliente já tem post; mantém ângulo "+ atendimento humano". |
| 6 | Verticais (FSI, Saúde, Mídia) = Everymind | Baixa-Média | **Baixa** | Everymind morreu; verticais agora estão menos disputados em PT-BR editorial |
| 7 | 5 dos 10 quick wins têm formato crítica/NÃO | Baixa | **Baixa** | balanceamento por #10 (diário) + #3 (comparativo) cumpriu |
| 8 | Cases-âncora bloqueados | Média | **Média** | inalterado — depende do Felipe |
| 9 | Domínio em staging | Média | **Resolvido** | site live em kliente360.com desde 2026-05-25 |
| 10 | 403 nos fetches dos concorrentes | Baixa | **Resolvido** | crawl v2 passou (Chrome real) |

### Riscos novos identificados na v2

| # | Risco | Severidade | Mitigação |
|---|---|---|---|
| 11 | **Indicium pode traduzir "Modern Data Stack" e "BI Tools Comparison" pra PT-BR a qualquer momento** — janela curta. | Média | Publicar #7 e #9 nas próximas 4 semanas. Garantir indexação rápida via internal linking + sitemap submit. |
| 12 | **"GEO" pode virar termo padronizado por outro player (AI/R, agências SEO)** antes da Kliente publicar. | Baixa-Média | Publicar #13 nas próximas 4 semanas. Definir vocabulário próprio ("GEO = como aparecer na resposta", não "GEO = SEO pra IA"). |
| 13 | **Sitemap do Indicium não tem `lastmod`** — não conseguimos inferir cadência. Podem estar publicando mais rápido do que pensamos. | Baixa | Revisitar a cada 4 semanas; se aparecer post novo competindo direto com a fila Kliente, re-ordenar. |

---

## Apêndice — dados crawl v2

- Indicium: `https://indicium.ai/robots.txt`, `https://indicium.ai/sitemap.xml`, `https://indicium.ai/pt-br/conteudo`, `https://indicium.ai/pt-br/content-hub/data-mesh-na-pratica-governanca-dados-federada-impulsiona-inovacao`
- Sottelli: `https://www.sottelli.com/sitemap.xml`, `https://www.sottelli.com/blog-posts-sitemap.xml`, `https://www.sottelli.com/blog`
- AI/R / Everymind: `https://everymind.com.br/robots.txt` (redir), `https://aircompany.ai/`, `https://aircompany.ai/en/about/insights.html`, `https://aircompany.ai/sitemap.xml` (404)
- Comparativo Kliente: `index.html`, `scripts/build-blog.mjs`, `EDITORIAL.md`, `seo-competitive-brief.md` (v1)

> **Próxima iteração recomendada (v3)**: re-crawl em 90 dias (2026-08-25) só pra checar (a) se Indicium traduziu "Modern Data Stack" / "BI Tools" / "Trends 2026" pra PT-BR, (b) se algum player começou a usar "GEO" em conteúdo editorial PT-BR, (c) se Sottelli voltou a publicar. Crawl curto, ~30 min.
