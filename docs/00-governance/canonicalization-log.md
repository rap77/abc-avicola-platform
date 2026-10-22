---
id: GOU-LOG-001
title: Registro de Canonicalización
version: 0.1.0
status: APPROVED
date: 2026-10-22
last_reviewed_at: 2026-10-23
approved_at: 2026-10-23
author: Qwen3.7
tags: [governance, canonicalization, log]
---

# Registro de Canonicalización

Registro de materializaciones documentales en el repositorio. Cada entrada consigna
documento, versión, estado, ruta, hash SHA-256, fuente, aprobación humana y notas.

## Entradas

### 2026-10-22 — AGENTS.md
- documento: AGENTS.md (id: AGT-001)
- versión: 0.1.0 (frontmatter del documento transferido; el prompt de materialización referenciaba "versión: 1.0.0" — se conservó el contenido EXACTO proporcionado por el stakeholder y se reporta la discrepancia)
- estado: PROPOSED
- ruta: /workspace/AGENTS.md
- hash SHA-256: 0da61f43148d32690158df9c4d5e7395d1b90b9c42eb89483ae74b44e80d8b11
- fuente: "transfer desde sesión de descubrimiento"
- versión supersedida: n/a (documento nuevo en repo)
- fecha: 2026-10-22
- aprobación humana: pendiente
- notas de materialización: Creado en la raíz del repositorio con contenido exacto
  proporcionado por el stakeholder. Estado bloqueado en PROPOSED; ningún agente
  puede cambiarlo a APPROVED sin autorización humana explícita.

### 2026-10-23 — AGENTS.md (v0.2.0)
- documento: AGENTS.md (id: AGT-001)
- versión: 0.2.0
- estado: PROPOSED
- ruta: /workspace/AGENTS.md
- hash SHA-256: 79a2d0c246021dae77f0df7d9ddbb8ebd983165fb856fb8b94e96e6e96193aa6
- fuente: "regeneración solicitada por el stakeholder para incorporar ajustes de gobernanza A/B/C"
- versión supersedida: 0.1.0 (hash 0da61f43148d32690158df9c4d5e7395d1b90b9c42eb89483ae74b44e80d8b11; recuperable vía commit 9050cd1)
- fecha: 2026-10-23
- aprobación humana: pendiente
- cambios incorporados:
  * AJUSTE A (§3): separación explícita de estado documental
    (DRAFT → PROPOSED → IN_REVIEW → APPROVED ↓ SUPERSEDED) y estado de entrega
    (NOT_STARTED → IN_PROGRESS → IMPLEMENTED → VERIFIED), con reglas de relación
    entre ambos ejes y nota sobre evidencia de pruebas vs. aceptación humana.
  * AJUSTE B (§4): toda autorización indica objeto, alcance y límites; aprobar un
    documento no autoriza dependencias, implementación, datos reales ni despliegue;
    modificación sustancial de documento aprobado vuelve a IN_REVIEW.
  * AJUSTE C (§5): definición de contrato atómico como unidad de trabajo
    comprobable con sus 11 secciones obligatorias; no se crea contrato por cada
    ajuste visual menor.
- notas de materialización: Se renumeraron las secciones subsiguientes
  (Materialización→§6, Rondas→§7, Contexto/Normativa→§8) tras insertar §4 nuevo.
  El frontmatter conserva status PROPOSED; se añadieron campos `supersedes` y
  `changelog`. Ningún agente cambió el estado; la aprobación sigue siendo
  exclusivamente humana. Conteo de secciones verificada: 8 secciones, numeración
  consecutiva sin duplicados.


## Source Declaration — 2026-10-23 (sin aprobación documental)

Registro de fuentes de la raíz del repositorio con su rol normativo y SHA-256 actual.
Esta entrada NO constituye aprobación de ningún documento; es declaración de fuentes
leídas en preflight conforme a AGENTS.md@0.2.0 §3.

| Archivo | Rol | SHA-256 |
|---|---|---|
| prompt universal.md | NORMATIVE (METODOLOGÍA NORMATIVA, máxima precedencia) | 6c18561582fd418d3d3cc384757c1fa66aac9cdf5b42cb3a8f92c6dfae9471b3 |
| prompt de anexo operativo.md | COMPLEMENT (COMPLEMENTO NORMATIVO subordinado) | 0bafc1a9cffd7c12ba22c702e2dac5fe8cd7d8e8d0a1c67f0aaf1dbb4ca296aa |
| ABC Avicola Analisis 1.md | EVIDENCE (evidencia de contexto, no normativa) | 3f5051abca7bb81efa0585e3b7610ca0b0d63a80cfb1a80a4ff720438d276f15 |
| Estudio Portal 3tres3.md | EVIDENCE (evidencia de contexto, no normativa) | 9a5b42abffbed4c74ebb25ff1bc783ef3529c305b612d3f3829594fb0760af26 |

