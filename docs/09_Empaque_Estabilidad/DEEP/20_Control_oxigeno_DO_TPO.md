---
status: active
scope: empaque_estabilidad
type: proceso
sources:
  - "Palmer — How to Brew (oxígeno en etapa final/envasado y vida útil)"
  - "White & Zainasheff — Yeast (riesgo de oxígeno en transferencias; DO como variable relevante)"
---

# 20 — Control de oxígeno en empaque: DO/TPO, purgas y transferencias (DEEP)

## Objetivo (en simple)
Reducir al mínimo el ingreso de oxígeno desde “Listo para Empaque” hasta el cierre final del envase.

¿Por qué importa? Porque en esta etapa el oxígeno te acorta la vida útil y te “apaga” la cerveza (aroma más bajo, envejecimiento acelerado).

---

## Navegación rápida (para trabajar en orden)
- Entrada desde 07: [05 — Preparación para envasar](05_Preparacion_para_envasar.md)
- Volver al final de 07 (antes de envasar): [07/30 — Transferencias, cold crash y salida](../../07_Fermentacion_Maduracion/DEEP/30_Transferencias_cold_crash_y_salida.md)
- Registro de corrida: [TP — Log de envasado y estabilidad](TP_Log_Envasado_y_Estabilidad.md)

---

## 1) Definiciones operativas (sin vueltas)
- **DO (Dissolved Oxygen):** oxígeno disuelto en la cerveza en un punto del proceso.
- **TPO (Total Package Oxygen):** oxígeno total en el envase (lo disuelto + lo que queda en el “aire” del headspace).

Nota práctica: aunque no midas DO/TPO, podés controlarlo muy bien con procedimiento:
**purga + circuito cerrado + cero salpicado + envase abierto el menor tiempo posible**.

---

## 2) Dónde entra oxígeno (mapa de riesgo)
Orden típico de riesgo (alto → bajo):

1) **Transferencias con aire**  
   (manguera sin purgar, caída libre, salpicado, espuma por turbulencia)
2) **Headspace sin purgar**  
   (keg/botella/lata con aire adentro)
3) **Paradas/demoras** con envase abierto  
   (llenaste y tardaste en cerrar)
4) **Microfugas** en conexiones/juntas/válvulas  
   (entra poco, pero durante mucho tiempo)

---

## 3) Gate previo (condición para habilitar empaque)
No se habilita empaque si:
- no está cerrado el final del proceso (densidad estable + diacetilo resuelto), o
- no podés ejecutar transferencia **sin aire** (sin purga / sin circuito cerrado / con salpicado).

Este bloque es “el seguro”: si acá aflojás, después la cerveza envejece y no hay forma de “arreglarla” en el paquete.

---

## 4) Estándar de transferencia cerrada (lo mínimo obligatorio)
Regla simple:
**la cerveza se mueve en circuito cerrado o purgado, sin caída libre y sin salpicado.**

Procedimiento mínimo:
1) Preparar línea/manguera sanitizada.
2) **Purgar la línea con CO2** (objetivo: que NO quede aire).
3) Purgar el recipiente destino (keg / bright / llenadora) con CO2.
4) Transferir con presión controlada (sin turbulencia innecesaria).
5) Mantener headspace mínimo y/o “manta” de CO2 donde aplique.

---

## 5) Purgas por tipo de empaque (estándar simple)

### 5.1 Keg
- Purgar el keg antes de llenar.
- Mantener CO2 en cabeza y cerrar sin “aspirar” aire.
- Registrar método (y cantidad de ciclos si usás ciclos).

Checklist rápido:
- [ ] Keg purgado
- [ ] Línea purgada
- [ ] Sin espuma excesiva durante llenado
- [ ] Cierre rápido

### 5.2 Botella
- Minimizar salpicado durante llenado.
- Controlar headspace (no dejar “aire de más”).
- Si purgás con CO2, estandarizar método (tiempo/boquilla) y registrarlo.

Checklist rápido:
- [ ] Llenado “suave” (sin turbulencia)
- [ ] Headspace controlado
- [ ] Cierre sin demoras

### 5.3 Lata
- Purgar envase y/o línea según tu equipo.
- Minimizar el tiempo entre llenado y cierre.
- Evitar demoras con lata abierta.

Checklist rápido:
- [ ] Envase/línea purgados
- [ ] Cierre inmediato
- [ ] Sin paradas largas con envase abierto

---

## 6) Monitoreo (si medís) y “proxies” (si no medís)

### Si medís DO/TPO
Usá las mediciones para aprender y corregir: compará corridas, detectá en qué parte sube, y fijá un estándar.

