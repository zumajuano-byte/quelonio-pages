# PROYECTO — Biblia (Quelonio Pages)

Este archivo es el **estado vivo** del proyecto Biblia.
Regla: al cerrar una sesión de Biblia, **se reemplaza este archivo completo** (copiar/pegar).

Links de referencia:
- [START_HERE](START_HERE.md)
- [LAUNCHER](LAUNCHER.md)
- [SESSIONS_LOG (Regla de oro + histórico)](SESSIONS_LOG.md)

---

## CURRENT_STATE — Biblia (leer esto primero)

- last_updated: 2025-12-18
- project: Biblia (Quelonio Pages)
- mode_default: Consolidación + Publicación

### objective_now (1 frase)
Consolidar módulos **07/09/11** como “cerrados operables”, dejar el **plan de trabajo inmediato** escrito, y **publicar** (commit + `gh-deploy`) sin deuda técnica.

### next_3 (máx 3)
1) **Cierre fino 11 (opcional, recomendado):**
   - En `docs/11_Sensorial/11_Sensorial.md`: agregar link a `DEEP/20_Pasar_Sensorial_a_Spec_y_Receta.md` y un **Gate sensorial** (Liberar / Retener / Investigar).
   - En `docs/11_Sensorial/DEEP/00_INDEX.md`: sumar puentes directos a **07 (troubleshooting)** y **10 (limpieza)**.
2) **Consolidación transversal (pasada corta):** revisar puentes/rutas entre **06/08/09/10/11** (consistencia, no duplicación) y dejar una lista de “canónicos vs puentes”.
3) **Publicar a GitHub Pages:** correr preflight/build, commitear a `main`, ejecutar `python -m mkdocs gh-deploy --clean`, verificar sitio online y registrar hashes (main + gh-pages) abajo.

### open_threads (máx 5)
- Auditoría de redundancias/solapamientos: definir qué es canónico vs “puentes”.
- Estandarizar formato de citas (plantilla simple) y ubicarla como norma.
- Gate mínimo de liberación (umbrales medibles) en QA/QC (incluye DO/TPO/CO₂ donde aplique).
- Pasada 2 (BIBLIO): convertir heurísticas clave a bibliografía, empezando por 07 + 09.

### truth_links (verdad vigente / stubs)
- 98 — Verdad de Negocio (Índice): `docs/98_Verdad_Negocio/98_Verdad_Negocio.md`
- Economía unitaria: `docs/98_Verdad_Negocio/01_Economia_Unitaria.md`
- Operaciones: `docs/98_Verdad_Negocio/02_Operaciones.md`
- Specs/Recetas: `docs/98_Verdad_Negocio/03_Specs_Recetas.md`
- QA/QC: `docs/98_Verdad_Negocio/04_QAQC.md`
- Branding/Comms: `docs/98_Verdad_Negocio/05_Branding_Comms.md`

---

## Estado técnico (APB)
- Preflight (`.\preflight.ps1`): POR CORRER (antes de commitear/deployar)
- Build strict (`python -m mkdocs build --strict`): OK (última corrida: 2025-12-18)
- Deploy (`python -m mkdocs gh-deploy --clean`): PENDIENTE (después del commit)
- Sitio: https://zumajuano-byte.github.io/quelonio-pages/

## Referencias de versión (para no “perderse”)
Completar estos dos renglones **después de publicar**:

- `main` (último commit): ejecutar `git log -1 --oneline`
- `gh-pages` (último deploy): ejecutar `git log -1 --oneline gh-pages`

## Qué quedó hecho (resumen corto)
- **07 Fermentación/Maduración**: cerrado operable (gates + TP + troubleshooting) y limpieza de `status:draft` → `active`.
- **07**: corrección de encoding/“mojibake” (ya no aparecen `Ã`, `â`, `Â` en textos).
- **09 Empaque/Estabilidad**: auditado sin flags `draft/placeholder/pendiente`; estructura operable confirmada.
- **11 Sensorial**: hub + DEEP index + manual v1 + TP + “pasar sensorial a spec/receta”; checks OK.

## Pendientes inmediatos (próximo bloque lógico)
1) Aplicar **cierre fino** en 11 (hub + puentes) y confirmar `python -m mkdocs build --strict` limpio.
2) Correr `.\preflight.ps1` y asegurar **OK**.
3) Publicar (commit + deploy) siguiendo el runbook de abajo.

---

## RUNBOOK — Publicar (Windows / PowerShell)

1) Verificar build (ya viene OK, pero repetir si hubo cambios):
   - `python -m mkdocs build --strict`

2) Ver estado git y commitear:
   - `git status`
   - `git add -A`
   - `git commit -m "docs: close modules 07-09-11 + consolidation"`
   - `git push origin main`

3) Deploy GitHub Pages:
   - `python -m mkdocs gh-deploy --clean`

4) Verificación post-deploy:
   - Abrir sitio y chequear navegación (07 → 09 → 11 y vuelta a 06/10)
   - Registrar hashes:
     - `git log -1 --oneline`
     - `git log -1 --oneline gh-pages`

---

## Regla APB vigente
- No commitear ni deployar sin correr `.\preflight.ps1` y que dé **OK**.
- No tocar `SESSIONS_LOG.md` (solo se usa si explícitamente se decide en una sesión).

# CHECKLIST — Cierre de sesión (Biblia Quelonio)

## 1) Estado técnico (MkDocs/Git)
- [ ] `python -m mkdocs build --strict` → OK (“built”)
- [ ] `git status` → working tree clean
- [ ] `git log -1 --oneline` copiado en “Referencias de versión”
- [ ] Deploy a GitHub Pages ejecutado: `python -m mkdocs gh-deploy --clean`
- [ ] `git log -1 --oneline gh-pages` copiado en “Referencias de versión”
- [ ] Sitio verificado online: navegación y links críticos OK

## 2) Normalización de saltos de línea (Windows)
- [ ] `.gitattributes` creado y trackeado (`git ls-files .gitattributes` → OK)
- [ ] `git add -A` sin warnings LF/CRLF

## 3) Módulos cerrados en esta sesión
- [x] 07 Fermentación/Maduración: TP + gates + troubleshooting + links OK
- [x] 09 Empaque/Estabilidad: SOP + TP + troubleshooting + links OK
- [x] 11 Sensorial: Manual v1 + TP + puente a Spec/Receta + links OK
- [ ] 10 Limpieza/CIP: (ya cerrado previamente; no tocado en esta sesión)

## 4) Próximo paso (para retomar sin perder hilo)
- [ ] Publicar (commit + gh-deploy) y registrar hashes en esta biblia.
- [ ] Continuar con **Módulo 03 — Levadura**
  - Archivos a abrir/subir:
    - `docs/03_Levadura/03_Levadura.md`
    - `docs/03_Levadura/DEEP/00_INDEX.md` (si existe)
  - Objetivo: dejar 03 “operable” como 07/09/10/11 (overview → DEEP → manual v1 → TP + puentes a 07 y 11)

## 5) Regla de arranque (cuando volvemos)
- [ ] Al iniciar nueva sesión: confirmar URL pública + abrir el módulo objetivo (03) antes de escribir contenido nuevo
