# PROYECTO — Biblia (Quelonio Pages)

Este archivo es el **estado vivo** del proyecto Biblia.
Regla: al cerrar una sesión de Biblia, **se reemplaza este archivo completo** (copiar/pegar).

Links de referencia:
- [START_HERE](START_HERE.md)
- [LAUNCHER](LAUNCHER.md)
- [SESSIONS_LOG (Regla de oro + histórico)](SESSIONS_LOG.md)

---

## CURRENT_STATE — Biblia (leer esto primero)

- last_updated: 2025-12-16
- project: Biblia (Quelonio Pages)
- mode_default: Continuar

### objective_now (1 frase)
Profundización v1 (estructura funcional end-to-end) — Specs → Fermentación/Maduración → Limpieza/Sanitización → Empaque/Estabilidad (+Log) → Sensorial/Liberación.

### next_3 (máx 3)
1) Iniciar “pasada 2” (BIBLIO): convertir HEURÍSTICAS a BIBLIO (libro→capítulo→sección/página), empezando por Fermentación/Maduración + Empaque/Estabilidad.
2) Definir formato canónico de cita y dejar **1 ejemplo** de “Matriz de afirmaciones” dentro de un DEEP.
3) Ejecutar 1 caso real end-to-end: Spec v1.0 + 1 lote (logs mínimos) + sensorial + ajuste de Spec.

### open_threads (máx 5)
- Auditoría de redundancias/solapamientos: definir qué es canónico vs “puentes”.
- Estandarizar formato de citas (plantilla simple) y ubicarla como norma.
- Gate mínimo de liberación (umbrales medibles) en QA/QC.

### truth_links (verdad vigente / stubs)
- 98 — Verdad de Negocio (Índice): `docs/98_Verdad_Negocio/98_Verdad_Negocio.md`
- Economía unitaria: `docs/98_Verdad_Negocio/01_Economia_Unitaria.md`
- Operaciones: `docs/98_Verdad_Negocio/02_Operaciones.md`
- Specs/Recetas: `docs/98_Verdad_Negocio/03_Specs_Recetas.md`
- QA/QC: `docs/98_Verdad_Negocio/04_QAQC.md`
- Branding/Comms: `docs/98_Verdad_Negocio/05_Branding_Comms.md`

---

## Checklist de publicación (canónico)
1) `git status`
2) `python -m mkdocs build --strict`
3) `git add -A` → `git commit -m "docs: update biblia <tema>"` → `git push`
4) `python -m mkdocs gh-deploy --force`
5) Verificación rápida web: Home + módulo tocado

---

## CHECKPOINT — Plantilla (copiar/pegar al cerrar sesión)

### Sesión: AAAA-MM-DD
- Objetivo (1 frase):
- Hecho (3–7 bullets):
  - 
  - 
- Archivos tocados (rutas):
  - 
- Resultado verificable:
  - build strict: OK/NO
  - deploy: OK/NO
- Pendientes inmediatos (máx 5):
  1)
  2)
  3)
- Próximo paso recomendado (1):
  - 
- Notas / decisiones:
  - 
