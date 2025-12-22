# PROYECTO — Biblia (Quelonio Pages)

Este archivo es el **estado vivo** del proyecto Biblia.  
Regla: al cerrar una sesión de Biblia, **se reemplaza este archivo completo** (copiar/pegar).

Links de referencia:
- [START_HERE](START_HERE.md)
- [LAUNCHER](LAUNCHER.md)
- [SESSIONS_LOG (Regla de oro + histórico)](SESSIONS_LOG.md)
- [PROYECTO_WEB_API (Quelonio Brew OS)](PROYECTO_WEB_API.md)

---

## CURRENT_STATE — Biblia (leer esto primero)

- last_updated: 2025-12-22
- project: Biblia (Quelonio Pages)
- mode_default: Operación + Iteración (post-publicación)

### objective_now (1 frase)
Mantener la Biblia “deployable sin deuda” (preflight OK siempre) y consolidar la **Pasada 2 (BIBLIO)** en 07+09 con formato canónico + ejemplos visibles, dejando trazabilidad lista para completar citas reales (cap/sección/página).

### next_3 (máx 3)
1) **Pasada 2 (BIBLIO) — Completar citas reales:** llenar “capítulo/sección/página” en BIBLIO de 07/20, 07/30 y 09/20 (mínimo 3–5 afirmaciones por doc).
2) **Extender BIBLIO a heurísticas de estabilidad/shelf-life:** sumar 1–2 docs DEEP adicionales (p.ej. shelf-life, carbonatación/CO2, DO/TPO operativo) con el mismo patrón.
3) **1 caso real end-to-end:** Spec v1.0 + 1 lote (logs mínimos) + sensorial + ajuste de Spec (registrar loop en 11/DEEP/20).

### open_threads (máx 5)
- Auditoría de redundancias/solapamientos: definir qué es canónico vs “puentes”.
- Estandarizar “BIBLIO canónico” como norma transversal (dónde vive la plantilla madre).
- Gate mínimo de liberación (umbrales medibles) en QA/QC (incluye DO/TPO/CO2 donde aplique).
- Cierre fino 11 Sensorial (opcional): Gate “Liberar / Retener / Investigar” en overview + puentes a 07/10.
- Targets operativos por familia de estilos (agua/pH, pitch/O2/temp, dry hop, DO) como “tablas de referencia”.

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
- Windows: vigilar LF/CRLF (ver Runbook).

---

## Runbook — “limpieza técnica” (atajos)

### A) Mojibake / encoding raro en .md (Ã â€” Â, etc.)
1) Detectar:
   - `Select-String -Path .\docs\...\**\*.md -Pattern 'Ã|â€”|Â|�' -AllMatches`
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

### D) PowerShell: no usar `&&`
En PowerShell, ejecutar comandos en líneas separadas o con `;` (no `&&`).

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

**Fecha:** 2025-12-22  
**Objetivo de la sesión:** Consolidar Pasada 2 (BIBLIO) inicial en 07+09 y publicar sin deuda (build strict + deploy OK).

## Estado técnico (APB)
- Preflight (`.\preflight.ps1`): OK  
- Build strict (`python -m mkdocs build --strict`): OK  
- Deploy (`python -m mkdocs gh-deploy --clean`): OK  
- Sitio: https://zumajuano-byte.github.io/quelonio-pages/

## Referencias de versión (para no “perderse”)
- `main` (commit): `558cf18 docs: fix 07/30 encoding and add BIBLIO blocks in 07/20 and 09/20`
- `gh-pages` (deploy): `7ab5093` (último push por `mkdocs gh-deploy`)

## Qué quedó hecho (resumen corto)
- Se incorporó/ajustó BIBLIO como base operativa en 07/20 y 09/20 (plantilla + afirmaciones).
- Se corrigió 07/30 (encoding/estandarización) y se validó publicación completa.
- Pipeline PowerShell confirmado: commit/push en `main` + build strict + deploy limpio.

## Pendientes inmediatos (próximo bloque lógico)
1) Completar citas reales (capítulo/sección/página) en los BIBLIO ya creados (07/20, 07/30, 09/20).
2) Extender BIBLIO a 1–2 docs DEEP adicionales (shelf-life y/o CO2/estabilidad).
3) Ejecutar 1 caso real end-to-end (Spec → lote → logs → sensorial → ajuste de Spec) y registrarlo como patrón.

## Regla APB vigente
- No commitear ni deployar sin correr `.\preflight.ps1` y que dé **OK**.
- No tocar `SESSIONS_LOG.md` (solo si se decide explícitamente en una sesión).
