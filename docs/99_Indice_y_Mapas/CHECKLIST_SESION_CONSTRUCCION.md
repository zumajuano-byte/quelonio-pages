---
status: canonical
owner: Quelonio
last_updated: 2025-12-15
---

# Checklist de sesión — Construcción de Biblia (CANÓNICO)

1) Abrir `CONTRATO_ESTRUCTURA.md` (recordatorio: no inventar convenciones).
2) Definir módulo dueño (03 vs 07 vs 06 vs 09, etc.).
3) Confirmar ruta exacta del módulo y del DEEP (si aplica).
4) Si el DEEP no tiene `00_INDEX.md`, crearlo primero.
5) Crear/editar bloques numerados 10/20/30… (no 1/2/3).
6) Cada bloque incluye: objetivo, gates, checklist, registro mínimo, puentes (no duplicar).
7) Al cerrar un bloque: actualizar `DEEP/00_INDEX.md` (micro-navegación).
8) Si se tocó estructura: actualizar `CONTRATO_ESTRUCTURA.md` antes de seguir.
9) Ejecutar `git status` y revisar que solo cambió lo esperado.
10) Publicar y validar navegación en GitHub Pages (solo al final).


volvemos
URL: https://zumajuano-byte.github.io/quelonio-pages/

OBJETIVO ACTUAL
- Profundizar Biblia con bibliografía, sin inconsistencias de estructura entre sesiones.

REGLAS CANÓNICAS (NO NEGOCIABLES)
1) Leer y respetar:
   - docs/99_Indice_y_Mapas/CONTRATO_ESTRUCTURA.md
   - docs/99_Indice_y_Mapas/CHECKLIST_SESION_CONSTRUCCION.md
2) DEEP estándar:
   - DEEP/00_INDEX.md + bloques 10/20/30/40…
   - Los v1 monolíticos quedan como “Legacy (no tocar)”
3) Links relativos:
   - misma carpeta: Archivo.md
   - carpeta hija: Carpeta/Archivo.md
   - subir nivel: ../Archivo.md
4) Anti-duplicación (ownership):
   - 03_Levadura = biología/gestión de levadura (pitch/oxígeno/repitch/floculación).
   - 07_Fermentacion_Maduracion = control end-to-end del proceso (curva, rampas, gates, transfers, cold crash, salida a empaque).
   - 06_Procesos_QA_QC = sistema QA/QC (CCP, límites, auditoría, metrología).
   - 09_Empaque_Estabilidad = empaque y vida útil (purga, DO/TPO, priming, storage, shelf-life).

ESTADO HECHO (EN ESTA RONDA)
- 03_Levadura/Fermentacion_DEEP: bloques 01–07 + 00_INDEX.md (ya creado).
- 07_Fermentacion_Maduracion/DEEP:
  - creado 00_INDEX.md (canónico) + bloques:
    - 10_Targets_y_control_minimo.md
    - 20_Curva_termica_y_diacetilo.md
    - 30_Transferencias_cold_crash_y_salida.md
    - 40_Troubleshooting_proceso.md
  - link desde 07_Fermentacion_Maduracion.md a DEEP/00_INDEX.md
- 09_Empaque_Estabilidad/DEEP:
  - creado 00_INDEX.md (canónico) + bloques:
    - 10_Priming_y_carbonatacion_en_botella.md
    - 20_Control_oxigeno_DO_TPO.md
    - 30_Luz_temperatura_almacenamiento.md
    - 40_Shelflife_y_troubleshooting_empaque.md
  - link desde 09_Empaque_Estabilidad.md a DEEP/00_INDEX.md
- Creado:
  - docs/99_Indice_y_Mapas/CONTRATO_ESTRUCTURA.md
  - docs/99_Indice_y_Mapas/CHECKLIST_SESION_CONSTRUCCION.md

PRÓXIMO PASO PROPUESTO
- Elegir siguiente módulo a profundizar con el mismo estándar (mi sugerencia: 06_Procesos_QA_QC o 04_Lupulo/05_IPA_Moderna según prioridades).
- Trabajar siempre “paso a paso”: crear 00_INDEX.md → crear bloque 10 → micro-navegación → siguiente bloque.
