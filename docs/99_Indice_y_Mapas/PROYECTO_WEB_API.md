# PROYECTO_WEB_API — Quelonio SaaS (Web App + API + DB)

**Última actualización:** 2025-12-23  
**Estado:** Sprint 1/2 — Vertical slice multi-tenant (Organizations + Memberships + Recipes) operativo  
**Regla de trabajo:** micro-pasos (1 paso por vez). Si un paso requiere admin, se aclara explícitamente.

---

## 0) Objetivo

Construir un **MVP tipo SaaS** para operación cervecera (recetas, lotes, stock, ventas, finanzas) + base para incorporar un **asistente IA** que responda en base a la Biblia (Quelonio Pages).

Principio de producto:
- **Excel** = modelo / plantilla / análisis (import-export, simulaciones).
- **SaaS** = operación diaria / “source of truth” (multiusuario, trazabilidad, consistencia).

Arquitectura (MVP):
- **Next.js (App Router) + TypeScript**
- **PostgreSQL**
- **Prisma**
- Endpoints API dentro de Next (`app/api/*`)
- Más adelante: auth/RBAC, auditoría, exports/imports, jobs/alertas

---

## 1) Repos / Ubicaciones

- **Repo Web App:** `C:\Users\flore\Documents\quelonio-saas`
- **Repo Biblia / Docs (GitHub Pages):** `C:\Users\flore\Documents\quelonio-pages`

Este archivo vive en **quelonio-pages** para que el “asistente” y el “método” queden publicados y versionados.

---

## 2) Estado técnico actual (CHECKPOINT REAL)

### 2.1 Node / NPM
- Node: **v20.19.0**
- npm: **10.8.2**

### 2.2 Next.js
- Next: **16.1.0**
- Dev: `npm run dev` (usa `next dev --webpack`)
- URL: `http://localhost:3000`

Notas:
- Si reiniciás `npm run dev` y el puerto está ocupado, es porque **hay otro Next corriendo**.
- Si ves: `Unable to acquire lock ... .next\dev\lock`, terminá el proceso anterior (o cerrá la terminal que lo estaba ejecutando) y volvé a correr dev.

### 2.3 PostgreSQL (Local Windows)
- Servicio: `postgresql-x64-18` **Running**
- Puerto: `localhost:5432`
- Base: `quelonio_saas`
- Usuario app: `quelonio`
- Password: `1204` (temporal; cambiar más adelante)

### 2.4 Prisma
- `npx prisma validate` OK
- `npx prisma generate` OK
- Migraciones: OK (sin pendientes)
- Migración creada para Recipes: `prisma/migrations/20251222214518_add_recipe/`

Nota importante (scripts Node):
- En este setup Prisma usa **adapter PG**. Si hacés scripts con `new PrismaClient()` “pelado”, puede fallar.
- Recomendación: en scripts, **importar el prisma centralizado** desde `lib/prisma.ts` (el mismo que usa la app).

### 2.5 Multi-tenant (estado funcional)
**Ya quedó operativo un vertical slice multi-tenant completo:**
- Organizations + Memberships (relación usuario↔org)
- Recipes con scoping por Organization
- UI “Dev Console” para operar todo lo anterior

---

## 3) Decisiones / aprendizajes del Sprint (lo importante)

### 3.1 Tenant enforcement (paso clave)
Antes: “confiar” en `X-Org-Id` (header libre) = fácil de romper.

Ahora: **enforcement por Membership**:
- Toda operación sensible valida que el “usuario dev actual” exista.
- Valida que ese usuario tenga **Membership** en la Organization activa.
- Resultado: separación real por tenant (base de un SaaS).

### 3.2 Org activa (cookie) vs header
Tenemos 2 caminos, en orden recomendado:

1) **Cookie (recomendado)**: `POST /api/active-org` setea la org activa (persistida en cookie del navegador / session).
   - A partir de ahí `GET/POST/PATCH/DELETE /api/recipes` funciona sin mandar headers.

2) **Header (temporal)**: `X-Org-Id` se mantiene como fallback para smoke tests rápidos.
   - Útil cuando probás con scripts o PowerShell sin sesión.

### 3.3 Variables de entorno (pitfall detectado)
- Si aparece error: `Dev user not found: <email>`
  - Revisar `.env` → `DEV_USER_EMAIL=...`
  - Debe coincidir con un `User.email` existente en DB.
  - Si bootstrap usa `owner@quelonio.local`, lo más seguro es setear:
    - `DEV_USER_EMAIL=owner@quelonio.local`

