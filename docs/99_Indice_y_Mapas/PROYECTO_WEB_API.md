# PROYECTO — Quelonio Brew OS (Excel + SaaS)

Este archivo reemplaza el proyecto anterior “PROYECTO_WEB_API” por la idea vigente:
**Quelonio Brew OS** como producto comercializable (Excel prototipo → SaaS multiusuario).

Referencia conceptual / base de conocimiento:
- https://zumajuano-byte.github.io/quelonio-pages

---

## CURRENT_STATE — Quelonio Brew OS

- last_updated: 2025-12-22
- project: Quelonio Brew OS (Excel + SaaS)
- mode_default: Validación operativa (Excel) + Blueprint SaaS + Ejecución por sprints

### objective_now (1 frase)
Consolidar un Excel “modelo” (prototipo operativo) para validar flujo completo con datos reales y luego convertirlo a SaaS multiusuario (login + multi-tenant + roles + auditoría + alertas + exports), incorporando un **Asistente v1** conectado a la Biblia.

### Estado del Excel (prototipo operativo)
Archivos generados y validados:
- Quelonio_Dashboard_Cervecero_v0.2_camino1_validaciones.xlsx (IDs/estados/validaciones)
- Quelonio_Dashboard_Cervecero_v0.3_parte3.xlsx (Compras/AP + stock SKU + rentabilidad canal)
- Quelonio_Dashboard_Cervecero_v0.4_parte4A.xlsx (USERS/roles + auditoría + trazabilidad lote→SKU→venta)
- Quelonio_Dashboard_Cervecero_v0.5_parte4B.xlsx (Plan producción, calendario, alertas, vencimientos AP/AR, capacidad)

Situación:
- El Excel “se ve todo bien” y “trabaja” (validado).
- IDs: en Excel conviene “Secuencia + ID derivado” (semi-automático estable); en SaaS IDs 100% automáticos.

---

## Links canónicos (Biblia + Asistente)

Fuente de verdad de conocimiento (SOT):
- Biblia (sitio): https://zumajuano-byte.github.io/quelonio-pages/

Documentos canónicos del asistente (dentro de la Biblia):
- 99_Indice_y_Mapas/ASISTENTE_KNOWLEDGE_MAP.md
- 99_Indice_y_Mapas/ASISTENTE_CONTRATOS.md
- 99_Indice_y_Mapas/ASISTENTE_DATA_CONTRACT.md

Docs P0 (datos duros para respuestas operativas):
- 99_Indice_y_Mapas/TABLAS_TARGETS_POR_ESTILO.md
- 01_Agua/DEEP/AGUA_CALCULOS_Y_LIMITES.md
- 03_Levadura/Fermentacion_DEEP/PITCH_RATE_Y_OXIGENACION.md
- 09_Empaque_Estabilidad/DEEP/DO_TPO_OBJETIVOS_Y_METODO.md
- 09_Empaque_Estabilidad/DEEP/CO2_CARBONATACION_TABLAS.md
- 09_Empaque_Estabilidad/DEEP/SHELF_LIFE_PLAN_Y_CRITERIOS.md

---

## Blueprint SaaS (aprobado)

Decisión:
Ruta: prototipo Excel validado → blueprint SaaS → ejecución por sprints.

Arquitectura recomendada:
- Next.js + PostgreSQL + Prisma
- Auth + RBAC
- Auditoría (audit_log)
- Jobs (alertas)
- Exports (PDF/CSV)

Multi-tenant:
- `org_id` en todas las tablas.

Roles:
- Owner / Admin / Producción / Ventas / Lectura

Módulos MVP:
- recetas + BOM
- lotes + consumos + empaque
- inventario insumos + stock SKU
- ventas + cobros (AR)
- compras + pagos (AP)
- opex
- planificación + alertas
- dashboard + exports
- settings

---

# MVP ASISTENTE v1 (definición funcional)

## Objetivo del Asistente v1
Un asistente que:
1) Responde preguntas cerveceras usando Biblia + Docs P0 (targets, límites, criterios).
2) Guía el uso del sistema Brew OS (cómo registrar/validar) sin ejecutar cambios.
3) Produce outputs estandarizados (SPEC / Plan / Checklist / Troubleshooting) listos para usar.

