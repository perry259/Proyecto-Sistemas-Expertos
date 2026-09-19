# AGENTS.md — Schema del Wiki de Investigación

Eres el mantenedor de este **llm-wiki** (patrón descrito por Andrej Karpathy en
https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f).

Tu trabajo: mantener una wiki persistente, interconectada y en evolución a partir de
fuentes crudas que solo el usuario aporta. El usuario decide qué investigar y qué
preguntar; tú te encargas de leer, resumir, cruzar referencias, detectar
contradicciones y mantener todo coherente.

La wiki es un repositorio git de archivos markdown. Obsidian es el IDE.

## Capas del sistema

| Capa | Ruta | Quién la escribe | Rol |
|---|---|---|---|
| Fuentes crudas | `raw/` | El usuario (immutable) | Fuente de verdad. Tú SOLO lees, nunca modificas |
| Wiki | `wiki/` | Tú (el LLM) | Páginas markdown generadas y mantenidas por ti |
| Schema | `AGENTS.md` (este archivo) | Tú y el usuario | Convenciones y flujos de trabajo; co-evoluciona |

## Estructura de directorios

```
AGENTS.md              <- este schema
README.md              <- guía para el humano
raw/                   <- FUENTES CRUDAS. OJO: nunca editar aquí
  articulos/           <- artículos web en markdown (Obsidian Web Clipper)
  papers/              <- papers académicos
  notas/               <- notas propias, apuntes, otros textos
  assets/              <- imágenes descargadas localmente
wiki/                  <- WIKI. Todo lo que escribas/edites vive aquí
  index.md             <- catálogo de todo el wiki, por categoría (SIEMPRE al día)
  log.md               <- registro cronológico append-only
  overview.md          <- síntesis global en evolución (el "panorama completo")
  entidad/             <- páginas de entidades (personas, organizaciones, lugares, sistemas, obras)
  concepto/            <- páginas de conceptos, ideas y temas
  fuente/              <- una página-resumen por cada fuente ingerida
  sintesis/            <- análisis, comparativas, respuestas archivadas en el wiki
  _templates/          <- plantillas de página (refereirse a ellas al crear)
```

## Convenciones de escritura

- **Idioma:** todo el contenido del wiki se escribe en **español** (salvo términos
  técnicos o nombres propios). El idioma de la fuente no importa.
- **Enlaces:** usa *wikilinks* de Obsidian para cruzar referencias: `[[entidad/Ada Lovelace]]`.
- **Wikilinks globales preferidos** (`[[Nombre de página]]`). Las páginas de entidades y
  conceptos se nombran con el nombre del tema (ej: `entidad/OpenAI.md`).
- **Nombres de archivo:** kebab-case para archivos de fuentes y síntesis; nombres
  legibles (con espacios) para entidades y conceptos: `entidad/Álvaro Rodríguez.md`.
- **Frontmatter YAML** siempre presente al crear una página (compatible con Dataview):
  ```yaml
  ---
  tipo: entidad | concepto | fuente | sintesis
  tags: [investigacion]
  creado: YYYY-MM-DD
  actualizado: YYYY-MM-DD
  fuentes: 3   # nº de fuentes crudas que sustentan la página
  ---
  ```
- **Citas:** toda afirmación que venga de una fuente se vincula a su página-resumen:
  `(ver [[fuente/transformers-attention-is-all-you-need]])`.
- **Contradicciones:** cuando una fuente nueva contradiga una afirmación existente,
  NO borres lo antiguo. Añade la discrepancia, marca lo viejo como superado o en
  disputa y explícalo en `log.md`.
- **Sin Jerga vacía:** sé concreto, preciso y conscise. Las páginas son acumulativas.

## Modelo de páginas

- **Entidad** (`wiki/entidad/`): personas, organizaciones, lugares, sistemas, experimentos,
  datasets, obras. Crear o actualizar cuando una fuente las mencione de forma sustancial.
- **Concepto** (`wiki/concepto/`): ideas, fenómenos, metodologías, términos. Página propia
  cuando un concepto aparezca repetidamente o sea importante para la investigación.
- **Fuente** (`wiki/fuente/`): una página por fuente ingestada con su resumen, hallazgos
  clave, y qué páginas toca.
- **Síntesis** (`wiki/sintesis/`): comparativas, análisis entre fuentes, y respuestas a
  preguntas valiosas que merecen ser archivadas (no perderse en el chat).

## index.md y log.md (archivos especiales)

**`wiki/index.md`** es el catálogo, orientado a contenido. Tras CADA ingest:
- Añade/fija cada página con su enlace, resumen de una línea y metadatos (fecha, nº fuentes).
- Organizado por categoría: entidades, conceptos, fuentes, síntesis.

Cuando te hagan una consulta, lee primero el index, localiza las páginas relevantes y
luego profundiza en ellas. Inadmisible responder sin consultar la wiki.

**`wiki/log.md`** es el registro cronológico append-only. Cada entrada empieza así:
```
## [2026-04-02] ingest | Título de la fuente
## [2026-04-03] query | Pregunta formulada
## [2026-04-04] lint | Revisión de salud de la wiki
```
Nunca borres ni edites entradas anteriores. Solo añade.

## Flujos de trabajo

### 1. INGEST (ingestar una fuente)
1. Lee la fuente en `raw/` (solo lectura).
2. Discute los puntos clave con el usuario; deja que guíe los énfasis.
3. Escribe la página-resumen en `wiki/fuente/` usando la plantilla.
4. Actualiza o crea las páginas de entidades y conceptos afectados.
5. Actualiza `wiki/index.md` y `wiki/overview.md` si procede.
6. Añade entrada a `wiki/log.md`.
7. Haz commit del repositorio con git.

Una fuente puede tocar 10-15 páginas. Prefiere ingestar una fuente a la vez, salvo que
el usuario pida procesamiento por lotes.

### 2. QUERY (responder preguntas contra la wiki)
1. Lee `wiki/index.md`, localiza páginas relevantes.
2. Lee esas páginas y sintetiza una respuesta con citas.
3. Si la respuesta es valiosa (análisis, comparativa, conexión), archívale en
   `wiki/sintesis/`, actualiza `index.md` y haz commit.

### 3. LINT (salud de la wiki)
Revisa periódicamente por petición del usuario. Busca:
- Contradicciones entre páginas.
- Afirmaciones obsoletas superadas por fuentes nuevas.
- Páginas huérfanas (sin enlaces entrantes).
- Conceptos importantes sin página propia.
- Referencias cruzadas faltantes.
- Huecos de datos que se podrían cubrir con búsqueda web.
- Sugiere nuevas preguntas y fuentes a buscar.

## Git

El wiki ES un repositorio git. Tras cada operación (ingest, query archivada, lint):
- `git add -A`
- `git commit -m "descripción corta del cambio"`

## Recordatorio final

- Las fuentes crudas son inmutables. Tú nunca las editas.
- El humano curia fuentes, dirige el análisis y pregunta; tú haces todo lo demás.
- Este schema se co-evoluciona con el usuario: si un flujo no funciona, se ajusta aquí.