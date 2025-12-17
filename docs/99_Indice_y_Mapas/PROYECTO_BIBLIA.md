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

---

# CHECKPOINT (sesión de cierre)

**Fecha:** <<<2025/12/16>>>
**Objetivo de la sesión:** <<<ej: estabilizar Fermentación/Maduración + APB preflight>>>

## Estado técnico (APB)
- Preflight (`.\preflight.ps1`): OK
- Build strict (`python -m mkdocs build --strict`): OK
- Deploy (`python -m mkdocs gh-deploy --clean`): OK
- Sitio: https://zumajuano-byte.github.io/quelonio-pages/

## Referencias de versión (para no “perderse”)
- `main` (último commit): <<<18f1a02 (HEAD -> main, origin/main, origin/HEAD) docs: remove contentReference artifacts (preflight clean)>>>
- `gh-pages` (último deploy): <<<7b4fe15 (origin/gh-pages, gh-pages) Deployed 18f1a02 with MkDocs version: 1.6.1>>>

## Qué quedó hecho (resumen corto)
- <<<1-5 bullets concretos>>>

## Pendientes inmediatos (próximo bloque lógico)
1) <<<pendiente 1>>>
2) <<<pendiente 2>>>
3) <<<pendiente 3>>>

## Regla APB vigente
- No commitear ni deployar sin correr `.\preflight.ps1` y que dé **OK**.
- No tocar `SESSIONS_LOG.md` (solo se usa si explícitamente se decide en una sesión).


# CHECKLIST — Cierre de sesión (Biblia Quelonio)

## 1) Estado técnico (MkDocs/Git)
- [ ] `python -m mkdocs build --strict` → OK (“built”)
- [ ] `git status` → working tree clean
- [ ] Cambios subidos a `main` (último commit relevante: `5167d92`)
- [ ] Deploy a GitHub Pages ejecutado: `python -m mkdocs gh-deploy --clean`
- [ ] Sitio verificado online: Centro de Incidentes visible y navegable

## 2) Normalización de saltos de línea (Windows)
- [ ] `.gitattributes` creado y trackeado (`git ls-files .gitattributes` → OK)
- [ ] `git add -A` sin warnings LF/CRLF

## 3) Módulos cerrados en esta sesión
- [ ] 09 Empaque/Estabilidad: SOP + TP + troubleshooting + links OK
- [ ] 10 Limpieza/CIP: Manual v1 + TP + Kunze nivel 2 + links OK
- [ ] 11 Sensorial: Manual v1 + TP + puente a Spec/Receta + links OK
- [ ] 08 Recetas/Specs: ticket de mejora + puente con Sensorial + links OK
- [ ] 06 QA/QC: Centro de Incidentes + TP CAPA + TP Liberación de Lote + links OK
- [ ] 07 Fermentación/Maduración: TP por lote + hub operativo + links a 09/06 OK

## 4) Próximo paso (para retomar sin perder hilo)
- [ ] Continuar con **Módulo 03 — Levadura**
  - Archivos a abrir/subir:  
    - `docs/03_Levadura/03_Levadura.md`  
    - `docs/03_Levadura/DEEP/00_INDEX.md` (si existe)
  - Objetivo: dejar 03 “operable” como 07/09/10/11 (overview → DEEP → manual v1 → TP + puentes a 07 y 11)

## 5) Regla de arranque (cuando volvemos)
- [ ] Al iniciar nueva sesión: confirmar URL pública + abrir el módulo objetivo (03) antes de escribir contenido nuevo