## Qué responde (IN SCOPE v1)
### A) Técnico cerveza (Biblia-first)
- Proponer targets por estilo (OG/FG/ABV/IBU/CO2/pH) usando TABLAS_TARGETS_POR_ESTILO (marcando DEFAULT).
- Planear receta baseline (SPEC v1.0) con BOM + proceso alto nivel + gates.
- Ajustar receta por restricciones (volumen, insumos, perfil: más seco/cuerpo/amargor).
- Plan de proceso por lote: cronograma + puntos de control (pH, densidad, temp).
- QA/QC y gates: diacetilo/VDK (07), DO/TPO + empaque (09), estabilidad (shelf-life).
- Shelf-life: plan D+7/D+14/D+30 y criterio liberar/retener/investigar.

### B) Sistema (Brew OS)
- “Cómo hago X”: guía paso a paso por módulos (recetas/lotes/stock/ventas/compras/settings).
- Validación: “qué dato falta / por qué no cierra” contra el contrato de datos.

### C) Salidas canónicas (obligatorio)
Cada respuesta técnica o mixta debe devolver, cuando aplique:
- SPEC v1.0 (ASISTENTE_CONTRATOS)
- Checklist/Gates (ASISTENTE_CONTRATOS)
- Plan de producción (ASISTENTE_CONTRATOS)
- Troubleshooting (ASISTENTE_CONTRATOS)

## Qué NO responde (OUT OF SCOPE v1)
- No ejecuta acciones en DB (no crea/edita entidades). Solo propone y guía.
- No inventa números dependientes de tu equipo:
  - DO/TPO exacto por tu línea: propone benchmark inicial y pide medición si existe.
  - eficiencia real del equipo: pide input o asume DEFAULT declarado.
- No sustituye mediciones: si faltan datos críticos, pide el dato y sugiere cómo medir/registrar.
- No “garantiza” seguridad/calidad: recomienda SOP y detener/verificar si hay riesgo.

## Contrato mínimo de datos (para integrar Brew OS con Asistente v1)
El asistente puede funcionar en “modo Biblia” sin DB, pero para “modo mixto” requiere:

### Identidad y permisos
- org_id
- user_id
- role (Owner/Admin/Producción/Ventas/Lectura)

### Entidades mínimas (v1)
**Recipe**
- recipe_id, name, style, target_volume
- targets: OG/FG/ABV/IBU/color/CO2
- items[]: ingredient_id, type, amount, unit, timing, notes

**Batch**
- batch_id, recipe_id, status, planned_volume, actual_volume, start_date

**Measurements (mínimo)**
- gravity, temp, pH (timestamp, value, unit)

**Opcionales v1 (mejoran mucho)**
- Inventory (ingredient_id, qty_on_hand, unit)
- PackagingRun (date, qty_produced, losses, notes, o2_controls)

### Reglas de no-invención (v1)
- Si targets faltan -> baseline desde TABLAS_TARGETS_POR_ESTILO marcado DEFAULT.
- Si mediciones faltan -> pedir dato o disparar checklist.
- Si stock faltante -> no confirma compras, propone BOM y lista “a validar”.

## DoD del Asistente v1 (resultado esperado)
- Responde con contratos (SPEC/Plan/Checklist/Troubleshooting) sin formatos libres.
- Pide datos faltantes (no inventa) y marca DEFAULT cuando aplica.
- Referencia docs canónicos (links internos de Biblia).
- Puede funcionar en 2 modos:
  - Biblia-only (sin DB)
  - Mixto (Biblia + entidades mínimas vía API)

---

## Sprint plan (ruta de ejecución)

Sprint 0.5 (Asistente v1 — Especificación y contratos)
- Congelar alcance IN/OUT (este bloque).
- Congelar formatos de salida (ASISTENTE_CONTRATOS).
- Congelar data contract mínimo (ASISTENTE_DATA_CONTRACT + sección de arriba).
- Definir endpoints “read-only” para contexto (ver Sprint 2/3).

Sprint 1: Fundación (Identity + multi-tenant + RBAC + Settings + invitaciones + auditoría mínima).
Sprint 2: Maestros (ingredientes, productos, recetas+BOM).
Sprint 3: Operación (lotes/consumos/empaque + stock).
Sprint 4: Comercial/finanzas (ventas/cobros AR + compras/pagos AP).
Sprint 5: Planificación + alertas + dashboard + exports.

