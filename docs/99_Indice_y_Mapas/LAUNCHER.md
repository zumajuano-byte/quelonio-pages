# LAUNCHER — Selector de proyectos (Quelonio OS Boot)

Este archivo existe para que el arranque sea determinista y para seleccionar **1** proyecto activo
cuando el usuario lo pide explícitamente o cuando `CURRENT_STATE` está incompleto.

---

## METHOD LOCK (publicación de este repo)

Para GitHub Pages de este repo, **publicar =**:

`python -m mkdocs gh-deploy --force`

No mezclar con otros métodos. Si algo se rompe, se diagnostica primero (ver “Quality Gate”).

---

## Orden de arranque (si venís desde la URL pública)

1) Leer **START_HERE** (reglas del sistema)
2) Leer **SESSIONS_LOG** (tomar `CURRENT_STATE` y continuar)
3) Este **LAUNCHER** se usa SOLO si:
   - `CURRENT_STATE` está vacío/incompleto, o
   - el usuario pide explícitamente cambiar de proyecto / crear uno nuevo / modo temporal.

Links:
- [START_HERE](START_HERE.md)
- [SESSIONS_LOG](SESSIONS_LOG.md)
- [CONTRATO_ESTRUCTURA](CONTRATO_ESTRUCTURA.md)

---

## Contrato de dependencia: Biblia como “Source of Truth” para otros proyectos

La Biblia (Quelonio Pages) es el **sistema de referencia** para:

### A) Web + API (MVP)
- Debe consumir definiciones canónicas de: specs, procesos, QA/QC, nomenclaturas.
- La UI y la API **no inventan** definiciones: si falta una definición, se registra como *pendiente* y se promueve a Pages.

### B) Latas (Quelonio Brew)
- Debe consumir definiciones canónicas de: branding/comms, mínimos técnicos de etiqueta, claims permitidos, estructura de línea.
- La creatividad (frases/lotes) vive en el proyecto “Latas”, pero los **criterios** viven en Pages.

### Regla de promoción (muy importante)
Si en Web+API o Latas aparece una decisión que “debería quedar como verdad vigente”:
1) Se escribe primero en el proyecto de trabajo (Web+API o Latas).
2) Se promueve a Pages en **98_Verdad_Negocio** (o módulo técnico correspondiente) con:
   - Qué queda vigente
   - Dónde quedó escrito (link/ruta)
   - Fuente (planilla, cálculo, medición, conversación, etc.)
   - Impacto y riesgos

---

## Elegí un modo

### A) Continuar (default)
- Continuar el proyecto indicado en `SESSIONS_LOG > CURRENT_STATE.project_active`.
- Cierre: dejar “Resultado verificable” + “NEXT_3” actualizado en SESSIONS_LOG.

---

### B) Nuevo (elegir 1 proyecto)

#### 1) Biblia (Quelonio Pages)
**Propósito:** ampliar la Biblia sin romper navegación ni estructura.

**Arranque mínimo (hoy):**
1) Declarar módulo/tema (ej. Fermentación, Recetas, Empaque, etc.)
2) Especificar si es “Pasada 1 (scaffolding)” o “Pasada 2 (anclaje BIBLIO)”
3) Trabajar con índices `00_INDEX.md` como entrypoint canónico (para DEEP)

**Quality Gate (QA local):**
- `python -m mkdocs build --strict`

**Release (si hubo cambios):**
- `git status`
- `git add -A`
- `git commit -m "docs: update <módulo>"`
- `git push`
- `python -m mkdocs gh-deploy --force`

**Reglas clave:**
- Guiado paso a paso.
- Diagnosticar antes de cambiar.
- Si funciona, no se toca.
- No cambiar rutas/estructura sin avisar explícitamente.
- “DEEP existe” pero no necesariamente vive en el nav global (se navega desde índices).

**Baseline entorno (si algo falla, comparar antes de tocar estructura):**
- Sistema: Windows (PC local)
- Terminal: Windows PowerShell 5.1 (Build 26100.7462)
- Python: 3.14.0
- Pip: 25.3
- MkDocs: 1.6.1
- Theme: mkdocs-material 9.7.0
- Plugin: mkdocs-roamlinks-plugin 0.3.2
- Git: 2.52.0.windows.1
- Baseline confirmado: 2025-12-14

---

#### 2) Web + API (MVP)
**Propósito:** estabilizar “quelonio-web-mvp” + “quelonio-api” con persistencia real y endpoints verificables.

**Arranque mínimo (diagnóstico):**
1) Confirmar carpeta exacta (PowerShell prompt) para WEB y para API.
2) `git status` en ambos (si repos separados).
3) Confirmar qué está corriendo:
   - API sí/no + comando exacto
   - WEB sí/no + comando exacto
4) Probar conectividad:
   - Web: carga o queda blanco
   - API: 1 endpoint en navegador o Thunder
5) Si falla: pegar error textual completo + comando ejecutado + URL.

**Puertos esperados:**
- API: `http://localhost:4000`
- Web: `http://localhost:5173`

**Criterio “listo por hoy”:**
- API + Web levantadas al mismo tiempo.
- No pantallas en blanco.
- 1 flujo CRUD mínimo: crea → lista → persiste.

**Regla de alineación con Biblia:**
- Si aparece una definición ambigua (spec, KPI, naming), se registra y se promueve a Pages (Verdad de negocio / Specs).

---

#### 3) Latas (Quelonio Brew — concepto)
**Propósito:** mantener coherente el concepto de línea premium y preparar criterios para escalar.

**Posicionamiento:**
“Especialistas en combustibles espirituales y lubricantes sociales”.

**Arquitectura de etiqueta (canónica):**
- Marca fija: Quelonio Brew.
- Combustible espiritual: frase breve variable por lote/edición (headline).
- Tortuga temática: icono/arquetipo según el tono (set finito).
- Lubricante social: estilo + mínimos técnicos (ABV, etc.) + notas sensoriales simples.

**Reglas:**
- Frases legibles y claras, con filo.
- Sin claims de salud.
- Si se define un estándar (tipografía, layout, mínimos legales), se promueve a Pages (Branding/Comms).

---

### C) Temporal (consulta puntual)
Para consejos rápidos (ej. receta de un colega, diagnóstico sensorial, ajuste de proceso).

**Salida esperada:**
- Recomendación accionable en pasos.
- Si vale la pena guardarlo: “promover a permanente” → mover a Biblia / Web+API / Latas.
