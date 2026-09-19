# raw/ — Fuentes crudas

Capa **inmutable** del wiki. El humano (o el plugin Obsidian Web Clipper) deposita aquí
los documentos; el LLM mantenedor **solo los lee, nunca los edita**.

## Cómo añadir una fuente

1. Coloca el archivo en la subcarpeta correspondiente:

   | Subcarpeta | Qué va | Cómo se añade |
   |---|---|---|
   | `articulos/` | Artículos web convertidos a markdown | Obsidian Web Clipper en `raw/articulos/` |
   | `papers/` | Papers académicos (PDF/markdown) | Copiar el archivo |
   | `notas/` | Notas propias, apuntes, otros textos | Copiar/crear el archivo |
   | `assets/` | Imágenes descargadas localmente | Hotkey de "descargar adjuntos" (Ctrl+Shift+D) |

2. Pide al LLM que ingeste la fuente: *"ingesta raw/articulos/mi-articulo.md"*.

## Reglas

- Un archivo de fuente puede tener metadatos en la parte superior (autor, fecha, url,
  tags) — el LLM los lee para citar correctamente.
- No borres fuentes del pasado: `wiki/log.md` y las citas del wiki dependen de ellas.
- Si una fuente necesita notas adjuntas propias, se pueden crear dentro de su misma
  subcarpeta sin reestructurar nada.