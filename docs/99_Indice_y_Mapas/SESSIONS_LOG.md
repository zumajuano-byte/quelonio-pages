# SESSIONS_LOG — Bitácora global (Quelonio)

Este archivo **no** es el “estado vivo” de ningún proyecto.  
El estado vivo está en `PROYECTO_*.md` (uno por proyecto).

## Archivos canónicos (OS Boot)

- `99_Indice_y_Mapas/START_HERE.md`
- `99_Indice_y_Mapas/LAUNCHER.md`
- `99_Indice_y_Mapas/CONTRATO_ESTRUCTURA.md`
- `99_Indice_y_Mapas/PROYECTO_BIBLIA.md`
- `99_Indice_y_Mapas/PROYECTO_WEB_API.md`
- `99_Indice_y_Mapas/PROYECTO_LATAS.md`

## Reglas globales (resumen)

- La sesión debe operar siempre desde el **CURRENT_STATE del proyecto**.
- Cierre: actualizar **solo** el `PROYECTO_*.md` del proyecto trabajado (evitar tocar muchos archivos).
- Antes de deploy: `mkdocs build --strict`.

---

## Bitácora (opcional)

> Usar solo si querés histórico transversal.  
> Si preferís “cero fricción”, logueá dentro de cada `PROYECTO_*.md`.

### Plantilla
**Fecha:** YYYY-MM-DD  
**Proyecto:** Biblia | Web+API | Latas  
**Qué se hizo (bullet points):**
- ...
**Qué quedó abierto:**
- ...
**Próximo paso (1):**
- ...
**Release:** build --strict OK / deploy OK / commit SHA
