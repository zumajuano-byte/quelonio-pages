# START_HERE — Arranque operativo (canónico)

Este archivo define **cómo arrancamos una sesión** cuando volvés con la URL pública del sitio.

## Objetivo del arranque

1) Evitar interpretaciones o “métodos alternativos” no acordados.
2) Continuar el **proyecto activo** sin perder contexto.
3) Si falta contexto o pedís cambiar de frente, usar un **menú único** (LAUNCHER).

## Paso 0 — Verificación rápida (si estás en el repo local)

- `git status` debe estar limpio (o, si hay cambios, que sean los que vos acabás de hacer).
- El sitio público es: https://zumajuano-byte.github.io/quelonio-pages/

## Paso 1 — Leer estado (Source of Truth del progreso)

Abrir: [SESSIONS_LOG](SESSIONS_LOG.md)

Ahí está el bloque `CURRENT_STATE` (proyecto activo, último update, próximos pasos, etc.).

## Paso 2 — Regla de navegación (clave)

- Si `CURRENT_STATE.project_active` **está definido** y vos no pedís cambiar:
  - Continuamos **directo** ese proyecto (sin menú).
- Si `CURRENT_STATE.project_active` **no está definido**, o vos decís explícitamente que querés cambiar:
  - Abrimos el menú: [LAUNCHER](LAUNCHER.md)

## Paso 3 — Regla de oro (método acordado)

Antes de proponer o ejecutar cambios: leer y respetar “Regla de oro” en:

[SESSIONS_LOG · Regla de oro](SESSIONS_LOG.md#reglas-de-trabajo-persistentes--regla-de-oro)

## Release mínimo (cuando tocaste archivos)

> Importante: el deploy “oficial” es con `gh-deploy` (no cambiamos esto).

1) Validación local (opcional pero recomendado):
   - `python -m mkdocs build --strict`

2) Commit + push (si hay cambios):
   - `git add -A`
   - `git commit -m "..."`  
   - `git push`

3) Deploy a GitHub Pages:
   - `python -m mkdocs gh-deploy --force`

4) Verificar en la web:
   - Home carga
   - Navegación principal funciona
   - No hay links rotos evidentes (START_HERE / LAUNCHER / SESSIONS_LOG / CONTRATO_ESTRUCTURA)
