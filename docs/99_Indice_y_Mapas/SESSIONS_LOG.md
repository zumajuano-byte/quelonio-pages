# SESSIONS_LOG — Quelonio Pages (MkDocs)

CURRENT_STATE:
  last_update: 2025-12-16
  project_active: quelonio-pages (biblia/mkdocs)
  last_commit_note: "Se arregló mkdocs.yml; se alineó LAUNCHER/START_HERE; se estabilizó el deploy a gh-pages."
  key_files_or_paths:
    - docs/99_Indice_y_Mapas/START_HERE.md
    - docs/99_Indice_y_Mapas/LAUNCHER.md
    - docs/99_Indice_y_Mapas/SESSIONS_LOG.md
    - docs/99_Indice_y_Mapas/CONTRATO_ESTRUCTURA.md
    - mkdocs.yml

  next_3:
    - "1) Release mínimo (validación + deploy + chequeo web)."
    - "2) Validar en web el arranque canónico: continuar directo si `project_active` está definido; mostrar LAUNCHER solo como fallback (si falta estado o si el usuario pide cambiar)."
    - "3) Continuar con Profundización (Fermentación/Maduración → Empaque/Estabilidad → Limpieza/Sanitización → Sensorial → Recetas/Specs)."

---

<a id="reglas-de-trabajo-persistentes--regla-de-oro"></a>

## REGLAS DE TRABAJO (PERSISTENTES) — “Regla de oro”

- **No inventar método**: si existe un método acordado en START_HERE/LAUNCHER/CONTRATO, se respeta.
- **Siempre anclar en archivos canónicos**: START_HERE → SESSIONS_LOG → LAUNCHER → CONTRATO.
- **Evitar micro-cambios dispersos**: si un cambio es estructural, se reescribe el archivo completo y se pega completo.
- **Deploy canónico**: `python -m mkdocs gh-deploy --force` (y opcionalmente `python -m mkdocs build --strict` como validación previa).

---

## HISTORIAL (alto nivel)

### 2025-12-16 — Estabilización del sitio y del método de arranque
- Se consolidó el arranque operativo y el deploy a GitHub Pages.
- Se alineó el criterio: continuar por `project_active` y usar LAUNCHER solo como fallback.
- Se revisó mkdocs.yml y navegación para minimizar fricción.

