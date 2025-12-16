---
status: draft
scope: operacion
sources:
  - "PENDIENTE_BIBLIO — White & Zainasheff — Yeast"
---

# Control de fermentación (operación)

## Objetivo
Ejecutar fermentaciones repetibles: medir lo mínimo, decidir por gates, y evitar envasar prematuro.

## Entrada rápida
- DEEP: [10 — Targets y control mínimo](DEEP/10_Targets_y_control_minimo.md)

## Checklist mínimo por lote (registro)
- [ ] Cepa y generación
- [ ] Volumen y OG/°P
- [ ] Pitch (tipo/cantidad si se conoce)
- [ ] Oxigenación (método y DO si se mide)
- [ ] Temperatura (setpoint + lectura real)
- [ ] Densidad (serie temporal)
- [ ] pH (opcional, recomendado)
- [ ] Observación sensorial rápida (manteca/solvente/fruta/sulfuro)

## Gates (decisión)
### Gate 1 — Arranque
- Señal: inicio de actividad y/o caída de densidad dentro del rango esperado. (HEURÍSTICA | PENDIENTE_BIBLIO)

### Gate 2 — Fermentación activa
- Señal: tendencia sostenida (no “plana”) + temperatura estable. (HEURÍSTICA | PENDIENTE_BIBLIO)

### Gate 3 — Cierre / maduración
- Señal: densidad estable + tiempo suficiente en condiciones correctas
- Si aplica: test de diacetilo forzado. (HEURÍSTICA | PENDIENTE_BIBLIO)

## Qué hacer si…
- **Densidad se plancha:** revisar temperatura real, viabilidad/pitch, oxígeno, nutrientes, contaminación.
- **Aparece manteca (diacetilo):** sostener/ajustar curva térmica + tiempo; evitar crash temprano.
- **Riesgo de O₂ al crash/transfer:** purgas, presiones, minimizar succión, evitar headspace.

## Puentes
- Biología de levadura: [03 — Levadura](../03_Levadura/03_Levadura.md)
- Curva térmica/VDK (DEEP): [20 — Curva térmica y diacetilo](DEEP/20_Curva_termica_y_diacetilo.md)
- Transferencias/crash/salida (DEEP): [30 — Transferencias y salida](DEEP/30_Transferencias_cold_crash_y_salida.md)
- Troubleshooting (DEEP): [40 — Troubleshooting](DEEP/40_Troubleshooting_proceso.md)
