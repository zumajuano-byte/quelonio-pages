# PROYECTO_WEB_API — Quelonio SaaS (Web App + API + DB)

**Última actualización:** 2025-12-22  
**Estado:** Sprint 1 en curso — Infra OK (PostgreSQL + Prisma + Next)  
**Regla de trabajo:** micro-pasos (1 paso por vez). Si un paso requiere admin, se aclara explícitamente.

---

## 0) Objetivo

Construir un **MVP tipo SaaS** para operación cervecera (recetas, lotes, stock, ventas, finanzas) + base para incorporar un **asistente IA** que responda en base a la Biblia (Quelonio Pages).

Arquitectura recomendada (MVP):
- **Next.js (App Router) + TypeScript**
- **PostgreSQL**
- **Prisma**
- Endpoints API dentro de Next (`app/api/*`)
- Más adelante: auth/RBAC, auditoría, exports, jobs/alertas

---

## 1) Repos / Ubicaciones

- **Repo Web App:** `C:\Users\flore\Documents\quelonio-saas`
- **Repo Biblia / Docs (GitHub Pages):** `C:\Users\flore\Documents\quelonio-pages`

Este archivo vive en **quelonio-pages** para que el “asistente” y el “método” queden publicados y versionados.

---

## 2) Estado técnico actual (CHECKPOINT REAL)

### 2.1 Node / NPM
- Node: **v20.19.0** (nvm4w)
- npm: **10.8.2**
- Señal importante: en tu máquina aparecen rutas duplicadas (`C:\nvm4w\nodejs\...` y `C:\Program Files\nodejs\...`). Funciona, pero conviene mantener consistencia (ver “Riesgos”).

### 2.2 Next.js
- Next: **16.1.0**
- `npm run dev` inicia el servidor local en `http://localhost:3000` **cuando está corriendo**.
- Importante: si el servidor no está corriendo, `curl http://localhost:3000/...` falla (normal).

### 2.3 PostgreSQL (Local Windows)
- Servicio: `postgresql-x64-18` **Running**
- Puerto: `localhost:5432`
- Base: `quelonio_saas`
- Usuario app: `quelonio`
- Password: `1204` (por ahora; si esto es sensible, cambialo luego y actualizá `.env`)

Prueba de conexión OK (ejemplo ya validado):
- `select current_database(), current_user;` devolvió `quelonio_saas | quelonio`

### 2.4 Prisma
- `npx prisma validate` OK
- `npx prisma generate` OK
- `npx prisma migrate dev --name init` quedó **“Already in sync”** (no hay migraciones pendientes)

Se resolvieron errores previos:
- P1000 credenciales: se corrigió creando/ajustando usuario/credenciales
- Permisos `_prisma_migrations`: se ajustaron owners/permisos
- Shadow DB (P3014): se resolvió dando `CREATEDB` al rol `quelonio`

---

## 3) Riesgos / alertas detectadas

### 3.1 Warning de Next: “multiple lockfiles”
Te apareció este warning:
- Next detectó un `package-lock.json` en `C:\Users\flore\package-lock.json` y lo tomó como “workspace root”.

Esto NO es bloqueante, pero ensucia y puede traer problemas de tooling.

Opciones (elige una, cuando estemos en “limpieza”):
1) **Eliminar/renombrar** `C:\Users\flore\package-lock.json` si no pertenece a nada importante.
2) Configurar `turbopack.root` en `next.config.ts` apuntando al repo actual.
3) Dejarlo así por ahora (válido para avanzar).

---

## 4) Convención de carpetas (importante)

En Next App Router:
- No existe `/api` en raíz.  
- Los endpoints se crean en: `app/api/<ruta>/route.ts`
- La capa “lib” la creamos nosotros (si queremos): `lib/prisma.ts`, `lib/auth.ts`, etc.

Si hoy “no tenés carpeta lib ni api”, es normal. Se crean en el siguiente paso de implementación.

---

## 5) Próximo objetivo inmediato (Sprint 1)

**Siguiente paso funcional mínimo:** un endpoint de salud + conexión DB real.

Entregables mínimos:
1) `GET /api/health` responde JSON `{ ok: true }`
2) Prisma client centralizado (`lib/prisma.ts`)
3) Un endpoint que pegue a DB (por ejemplo: `GET /api/db-ping` o listar “usuarios” si el schema ya tiene User)

---

## 6) Método operativo (micro-pasos)

**Regla:** 1 comando / 1 cambio por vez.  
Vos pegás output, yo doy el siguiente paso.

**Cuando hay servidores corriendo:**
- Abrí **otra terminal** (VS Code: *Terminal → New Terminal*).  
No hace falta cortar un server para ejecutar comandos en paralelo.

---

## 7) Prompt de reinicio (para retomar en un chat nuevo)

Pegá esto tal cual en un chat nuevo cuando quieras retomar:

---
**PROMPT CHECKPOINT — Quelonio SaaS (Web/API)**

Contexto:
- Repo app: `C:\Users\flore\Documents\quelonio-saas`
- Repo docs: `C:\Users\flore\Documents\quelonio-pages`
- Stack: Next 16.1 + TS + Prisma 7.2 + PostgreSQL local (Windows service postgresql-x64-18)
- DB: `quelonio_saas` en `localhost:5432`
- Usuario DB: `quelonio` (tiene CREATEDB)
- Prisma: migrate en sync (“Already in sync”)
- Regla: micro-pasos (1 paso por vez)

Qué quiero ahora:
- Continuar Sprint 1 creando:
  1) `app/api/health/route.ts`
  2) `lib/prisma.ts`
  3) Endpoint DB ping o primer modelo simple

Restricciones:
- No avances con 10 pasos juntos.
- Si un paso requiere Admin, avisar explícitamente.
- Si hay que tocar archivos, decime exactamente ruta + contenido a pegar.
---

---

## 8) Changelog (resumen técnico de lo logrado)
- Prisma instalado y funcionando
- Postgres local operativo
- Credenciales y permisos corregidos
- Migrate OK (sin pendientes)
- Prisma Studio se abrió (cuando lo corriste)

Siguiente: endpoints API dentro de Next.
