---
status: canonical
owner: Quelonio
last_updated: 2025-12-15
---

# Contrato de Estructura — Biblia Quelonio (CANÓNICO)

## Propósito
Eliminar inconsistencias entre sesiones. A partir de este contrato:
- toda nueva carpeta/archivo/link sigue reglas fijas,
- lo histórico/legacy no se rompe,
- y cada módulo mantiene un alcance claro (anti-duplicación).

---

## Regla 0 — Fuente de verdad
Este archivo es la referencia canónica de estructura.
Si un cambio no está reflejado aquí, no se considera “estándar”.

---

## Regla 1 — Índices
### 1.1 Índice de módulo
Cada módulo NN tiene:
- carpeta: `docs/NN_Nombre/`
- índice de módulo: `docs/NN_Nombre/NN_Nombre.md`

### 1.2 Índice DEEP
Todo DEEP tiene un único punto de entrada canónico:
- `DEEP/00_INDEX.md`

Si existe un índice histórico (ej. `00_Indice_*.md`), NO se renombra en caliente.
Se crea un `00_INDEX.md` que linkea al legacy y al nuevo estándar.

---

## Regla 2 — Convención DEEP (estándar único)
### 2.1 Estructura canónica
Dentro del módulo dueño:
- `DEEP/00_INDEX.md`
- `DEEP/10_*.md`
- `DEEP/20_*.md`
- `DEEP/30_*.md`
- ...

### 2.2 Legacy (v1)
Los archivos monolíticos tipo `01_DEEP_*_v1.md` quedan como:
- “Legacy (no tocar)” y siempre linkeados desde `00_INDEX.md`.

### 2.3 Numeración
Siempre usar saltos de 10 (10/20/30/40…).
Permite insertar sin renumerar y mantiene estabilidad de links.

---

## Regla 3 — Links (rutas)
Links siempre relativos desde el archivo actual:
- misma carpeta: `Archivo.md`
- carpeta hija: `Carpeta/Archivo.md`
- carpeta padre: `../Archivo.md`

Dentro de un mismo `DEEP/`, NO usar `../` para linkear bloques.

---

## Regla 4 — Alcance por módulo (anti-duplicación)
Para evitar duplicar “el mismo tema en 2 lugares”, se define ownership:

- **03_Levadura**
  - Biología y gestión de levadura: pitch, oxígeno (desde fisiología), salud/viabilidad, repitch, floculación, troubleshooting centrado en levadura.

- **07_Fermentacion_Maduracion**
  - Control end-to-end del proceso: curva térmica, rampas, gates, transferencias, cold crash, criterio “listo para empaque”, troubleshooting de proceso.

- **06_Procesos_QA_QC**
  - Sistema QA/QC: CCP, límites, checklists, auditoría interna, metrología, registros.

- **09_Empaque_Estabilidad**
  - Técnica y operación del empaque: purgas, DO/TPO, headspace, priming, almacenamiento, shelf-life, troubleshooting de empaque.

Regla práctica:
- Si es “procedimiento y gate operativo del proceso completo” → 07.
- Si es “biología/gestión de levadura” → 03.
- Si es “sistema de control y documentación QA/QC” → 06.
- Si es “paquete y su vida útil” → 09.

---

## Regla 5 — Control de cambios estructurales
Cualquier cambio que mueva carpetas o cree convenciones nuevas sigue este orden:
1) Actualizar este contrato (2–10 líneas).
2) Ejecutar cambio en repo.
3) Verificar navegación (links) y publicar.

No se aceptan “convenciones nuevas” dentro de una sesión.
