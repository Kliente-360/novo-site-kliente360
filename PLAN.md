# Plano vivo — Rebrand Kliente 360 (2026)

Documento mantido em main. Registra contexto, decisões tomadas e próximos passos. Atualizar a cada sessão.

Última atualização: 2026-05-22 (terceira passada — lote de 10 posts + audit SEO).

---

## 1. Contexto

Site institucional novo da **Kliente 360** — consultoria CRM/BI, parceira Salesforce. Single-page em HTML/CSS/JS puro + blog estático (Markdown→HTML).

Decisor: Felipe Silva (felipe@kliente360.com).

Repositório: `novo-site-kliente360`. Branch: `main`. Scaffold inicial já criado (commit `165f314`).

## 2. Direção definida

| Tema | Decisão |
|---|---|
| Público-alvo | Misto — decisor C-level + executor (head de ops/atendimento) |
| Tom visual | Moderno-tech com alma corporativa premium. Sem paleta digital saturada. |
| Blog | Gerador estático leve: Markdown → HTML. Entrega final 100% estática. |
| Logo | Mantido (wordmark "kliente 360" verde + 4 círculos). PNG fornecido pelo Felipe. |
| Verde do logo | Tratar como **acento** sobre base neutra/escura — não como tema dominante. |

## 3. Identidade antiga (referência histórica, não destino)

Levantado do arquivo Figma "Kliente 360" (autora Bruna Slongo, 2022).

**Paleta antiga** (Lato Regular/Medium/Bold):
- Neutral: `#000000` / `#7D8185` / `#E6E6E6` / `#F1F2F0` / `#FFFFFF`
- Green: `#006600` / `#008000` / `#009900` / `#00B300` / `#00CC00`
- Yellow: `#F8DF61` / `#F9E47A` / `#FAE992` / `#FBEEAA` / `#FCF3C3`
- Cyan: `#0084E1` / `#0093FA` / `#159EFF` / `#2EA9FF` / `#48B3FF`
- Navy ("Blue"): `#01020F` / `#040427` / `#06073E` / `#080A55` / `#0B0C6C`

**Escala tipográfica antiga (Lato)** — desktop: H1 64/130 · H2 48/130 · H3 40/130 · H4 32/130 · H5 24/Auto · H6 20/Auto · H7 18/Auto · P1 16/28 · P2 14/Auto · Label 12/Auto. Mobile: mH1 34 · mH2 30 · mH3 24 · mH4 22 · mH5 20 · mH6 18 · mH7 16.

**Arquitetura antiga**: Home / Sobre / Serviços CRM / Serviços BI / Blog / Contato. Header com badge "Salesforce partner". Copy de prova técnica ("dados reais", "profissionais certificados").

## 3.1. Três pilares do novo portfólio (definidos 2026-05-22)

1. **Salesforce — core CRM.** Sales Cloud, Service Cloud, Data Cloud, Agentforce. Reforça a herança/parceria.
2. **Data & Analytics — agnóstico de marca.** Engenharia de dados + analytics avançado / data science. **Expertise interna em Tableau (não declarada como viés ao mercado — decisão 2026-05-22).**
3. **IA Aplicada — pilar novo.** Aplicações práticas de IA em empresas de segmentos diversos. Pegada de **software house / produtos SaaS**. Vocabulário: "agentes de IA" (não "copilots").

## 3.2. Shortlist competitiva (para o brief)

Dois concorrentes por pilar, mistura de boutique + mid/enterprise:

| Pilar | Especializada (espelho) | Mid/Enterprise (teto aspiracional) |
|---|---|---|
| Salesforce | Sottelli | Everymind |
| Data & Analytics | Somativa | Indicium |
| IA Aplicada | Mind Group | CI&T |

Referências secundárias mapeadas, fora do recorte: WeUse, Valtech, Capgemini, beAnalytic, Active BI, BDA Solutions, Aquarela, Zup, Slalom Build, Thoughtworks.

## 3.4. Sistema de cor (definido 2026-05-22)

- **Logo green `#009900`**: sagrado. Só no wordmark/dots. Não usar em UI.
- **UI green `#007A3D`**: verde editorial. Usado em CTAs, eyebrows, links, hover e ícones de pilar. Estratégia "logo ≠ UI" (Starbucks, Spotify).
- **Cores secundárias por pilar** (aparecem só dentro da seção do respectivo pilar):
  - Salesforce → azul profundo `#0B5394`
  - Data & Analytics → âmbar `#C9A227`
  - IA Aplicada → violeta `#6D28D9`
- **Navy `#06073E`** reaproveitado da paleta antiga como `--bg-deep` — fundo escuro alternativo opcional para hero/seção de IA. Não usar como acento.
- **Yellow `#F8DF61` e Cyan `#0093FA` da paleta antiga**: descartados. Não combinam com o posicionamento de consultoria especializada premium.

