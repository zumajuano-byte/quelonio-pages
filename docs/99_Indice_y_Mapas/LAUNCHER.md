# LAUNCHER — Selector de proyectos

Elegí un modo:

## A) Continuar (si ya hay proyecto en curso)
- Continuar el último proyecto trabajado y aplicar su checklist de arranque.
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

**Regla de estabilidad:** si algo deja de funcionar, primero comparar contra este baseline (versiones) antes de cambiar estructura o comandos.

**Publicación:** para que los cambios se vean en la web se usa:
`python -m mkdocs gh-deploy --force`


---

### 2) Web + API (MVP)
Propósito: estabilizar el stack “quelonio-web-mvp” + “quelonio-api” con persistencia real y endpoints verificables (UI después).

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



