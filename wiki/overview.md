---
tipo: sintesis
tags: [investigacion, panorama]
creado: 2026-09-18
actualizado: 2026-09-18
fuentes: 11
---


# Panorama general (overview)

Esta página es la **síntesis global** de tu investigación sobre *cómo los automóviles se
van degradando con el tiempo*. Se actualiza en cada ingest.

---

## Tesis / panorama

El automóvil se degrada por **dos relojes que corren a la vez**:

1. **Reloj de uso (kilómetros)** — el desgaste mecánico: fricción, fatiga y abrasión en
   motor, transmisión, suspensión y frenos ([[Desgaste mecánico]]).
2. **Reloj de tiempo (años)** — la degradación química: corrosión ([[Corrosión
   electroquímica]]), caucho y polímeros ([[Envejecimiento del caucho]], [[Degradación por
   UV y calor]]), fluidos ([[Oxidación de fluidos]]), combustible ([[Degradación del
   combustible]]), baterías ([[Envejecimiento calendario vs ciclo]]) y electrónica
   ([[Fatiga térmica y electrónica]]).

La conclusión que atraviesa todas las fuentes: **el coche envejece aunque esté parado**.
Los componentes no metálicos (caucho, plásticos, fluidos, baterías, electrónica) se
degradan por tiempo y temperatura, no por uso. Por eso el mantenimiento por **calendario**
(aceite, correas, neumáticos, fluidos) es tan importante como el de kilometraje
([[Edad vs kilometraje]], [[Mantenimiento preventivo]]).

## Línea de investigación

### Preguntas abiertas

- ¿La carga rápida DC (>100 kW) acelera o no la degradación de las baterías EV? Geotab
  (2026) mide hasta 3,0 %/año; Recurrent (13.000 Teslas) aún no encuentra diferencia.
  Falta más datos de campo.
- ¿Hasta qué punto el almacenamiento en garaje templado empeora la corrosión invernal
  frente a un coche a la intemperie?
- Qué combinación de edad/km degrada más el valor (chatarra) de un EV cuando su batería
  cae del 80 % de SOH.

### Hipótesis principales

- **H1 (central)**: el envejecimiento por tiempo domina sobre el desgaste por uso en
  todo lo no metálico; por eso "poco usado" ≠ "bien conservado".
- **H2**: la temperatura es el acelerador universal de la degradación (Arrhenius): se
  aplica a baterías, condensadores, caucho, plásticos y fluidos.
- **H3**: en coches de 10+, el costo y los fallos pasan de la mecánica a la electrónica
  (conectores, soldaduras, cableado).

### Contradicciones / debates abiertos

- **Carga rápida DC y baterías EV**: Geotab la asocia con mayor degradación; Recurrent no
  (ver [[Batería de iones de litio]]).
- **Garaje vs intemperie**: el garaje templado funde nieve+sal y puede acelerar la
  corrosión, pero protege del sol que daña interiores y caucho.

## Conexiones clave

- [[Edad vs kilometraje]] es el hub que conecta los dos relojes con cada sistema.
- [[Mantenimiento preventivo]] es la respuesta operativa a ambos relojes.
- El calor conecta [[Envejecimiento calendario vs ciclo]], [[Fatiga térmica y
  electrónica]], [[Envejecimiento del caucho]] y [[Degradación por UV y calor]]:
  temperatura alta acelera todo.
- [[Batería de plomo-ácido]] y [[Batería de iones de litio]] comparten el concepto
  [[Envejecimiento calendario vs ciclo]].

## Cómo navegar

- Catálogo completo: [[index]].
- Historial de operaciones: [[log]].
- Las fuentes originales (inmutables) viven en `raw/articulos/`.