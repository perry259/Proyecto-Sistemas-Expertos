# Wiki de Investigación (LLM-Wiki)

## La idea en 1 minuto

En lugar de un RAG clásico (recuperar trozos de documentos en cada pregunta), el LLM
**construye y mantiene de forma persistente una wiki** de archivos markdown que se
apoya entre tus fuentes crudas y tú. El conocimiento se compila una vez y se mantiene
actualizado: cada fuente nueva se integra, las contradicciones se señalan, y la síntesis
refleja todo lo que has leído. El wiki se vuelve más rico con cada fuente y cada pregunta.

## Cómo usarlo

1. **Aporta fuentes** → deja los documentos en `raw/` (artículos web con el clipper de
   Obsidian en `raw/articulos/`, papers en `raw/papers/`, notas propias en `raw/notas/`).
   Las fuentes crudas son inmutables: nadie las edita.
2. **Di "ingesta" a tu agente LLM** (por ejemplo: *"ingesta la fuente raw/articulos/x.md"*).
   El agente lee la fuente, conversa contigo, escribe la página-resumen, actualiza las
   páginas de entidades/conceptos, el `index.md`, el `log.md` y hace commit.
3. **Pregunta al wiki** → el agente busca en `wiki/index.md`, lee las páginas relevantes y
   responde con citas. Las respuestas valiosas se pueden archivar en `wiki/sintesis/`.
4. **Pide un *lint*** para revisar la salud de la wiki: contradicciones, páginas huérfanas,
   contenido obsoleto, huecos de datos.

## Estructura

| Ruta | Contenido |
|---|---|
| `AGENTS.md` | Schema: el manual del LLM mantenedor (estructura, convenciones, flujos) |
| `raw/` | Fuentes crudas (artículos, papers, notas, assets). Inmutables |
| `wiki/index.md` | Catálogo de todas las páginas, por categoría |
| `wiki/log.md` | Registro cronológico de todo lo que se hace |
| `wiki/overview.md` | Síntesis global en evolución |
| `wiki/entidad/` | Páginas de personas, orgs, sistemas, etc. |
| `wiki/concepto/` | Páginas de ideas, términos y temas |
| `wiki/fuente/` | Resumen por cada fuente ingestada |
| `wiki/sintesis/` | Análisis, comparativas, respuestas archivadas |
| `wiki/_templates/` | Plantillas de página |

## Consejos

- Los archivos markdown se abren y navegan en **Obsidian** (vista de grafo incluida).
- La carpeta de adjuntos de Obsidian está configurada en `raw/assets/` para descargar
  imágenes localmente tras recortar artículos (Ctrl+Shift+D con el plugin activo).
- La wiki es un repositorio git: tienes historial, versiones y auditoría gratis.