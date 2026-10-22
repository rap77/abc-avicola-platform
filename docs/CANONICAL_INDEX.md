---
document_id: CANONICAL_INDEX
title: Índice de Documentación Canónica - ABC Avícola Platform
version: 0.1.0
status: APPROVED
authority: NORMATIVE
document_owner:
  - ABC Avícola Platform Owner
language: es
created_at: 2026-10-23
last_reviewed_at: 2026-10-23
approved_at: 2026-10-23
supersedes: []
superseded_by: []
source_documents:
  - prompt universal.md
  - AGENTS.md@0.2.0 (APPROVED)
related_documents:
  - docs/00-governance/canonicalization-log.md
change_control: DECISION_CONTROLLED
obsidian_compatible: true
---

# Índice de Documentación Canónica

Índice maestro de la documentación canónica del proyecto. Toda entrada declara
identificador, versión, estado documental, ruta y hash SHA-256 vigente. Este índice
debe actualizarse en cada cambio de estado o materialización (AGENTS.md@0.2.0 §8).

## Documentos normativos del repositorio (raíz)

| ID | Título | Versión | Estado | Precedencia | Ruta | SHA-256 |
|---|---|---|---|---|---|---|
| prompt universal | Prompt Universal (metodología normativa) | n/a | EXTERNA APROBADA (fuente de máxima precedencia) | 1 | /workspace/prompt universal.md | 6c18561582fd418d3d3cc384757c1fa66aac9cdf5b42cb3a8f92c6dfae9471b3 |
| prompt anexo operativo | Prompt de Anexo Operativo (complemento normativo subordinado) | n/a | EXTERNA APROBADA | 2 | /workspace/prompt de anexo operativo.md | 0bafc1a9cffd7c12ba22c702e2dac5fe8cd7d8e8d0a1c67f0aaf1dbb4ca296aa |
| AGENTS | Reglas de Operación para Agentes de IA | 0.2.0 | APPROVED | 3 (adaptador) | /workspace/AGENTS.md | d7c46367b4f14555c9613708b5f6f5de323e5cfe08d3e18178e0e779336a9eb9 |

Nota: `prompt universal.md` y `prompt de anexo operativo.md` son fuentes normativas
humanas aportadas al repo; no se canonicalizan con frontmatter propio ni se modifican.
Los archivos `ABC Avicola Analisis 1.md` y `Estudio Portal 3tres3.md` son EVIDENCIA DE
CONTEXTO (no normativa, AGENTS.md@0.2.0 §2 punto 4) y por tanto NO figuran en este
índice canónico; sus hashes constan en el canonicalization-log (Source Declaration).

## Documentos internos docs/**

| ID | Título | Versión | Estado | Ruta | SHA-256 |
|---|---|---|---|---|---|
| GOU-LOG-001 | Registro de Canonicalización | 0.1.0 | PROPOSED | docs/00-governance/canonicalization-log.md | ver nota abajo |
| CANONICAL_INDEX | Índice de Documentación Canónica (este documento) | 0.1.0 | APPROVED | docs/CANONICAL_INDEX.md | ver canonicalization-log "Aprobación humana — CANONICAL_INDEX@0.1.0" (el hash final APPROVED no puede incluirse auto-referencialmente en este mismo archivo; queda registrado en el log) |

Notas:
- El Registro de Canonicalización conserva frontmatter no canónico heredado
  (id/date/author/tags); su migración al esquema canónico queda pendiente de
  autorización humana explícita (AGENTS.md@0.2.0 §6: no modificar documentos sin orden).
- Ningún agente puede cambiar estados a APPROVED por iniciativa propia. Aprobaciones
  registradas: AGENTS@0.2.0 y CANONICAL_INDEX@0.1.0 (aprobador en ambos casos: ABC Avícola
  Platform Owner, 2026-10-23; referencias: canonicalization-log "Aprobación humana —
  AGENTS@0.2.0" y "Aprobación humana — CANONICAL_INDEX@0.1.0").

## Pendientes de este índice
- Migrar GOU-LOG-001 a frontmatter canónico cuando el stakeholder lo autorice.
- Añadir entradas para los documentos de la siguiente entrega autorizada
  (project-vision, scope-and-mvp-definition, decision-register,
  assumptions-and-open-questions, acceptance-and-success-metrics) cuando se materialicen.
