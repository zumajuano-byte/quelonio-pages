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
- mode_default: Operación + Iteración (post-publicación)

### objective_now (1 frase)
Mantener la Biblia “deployable sin deuda” (preflight OK siempre) y arrancar la **Pasada 2 (BIBLIO)** en 07+09 con formato de cita canónico y 1 ejemplo completo.

### next_3 (máx 3)
1) **Pasada 2 (BIBLIO) — Sprint corto en 07 + 09:** convertir heurísticas clave a BIBLIO (libro → capítulo → sección/página) empezando por: curva térmica/diacetilo, O₂ en transferencias, DO/TPO en empaque, shelf-life.
2) **Gate y criterio canónico de cita (mínimo viable):** definir plantilla simple (1 bloque) y dejar **1 ejemplo completo** dentro de un DEEP (ideal: “Matriz de afirmaciones” con 3–5 items ya citados).
3) **1 caso real end-to-end:** Spec v1.0 + 1 lote (logs mínimos) + sensorial + ajuste de Spec (registrar el loop en 11/DEEP/20).

### open_threads (máx 5)
- Auditoría de redundancias/solapamientos: definir qué es canónico vs “puentes”.
- Estandarizar formato de citas (plantilla simple) y ubicarla como norma.
- Gate mínimo de liberación (umbrales medibles) en QA/QC (incluye DO/TPO/CO₂ donde aplique).
- Cierre fino 11 Sensorial (opcional): Gate “Liberar / Retener / Investigar” en overview + puentes a 07/10.
- Definir “targets operativos por familia de estilos” (agua/pH, pitch/O₂/temp, dry hop, DO).

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
4) `python -m mkdocs gh-deploy --clean`  
5) Verificación rápida web: Home + módulo tocado

Notas:
- Regla APB: **no deploy** si `.\preflight.ps1` no da OK.
- Si estás en Windows: vigilar LF/CRLF (ver “Runbook de line endings” abajo).

---

## Runbook — “limpieza técnica” (atajos)

### A) Mojibake / encoding raro en .md (Ã â€” Â, etc.)
1) Detectar:
   - `Select-String -Path .\docs\...\**\*.md -Pattern 'Ã|â€”|Â' -AllMatches`
2) Fix (re-interpretar ISO-8859-1 → UTF-8) sobre lista `$files`:
   - `$latin1 = [System.Text.Encoding]::GetEncoding(28591)`
   - `$utf8   = [System.Text.Encoding]::UTF8`
   - `foreach ($f in $files) { $content = Get-Content -LiteralPath $f -Raw; $fixed = $utf8.GetString($latin1.GetBytes($content)); Set-Content -LiteralPath $f -Value $fixed -Encoding utf8 }`
3) Revalidar con `Select-String` y correr `python -m mkdocs build --strict`.

### B) Restos “:contentReference[...]”
- Detectar:
  - `Select-String -Path .\docs\**\*.md -Pattern ":contentReference" -AllMatches`
- Limpiar: borrar esos tokens/líneas y re-correr `.\preflight.ps1`.

### C) Normalización LF (Windows)
1) `.gitattributes` (ejemplo mínimo):
   - `* text=auto eol=lf`
   - `*.ps1 text eol=lf`
2) Git:
   - `git config --global core.autocrlf false`
   - `git config --global core.eol lf`
3) Renormalizar:
   - `git add --renormalize .`
   - `git commit -m "chore: renormalize line endings"`

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
  - preflight: OK/NO
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

**Fecha:** 2025-12-18  
**Objetivo de la sesión:** Consolidación + limpieza técnica (encoding + contentReference + line endings LF) y publicación en GitHub Pages.

## Estado técnico (APB)
- Preflight (`.\preflight.ps1`): OK  
- Build strict (`python -m mkdocs build --strict`): OK  
- Deploy (`python -m mkdocs gh-deploy --clean`): OK  
- Sitio: https://zumajuano-byte.github.io/quelonio-pages/

## Referencias de versión (para no “perderse”)
- `main` (último commit): `e373346 chore: renormalize line endings`
- `gh-pages` (último deploy): `2400762 Deployed e373346 with MkDocs version: 1.6.1`

## Qué quedó hecho (resumen corto)
- Reparación de encoding mojibake (Ã/Â/â—) en docs relevantes; build vuelve a pasar en strict.
- Eliminación de artefactos `:contentReference[...]` detectados por preflight.
- Normalización de line endings (LF) en repo: `.gitattributes` + `core.autocrlf=false` + `core.eol=lf` + `--renormalize`.
- Publicación actualizada en GitHub Pages (gh-pages en sync con main).

## Pendientes inmediatos (próximo bloque lógico)
1) Pasada 2 (BIBLIO) en **07 Fermentación/Maduración** y **09 Empaque/Estabilidad** (3–5 citas completas mínimo).
2) Definir formato canónico de cita + 1 ejemplo dentro de un DEEP (incluye “Matriz de afirmaciones”).
3) Ejecutar 1 caso real end-to-end (Spec → lote → logs → sensorial → ajuste de Spec) y registrarlo como patrón.

## Regla APB vigente
- No commitear ni deployar sin correr `.\preflight.ps1` y que dé **OK**.
- No tocar `SESSIONS_LOG.md` (solo si se decide explícitamente en una sesión).
