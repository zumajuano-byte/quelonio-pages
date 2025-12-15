# Sessions Log — Checkpoints

Este archivo cumple 3 funciones:
1) Arranque determinístico: permite retomar contexto sin depender del mensaje del usuario.
2) Bitácora: registra sesiones y resultados verificables.
3) Trazabilidad: registra cambios en la “verdad vigente” del negocio (definiciones, supuestos, números, decisiones).

---

## CURRENT_STATE (leer esto primero)

- last_updated: AAAA-MM-DD
- project_active: Biblia | Web+API | Latas
- mode_default: Continuar
- objective_now: (1 línea)
- next_3:
  1)
  2)
  3)
- open_threads (máx 5):
  - 
  - 
  - 
- pointers (links/rutas):
  - launcher_or_overview: (ruta/link interno)
  - last_session: AAAA-MM-DD
  - key_files_or_paths: (rutas/URLs relevantes)

Regla: si el usuario solo pega la URL, el asistente asume "Continuar" y toma el proyecto desde `project_active`.

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