## 3.5. Atributo de marca — sócios na operação (2026-05-22)

Decidido **não fazer propaganda explícita** ("sócios na linha de frente" como manchete) nem mostrar fotos/nomes — soaria autoelogiosos. A credibilidade entra de forma **incorporada ao tom**, não como bullet de venda:

- Frases-ancora no copy: *"atendidos por quem entrega"*, *"conversa direta com quem decide"*, *"sem camadas de account manager"*.
- CTA padrão pode ser **"Falar com um sócio"** em contextos específicos (rodapé, contato), não como botão dominante.
- Sem seção "Quem somos" com fotos.

## 3.3. Marca e posicionamento (definidos 2026-05-22)

- **Posicionamento**: consultoria especializada premium. Altíssima expertise, alta personalização, time enxuto, poucos clientes estratégicos. Os 3 pilares costurados como diferencial único no mercado local. **Decisão de copy 2026-05-22**: a palavra "boutique" não é usada externamente (interna ou competitivamente pode ser categoria); externamente usa-se "consultoria especializada".
- **Tagline**: **"Conhecimento aplicado, como serviço."** *(evolução sutil de "Conhecimento como serviço")*
- **Metodologia própria**: **Trilha 360** — narrativa de jornada do cliente ao longo dos pilares. Detalhamento das etapas a definir.
- **Cases para o site** (conteúdo a alimentar depois — placeholders no HTML):
  - Sem Parar
  - Bodytech
- **Produtos SaaS de IA** (pilar 3 — placeholders, ideia ainda em revisão):
  - Agente autônomo de atendimento interno (RH)
  - Analytics contábil para PME

## 3.4. Inspirações de design (definidas 2026-05-22)

Referências: **Apple**, **Google**, **Salesforce**. Síntese aplicada:

- **Base visual ← Apple**: neutro escuro ou off-white dominante, tipografia grande como protagonista, hero respirando, paleta restrita.
- **Acento de cor ← Google**: o verde do logo entra pontual e com intenção (CTAs, palavra-chave do título, linha decorativa) — nunca em blocos inteiros.
- **Camada de confiança ← Salesforce**: bloco de parceria/certificações, cases nomeados com números, copy explicativa sem rebuscar.
- **Tipografia**: sans humanista única, 2 pesos. Candidatos: **Inter**, **Söhne**, **GT America**. Reverte a sugestão anterior de serif editorial — não combina com o trio.

## 4. Sequência de trabalho — entregue

| # | Etapa | Status |
|---|---|---|
| 1 | Levantamento da marca antiga (Figma) | ✅ |
| 2 | Direção visual macro (consultoria especializada premium, verde como acento) | ✅ |
| 3 | Portfólio repensado — três pilares + competitive-brief (`research/competitive-brief.md`) | ✅ |
| 4 | Arquitetura do site (single-page, 10 seções, pilares com cor secundária) | ✅ |
| 5 | Sistema visual definitivo — tokens, paleta, tipografia (§3.4) | ✅ |
| 6 | Implementação `index.html` + tokens.css + reset.css + main.css | ✅ |
| 7 | Build do blog Markdown→HTML (`scripts/build-blog.mjs`) | ✅ |

### Entregas adicionais (além da sequência inicial)

- **Mark "Aperture"** — 4 pontos em losango compacto, escolhido em §3.4.
- **Styleguide** publicado em `/styleguide.html`.
- **Blog multilíngue PT/EN/ES** com 3 posts iniciais publicados (`/blog/`, `/blog/en/`, `/blog/es/`).
- **i18n real** — dicionário + redirect entre variantes nas páginas do blog.
- **SEO + GEO**: JSON-LD `Article`, OG, canonical, sitemap auto, robots, favicon SVG, og-image.png renderizado no build.
- **Home teaser de blog** auto-popular (3 mais recentes a partir de `assets/data/posts.json`).
- **34 temas de back-catálogo 2026** mapeados, datas Tue/Wed válidas atribuídas.
- **Routine de publicação** ativada com prompt completo (cadência, pilares rotacionados, SEO/GEO, idiomas).
- **Cache invalidation** robusto no Netlify (`_headers` + `netlify.toml` + meta + querystring).
- **Cadência editorial documentada**: 1 post Tue + 1 Wed, pulando feriados nacionais e Aniversário de SP.

## 5. Próximos passos imediatos

- ⏳ Observar a routine rodar pelas próximas semanas e ajustar prompt se necessário.
- ⏳ Quando aprovados pelos clientes: alimentar métricas reais dos cases Sem Parar e Bodytech.
- ⏳ Conectar o form de contato a um endpoint real (Formspree / Netlify Forms / API própria) — hoje só faz feedback visual.
- ⏳ Trocar WhatsApp e badge Salesforce (ver §7.1).