Notas:
- AGENTS.md@0.2.0 se registra como ADAPTADOR DEL REPOSITORIO (precedencia 3), subordinado a las dos primeras fuentes.
- docs/CANONICAL_INDEX.md aún no existe en el repo; se señala como pendiente (no creado por iniciativa propia sin autorización).

### Pendiente de actualización — entradas anteriores de AGENTS.md
Las entradas de v0.1.0 y v0.2.0 arriba referencian `id: AGT-001` y frontmatter no canónico
(id/date/author/tags/changelog). El frontmatter de v0.2.0 fue corregido el 2026-10-23 al
esquema canónico (document_id: AGENTS, authority, supersedes: [AGENTS@0.1.0], etc.) y el
estado pasó de PROPOSED a IN_REVIEW por instrucción explícita del stakeholder. Hash vigente
de v0.2.0 (working tree, sin commit): 4d75d5f4e9d33d9d290d59fc194b15bc18b21b2d2d81b4d2d22f28a914c8c4df.
Aprobación humana: pendiente. Commit: pendiente (orden explícita: NO commitear aún).

### Ronda de correcciones HUMAN_REVIEW — 2026-10-23 (CORRECTIONS_REQUIRED)
Resultado de revisión humana sobre AGENTS.md@0.2.0 (IN_REVIEW): CORRECTIONS_REQUIRED.
Cambios aplicados en working tree conforme a Sección 13 (corrección sustantiva durante
revisión humana; NO genera bump de versión — la versión sigue siendo 0.2.0):
  * §2 (Fuentes Normativas y Precedencia): añadido al final el párrafo "Alcance de esta
    jerarquía" con texto exacto provisto por el revisor (precedencia de Sección 20 de
    prompt universal.md para implementación y ejecución).
  * §5 (Estados): añadida viñeta sobre PILOT_READY y PRODUCTION_READY como estados
    operativos separados (Sección 2.3 y Ronda 12 de prompt universal.md), no implicados
    desde VERIFIED, tras las "Reglas de relación entre ejes". Texto exacto provisto.
- hashes de v0.2.0: pre-corrección 4d75d5f4e9d33d9d290d59fc194b15bc18b21b2d2d81b4d2d22f28a914c8c4df →
  post-corrección 7555aca713d49f8590a7057edda019c3d802f6b2bdc5ac02bb5e9a12b37c2e66 (working tree).
- estado documental: IN_REVIEW (sin cambio); aprobación humana: pendiente; commit: pendiente
  (orden explícita: SIN commit).

### Aprobación humana — AGENTS@0.2.0 — 2026-10-23
- documento: AGENTS (document_id canónico, v0.2.0)
- ruta: /workspace/AGENTS.md
- resultado de revisión: APPROVED (aprobación humana explícita del stakeholder)
- aprobador: ABC Avícola Platform Owner
- fecha de aprobación: 2026-10-23 (approved_at y last_reviewed_at llenados en frontmatter)
- referencia de aprobación: mensaje del stakeholder "Apruebo explícitamente AGENTS@0.2.0
  para materializarlo como APPROVED" (ronda posterior a CORRECTIONS_REQUIRED; correcciones
  §2 "Alcance de esta jerarquía" y §5 PILOT_READY/PRODUCTION_READY verificadas e incorporadas)
- cambio de estado: IN_REVIEW → APPROVED (ejecutado por el agente POR ORDEN EXPLÍCITA HUMANA;
  no es autoaprobación)
- hash SHA-256 final (APPROVED): d7c46367b4f14555c9613708b5f6f5de323e5cfe08d3e18178e0e779336a9eb9
- versión supersedida: AGENTS@0.1.0 (hash 0da61f43...d8b11, recuperable vía commit 9050cd1)
- aprobación humana: SÍ
- notas: la aprobación de este documento NO autoriza implementación, instalación de
  dependencias, acceso a datos reales ni despliegues (AGENTS.md §6, AJUSTE B). Estado de
  entrega de las funcionalidades descritas: NOT_STARTED.

