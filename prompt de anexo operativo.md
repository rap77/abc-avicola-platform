======================================================================
ANEXO OPERATIVO: ROADMAP DE DESARROLLO SUBORDINADO A LA DOCUMENTACIÓN CANÓNICA
======================================================================

El siguiente anexo proviene de un prompt clásico de planificación de software.
No debe ejecutarse como instrucción independiente ni prevalecer sobre la
metodología canónica. Su propósito es asegurar que la documentación canónica
cubra todos los artefactos necesarios para una implementación profesional.

Cuando corresponda, convierte cada punto del roadmap en documentos canónicos,
decisiones trazables, quality gates y contratos atómicos.

1. Definición del proyecto
   Generar documentos de:
   - visión;
   - problema;
   - propuesta de valor;
   - usuarios;
   - actores;
   - clientes;
   - operadores;
   - administradores;
   - métricas de éxito;
   - diferenciadores frente a alternativas existentes.

2. Análisis de requerimientos
   Generar documentos de:
   - requisitos funcionales;
   - requisitos no funcionales;
   - priorización MoSCoW o RICE;
   - user journeys;
   - casos de uso;
   - criterios de aceptación;
   - flujos de error;
   - flujos de excepción.

3. Diseño del software
   Generar documentos de:
   - arquitectura lógica;
   - arquitectura de componentes;
   - arquitectura de datos;
   - arquitectura de seguridad;
   - arquitectura de streaming;
   - arquitectura de pagos;
   - arquitectura de integración;
   - ADRs;
   - modelo físico condicional;
   - lineamientos UI/UX;
   - accesibilidad.

   No elegir stack tecnológico antes de tener suficientes decisiones de
   producto, dominio, seguridad, escala, presupuesto y operaciones.

4. Desarrollo del software
   Generar documentos de:
   - estrategia de implementación;
   - orden de implementación;
   - backlog atómico;
   - contratos atómicos;
   - estándar de ramas Git;
   - coding standards;
   - dependency policy;
   - definición de done;
   - política de revisión de código;
   - política de uso de agentes IA;
   - límites de gasto de tokens/APIs.

   Las prácticas de OOP y patrones de diseño deben recomendarse solo cuando
   aporten claridad, mantenibilidad y testabilidad. No imponer OOP como
   obligación dogmática si el stack o el dominio sugieren otro paradigma.

5. Pruebas del software
   Generar documentos de:
   - testing policy;
   - pruebas unitarias;
   - pruebas de integración;
   - pruebas E2E;
   - pruebas de seguridad;
   - pruebas de acceso a video;
   - pruebas de pagos;
   - pruebas de roles;
   - pruebas de tenancy;
   - pruebas de performance;
   - evidencia requerida;
   - quality gates.

   Aplicar SDD/TDD:
   - primero especificación;
   - luego criterios de aceptación;
   - luego tests;
   - luego implementación;
   - luego evidencia;
   - luego verificación.

6. Implementación y puesta en marcha
   Generar documentos de:
   - estrategia de ambientes;
   - despliegue;
   - rollback;
   - backup;
   - restore;
   - monitoreo;
   - alertas;
   - incidentes;
   - piloto;
   - producción;
   - soporte post-lanzamiento;
   - mantenimiento;
   - runbooks.

   Mantener separados:
   - IMPLEMENTED;
   - VERIFIED;
   - PILOT_READY;
   - PRODUCTION_READY.

7. Documentación
   Generar documentos de:
   - canonical index;
   - decision register;
   - glosario;
   - documentación técnica;
   - manuales operativos;
   - manuales de administrador;
   - guía de soporte;
   - documentación de APIs;
   - documentación de seguridad;
   - documentación de cumplimiento.

Restricciones del anexo:
- No iniciar implementación.
- No autoaprobar documentos.
- No crear infraestructura real.
- No procesar datos reales.
- No ejecutar pagos reales.
- No publicar contenido real.
- No desplegar a producción.
- Toda decisión técnica relevante debe quedar registrada como PROPOSED,
  DECISION_REQUIRED o ACCEPTED_DECISION según corresponda.

Si existe conflicto entre este anexo y el Prompt Universal, prevalece el
Prompt Universal.