---
status: draft
scope: empaque_estabilidad
type: proceso
sources:
  - "White & Zainasheff — Yeast (carbonatación en botella; exceso/defecto; salud de levadura; sanitizantes)"
  - "Palmer — How to Brew (embotellado; acondicionamiento; impacto del oxígeno en vida útil)"
---

# 10 — Priming y carbonatación en botella (gates, cálculo y fallas)

## Objetivo
Estandarizar el acondicionamiento en botella con foco en:
- carbonatación consistente,
- seguridad (evitar sobrecarbonatación),
- y estabilidad (no degradar el lote por oxígeno o sanitización mal aplicada).

---

## 1) Gate previo “listo para envasar”
No embotellar si no se cumple:
- Densidad estable (y atenuación razonable).
- Gate sensorial/técnico (sin diacetilo evidente).
- Claridad/turbidez aceptada según estilo (decisión explícita).

Nota práctica: el acondicionamiento agrega carbonatación y también tiempo de balance; y la vida útil depende fuertemente de la exposición al oxígeno en la fase final y durante el envasado. :contentReference[oaicite:1]{index=1}

---

## 2) Levadura para carbonatar: “mínimo viable” y riesgo de exceso
- No hace falta mucha levadura: el orden de magnitud para carbonatar adecuadamente es bajo.
- Exceso de levadura en el envase aumenta el riesgo de sabores de autólisis con el tiempo. :contentReference[oaicite:2]{index=2}

Regla operativa:
- priorizar levadura saludable + condiciones constantes antes que “más levadura”.

---

## 3) Priming: lógica de cálculo (sin tabla, con criterio)
Variables que definen el azúcar de cebado:
- CO2 residual (depende de la temperatura de la cerveza al envasar),
- objetivo de volúmenes de CO2 por estilo,
- volumen real a envasar.

Criterio: si ignorás CO2 residual y/o temperatura, aumentás el riesgo de sobrecarbonatación. :contentReference[oaicite:3]{index=3}

---

## 4) Condición y almacenamiento para carbonatar
- Guardar botellas en lugar oscuro y templado (rango típico de acondicionamiento).
- Esperar un plazo estándar para que la carbonatación se complete (orden de ~2 semanas).
- La cerveza “joven” puede requerir más tiempo de balance. :contentReference[oaicite:4]{index=4}

---

## 5) Fallas típicas (diagnóstico rápido)
### 5.1 Falta de carbonatación
Causas frecuentes:
- levadura no saludable / temperatura insuficiente / tiempo insuficiente,
- priming incorrecto,
- sanitización química fuera de concentración (daño a la levadura).

Acciones:
- verificar cálculo vs temperatura,
- asegurar temperatura adecuada y homogénea,
- medir concentración de sanitizante (no “a ojo”). :contentReference[oaicite:5]{index=5}

### 5.2 Sobrecarbonatación
Causas frecuentes:
- exceso de azúcar,
- cerveza no completamente atenuada,
- contaminación con organismos que consumen carbohidratos complejos.

Acciones:
- reforzar gate “atenuación completa” antes de envasar,
- revisar cálculo (incluye CO2 residual),
- disparar investigación microbiológica si hay deriva sensorial. :contentReference[oaicite:6]{index=6}

---

## 6) Registro mínimo (para que el sistema aprenda)
- Temperatura de la cerveza al envasar.
- Azúcar de cebado (tipo y gramos totales).
- Volumen envasado.
- Fecha/hora y temperatura de acondicionamiento.
- Resultado: días hasta carbonatación + evaluación sensorial.

---

## Puentes (no duplicar)
- Oxígeno/DO/TPO en empaque: ver Bloque 20 + nota base `../Oxidacion_y_DO.md`.
- Log operativo: usar `TP_Log_Envasado_y_Estabilidad.md`.
