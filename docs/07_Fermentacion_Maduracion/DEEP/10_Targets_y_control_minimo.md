---
status: draft
scope: proceso
sources:
  - "PENDIENTE_BIBLIO — White & Zainasheff — Yeast (monitoreo y control; oxígeno/pitch como fundamentos)"
  - "PENDIENTE_BIBLIO — Palmer — How to Brew (efecto de temperatura; riesgos por fermentación caliente)"
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
5) CO₂ (HEURÍSTICA OPERATIVA | PENDIENTE_BIBLIO)

**Regla práctica:** si temperatura y densidad están “bajo control”, el 80% de los problemas se vuelven diagnosticables. (HEURÍSTICA OPERATIVA | PENDIENTE_BIBLIO)

---

## 2) Targets operativos por fase (sin números “mágicos”)
### Fase A — Arranque (lag → inicio actividad)
- Objetivo: levadura activa sin stress.
- Gate: inicio visible y/o caída de densidad dentro del tiempo esperado (según cepa y pitch). (HEURÍSTICA OPERATIVA | PENDIENTE_BIBLIO)

### Fase B — Fermentación activa
- Objetivo: caída de densidad sostenida y temperatura estable.
- Gate: tendencia consistente (no “plana”). (HEURÍSTICA OPERATIVA | PENDIENTE_BIBLIO)

### Fase C — Cierre / maduración
- Objetivo: terminar atenuación + limpieza de subproductos (diacetilo/precursor).
- Gate: densidad estable + tiempo suficiente en condiciones correctas (y, si aplica, test de diacetilo forzado). (HEURÍSTICA OPERATIVA | PENDIENTE_BIBLIO)

---

## 3) Control térmico: criterio técnico
Fermentar demasiado caliente incrementa:
- ésteres,
- alcoholes superiores (fuseles),
- y riesgo de diacetilo/residual si el cierre es deficiente. (HEURÍSTICA OPERATIVA | PENDIENTE_BIBLIO)

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

---

* * *
## Matriz de afirmaciones (anclaje bibliográfico)

| Afirmación | Tag | Fuente | Métrica/validación | Estado |
|---|---|---|---|---|
| Temperatura es la variable #1 por impacto y controlabilidad | HEURÍSTICA OPERATIVA \| PENDIENTE_BIBLIO | — | Overshoot térmico; defectos sensoriales | Pendiente |
| Densidad (serie temporal) permite gates repetibles de avance de fase | HEURÍSTICA OPERATIVA \| PENDIENTE_BIBLIO | — | Varianza FG; “stalls”; retrabajos | Pendiente |
| pH agrega capacidad diagnóstica (fermentación desviada/infección) | HEURÍSTICA OPERATIVA \| PENDIENTE_BIBLIO | — | pH vs curva densidad; defectos | Pendiente |
| DO y/o método de oxigenación condiciona arranque y performance | HEURÍSTICA OPERATIVA \| PENDIENTE_BIBLIO | — | Lag time; atenuación; off-flavors | Pendiente |
| “Densidad estable + cierre” reduce empaque prematuro e inestabilidad | HEURÍSTICA OPERATIVA \| PENDIENTE_BIBLIO | — | gushing; sobre/infra-carb; diacetilo | Pendiente |
