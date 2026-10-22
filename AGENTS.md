---
document_id: AGENTS
title: Reglas de Operación para Agentes de IA - ABC Avícola Platform
version: 0.2.0
status: APPROVED
authority: NORMATIVE
document_owner:
  - ABC Avícola Platform Owner
language: es
created_at: 2026-10-23
last_reviewed_at: 2026-10-23
approved_at: 2026-10-23
supersedes:
  - AGENTS@0.1.0
superseded_by: []
source_documents:
  - prompt universal.md
  - prompt de anexo operativo.md
related_documents:
  - docs/00-governance/canonicalization-log.md
change_control: DECISION_CONTROLLED
obsidian_compatible: true
---

# Reglas de Operación para Agentes de IA - ABC Avícola Platform

## 1. Autoridad Humana y Aprobación
- Ningún agente puede autoaprobar documentos, cambiar estados a `APPROVED` o `IMPLEMENTED`, ni interpretar el silencio como consentimiento.
- Toda aprobación debe ser humana, explícita y documentada.
- Un documento `APPROVED` NO autoriza automáticamente su implementación.

## 2. Fuentes Normativas y Precedencia
Jerarquía normativa del proyecto (de mayor a menor precedente):

1. `prompt universal.md` — METODOLOGÍA NORMATIVA. Prevalece sobre cualquier preferencia del modelo. Define estados, gates, formato de entrega, prohibiciones y ciclo de aprobación.
2. `prompt de anexo operativo.md` — COMPLEMENTO NORMATIVO subordinado. En conflicto, prevalece `prompt universal.md`.
3. `AGENTS.md` — ADAPTADOR DEL REPOSITORIO. No puede contradecir 1 ni 2; si lo hace, prevalecen 1 y 2 y se registra el conflicto normativo.
4. `ABC Avicola Analisis 1.md` y `Estudio Portal 3tres3.md` — EVIDENCIA DE CONTEXTO. No normativos: informan, no generan obligaciones.
5. `docs/**` — DOCUMENTACIÓN CANÓNICA DEL PROYECTO. Normativa interna una vez `APPROVED`; siempre derivada de 1-3 y de decisiones humanas.

Alcance de esta jerarquía: rige la metodología, el proceso y la interpretación normativa durante el descubrimiento y la documentación. Para implementación y ejecución aplica la precedencia de la Sección 20 de `prompt universal.md`: la documentación canónica aprobada y los contratos aprobados prevalecen sobre este adaptador y sobre cualquier instrucción de agente.

## 3. Obligación de Lectura en Preflight
En CADA sesión nueva, antes de responder o modificar cualquier cosa:
- Leer `prompt universal.md` y `prompt de anexo operativo.md`.
- Leer `AGENTS.md`.
- Leer `docs/CANONICAL_INDEX.md` y `docs/00-governance/canonicalization-log.md`.
- Declarar en la primera entrega qué fuentes leyó y sus SHA-256.

## 4. Prohibiciones Absolutas (Sin Autorización Separada)
- No escribir código funcional.
- No instalar dependencias.
- No crear infraestructura real.
- No ejecutar migraciones de datos reales.
- No procesar datos reales de usuarios ni pagos reales.
- No desplegar a producción.
- No fijar Stripe, DRM, marca de agua ni certificados como dependencias obligatorias sin aprobación específica.

## 5. Estados — Separación Documental y de Entrega [AJUSTE A]
Mantener estricta separación entre dos ejes de estado independientes:

```text
Estado documental:
DRAFT → PROPOSED → IN_REVIEW → APPROVED
                              ↓
                         SUPERSEDED

Estado de entrega:
NOT_STARTED → IN_PROGRESS → IMPLEMENTED → VERIFIED
```

Definiciones — estado documental:
- `DRAFT`: Borrador interno, aún no presentado a revisión.
- `PROPOSED`: Propuesta inicial, requiere revisión.
- `IN_REVIEW`: En evaluación por stakeholders.
- `APPROVED`: Aprobado por humano, listo para planificación.
- `SUPERSEDED`: Reemplazado por una versión posterior.

Definiciones — estado de entrega:
- `NOT_STARTED`: No se ha iniciado trabajo de implementación.
- `IN_PROGRESS`: Implementación en curso bajo autorización vigente.
- `IMPLEMENTED`: Código/infraestructura desplegada según el documento aprobado.
- `VERIFIED`: Validado contra criterios de aceptación.

Reglas de relación entre ejes:
- Un documento puede estar `APPROVED` mientras su funcionalidad sigue `NOT_STARTED` o `IN_PROGRESS`.
- El agente puede ejecutar pruebas autorizadas y adjuntar evidencia al registro correspondiente, pero no debe confundir ese resultado con aceptación humana final (`APPROVED`) ni con validación formal (`VERIFIED`).
- `PILOT_READY` y `PRODUCTION_READY` son estados operativos separados (Sección 2.3 y Ronda 12 de `prompt universal.md`): NO se implican desde `VERIFIED` y requieren sus propios quality gates y aprobación humana explícita.

## 6. Alcance de las Autorizaciones [AJUSTE B]
- Toda autorización debe indicar objeto, alcance y límites. Aprobar un documento NO autoriza instalar dependencias, implementar sus funcionalidades, acceder a datos reales ni desplegar.
- Cada autorización queda registrada con: quién autoriza, qué autoriza exactamente, bajo qué límites y con qué vigencia.
- Una modificación sustancial de un documento aprobado debe volver a revisión (`IN_REVIEW`) antes de considerarse válida; no se materializa silenciosamente sobre la versión aprobada.

## 7. Metodología de Implementación — Contrato Atómico [AJUSTE C]
Un contrato atómico representa una unidad de trabajo comprobable. No se crea un contrato separado para cada etiqueta o ajuste visual menor.

Cada contrato debe contener:
- Objetivo
- Precondiciones
- Incluye
- Excluye
- Archivos o componentes afectados
- Reglas y permisos
- Criterios de aceptación
- Pruebas y evidencia
- Riesgos
- Reversión, cuando aplique
- Autorización requerida

Toda implementación futura debe seguir contratos atómicos con SDD/TDD y quality gates.
- La carga manual de datos de mercado es el mecanismo operativo propuesto para CUT-1. No se implementará integración automatizada hasta confirmar fuente.
- No se asume migración masiva del sitio WordPress anterior hasta validar inventario con el cliente.

## 8. Materialización y Trazabilidad
- Toda aprobación se materializa en el repo bajo `docs/` con frontmatter canónico.
- Se debe actualizar `docs/CANONICAL_INDEX.md` y `docs/00-governance/canonicalization-log.md` en cada cambio de estado.
- Todo documento canónico debe incluir el frontmatter canónico definido en la Sección 9 de `prompt universal.md` (`document_id`, `title`, `version`, `status`, `authority`, `document_owner`, `language`, `created_at`, `last_reviewed_at`, `approved_at`, `supersedes`, `superseded_by`, `source_documents`, `related_documents`, `change_control`, `obsidian_compatible`).

## 9. Metodología de Trabajo por Rondas
- Las entrevistas con el stakeholder se realizan por rondas de 3 a 7 preguntas.
- Prohibido realizar interrogatorios masivos.
- Cada ronda debe enfocarse en vacíos reales no cubiertos por la documentación existente.

## 10. Separación de Contexto y Normativa
- Los archivos de análisis (`ABC Avicola Analisis 1.md`, `Estudio Portal 3tres3.md`) son evidencia de contexto, NO normativa aprobada.
- La fuente de verdad es únicamente la documentación canónica en `docs/` con estado `APPROVED` o superior.
