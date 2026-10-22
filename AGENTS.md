---
id: AGT-001
title: Reglas de Operación para Agentes de IA
version: 0.2.0
status: PROPOSED
date: 2026-10-23
author: Qwen3.7
tags: [governance, agents, rules, operations]
supersedes: AGENTS.md@0.1.0
changelog: "Incorpora ajustes de gobernanza A (separación estado documental/entrega), B (autorizaciones acotadas) y C (definición de contrato atómico) solicitados en sesión de descubrimiento."
---

# Reglas de Operación para Agentes de IA - ABC Avícola Platform

## 1. Autoridad Humana y Aprobación
- Ningún agente puede autoaprobar documentos, cambiar estados a `APPROVED` o `IMPLEMENTED`, ni interpretar el silencio como consentimiento.
- Toda aprobación debe ser humana, explícita y documentada.
- Un documento `APPROVED` NO autoriza automáticamente su implementación.

## 2. Prohibiciones Absolutas (Sin Autorización Separada)
- No escribir código funcional.
- No instalar dependencias.
- No crear infraestructura real.
- No ejecutar migraciones de datos reales.
- No procesar datos reales de usuarios ni pagos reales.
- No desplegar a producción.
- No fijar Stripe, DRM, marca de agua ni certificados como dependencias obligatorias sin aprobación específica.

## 3. Estados — Separación Documental y de Entrega [AJUSTE A]
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

## 4. Alcance de las Autorizaciones [AJUSTE B]
- Toda autorización debe indicar objeto, alcance y límites. Aprobar un documento NO autoriza instalar dependencias, implementar sus funcionalidades, acceder a datos reales ni desplegar.
- Cada autorización queda registrada con: quién autoriza, qué autoriza exactamente, bajo qué límites y con qué vigencia.
- Una modificación sustancial de un documento aprobado debe volver a revisión (`IN_REVIEW`) antes de considerarse válida; no se materializa silenciosamente sobre la versión aprobada.

## 5. Metodología de Implementación — Contrato Atómico [AJUSTE C]
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

## 6. Materialización y Trazabilidad
- Toda aprobación se materializa en el repo bajo `docs/` con frontmatter canónico.
- Se debe actualizar `docs/CANONICAL_INDEX.md` y `docs/00-governance/canonicalization-log.md` en cada cambio de estado.
- Todo documento canónico debe incluir frontmatter YAML con `id`, `title`, `version`, `status`, `date`, `author` y `tags`.

## 7. Metodología de Trabajo por Rondas
- Las entrevistas con el stakeholder se realizan por rondas de 3 a 7 preguntas.
- Prohibido realizar interrogatorios masivos.
- Cada ronda debe enfocarse en vacíos reales no cubiertos por la documentación existente.

## 8. Separación de Contexto y Normativa
- Los archivos de análisis (`ABC Avicola Analisis 1.md`, `Estudio Portal 3tres3.md`) son evidencia de contexto, NO normativa aprobada.
- La fuente de verdad es únicamente la documentación canónica en `docs/` con estado `APPROVED` o superior.
