# START HERE — Quelonio (Orden de arranque)

Este sitio es la “pantalla de inicio” de Quelonio: una base de conocimiento y panel de trabajo para decidir qué hacemos en cada sesión.

## Cómo se usa (en 30 segundos)
1) Vos me pasás: **“volvemos” + URL del sitio**.
2) Yo leo esta página y luego abro el **LAUNCHER** (selector de proyectos).
3) Te ofrezco 3 caminos: **Continuar / Nuevo / Temporal**.
4) Trabajamos 1 paso por vez.
5) Cerramos con un **Checkpoint** (para retomar sin perder contexto).

## Regla de MODO (importante)
- Si vos decís **“volvemos”**, continuamos con contexto como si ya conociéramos el proyecto y el historial.
- Si NO decís “volvemos”, tratamos la sesión como nueva (sin asumir contexto).

## Reglas de trabajo (no negociables)
- Si hay terminal/comandos: 1 comando por vez (copiar/pegar), esperamos salida, recién después el siguiente.
- Si hay opciones múltiples: se listan opciones y se marca una recomendación.
- Si hay riesgo de romper algo: plan de bajo riesgo (validación/rollback).
- Prioridad: acceso al contenido > estética.
- Si hay contradicción entre instrucciones: se define qué regla manda primero. 

## Qué significa cada término (lenguaje simple)
- **Build estricto**: una “prueba de seguridad” para confirmar que el sitio arma y que los links no están rotos.
- **Deploy**: publicar los cambios para que se vean en la web.
- **Links relativos**: links “por carpetas”. Ojo: desde `99_Indice_y_Mapas/` muchas veces hay que usar `../` para salir de esa carpeta.
- **DEEP**: contenido profundo/extendido. No hace falta que esté todo en el menú; lo importante es que sea accesible por índices.

## Reglas del proyecto Biblia (estabilidad primero)
- La estructura actual es estable y no debe romperse.
- Links en Markdown estándar (no Obsidian `[[ ]]`).
- Links siempre con `/` (no usar `\`).
- Si algo ya funciona, no se toca sin razón.

## Publicación (checklist rápido)
Si hicimos cambios en la Biblia (MkDocs):
1) `git status`
2) `python -m mkdocs build --strict`
3) `git add -A` → `git commit -m "docs: ..."` → `git push`
4) Publicar: `python -m mkdocs gh-deploy --force`
5) Verificación rápida en la web: Inicio + módulo tocado

## ¿Qué vamos a hacer hoy?
Ir al LAUNCHER (selector de proyectos):
- [Abrir LAUNCHER](LAUNCHER.md)
