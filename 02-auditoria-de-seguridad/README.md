# Proyecto 2 — Auditoría de Seguridad Interna (Botium Toys)

**Competencia:** Controles de seguridad y cumplimiento normativo
**Marco de referencia:** NIST Cybersecurity Framework (CSF)
**Escenario:** Caso práctico ficticio del Certificado Profesional de Ciberseguridad de Google.

---

## Contexto del caso

Botium Toys es una pequeña empresa de juguetería (tienda física y comercio electrónico) cuyo departamento de TI solicita una auditoría de seguridad interna para evaluar su postura actual y determinar qué controles y buenas prácticas de cumplimiento debe implementar.

### Alcance y objetivos

- **Alcance:** todo el programa de seguridad de Botium Toys. Se evalúan todos los activos junto con los procesos y procedimientos internos relacionados con la implementación de controles y buenas prácticas de cumplimiento.
- **Objetivo:** evaluar los activos existentes y completar la lista de verificación de controles y cumplimiento para determinar qué medidas deben implementarse para mejorar la postura de seguridad.

### Evaluación de riesgo

- **Puntuación de riesgo:** 8 de 10 (alto), por la falta de controles y de adherencia a buenas prácticas de cumplimiento.
- **Impacto potencial por pérdida de activos:** medio (el departamento de TI no tiene identificados todos los activos en riesgo).
- **Riesgo de sanciones regulatorias:** alto (no se cumplen plenamente las normativas que mantienen privada y segura la información crítica).

---

## Evaluación de controles

*¿Botium Toys cuenta actualmente con este control?*

| Control | ¿Implementado? |
|---------|:---:|
| Principio de mínimo privilegio (Least Privilege) | No |
| Plan de recuperación ante desastres | No |
| Políticas de contraseñas (existen pero insuficientes) | No |
| Separación de funciones | No |
| Firewall | Sí |
| Sistema de detección de intrusiones (IDS) | No |
| Copias de seguridad (Backups) | No |
| Software antivirus | Sí |
| Monitoreo/mantenimiento manual de sistemas heredados (sin calendario formal) | No |
| Cifrado (Encryption) | No |
| Sistema de gestión de contraseñas | No |
| Cerraduras (oficinas, tienda, bodega) | Sí |
| Vigilancia CCTV | Sí |
| Detección/prevención de incendios | Sí |

---

## Evaluación de cumplimiento

### PCI DSS (Estándar de Seguridad de Datos de la Industria de Tarjetas de Pago)

| Buena práctica | ¿Cumple? |
|----------------|:---:|
| Solo usuarios autorizados acceden a la información de tarjetas de crédito | No |
| La información de tarjetas se almacena, procesa y transmite en un entorno seguro | No |
| Cifrado en los puntos de contacto y datos de transacciones | No |
| Políticas de gestión segura de contraseñas | No |

### GDPR (Reglamento General de Protección de Datos)

| Buena práctica | ¿Cumple? |
|----------------|:---:|
| Los datos de clientes de la U.E. se mantienen privados/seguros | No |
| Plan para notificar a clientes de la U.E. dentro de 72 h ante una brecha | Sí |
| Datos correctamente clasificados e inventariados | No |
| Políticas de privacidad aplicadas para documentar y mantener los datos | Sí |

### SOC (System and Organization Controls, tipo 1 y tipo 2)

| Buena práctica | ¿Cumple? |
|----------------|:---:|
| Políticas de acceso de usuarios establecidas | No |
| Datos sensibles (PII/SPII) confidenciales/privados | No |
| Integridad de datos (consistentes, completos, exactos y validados) | Sí |
| Datos disponibles para los individuos autorizados | Sí |

---

## Recomendaciones

Priorizar la implementación del **principio de mínimo privilegio** y la **separación de funciones**, junto con el **cifrado** de los datos sensibles, un **sistema centralizado de gestión de contraseñas**, **copias de seguridad** y un **plan de recuperación ante desastres**. También se recomienda implementar un **IDS**, fortalecer la política de contraseñas y establecer un calendario formal para el mantenimiento de sistemas heredados.

Estas medidas reducirían el riesgo para los activos y mejorarían la postura general de seguridad y cumplimiento de Botium Toys.

---

*Proyecto 2 del Certificado Profesional de Ciberseguridad de Google — trabajo propio basado en un escenario ficticio del curso.*
