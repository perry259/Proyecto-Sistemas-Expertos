# wiki/fuente/ — Páginas-resumen de fuentes

Una página por cada fuente ingestada (artículo, paper, nota). Es el puente entre `raw/`
(la fuente original, inmutable) y el resto del wiki.

**Normas (ver `AGENTS.md`):**
- Nombre: `fuente/<slug-de-la-fuente>.md` (kebab-case).
- Frontmatter YAML completo (tipo `fuente`, creado, actualizado; más autor, fecha y URL
  si se conocen).
- Todo en español, con enlaces a las entidades y conceptos que la fuente toca.
- Plantilla: [[_templates/fuente]]