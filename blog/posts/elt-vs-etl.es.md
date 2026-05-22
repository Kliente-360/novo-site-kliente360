---
title: "ELT vs ETL: por qué cambió la moda y qué importa de verdad"
slug: "elt-vs-etl"
pillar: "data"
date: "2026-01-28"
readMinutes: 6
excerpt: "ELT se volvió consenso en casi todo deck de arquitectura. Pero el cambio de letras no es la ganancia real — y copiar el patrón sin entender el motivo traba más proyectos de los que destraba."
tldr: "ELT le ganó a ETL porque el warehouse creció en compute, no porque transformar después sea virtud. La ganancia real es separar la ingesta de la modelación — y eso puede hacerse en cualquier orden. Equipo que adopta ELT sin esa claridad solo cambia un silo por otro."
keywords: ["ELT", "ETL", "data warehouse", "ingeniería de datos", "Fivetran"]
---

La reunión de arquitectura de datos en 2026 casi siempre tiene la misma diapositiva: ELT en destaque, ETL marcado como legado. El argumento que viene con eso es "transformá después, dejá que el warehouse haga el trabajo pesado". Suena moderno. Y es, en la mayoría de los casos, la elección correcta. Pero la explicación que suele acompañarlo — "ELT es mejor que ETL" — es simplista y oculta el punto real. Lo que cambió no fue la virtud de transformar antes o después. Fue el costo relativo del compute del warehouse, y lo que eso permitió organizar distinto.

Este texto va sobre por qué ELT ganó, qué significa eso de verdad para un equipo de datos, y dónde copiar el patrón a ciegas todavía estorba.

## Lo que cambió desde 2018

ETL nació en un mundo donde almacenar era barato y procesar era caro. Storage local + compute en servidor dedicado significaba que transformar dato antes de cargar tenía sentido — no querías cargar 100 GB para extraer 10 GB de KPI. La transformación era un filtro de costo.

En 2026, la cuenta se invirtió. [Warehouse cloud — Snowflake, BigQuery, Databricks](/blog/es/snowflake-bigquery-databricks.html) — cobra storage muy barato y compute elástico bajo demanda. Cargar dato bruto cuesta casi nada; procesar cuando hace falta cuesta lo que cuesta el uso. Mantener dato bruto histórico se volvió económicamente trivial. Y ahí transformar antes de cargar dejó de tener sentido — estás pagando dos veces (compute en la transformación previa + carga), para ahorrar storage que ya no es caro.

Ese es el motivo técnico de fondo. No es "ELT es más moderno". Es "el cuello de botella de costo se movió".

## La ganancia real: separar ingesta de modelación

La consecuencia más valiosa de ELT no está en el E-L-T versus E-T-L. Está en romper la operación en dos proyectos independientes.

**Ingesta (EL).** Traer dato de Salesforce, Stripe, Postgres, planillas, APIs externas. Idealmente automatizado por herramienta (Fivetran, Airbyte, Meltano). Schedule, schema, retry, monitoring. Es commodity. Quien todavía escribe conector propio en Python para ingesta de SaaS está tirando plata.

**Modelación (T).** Transformar dato bruto en modelo de negocio: staging → intermediate → marts. [Acá dbt se vuelve la pieza central](/blog/es/dbt-na-pratica.html), con SQL versionado, tests, documentación, lineage.

Equipo que organiza así deja de pagar consultoría para reinventar el conector de Salesforce y gasta el tiempo donde está el valor — modelar el negocio. ELT se volvió consenso porque esa separación se volvió barata. En ETL, ingesta y transformación quedaban acopladas en el mismo job — romper una rompía la otra.

> ELT no ganó porque transformar después sea virtud. Ganó porque permite separar ingesta (commodity) de modelación (valor) — y organizar cada una como debe.

## Dónde el ELT a ciegas sigue estorbando

La adopción de ELT por cargo-cult, sin entender el porqué, genera tres problemas comunes.

**Cargar todo "porque el storage es barato".** Verdad, el storage es barato, pero *encontrar* dato en medio de 800 tablas brutas no lo es. El equipo carga todos los schemas de todos los sistemas, y seis meses después nadie sabe qué tabla usar. Cantidad se vuelve ruido. Principio mejor: ingerí lo que sirve a un caso de uso, expandí cuando aparece otro caso.

**Transformar dentro del warehouse sin dbt.** Equipos migran de ETL a ELT pero escriben transformación como `CREATE TABLE AS SELECT` suelto, sin versionado, sin test, sin documentación. Es solo ETL peor, ahora corriendo dentro del warehouse. ELT sin disciplina es ETL con más quilombo.

**Olvidar compliance.** En ETL clásico, dato sensible (CUIT, e-mail, tarjeta) podía filtrarse *antes* de la carga. En ELT, el dato bruto va al warehouse — incluyendo el sensible. Sin masking, encryption-at-rest y tagging desde el día 1, ELT puede crear pasivo de privacidad que ETL evitaba por diseño.

Esos tres casos no invalidan a ELT. Invalidan ELT *mal hecho*, del mismo modo que ETL bien hecho todavía existe y funciona en algunos nichos.

## Cuándo ETL todavía es la respuesta correcta

La discusión pública hace parecer que ETL murió. No murió. Hay tres contextos donde sigue siendo la elección correcta.

**Compliance restrictivo donde el dato sensible no puede circular.** Salud, financiero con reglas específicas, dato personal bajo jurisdicción que prohíbe cierto almacenamiento. Acá filtrar antes de cargar es diseño, no elección técnica.

**Volumen tan grande que el storage cloud bruto se vuelve caro.** IoT a escala, log de transacción financiera en millones de TPS, datos de sensor industrial. En algunos de esos, agregar antes de cargar cambia el orden de magnitud del costo. No es regla; es excepción que vale calcular.

**Sistema fuente viejo con latencia alta.** Cuando extraer dato ya cuesta horas y el destino necesita dato listo, transformar en el camino ahorra un paso. Común en integración con mainframe legado.

Fuera de esos contextos, ELT es el default razonable.

## La pregunta correcta, en lugar de ELT vs ETL

La conversación que importa no es "qué sigla". Es: **quién es dueño de la modelación, y cómo está versionada**. Eso vale tanto en ETL como en ELT. Equipo que tiene dueño claro, transformación en Git, tests automatizados y documentación viva entrega valor. Equipo que no lo tiene va a entregar quilombo — independiente de la sigla en la arquitectura.

[El mito del dato limpio sigue valiendo en ambos](/blog/es/dado-limpo-e-um-mito.html) — la calidad es relativa al uso, no absoluta. ELT facilita iterar (podés remodelar sin rehacer la ingesta), pero no cambia la regla fundamental.

Si tu empresa está discutiendo ELT vs ETL como decisión estratégica, probablemente está en la pregunta equivocada. La decisión estratégica es cómo organizar la ingesta (comprá, no construyas) y la modelación (versionada, testeada, documentada). La sigla es detalle.
