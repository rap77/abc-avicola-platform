---
id: AGT-001
title: Reglas de Operación para Agentes de IA
version: 0.1.0
status: PROPOSED
date: 2026-10-22
author: Qwen3.7
tags: [governance, agents, rules, operations]
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

## 3. Estados Documentales
Mantener estricta separación entre:
- `PROPOSED`: Propuesta inicial, requiere revisión.
- `IN_REVIEW`: En evaluación por stakeholders.
- `APPROVED`: Aprobado por humano, listo para planificación.
- `IMPLEMENTED`: Código/infraestructura desplegada según el documento aprobado.
- `VERIFIED`: Validado contra criterios de aceptación.

## 4. Metodología de Implementación
- Toda implementación futura debe seguir contratos atómicos con SDD/TDD y quality gates.
- La carga manual de datos de mercado es el mecanismo operativo para CUT-1. No se implementará integración automatizada hasta confirmar fuente.
- No se asume migración masiva del sitio WordPress anterior hasta validar inventario con el cliente.

## 5. Materialización y Trazabilidad
- Toda aprobación se materializa en el repo bajo `docs/` con frontmatter canónico.
- Se debe actualizar `docs/CANONICAL_INDEX.md` y `docs/00-governance/canonicalization-log.md` en cada cambio de estado.
- Todo documento canónico debe incluir frontmatter YAML con `id`, `title`, `version`, `status`, `date`, `author` y `tags`.

## 6. Metodología de Trabajo por Rondas
- Las entrevistas con el stakeholder se realizan por rondas de 3 a 7 preguntas.
- Prohibido realizar interrogatorios masivos.
- Cada ronda debe enfocarse en vacíos reales no cubiertos por la documentación existente.

## 7. Separación de Contexto y Normativa
- Los archivos de análisis (`ABC Avicola Analisis 1.md`, `Estudio Portal 3tres3.md`) son evidencia de contexto, NO normativa aprobada.
- La fuente de verdad es únicamente la documentación canónica en `docs/` con estado `APPROVED` o superior.