---

## 4) Endpoints actuales (resumen)

Base: `http://localhost:3000`

### Health / debug
- `GET /api/health`
- `GET /api/debug/users` (inspección rápida)

### Bootstrap / orgs / memberships
- `POST /api/bootstrap` (crea Org + User + Membership de forma idempotente por email)
- `GET /api/organizations`
- `POST /api/organizations`
- `GET /api/memberships`
- `GET /api/memberships?orgId=<ORG_ID>`

### Tenant context
- `POST /api/active-org` (setea cookie de org activa)

### Recipes (multi-tenant)
- `GET /api/recipes`
- `POST /api/recipes`
- `GET /api/recipes/[id]`
- `PATCH /api/recipes/[id]`
- `DELETE /api/recipes/[id]`

---

## 5) UI (Dev Console) — lo que existe hoy

Página: `GET /` (http://localhost:3000)

Incluye:
- Selector de Organization activa (persistida en `localStorage` con key `quelonio.activeOrgId`)
- Crear Organization
- Ejecutar Bootstrap y auto-seleccionar la org creada
- Sección Recipes:
  - Crear recipe
  - Listar recipes por org activa
  - Editar / Borrar recipes

Objetivo: consola mínima para validar APIs sin construir UI final todavía.

---

## 6) Smoke tests útiles (PowerShell)

### 6.1 Nota sobre `Invoke-RestMethod`
En PowerShell puede que NO exista `-SkipHttpErrorCheck`. En ese caso, usar `try/catch` para ver status y body (patrón estándar):

```powershell
$s = New-Object Microsoft.PowerShell.Commands.WebRequestSession
try {
  Invoke-RestMethod -WebSession $s -Method Post -Uri http://localhost:3000/api/active-org `
    -ContentType "application/json" `
    -Body (@{ orgId = "PEGAR_ORG_ID" } | ConvertTo-Json)
} catch {
  $_.Exception.Response.StatusCode.value__
  $r = New-Object IO.StreamReader($_.Exception.Response.GetResponseStream())
  $r.ReadToEnd()
}
```

### 6.2 Cookie path (recomendado)
```powershell
# 1) Crear sesión
$s = New-Object Microsoft.PowerShell.Commands.WebRequestSession

# 2) Setear org activa (cookie)
$orgId="PEGAR_ORG_ID"
Invoke-RestMethod -WebSession $s -Method Post -Uri http://localhost:3000/api/active-org `
  -ContentType "application/json" `
  -Body (@{ orgId = $orgId } | ConvertTo-Json)

# 3) Listar recipes (sin headers)
Invoke-RestMethod -WebSession $s -Uri http://localhost:3000/api/recipes

# 4) Crear recipe (sin headers)
Invoke-RestMethod -WebSession $s -Method Post -Uri http://localhost:3000/api/recipes `
  -ContentType "application/json" `
  -Body '{"name":"IPA Cookie","style":"IPA","notes":"ok cookie+membership"}'
```

### 6.3 Header path (fallback)
```powershell
$orgId="PEGAR_ORG_ID"

Invoke-RestMethod -Method Post -Uri http://localhost:3000/api/recipes `
  -Headers @{ "X-Org-Id" = $orgId } `
  -ContentType "application/json" `
  -Body '{"name":"IPA Header","style":"IPA","notes":"header path"}'

Invoke-RestMethod -Uri http://localhost:3000/api/recipes `
  -Headers @{ "X-Org-Id" = $orgId }
```

---

## 7) Mapa de producto (visión simple, sin tecnicismos)

Orden lógico de módulos (uno alimenta al siguiente):

1) **Recetas** (especificación)  ✅ HOY (multi-tenant)
2) **Lotes** (producción real)  ⏭️ PRÓXIMO
3) **Inventario** (entradas/salidas por movimientos)
4) **Empaque** (lote → SKUs → unidades)
5) **Ventas + Cobros**
6) **Compras + Pagos**
7) **Costos + Rentabilidad**
8) **QA/QC** (controles y desvíos)
9) **Dashboard** (decisión)

Dónde entra Excel:
- **Modelado** (costos, simulaciones, escenarios).
- **Carga inicial** (import de catálogos/stock).
- **Export/reportes** (contabilidad, socios, análisis).
- **Portabilidad** (backup).

---

## 8) Próximo objetivo inmediato (Sprint 2)

**Siguiente vertical slice recomendado:** módulo **Lotes (Batch)**, porque conecta Receta ↔ Producción real.

Entregables mínimos:
1) Modelo Prisma `Batch` (organizationId + recipeId + fechas + volumen + notas)
2) CRUD API `/api/batches` scoping por org activa (mismo patrón que recipes)
3) UI mínima en Dev Console: listar/crear batches

---

## 9) Método operativo (micro-pasos)

**Regla:** 1 comando / 1 cambio por vez.  
Vos pegás output, yo doy el siguiente paso.

**Cuando hay servidores corriendo:**
- Abrí **otra terminal** (VS Code: *Terminal → New Terminal*).  
No hace falta cortar un server para ejecutar comandos en paralelo.

---

## 10) Prompt de reinicio (para retomar en un chat nuevo)

Pegá esto tal cual en un chat nuevo cuando quieras retomar:

---
**PROMPT CHECKPOINT — Quelonio SaaS (Web/API)**

Contexto:
- Repo app: `C:\Users\flore\Documents\quelonio-saas`
- Repo docs: `C:\Users\flore\Documents\quelonio-pages`
- Stack: Next 16.1 + TS + Prisma + PostgreSQL local
- Multi-tenant operativo: Organizations + Memberships + Recipes
- Tenant context: cookie `POST /api/active-org` (recomendado) y fallback `X-Org-Id`
- Regla: micro-pasos (1 paso por vez)

Qué quiero ahora:
- Implementar **Lotes (Batch)**:
  1) Schema Prisma `Batch` con `organizationId` + `recipeId` + campos mínimos
  2) API routes `/api/batches` (GET/POST) y `/api/batches/[id]` (PATCH/DELETE)
  3) UI mínima en `app/page.tsx` para listar/crear batches

Restricciones:
- No avances con 10 pasos juntos.
- Si un paso requiere Admin, avisar explícitamente.
- Si hay que tocar archivos, decime exactamente ruta + contenido a pegar.
---

---

## 11) Publicación en la Biblia (quelonio-pages)

Desde `C:\Users\flore\Documents\quelonio-pages`:
1) Copiar este archivo actualizado a su ubicación en docs (si aplica en tu árbol).
2) `python -m mkdocs build --strict` (opcional pero recomendado)
3) Commit + push:
```bash
git add -A
git commit -m "docs: update PROYECTO_WEB_API checkpoint (2025-12-23)"
git push
```
## Entrada 2025-12-23 — Quelonio SaaS (API multi-tenant + reportes + idempotencia)

### Qué se logró (backend/API)
- Multi-tenant operativo:
  - Active org por cookie (`POST /api/active-org`)
  - Alternativa por header `X-Org-Id` (estandarizado en scripts dev).
- Dev tooling por terminal:
  - `scripts/dev.ps1`: helpers `Set-Org`, `Q`, `QGet/QPost/QDel`, `QSmoke`.
- Ventas:
  - Invoices + lines + totals (subtotal/tax/total/paid/balance) y status auto (ISSUED/PAID).
  - Payments con actualización de status de invoice según balance.
- Reportes (KPIs):
  - `GET /api/reports/sales-summary?from=YYYY-MM-DD&to=YYYY-MM-DD`
  - `GET /api/reports/inventory-summary?from=YYYY-MM-DD&to=YYYY-MM-DD`

### Idempotencia (verificada)
- Recipes: por (organizationId, name) → mismo name no duplica.
- Batches: por (organizationId, code) → upsert.
- Invoices: por (organizationId, number) → mismo number no duplica.
- StockMoves: `clientRef` + unique DB por (organizationId, clientRef) → mismo clientRef devuelve mismo move.id.
- Payments: `clientRef` + unique DB por (organizationId, clientRef) → mismo clientRef devuelve mismo payment.id.

### Notas operativas / lecciones
- Si aparece “Forbidden: user is not a member of this organization”, crear/asegurar Membership OWNER del dev user en esa org.
- Si VSCode marca en rojo delegates Prisma (ej: `prisma.invoice...`), correr `npx prisma generate` y luego reiniciar TS Server / Reload Window.

### Comandos estándar (terminal) — forma de trabajo
1) Cargar helpers:
   - `. .\scripts\dev.ps1`
2) Setear org activa:
   - `Set-Org "<orgId>"`
3) Smoke test rápido:
   - `QSmoke`
4) Requests:
   - `QGet "/api/reports/sales-summary"`
   - `QGet "/api/reports/inventory-summary"`

### Próximo paso
- Dashboard UI mínimo consumiendo `sales-summary` + `inventory-summary`.
