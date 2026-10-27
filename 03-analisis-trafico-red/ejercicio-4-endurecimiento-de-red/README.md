# Evaluación de riesgos de seguridad: Endurecimiento de la red

[Ver informe completo (PDF)](Informe-de-evaluacion-de-riesgos.pdf)

## Contexto del escenario

Como analista de seguridad en una organización de medios sociales que sufrió una **violación de datos** (quedó expuesta información personal de clientes: nombres y direcciones),se inspeccionó la red y se detectaron **cuatro vulnerabilidades**:

1. Los empleados comparten contraseñas.
2. La contraseña de administrador de la base de datos está por defecto.
3. Los cortafuegos no tienen reglas para filtrar el tráfico de entrada y salida.
4. No se usa autenticación multifactor (MFA).

El objetivo es proponer **prácticas de endurecimiento de la red** que se puedan aplicar de forma coherente para evitar futuras brechas.

## Preguntas de la actividad

**Parte 1 — Seleccionar hasta tres herramientas y métodos de endurecimiento**
- ¿Qué tareas de endurecimiento serían la forma más eficaz de responder a esta situación?

**Parte 2 — Explicar las recomendaciones**
- ¿Por qué es eficaz cada técnica de endurecimiento recomendada?
- ¿Con qué frecuencia debe implementarse?

---

## Parte 1: Herramientas y métodos seleccionados

1. **Autenticación multifactor (MFA):** exige verificar la identidad de dos o más formas (contraseña + OTP, huella o PIN) para acceder.
2. **Políticas de contraseñas:** salting y hashing, prohibición de contraseñas por defecto o reutilizadas y límite de intentos de inicio de sesión.
3. **Filtrado de puertos y mantenimiento del cortafuegos:** permitir solo los puertos necesarios, bloquear el resto y revisar/actualizar las reglas con regularidad para controlar el tráfico de entrada y salida.

## Parte 2: Recomendaciones (eficacia y frecuencia)

- **MFA** → aunque una contraseña se comparta, quede por defecto o sea adivinada, el atacante no tiene el segundo factor, por lo que no accede. Neutraliza la ausencia de MFA, el uso compartido y la contraseña por defecto, y mitiga la fuerza bruta. *Frecuencia:* se configura una vez y se mantiene.
- **Políticas de contraseñas** → impiden contraseñas débiles, por defecto o reutilizadas (salting/hashing según NIST, límite de intentos). Corrigen la contraseña de administrador por defecto y desalientan compartir credenciales. *Frecuencia:* continua.
- **Filtrado de puertos + mantenimiento del cortafuegos** → controlan qué tráfico entra y sale, subsanando la falta de reglas; las reglas se actualizan ante eventos de seguridad y protegen frente a DoS/DDoS. *Frecuencia:* filtrado una vez y revisión periódica; mantenimiento regular.

---

*Ejercicio 4 — Curso 3 (Seguridad de redes) del Certificado Profesional de Ciberseguridad de Google. Trabajo propio basado en un escenario ficticio del curso.*
