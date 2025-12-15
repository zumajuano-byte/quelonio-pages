---
status: draft
scope: empaque_estabilidad
type: troubleshooting
sources:
  - "Palmer — How to Brew (oxidación/cartón; almacenaje; chill haze y estabilidad; vida útil depende del envasado)"
  - "White & Zainasheff — Yeast (fallas de carbonatación; sobrecarbonatación por contaminación; sanitizantes)"
---

# 40 — Shelf-life y Troubleshooting de Empaque (síntomas → causas → acciones)

## Objetivo
Cerrar el loop de estabilidad:
- detectar temprano degradación,
- identificar causa raíz (empaque vs almacenamiento vs microbiología),
- ejecutar acciones correctivas,
- y registrar para mejorar el SOP.

---

## 1) Gates de estabilidad (mínimos)
### Gate A — Al cierre del envasado
- Procedimiento de purga y transferencia ejecutado (Bloque 20).
- Headspace controlado.
- Incidentes registrados (paradas, mangueras, envase abierto).

### Gate B — 7 días
- Chequeo sensorial rápido (aroma “apagado”, papel/cartón, azufre, solvente).
- Chequeo de carbonatación (en botella/keg).

### Gate C — 14–30 días
- Evaluación de estabilidad real por estilo (especial foco en hoppy).

---

## 2) Síntoma: oxidación / “papel-cartón” / envejecimiento acelerado
### Lectura técnica (qué significa)
Si una cerveza toma carácter a cartón con el tiempo, se interpreta como oxidación; la vida útil real depende de cómo se embotelló/envasó y se almacenó. :contentReference[oaicite:0]{index=0}

### Causas probables (orden típico)
1) Purga insuficiente (línea/envase).
2) Transferencia con aire (salpicado, caída libre).
3) Headspace alto o envase abierto demasiado tiempo.
4) Almacenamiento caliente o con ciclos térmicos (acelera degradación).

### Acciones correctivas
- Detener y auditar SOP de purgas y transferencias (checklist obligatorio).
- Reducir tiempos entre llenado y cierre.
- Mejorar control de almacenamiento y logística.

---

## 3) Síntoma: aroma “apagado” muy rápido (especialmente cervezas lupuladas)
### Causas probables
- Oxígeno en empaque (misma lógica que arriba).
- Temperatura de guarda inadecuada / fluctuante.

### Acciones
- Reforzar Bloque 20 (purga y circuito cerrado).
- En logística: definir estándar mínimo de almacenamiento para esa familia de cerveza.

---

## 4) Síntoma: falta de carbonatación (botella)
### Causas probables
- Priming mal calculado (temperatura/CO₂ residual).
- Temperatura de acondicionamiento insuficiente o variable.
- Levadura debilitada o dañada.
- Sanitizante usado fuera de concentración (residuo que daña levadura). :contentReference[oaicite:1]{index=1}

### Acciones
- Verificar cálculo vs temperatura de cerveza y objetivo CO₂.
- Asegurar acondicionamiento templado estable y tiempo suficiente.
- Estandarizar sanitización (medición de concentración, drenaje).

---

## 5) Síntoma: sobrecarbonatación / “botellas explosivas”
### Causas probables
- Exceso de azúcar.
- Cerveza no completamente atenuada.
- Contaminación con organismo que consume carbohidratos complejos → gas + deriva sensorial. :contentReference[oaicite:2]{index=2}

### Acciones
- Gate previo estricto: densidad estable + (si aplica) fermentación forzada como verificación.
- Auditar higiene y proceso de envasado (micro).
- Si hay evidencia de contaminación: disparar protocolo QA/QC (aislar lote, revisar limpieza/sanitización).

---

## 6) Síntoma: “haze” en frío / estabilidad visual inconsistente
### Lectura
La bruma en frío (chill haze) no da sabor, pero se relaciona con estabilidad de largo plazo: cervezas con haze tienden a deteriorar sabor antes que cervezas sin haze. :contentReference[oaicite:3]{index=3}

### Acciones
- Revisar proceso de clarificación/frío (en 07 y 03).
- Definir objetivo por estilo (turbidez intencional vs claridad).

---

## 7) Registro mínimo (obligatorio)
Por corrida de envasado:
- Fecha/hora, lote, tipo de envase
- Procedimiento de purga/transferencia (sí/no; método)
- Incidentes (paradas, desconexiones, envase abierto)
- Condición de almacenamiento (ambiente/frío) + temperatura
- Checkpoints sensoriales: 7/14/30/60 días
- Resultados de carbonatación (si aplica)

---

## Puentes
- Priming/botella: ver Bloque 10
- Oxígeno (DO/TPO, purga, transferencias): ver Bloque 20 + `../Oxidacion_y_DO.md`
- Almacenamiento: ver Bloque 30
- Fermentación “listo para empaque”: ver 07_Fermentacion_Maduracion/DEEP