## 6. Decisões fechadas

| Tema | Decisão |
|---|---|
| Tagline | "Conhecimento aplicado, como serviço." |
| Tipografia | **Inter** como sans humanista única, 2–3 pesos. *Serif editorial descartado.* |
| Badge "Salesforce Partner" | Mantido no hero. Atualizar pra badge oficial recomendado pelo branding Salesforce (ver §7.1). |
| Cases públicos vs depoimentos | Cases nomeados (Sem Parar, Bodytech) com métricas a alimentar quando aprovadas. |
| Cores antigas | Yellow e Cyan descartados. Navy reaproveitado como `--bg-deep`. |
| Workflow Git | Direto em `main`, sem feature branches. |
| Cadência do blog | Tue + Wed, pulando feriados nacionais BR + Aniversário SP. Rotação dos 3 pilares. |

## 7. Notas técnicas

- Stack: HTML5 + CSS (com `tokens.css`, `reset.css`, `main.css`) + JS módulo. Sem frameworks.
- Estrutura de pastas já criada: `assets/{css,js,img,fonts}/`, `blog/posts/`.
- Blog usará build Markdown→HTML (script Node minimal, sem dependências pesadas — definir na fase 7).
- **Workflow Git (decidido 2026-05-22)**: trabalhamos direto em `main`. Sem feature branches. Netlify deploya de `main`. Mudança aceita por se tratar de site institucional pequeno, com um único decisor.

## 7.1. Parking lot — pendências a resolver

- **WhatsApp**: número atual `5511961875594` (link `http://wa.me/5511961875594`) é provisório — trocar pelo número oficial da Kliente 360 quando definido. Aparece em `index.html` (seção Contato + footer) e em `scripts/build-blog.mjs` (footer das páginas geradas).
- **Badge "Salesforce Partner"**: hoje é uma pílula `pill-line` textual no hero (`index.html` §"Hero"). Trocar pelo badge oficial recomendado pelo branding Salesforce assim que tivermos acesso ao kit oficial — pode exigir SVG/PNG fornecido pela Salesforce + manter requisitos de uso da marca.
- **Cases com métricas reais**: Sem Parar e Bodytech estão como placeholders dashed em `index.html` §"Cases". Trocar `—` pela métrica e o `lbl` pelo dado quando aprovados pelos clientes.
- **Endpoint do form de contato**: hoje só faz feedback visual no submit (em `assets/js/main.js`). Integrar com Formspree / Netlify Forms / API própria quando definirmos.
- **OG image PNG via build**: hoje funciona via `@resvg/resvg-js`. Se quisermos imagens OG dinâmicas por post (com título do post), virar tarefa futura.

## 9. Roadmap SEO/Conteúdo (derivado do audit pós-#10)