### Si NO medís DO/TPO (totalmente válido al principio)
Usá estos “sí/no” y registralos:
- purga de línea ejecutada (sí/no)
- purga de envase ejecutada (sí/no)
- transferencia sin caída libre (sí/no)
- sin salpicado/turbulencia (sí/no)
- envase abierto el menor tiempo posible (sí/no)
- sensorial acelerado: ¿aparece “cartón/papel” temprano? (sí/no)

---

## 7) Registro mínimo (para que el sistema aprenda)
Por lote y por corrida de envasado, anotar:
- temperatura de cerveza al envasar
- método de transferencia (cerrada / semi / abierta)
- método de purga (línea y envase)
- incidentes (paradas, demoras, desconexión, salpicado)
- resultado sensorial a 7 / 14 / 30 días (nota corta)

→ [TP — Log de envasado y estabilidad](TP_Log_Envasado_y_Estabilidad.md)

---

## 8) Troubleshooting rápido (oxígeno)

### Síntomas típicos
- “apagado” aromático rápido
- notas a cartón/papel (envejecimiento)
- vida útil corta (se cae antes de lo esperable)

### Causas probables
- purga insuficiente (línea o envase)
- headspace alto (mucho aire)
- salpicado / turbulencia / espuma excesiva
- paradas prolongadas con envase abierto
- microfugas (conexiones/juntas)

### Acciones
- Pausar corrida y re-purgar línea y envases.
- Volver al estándar de transferencia cerrada (no seguir “a medias”).
- Registrar incidente y ajustar el SOP (qué falló y dónde).

---

## BIBLIO (canónico) — plantilla mínima
> Regla: no alcanza con “X dice…”. Registrar edición y ubicación (capítulo/sección/página).  
> Si hay conflicto entre heurística y BIBLIO, manda BIBLIO y se actualiza la heurística.

### Fuente (1)
- source_id: BIB-09-O2-001
- Obra: How to Brew
- Autor: John Palmer
- Edición / Año / Editorial: [COMPLETAR]
- Capítulo / Sección: [COMPLETAR]
- Página(s): [COMPLETAR]
- Nota breve: oxígeno en etapas finales/envasado como driver de vida útil y “apagado” aromático.

### Fuente (2)
- source_id: BIB-09-O2-002
- Obra: Yeast: The Practical Guide to Beer Fermentation
- Autores: Chris White; Jamil Zainasheff
- Edición / Año / Editorial: [COMPLETAR]
- Capítulo / Sección: [COMPLETAR]
- Página(s): [COMPLETAR]
- Nota breve: riesgo de oxígeno en transferencias y efectos cuando ya hay poca levadura disponible.

### Matriz de afirmaciones (3–5) — vinculadas a Fuente (1) y/o (2)
- A1 (Oxígeno final = vida útil): el O2 en empaque acorta vida útil y reduce aroma percibido (“apagado”).
  - Evidencia: BIB-09-O2-001 → cap/sección/pág [COMPLETAR]
  - Impacto: prioridad operacional en purgas/cierre rápido.
- A2 (TPO importa aunque no midas): TPO combina DO + headspace; por eso el headspace/purga y el cierre son críticos.
  - Evidencia: BIB-09-O2-001 → cap/sección/pág [COMPLETAR]
  - Impacto: estándares por tipo de envase (keg/botella/lata).
- A3 (Transferencia cerrada reduce DO): circuito cerrado + línea purgada + sin salpicado reduce incorporación de O2.
  - Evidencia: BIB-09-O2-002 → cap/sección/pág [COMPLETAR]
  - Impacto: gate: “no envasar si no puedo transferir sin aire”.
- A4 (Demoras con envase abierto elevan riesgo): cuanto más tiempo abierto, mayor TPO por headspace.
  - Evidencia: BIB-09-O2-001 → cap/sección/pág [COMPLETAR]
  - Impacto: regla: “cerrar inmediatamente” y evitar paradas.
- A5 (Microfugas degradan a lo largo del tiempo): pequeñas entradas sostenidas elevan oxidación y aceleran envejecimiento.
  - Evidencia: BIB-09-O2-001 y/o BIB-09-O2-002 → cap/sección/pág [COMPLETAR]
  - Impacto: checklist de juntas/válvulas + registro de incidentes.

---

## Referencias (nota)
- Palmer — el oxígeno en etapas finales/envasado es crítico para vida útil.
- Yeast — el oxígeno en transferencias es un riesgo clave en el cierre del proceso.
