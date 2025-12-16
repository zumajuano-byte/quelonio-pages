# LAUNCHER — Selector de proyectos

## METHOD LOCK

Para GitHub Pages de este repo: **publicar = `python -m mkdocs gh-deploy --force` (canónico)**.  
No mezclar con otros métodos.

## Orden de arranque (importante)

- Primero se lee: **START_HERE** (reglas del sistema).
- Segundo se lee: **SESSIONS_LOG**, se toma `CURRENT_STATE` y se continúa automático.
- Este **LAUNCHER** se usa SOLO si:
  1) `CURRENT_STATE` está vacío/incompleto, o
  2) el usuario pide explícitamente cambiar de proyecto, crear uno nuevo, o trabajar temporal.

Links directos (sin rutas raras):
- [START_HERE](START_HERE.md)
- [SESSIONS_LOG](SESSIONS_LOG.md)
- [CONTRATO_ESTRUCTURA](CONTRATO_ESTRUCTURA.md)

---

## Contrato de dependencia — Biblia como “Source of Truth” para otros proyectos

La **Biblia (Quelonio Pages)** es el sistema de referencia vigente para:

### A) Web + API (MVP)
- Consume definiciones canónicas de: **specs, procesos, QA/QC, nomenclaturas**.
- Web/API **no inventa** definiciones: si falta una definición, se registra como pendiente y se promueve a Pages.

### B) Latas (Quelonio Brew)
- Consume definiciones canónicas de: **branding/comms, mínimos de etiqueta, claims permitidos, estructura de línea**.
- La creatividad (frases por lote) vive en “Latas”, pero los **criterios** viven en Pages.

### Regla de promoción (temporal → permanente)
Si en Web+API o Latas aparece una decisión que debería quedar como verdad vigente:
1) Se documenta en el proyecto de trabajo (Web+API o Latas).
2) Se promueve a Pages (98_Verdad_Negocio o módulo técnico) con:
   - Qué queda vigente
   - Dónde quedó escrito (ruta/link)
   - Fuente (medición, planilla, cálculo, etc.)
   - Impacto/riesgo

---

Elegí un modo:

## A) Continuar (si ya hay proyecto en curso)

- Por defecto: continuar el proyecto indicado en `SESSIONS_LOG > CURRENT_STATE.project_active` (sin menú).
- Al final: generar Checkpoint.

## B) Nuevo (elegir 1 proyecto)

### 1) Biblia (Quelonio Pages)

Propósito: seguir ampliando la Biblia Cervecera sin romper navegación ni estructura.

Arranque mínimo (hoy):
1) Decir qué módulo se trabaja (ej. Fermentación, Recetas, Empaque, etc.).
2) Si hay cambios: correr build estricto y publicar.

Checklist de release:
- `git status`
- `python -m mkdocs build --strict`
- `git add -A` → `git commit -m "docs: update <módulo>"` → `git push`
- `python -m mkdocs gh-deploy --force`

Reglas clave:
- Guiado paso a paso.
- Diagnosticar antes de cambiar.
- Si funciona, no se toca.
- No cambiar estructura/rutas sin avisar explícitamente.

Estado base:
- Sitio publicado y navegable.
- Se trabaja sobre `quelonio-pages/docs/`.

#### Entorno y versiones (Biblia / Quelonio Pages) — Baseline

- Sistema: Windows (PC local)
- Terminal: Windows PowerShell 5.1 (Build 26100.7462)
- Python: 3.14.0
- Pip: 25.3
- MkDocs: 1.6.1
- Theme: mkdocs-material 9.7.0
- Plugins / extensiones:
  - mkdocs-roamlinks-plugin 0.3.2
- Paquetes MkDocs relacionados:
  - mkdocs-get-deps 0.2.0
  - mkdocs-material-extensions 1.3.1
- Git: 2.52.0.windows.1

Baseline confirmado: 2025-12-14  
Regla de estabilidad: si algo deja de funcionar, primero comparar contra este baseline (versiones) antes de cambiar estructura o comandos.

Publicación: para que los cambios se vean en la web se usa: `python -m mkdocs gh-deploy --force`

---

### 2) Web + API (MVP)

Propósito: estabilizar “quelonio-web-mvp” + “quelonio-api” con persistencia real y endpoints verificables (UI después).

Arranque mínimo (diagnóstico):
1) Confirmar carpeta exacta (PowerShell prompt).
2) `git status` en web y api (si son repos separados).
3) Confirmar qué está corriendo: API sí/no + comando; WEB sí/no + comando.
4) Probar conectividad: web carga o queda blanco; probar 1 endpoint en navegador o Thunder.
5) Si falla: pegar error textual completo + URL + comando ejecutado.

Puertos esperados:
- API: `http://localhost:4000`
- Web: `http://localhost:5173`

Criterio de “listo por hoy”:
- API + Web levantadas al mismo tiempo.
- No pantallas en blanco.
- 1 flujo CRUD mínimo que crea → lista → persiste.

---

### 3) Latas (Quelonio Brew — concepto congelado)

Propósito: mantener coherente el concepto de línea premium y preparar criterios para escalar (sin recetas, sin diseño final todavía).

Posicionamiento:
“Especialistas en combustibles espirituales y lubricantes sociales”.

Arquitectura de etiqueta:
- Marca fija: Quelonio Brew.
- Combustible espiritual: frase breve variable por lote/edición (headline).
- Tortuga temática: icono/arquetipo según el tono (set finito).
- Lubricante social: estilo + datos técnicos mínimos (ABV, etc.) + notas sensoriales simples.

Reglas:
- Frases legibles y claras, con filo.
- Sin claims de salud.

---

## C) Temporal (consulta puntual)

Para consejos rápidos (ej. mejorar receta de un colega, diagnóstico sensorial, ajustes de proceso).
Salida esperada:
- Recomendación accionable en pasos.
- Si vale la pena guardarlo, se mueve a uno de los 3 proyectos principales.