Auditoria SEO/GEO completa rodada com 13 posts publicados (3 back-catálogo + #01–#10). Quick wins do Bloco A já aplicados (títulos encurtados, links internos balanceados, backlinks). Pendências organizadas por dono.

### 9.1. Conteúdo a escrever (eu, em sessões dedicadas)

| Item | Esforço | Impacto | Notas |
|---|---|---|---|
| **3 pillar pages** (Salesforce, Data, IA Aplicada) | 1 sessão por pillar | Alto | Agregador temático linkando todos os posts do cluster + manifesto curto da prática Kliente 360. PT/EN/ES. |
| **Glossário Kliente 360** | 1 sessão | Alto | 20–30 termos (Agentforce, Data Cloud, RAG, dbt, ELT, embedding, MRR, recall@k, etc.), 1 parágrafo cada + link pro post canônico. GEO-friendly. PT/EN/ES. |
| **Cases-âncora** (Sem Parar, Bodytech) | 2 sessões | Alto | Bloqueado por input do Felipe sobre escopo, números aprovados e o que pode ser dito publicamente. |
| **Página comercial** ("Como contratar consultoria especializada de CRM/Data/IA") | 1 sessão | Alto | Captura query comercial direta. Liga pillar pages. |
| **Pass de backlinks dedicado** após cada lote de 5 posts novos | 0,5 sessão/lote | Médio | Revisar posts antigos pra linkar novos onde fizer sentido. Hoje feito ad-hoc. |

### 9.2. Mudanças no build/infra (Felipe ou outro mantenedor — fora do escopo do agente de blog)

| Item | Esforço | Impacto | Onde |
|---|---|---|---|
| **Confirmar hreflang** entre PT/EN/ES + `x-default` | 30 min | Médio | `scripts/build-blog.mjs` — injetar `<link rel="alternate" hreflang="...">` no `<head>` de cada variante |
| **Verificar robots.txt** permite `/blog/*`, `/blog/en/*`, `/blog/es/*` e o sitemap | 5 min | Crítico se errado | raiz |
| **FAQ schema** auto-injetado | 0,5 dia | Alto | `scripts/build-blog.mjs` — detectar H2 terminados em `?` (ou flag `faq: true` no frontmatter) → emitir `FAQPage` JSON-LD. Posts-alvo: quando-agente-e-resposta, mapear-processos, rag-na-pratica, avaliacao-de-agentes |
| **BreadcrumbList schema** | 0,5 dia | Médio | `scripts/build-blog.mjs` — `Blog › Pilar › Post` |
| **OG image dinâmica por post** | 1 dia | Médio | Hoje usa `og-image.png` genérica. Virar template SVG → PNG por post no build (título + pilar + cor secundária). Já listado em §7.1. |
| **Rodar PageSpeed Insights** em 2–3 posts típicos | 15 min | Médio | Calibrar Core Web Vitals reais |

### 9.3. Competitive SEO (futuro, quando houver capacidade)

Rodar `marketing:competitive-brief` específico de SEO contra Indicium, Everymind e Sottelli (os 3 da shortlist competitiva §3.2 que mantêm blog ativo). Identificar keyword overlap e gaps.

## 8. Histórico de sessões

- **2026-05-21** — Scaffold criado. Levantamento Figma feito. Direção visual macro acordada. Portfólio entrou em revisão (competitive-brief). Documento PLAN.md criado em main.
- **2026-05-22** — Três pilares do portfólio definidos (Salesforce / Data & Analytics / IA Aplicada — pilar 3 renomeado de "IA & Aplicações" em 2026-05-22). Shortlist de 6 concorrentes consolidada. Brief competitivo rodado — resultados em `research/competitive-brief.md`. Marca consolidada: tagline "Conhecimento aplicado, como serviço.", metodologia "Trilha 360", posicionamento de **consultoria especializada premium** (decisão 2026-05-22: descartar "boutique" como label externa). Cases-âncora: Sem Parar, Bodytech (métricas a alimentar). Produtos SaaS placeholders: agente RH, analytics contábil PME. Inspirações de design definidas: Apple (base), Google (acento), Salesforce (confiança). Arquitetura da home decidida (single-page, 10 seções, pilares na home). Idiomas: PT/EN/ES. Trilha 360 definida: Mapear → Prototipar → Validar → Implantar → Sustentar. Styleguide v0.1 publicado em `styleguide.html` para validação antes do site grande.
- **2026-05-22 (segunda passada)** — Site grande implementado e refinado: nav sticky com blur, hero com mark Aperture, 3 pilares + 3 seções deep, Trilha 360 horizontal, cases, confiança, blog teaser, contato, footer. Sistema de cor refinado (logo green sagrado vs UI green editorial; secundárias por pilar; navy resgatado como `--bg-deep`). i18n real PT/EN/ES com redirect inteligente. Build MD→HTML multilíngue (`scripts/build-blog.mjs`) — 3 posts publicados em PT/EN/ES com cadência Tue/Wed (13, 19, 20 mai). 34 temas mapeados para back-catálogo 2026. Routine de blog ativada. Favicon SVG + og-image.png gerado por `@resvg/resvg-js`. Sitemap + robots + JSON-LD `Article`. Cache invalidation robusto no Netlify. Tipografia do post editorial (escala suave, sem barra colorida, padrão bold-lead-in para subseções curtas). LinkedIn oficial + WhatsApp provisório adicionados (parking).
- **2026-05-22 (terceira passada)** — Lote de blog posts #01–#10 publicado direto via skill `marketing:draft-content` + routine manual: mapear-processos-antes-do-salesforce (sf), dado-limpo-e-um-mito (data), rag-na-pratica (ai), sales-cloud-cinco-antipadroes (sf), dbt-na-pratica (data), llm-como-agente-interno (ai), service-cloud-sla-nao-e-decoracao (sf), elt-vs-etl (data), avaliacao-de-agentes (ai), customer-360-vs-cdp (sf). Todos PT/EN/ES com forward links contextuais entre posts. EDITORIAL.md atualizado por commit. Diretriz de links internos formalizada no `blog/posts/README.md` (§"Estratégia de links internos"). Audit SEO/GEO completo rodado — quick wins aplicados (títulos de #02 e #07 encurtados, +1 link interno em 3 posts subconectados, backlinks dedicados). Roadmap §9 criado com itens de conteúdo restantes (pillar pages, glossário, cases, página comercial) e itens de build (hreflang, FAQ schema, BreadcrumbList, OG dinâmica).
