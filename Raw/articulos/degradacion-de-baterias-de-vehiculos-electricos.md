---
tema: vehículos eléctricos, batería litio, capacidad, carga
tipo: articulo
fecha: 2026-09-18
autor: Equipo de investigación (compilación web)
tags: [vehiculos-electricos, litio, capacidad]
---

# Degradación de baterías de vehículos eléctricos (iones de litio)

## Dos relojes: calendario y ciclo

El envejecimiento **por calendario** domina en vehículos eléctricos: representa >75 % de
la pérdida de capacidad frente al envejecimiento **por ciclo** (carga/descarga).

- **Estado de carga (SOC)**: un estudio de Sandia mostró que mantener la batería al 90 %
  de SOC pierde ~9 % de capacidad vs ~2,5 % a 25 %. La regla "stash 20–80 %" reduce el
  *fade* un 20–30 %.
- **Temperatura**: el calor acelera la degradación (≈2× por cada 10–18 °C). En pruebas
  WLTC a 45 °C con 2.184 ciclos la capacidad cae **−19,2 %**; a 10 °C casi no hay pérdida
  por ciclo.
- **Química**: LFP se degrada ~1–1,5 %/año vs NMC/NCA ~2–2,5 %/año.
- **Carga rápida DC (>100 kW)**: hasta **3,0 %/año** frente a ~2,3 % global (~2× vs carga
  en CA), según Geotab; aunque Recurrent (13.000 Teslas) no encontró aún diferencia
  atribuible a la carga rápida.

## Datos reales de campo

- Geotab (2026, 22.700 vehículos): degradación media **2,3 %/año** (1,8 % en 2024);
  tras 8 años ≈**81,6 %** de estado de salud (SOH). Clima caluroso añade ~+0,4 %/año.
- Garantías típicas: ≥70 % de retención a 8 años / 100.000 mi. Estudio con ~8.000
  vehículos: retención media **95,15 %** de capacidad.
- 6 meses al 100 % SOC y 35 °C: ~4–6 % de pérdida vs 1–2 % al 50 %.

## Mitigación

- Mantener el SOC entre 20–80 % para el uso diario; cargar al 100 % solo para viajes.
- Evitar aparcar al sol / con batería cerca del 0 % o 100 % en calor extremo.
- Preferir carga en CA (lenta) para el día a día.
- El BMS del vehículo ya aplica márgenes: la "100 %" que ves no es física.

## Referencias consultadas

- Geotab, *EV battery health: degradation & fast-charging study*: https://www.geotab.com/press-release/ev-battery-health-degradation-fast-charging-study
- Midtronics, *la ciencia de la degradación de baterías EV*: https://www.midtronics.com/es/blog/the-science-behind-ev-battery-degradation-and-how-to-mitigate-it
- MDPI Energies, *capacity fade en baterías de litio*: https://www.mdpi.com/1996-1073/14/17/5220
- ScienceDirect, *envejecimiento por calendario y ciclo*: https://www.sciencedirect.com/science/article/pii/S002627142200275X