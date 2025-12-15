# Sessions Log — Checkpoints

Este archivo cumple 3 funciones:
1) Arranque determinístico: permite retomar contexto sin depender del mensaje del usuario.
2) Bitácora: registra sesiones y resultados verificables.
3) Trazabilidad: registra cambios en la “verdad vigente” del negocio (definiciones, supuestos, números, decisiones).

---

## CURRENT_STATE (leer esto primero)

- last_updated: 2025-12-15
- project_active: Biblia
- mode_default: Continuar
- objective_now: Consolidar OS Boot v1 (arranque determinístico + verdad de negocio) y validar retoma sin literalidad
- next_3:
  1) Actualizar START_HERE para que el orden sea START_HERE → SESSIONS_LOG → LAUNCHER (solo fallback)
  2) Actualizar LAUNCHER para que “Continuar” use CURRENT_STATE por defecto
  3) Registrar primera sesión real (con “Actualizaciones de Verdad” si aplica) y completar BUSINESS_TRUTH_STATUS

- open_threads (máx 5):
  - START_HERE aún apunta a LAUNCHER como paso 2
  - LAUNCHER aún no declara “fallback por CURRENT_STATE”
  - Definir truth_links canónicos por proyecto (negocio)
  - Revisar “Inicializando búsqueda” si queda colgado
  - (vacío)

- pointers (links/rutas):
  - launcher_or_overview: ../LAUNCHER/
  - last_session: 2025-12-15
  - key_files_or_paths: docs/99_Indice_y_Mapas/START_HERE.md; docs/99_Indice_y_Mapas/SESSIONS_LOG.md; docs/99_Indice_y_Mapas/LAUNCHER.md

---

## BUSINESS_TRUTH (verdad vigente del negocio)

Quelonio Pages es la fuente de verdad para:
- Definiciones operativas (qué significa cada KPI, estándar, proceso).
- Supuestos vigentes (costos, capacidades, restricciones, pricing, objetivos).
- Decisiones aprobadas y su justificación.
- Valores “vigentes” (aunque el cálculo viva en planillas o fuentes externas).

Regla de trazabilidad:
- Todo cambio relevante de verdad debe dejar:
  1) Qué queda vigente (en texto)
  2) Dónde quedó escrito (ruta/link)
  3) Fuente (medición / planilla / cotización / cálculo / KB)

Estado (marcar):
- unit_economics_status: vigente | en revisión
- ops_process_status: vigente | en revisión
- recipes_specs_status: vigente | en revisión
- qa_qc_status: vigente | en revisión
- branding_comms_status: vigente | en revisión
- last_truth_update: AAAA-MM-DD
- truth_links (dónde vive lo vigente):
  - Economía unitaria: (ruta/link)
  - Operaciones y procesos: (ruta/link)
  - Especificaciones recetas: (ruta/link)
  - QA/QC: (ruta/link)
  - Branding/comms: (ruta/link)

---

## Plantilla (copiar/pegar por sesión)

### Sesión: AAAA-MM-DD
- Modo: Continuar / Nuevo / Temporal
- Proyecto: Biblia / Web+API / Latas / Temporal
- Objetivo de la sesión (1 frase):

- Hecho (3–7 bullets):
  - 
  - 
  - 

- Archivos tocados (rutas):
  - 

- Resultado verificable (ej. build strict OK / deploy OK / endpoint OK):
  - 

- Pendientes inmediatos (máx 5):
  1)
  2)
  3)
  4)
  5)

- Próximo paso recomendado (1):
  - 

- Notas / decisiones (si aplica):
  - 

- Actualizaciones de Verdad (si aplica; negocio):
  - Qué queda vigente:
  - Dónde quedó escrito (ruta/link):
  - Fuente (medición/planilla/cotización/cálculo/KB):
  - Impacto (costos, calidad, plazo, ventas, riesgo):

Regla “Temporal”:
- Si el modo es Temporal, no se registra aquí, salvo que el usuario diga explícitamente “promover a permanente”.
