---
id: GOU-LOG-001
title: Registro de Canonicalización
version: 0.1.0
status: PROPOSED
date: 2026-10-22
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
