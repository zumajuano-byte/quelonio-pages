---
status: draft
scope: proceso
sources:
  - "PENDIENTE_BIBLIO — White & Zainasheff — Yeast (temperatura como control; precursor de diacetilo)"
  - "PENDIENTE_BIBLIO — Palmer — How to Brew (temperatura alta: ésteres/fuseles/diacetilo)"
---

# 20 — Curva térmica, rampas y descanso de diacetilo (DEEP)

## Objetivo del bloque
Definir un **perfil térmico controlable** (no una receta fija), con gates claros:
- arranque controlado,
- fase activa estable,
- rampa de cierre,
- descanso de diacetilo (cuando aplique),
- y criterios para pasar a frío/transferencias.

---

## 1) Principio rector: temperatura = palanca #1 de consistencia
- La temperatura afecta la velocidad y el perfil sensorial; cambios en temperatura cambian el resultado. (HEURÍSTICA OPERATIVA | PENDIENTE_BIBLIO)
- Fermentar demasiado caliente incrementa **ésteres**, **alcoholes superiores (fuseles)** y **riesgo de diacetilo**. (HEURÍSTICA OPERATIVA | PENDIENTE_BIBLIO)

---

## 2) Perfil térmico por fases (modelo operativo)
### Fase A — Arranque (primeras 24–72h típicas)
**Objetivo:** evitar picos de temperatura (sobre todo por calor metabólico).  
**Criterio:** setpoint inicial conservador + medición de temperatura real del fermentador.

Gate de salida:
- caída de densidad sostenida,
- temperatura estable (sin overshoot).

### Fase B — Fermentación activa
**Objetivo:** mantener el fermentador dentro del rango de cepa con mínima oscilación.  
**Criterio:** control estable > “ajustar todo el tiempo”. (HEURÍSTICA OPERATIVA | PENDIENTE_BIBLIO)

Gate de salida:
- acercarse a densidad terminal (criterio de tendencia). (HEURÍSTICA OPERATIVA | PENDIENTE_BIBLIO)

### Fase C — Cierre / rampa final (maduración)
**Objetivo:** terminar atenuación y permitir que la levadura reduzca subproductos.  
**Criterio:** una **rampa moderada** puede acelerar el cierre (según cepa/estilo). (HEURÍSTICA OPERATIVA | PENDIENTE_BIBLIO)

---

## 3) Diacetilo y precursor: criterio de proceso
- Parte del control de cierre es permitir que la levadura reduzca compuestos no deseados; el **precursor de diacetilo** es relevante si se corta/enfría antes de tiempo. (HEURÍSTICA OPERATIVA | PENDIENTE_BIBLIO)
- Implicancia: **no cold crash / no separar levadura** hasta que el lote haya “cerrado” (densidad estable + gate sensorial o test).

---

## 4) Gates recomendados (para decidir rampas y frío)
Usar gates simples y repetibles:
- **Gate 1 (inicio):** caída de densidad confirmada.
- **Gate 2 (fase final):** estás a pocos puntos de FG (o tendencia de densidad desacelera). (HEURÍSTICA OPERATIVA | PENDIENTE_BIBLIO)
- **Gate 3 (cierre):** densidad estable + tiempo mínimo de maduración (y test de diacetilo si aplica).
- **Gate 4 (frío):** recién aquí se habilita cold crash / transferencia a empaque.

---

## 5) Registro mínimo (para comparar lotes)
- Setpoint por fase + temperatura real.
- Densidad (serie temporal).
- Momento de rampa final (fecha/hora y “por qué”).
- Resultado sensorial (diacetilo sí/no; solvente; frutado).
- Tiempo total hasta “listo para frío”.

---

## 6) Puentes (no duplicar)
- Detalle de “pitch rate” y “oxígeno” vive en 03_Levadura (Bloque 02).
- Detalle de diacetilo test / acondicionamiento vive en 03_Levadura (Bloque 04) como técnica; aquí se usa como gate de proceso.

---

* * *
## Matriz de afirmaciones (anclaje bibliográfico)

| Afirmación | Tag | Fuente | Métrica/validación | Estado |
|---|---|---|---|---|
| La temperatura es la palanca #1 para consistencia y perfil sensorial | HEURÍSTICA OPERATIVA \| PENDIENTE_BIBLIO | — | Deriva sensorial; varianza curva | Pendiente |
| Evitar overshoot en arranque reduce defectos y desvíos | HEURÍSTICA OPERATIVA \| PENDIENTE_BIBLIO | — | Overshoot vs ésteres/fuseles | Pendiente |
| Una rampa moderada al final puede ayudar al cierre según cepa/estilo | HEURÍSTICA OPERATIVA \| PENDIENTE_BIBLIO | — | Tiempo a FG; diacetilo | Pendiente |
| No habilitar frío/transferencia antes de “cierre” reduce diacetilo residual | HEURÍSTICA OPERATIVA \| PENDIENTE_BIBLIO | — | Test diacetilo; panel sensorial | Pendiente |
| Gates simples (densidad+tiempo+sensorial/test) mejoran repetibilidad | HEURÍSTICA OPERATIVA \| PENDIENTE_BIBLIO | — | Repetibilidad por receta | Pendiente |
