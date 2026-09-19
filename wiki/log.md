---
tipo: log
tags: [investigacion]
creado: 2026-09-18
---

# Log

Registro cronológico **append-only** del trabajo sobre el wiki: ingests, queries
archivadas y pases de lint. Nunca se borran ni editan entradas anteriores; solo se añaden.

Formato de cada entrada:
`## [AAAA-MM-DD] operacion | Título`

Comandos útiles:
```bash
grep "^## \[" log.md | tail -5   # últimas 5 entradas
```

---

## [2026-09-18] setup | Creación inicial del wiki

- Inicializado el vault como llm-wiki (schema en `AGENTS.md`).
- Creada la estructura `raw/` (fuentes) y `wiki/` (entidades, conceptos, fuentes,
  síntesis), con `index.md`, `log.md` y `overview.md`.
- Repositorio git inicializado y primer commit realizado.

## [2026-09-18] ingest | Lote inicial de 11 fuentes sobre degradación de automóviles

- Investigación web en 4 frentes (corrosión, mecánica, polímeros/fluidos, baterías/electrónica).
- Añadidas 11 fuentes en `raw/articulos/` (inmutables) y sus páginas-resumen en `wiki/fuente/`:
  corrosión y óxido, desgaste mecánico motor/transmisión, suspensión y frenos, edad vs
  kilometraje, caucho/neumáticos, interiores UV, fluidos, combustible, batería 12 V,
  baterías EV, electrónica.
- Creadas 8 entidades (motor, transmisión, suspensión, frenos, baterías, neumático, ECU)
  y 10 conceptos (corrosión, desgaste, caucho, UV, fluidos, combustible, calendario vs
  ciclo, edad vs km, mantenimiento, fatiga térmica).
- `index.md` y `overview.md` actualizados con la síntesis inicial.