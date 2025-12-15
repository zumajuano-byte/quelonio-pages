---
status: draft
scope: proceso
sources:
  - "White & Zainasheff — Yeast (monitoreo y control; oxígeno/pitch como fundamentos)"
  - "Palmer — How to Brew (efecto de temperatura; riesgos por fermentación caliente)"
---

# 10 — Targets y control mínimo de fermentación (DEEP)

## Objetivo del bloque
Definir el set mínimo de variables y gates para que Fermentación sea repetible:
- qué controlar,
- con qué frecuencia,
- y con qué criterio se decide avanzar a maduración/transferencias/envasado.

---

## 1) Variables mínimas (orden de prioridad)
Prioridad típica de control y monitoreo:
1) Temperatura
2) Densidad
3) pH
4) Oxígeno disuelto
5) CO₂ :contentReference[oaicite:3]{index=3}

**Regla práctica:** si temperatura y densidad están “bajo control”, el 80% de los problemas se vuelven diagnosticables.

---

## 2) Targets operativos por fase (sin números “mágicos”)
### Fase A — Arranque (lag → inicio actividad)
- Objetivo: levadura activa sin stress.
- Gate: inicio visible y/o caída de densidad dentro del tiempo esperado (según cepa y pitch).

### Fase B — Fermentación activa
- Objetivo: caída de densidad sostenida y temperatura estable.
- Gate: tendencia consistente (no “plana”).

### Fase C — Cierre / maduración
- Objetivo: terminar atenuación + limpieza de subproductos (diacetilo/precursor).
- Gate: densidad estable + tiempo suficiente en condiciones correctas (y, si aplica, test de diacetilo forzado).

---

## 3) Control térmico: criterio técnico
Fermentar demasiado caliente incrementa:
- ésteres,
- alcoholes superiores (fuseles),
- y riesgo de diacetilo/residual si el cierre es deficiente. :contentReference[oaicite:4]{index=4}

---

## 4) Checklist mínimo de registro (QA/QC de proceso)
Por lote:
- [ ] Cepa y generación (si aplica)
- [ ] Volumen y °P/OG
- [ ] Pitch (tipo y cantidad; si se conoce)
- [ ] Método de oxigenación (y DO si se mide)
- [ ] Temperatura real (setpoint + lectura)
- [ ] Densidad (serie temporal)
- [ ] pH (opcional pero recomendado)
- [ ] Observación sensorial rápida (manteca/solvente/frutado/sulfuro)

---

## 5) Puentes (no duplicar)
Para profundidad “biológica” (pitch rate, oxigenación, repitch, floculación), usar el módulo 03_Levadura:
- allí está el detalle “por qué” y “cómo” desde levadura; acá consolidamos el “control de proceso”.