### Materialización — CANONICAL_INDEX@0.1.0 (PROPOSED) — 2026-10-23
- documento: CANONICAL_INDEX
- ruta: docs/CANONICAL_INDEX.md
- estado documental: PROPOSED (creado por orden explícita del stakeholder; commit cb62b17)
- hash SHA-256 (PROPOSED): e4a7090040edf0c4a430f4c72a041eeb438ea5d9f4af42d69cf646b8c285c42e
- fuente: "creación autorizada en la orden de aprobación de AGENTS@0.2.0"
- aprobación humana: pendiente en ese momento

### Aprobación humana — CANONICAL_INDEX@0.1.0 — 2026-10-23
- documento: CANONICAL_INDEX (document_id canónico, v0.1.0)
- ruta: docs/CANONICAL_INDEX.md
- resultado de revisión: APPROVED (aprobación humana explícita del stakeholder)
- aprobador: ABC Avícola Platform Owner
- fecha de aprobación: 2026-10-23 (approved_at y last_reviewed_at llenados en frontmatter)
- referencia de aprobación: mensaje del stakeholder "Apruebo explícitamente
  CANONICAL_INDEX@0.1.0 con SHA-256 e4a70900... para materializarlo como APPROVED"
  (el hash citado coincide con el archivo PROPOSED verificado: e4a7090040edf0c4...85c42e)
- cambio de estado: PROPOSED → APPROVED (ejecutado por el agente POR ORDEN EXPLÍCITA HUMANA;
  no es autoaprobación)
- ajustes menores derivados de la materialización (mismo contenido sustantivo, sin bump):
  * tabla interna docs/**: fila de este índice actualizada de PROPOSED a APPROVED y nota de
    auto-referencia de hash reformulada (ver abajo);
  * nota "única aprobación registrada" ampliada para incluir esta segunda aprobación.
- hash SHA-256 final (APPROVED): f8554e0da614f71466183bc316af825a3745fb170ef6b89d49c1dfc7e1127965
- limitación técnica de auto-referencia: el hash APPROVED no puede escribirse dentro del
  propio archivo sin invalidarse; el valor canónico de referencia queda registrado en esta
  entrada del log. El hash PROPOSED aprobado por el stakeholder (e4a70900...) corresponde al
  contenido sustantivo aprobado.
- aprobación humana: SÍ
- notas: la aprobación de este índice NO autoriza implementación, instalación de
  dependencias, acceso a datos reales ni despliegues (AGENTS@0.2.0 §6, AJUSTE B).

### Aprobación humana — canonicalization-log@0.1.0 (GOU-LOG-001) — 2026-10-23
- documento: GOU-LOG-001 (este Registro de Canonicalización), v0.1.0
- ruta: docs/00-governance/canonicalization-log.md
- resultado de revisión: APPROVED (aprobación humana explícita del stakeholder)
- aprobador: ABC Avícola Platform Owner
- fecha de aprobación: 2026-10-23 (approved_at y last_reviewed_at llenados en frontmatter)
- referencia de aprobación: mensaje del stakeholder "Apruebo explícitamente el
  canonicalization-log.md actual para materializarlo como APPROVED"
- cambio de estado: PROPOSED → APPROVED (ejecutado por el agente POR ORDEN EXPLÍCITA HUMANA;
  no es autoaprobación)
- ajustes aplicados (sin bump de versión, mismo contenido sustantivo):
  * status: PROPOSED → APPROVED
  * añadidos last_reviewed_at: 2026-10-23 y approved_at: 2026-10-23
  * conservado el frontmatter heredado no canónico (id/date/author/tags): la orden solo
    exigía cambiar status y llenar fechas; la migración al esquema canónico sigue pendiente
    de autorización explícita (se mantiene en "Pendientes")
- hash SHA-256 final (APPROVED): registrado en CANONICAL_INDEX.md y en la entrega de
  materialización (limitación de auto-referencia: el hash no puede escribirse dentro del
  propio archivo sin invalidarse; el valor canónico queda consignado en la tabla interna
  del índice y en esta entrada se describe su procedencia)
- actualización coordinada: docs/CANONICAL_INDEX.md actualiza la fila de este documento
  de PROPOSED a APPROVED (cambio derivado directamente de la orden, punto 5)
- aprobación humana: SÍ
- notas: la aprobación de este log NO autoriza implementación, instalación de
  dependencias, acceso a datos reales ni despliegues (AGENTS@0.2.0 §6, AJUSTE B).