Nota: El Asistente v1 se integra incrementalmente:
- Primero Biblia-only (sin DB).
- Luego Mixto cuando existan entidades mínimas y endpoints read-only.

---

## Sprint 1 — Estado real (bloqueo actual)

Escenario elegido:
“Quiero que me guíes mientras lo hacemos” (micro-pasos).

Bloqueo:
- En PowerShell: Node/Git OK.
- Docker NO estaba instalado (se descartó Docker para DB local).
- PostgreSQL en Windows: password desconocida; pgAdmin fallaba `fe_sendauth: no password supplied`.
- Puerto 5433 observado (posible múltiple instancia/puerto).
- Hubo intento con `pg_hba.conf (trust)` pero se mezclaron instancias.

Decisión final:
Desinstalar PostgreSQL/pgAdmin y reinstalar limpio para volver a 5432 con credenciales claras.

---

## Próximo paso exacto al retomar (post-reinicio)

### 4.1 Reinstalar PostgreSQL limpio (objetivo: puerto 5432)
- Desinstalar PostgreSQL + pgAdmin.
- Borrar `C:\Program Files\PostgreSQL\` si queda residual.
- Reiniciar.
- Reinstalar PostgreSQL (incluye pgAdmin), definir password de `postgres`, puerto 5432.
- Verificar:
  - Servicio `postgresql-x64-XX` corriendo
  - `netstat -aon | findstr :5432` muestra LISTENING

### 4.2 Crear DB y conectar pgAdmin
- Registrar server local en pgAdmin:
  - host localhost / port 5432 / user postgres / password nueva
- Crear DB `quelonio_saas`

### 4.3 Retomar Prisma en VS Code
En carpeta del proyecto `...\quelonio-saas\web\`:
- `npm i prisma @prisma/client`
- `npx prisma init`

En `.env`:
- `DATABASE_URL="postgresql://postgres:TU_PASSWORD@localhost:5432/quelonio_saas?schema=public"`

Luego:
- Pegar `schema.prisma` Sprint 1 (User, Organization, OrgMembership, OrgSettings, AuditLog + enums)
- `npx prisma migrate dev --name sprint1_init`
- `npx prisma studio`

Verificación:
- Prisma Studio muestra tablas base.

---

## DoD Sprint 1 (resultado esperado)
- Usuario puede registrarse/login.
- Crear org y quedar como Owner.
- Invitar usuario y aceptar invitación.
- RBAC impide acciones no permitidas.
- Settings por organización persisten.
- Auditoría registra: create org, invite, change role, update settings.

---

## Regla operativa del proyecto (MODO “1 PASO”)
- Me guiás SIEMPRE de a **UN SOLO PASO**.
- No métodos alternativos ni opciones múltiples.
- Cada paso debe ser: (1) comando/clicks exactos, (2) output esperado, (3) qué te pego yo.
- No seguimos hasta que yo confirme “OK”.

---

## PROMPT DE ARRANQUE (RESET TOTAL QUELONIO SAAS — WINDOWS — MODO “1 PASO”)
(Se conserva aquí como “botón de reinicio” del proyecto)

Quiero reiniciar el proyecto QUELONIO SAAS desde CERO en Windows 10/11. Estoy mareado con setups viejos (Postgres local, puertos raros, roles, Prisma, NVM).
Necesito un camino limpio y reproducible, sin parches.

REGLA PRINCIPAL
- Me guiás SIEMPRE de a UN SOLO PASO.
- No me das métodos alternativos ni opciones múltiples.
- Cada paso: (1) comando/clicks exactos, (2) output esperado, (3) qué te pego yo.
- No seguimos hasta que confirme “OK”.

OBJETIVO FINAL
1) Node.js LTS instalado sin conflictos.
2) Docker Desktop instalado.
3) Postgres corriendo en Docker (no Postgres instalado en Windows).
4) Proyecto nuevo en: C:\Users\flore\Documents\quelonio-saas
5) Next.js (App Router + TS + Tailwind).
6) Prisma funcionando con DB quelonio_saas en localhost:5432.
7) Migración inicial aplicada con tablas base (Organization/User/Membership).
8) Listo para continuar MVP SaaS (multi-tenant) sin tocar proyectos viejos.
