# Sessions Log — Checkpoints

Este archivo cumple 3 funciones:
1) Arranque determinístico: permite retomar sin depender del mensaje del usuario.
2) Bitácora: registra sesiones y resultados verificables.
3) Trazabilidad: registra cambios en la “verdad vigente” del negocio (definiciones, supuestos, números, decisiones).

---
<a id="reglas-de-trabajo-persistentes--regla-de-oro"></a>
## REGLAS DE TRABAJO (PERSISTENTES) — “Regla de oro”
Objetivo: evitar ambigüedad entre “bibliografía” y “heurística operativa” durante la profundización.

### Clasificación obligatoria de contenido
- **(BIBLIO)**: afirmaciones/decisiones respaldadas por bibliografía (referencia: libro → capítulo → sección/página).
- **(HEURÍSTICA OPERATIVA | PENDIENTE_BIBLIO)**: prácticas operativas útiles aún no ancladas a bibliografía dentro del vault.

### Regla principal
- **Ninguna HEURÍSTICA puede presentarse como BIBLIO.**  
  Si no está citada, debe quedar rotulada como **(HEURÍSTICA OPERATIVA | PENDIENTE_BIBLIO)**.

### Regla de arranque (boot determinístico)
Cuando el usuario pegue `volvemos + URL`:
1) Leer `START_HERE` completo.
2) Abrir `SESSIONS_LOG` y trabajar **solo desde `CURRENT_STATE`**.
3) Usar `LAUNCHER` solo para comandos/protocolo (publicación/validación) o fallback.
4) Si hay duda, **gana el método canónico del LAUNCHER**.

---

## CURRENT_STATE (leer esto primero)
- last_updated: 2025-12-15
- project_active: Biblia
- mode_default: Continuar
- objective_now: Profundización v1 (estructura funcional end-to-end) — Hoy se cerró normalización de entrypoints + arranque definitivo
- next_3:
  1) Verificar build strict + deploy (cero warnings) y validar navegación/links DEEP en web (entradas canónicas `00_INDEX.md`)
  2) Publicar cambios de arranque definitivo (START_HERE + LAUNCHER + SESSIONS_LOG) y validar en web que el arranque muestra LAUNCHER siempre
  3) Iniciar “pasada 2” de anclaje bibliográfico: convertir HEURÍSTICAS a BIBLIO (refs libro→capítulo→sección/página)
- open_threads (máx 5):
  - Auditoría de redundancias/solapamientos: definir qué es canónico vs “puentes” (ej. Empaque en QA/QC vs Módulo 09)
  - Anclaje bibliográfico: definir formato de cita y ubicación de referencias por módulo
  - Completar tolerancias iniciales del Spec (OG/FG/ABV/CO2/pH) con datos y/o bibliografía
  - Definir umbrales de liberación por estilo (QA/QC mínimo viable)
  - Consolidar mapa de navegación (Índice total / Mapa general / links canónicos)

---

## CHECKPOINTS (historial por sesión)

### 2025-12-15 — Arranque definitivo + normalización entrypoints (publicado)
- resultado: navegación en home + módulos base OK
- notas:
  - Se corrigieron inconsistencias de links y entrypoints (índices y mapas).
  - Se acordó mantener “DEEP v1” como baseline y migrar hacia `00_INDEX + bloques 10/20/30/40`.
- pointers (links/rutas):
  - launcher_or_overview: ./LAUNCHER.md
  - last_session: 2025-12-15
  - key_files_or_paths:
    - docs/99_Indice_y_Mapas/START_HERE.md
    - docs/99_Indice_y_Mapas/LAUNCHER.md
    - docs/99_Indice_y_Mapas/SESSIONS_LOG.md
    - docs/99_Indice_y_Mapas/CONTRATO_ESTRUCTURA.md
    - docs/99_Indice_y_Mapas/CHECKLIST_SESION_CONSTRUCCION.md
    - docs/08_Recetas_Formulacion/DEEP/00_INDEX.md
    - docs/08_Recetas_Formulacion/DEEP/01_DEEP_Recetas_Specs_v1.md
    - docs/07_Fermentacion_Maduracion/DEEP/00_INDEX.md
    - docs/07_Fermentacion_Maduracion/DEEP/01_DEEP_Fermentacion_Maduracion_v1.md
    - docs/09_Empaque_Estabilidad/DEEP/00_INDEX.md
    - docs/09_Empaque_Estabilidad/DEEP/01_DEEP_Empaque_Estabilidad_v1.md
    - docs/10_Limpieza_Sanitizacion/DEEP/00_INDEX.md
    - docs/10_Limpieza_Sanitizacion/DEEP/01_DEEP_Limpieza_Sanitizacion_v1.md
    - docs/11_Sensorial/DEEP/00_INDEX.md
    - docs/11_Sensorial/DEEP/01_DEEP_Sensorial_v1.md

---

## PLANTILLA — Nueva sesión (copiar/pegar y completar)

### YYYY-MM-DD — <título corto verificable>
- objetivo:
- cambios (archivos tocados):
- verificación:
  - build strict:
  - deploy:
  - validación web:
- pendientes:
- notas:
