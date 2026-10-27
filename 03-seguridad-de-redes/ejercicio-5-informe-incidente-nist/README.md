# Análisis de incidente de seguridad (NIST CSF): Ataque DoS por inundación ICMP

[Ver informe completo (PDF)](Informe-incidente-DoS-ICMP-NIST.pdf)

Análisis de un incidente de red aplicando las cinco funciones principales del **Marco de Ciberseguridad del NIST (NIST CSF)**: Identificar, Proteger, Detectar, Responder y Recuperar.

## Contexto del escenario

Como analista de ciberseguridad en una empresa multimedia (diseño web, diseño gráfico y marketing en redes sociales), la organización sufrió un **ataque de denegación de servicio (DoS)** que comprometió la red interna durante unas dos horas. Los servicios de red dejaron de responder por una avalancha de **paquetes ICMP entrantes (ping flood)** enviada por un actor malicioso externo a través de un **cortafuegos sin configurar**, lo que permitió saturar la red.

---

## Resumen

La red interna sufrió un ataque DoS que la mantuvo comprometida durante aproximadamente dos horas. Los servicios de red dejaron de responder debido a una avalancha de paquetes ICMP entrantes (ping flood), lo que impidió que el tráfico interno legítimo accediera a los recursos. La investigación determinó que un actor malicioso externo envió la inundación de pings ICMP a través de un cortafuegos sin configurar; esa vulnerabilidad le permitió saturar la red. El equipo de gestión de incidentes respondió bloqueando los paquetes ICMP entrantes, poniendo fuera de línea los servicios no críticos y restableciendo los servicios críticos. El impacto fue sobre la **disponibilidad**: indisponibilidad temporal de los servicios internos, sin pérdida de datos reportada.

## Identificar

- **Tipo de ataque:** denegación de servicio (DoS) mediante inundación de paquetes ICMP (ping flood).
- **Sistemas afectados:** los servicios de red internos y todos los recursos de la red interna, inaccesibles durante unas dos horas.
- **Origen:** un actor malicioso externo que envió el tráfico ICMP a través de internet.
- **Causa / vulnerabilidad:** un cortafuegos sin configurar que no limitaba ni filtraba los paquetes ICMP entrantes.
- Se auditan redes internas, sistemas, dispositivos y privilegios de acceso para detectar otras brechas similares (p. ej., reglas de cortafuegos ausentes).

## Proteger

- Nueva regla de cortafuegos para **limitar la tasa (rate limiting)** de los paquetes ICMP entrantes.
- **Verificación de la IP de origen** en el cortafuegos para detectar IP falsificadas (anti-spoofing) en los paquetes ICMP.
- **Endurecimiento de la configuración** del cortafuegos.
- **Principio de mínimo privilegio** y revisión de los accesos.
- **Capacitación** del personal para reconocer y reportar actividad anómala.

## Detectar

- **Software de supervisión de red** para identificar patrones de tráfico anómalos (picos de ICMP).
- **IDS/IPS** para filtrar el tráfico ICMP con características sospechosas y alertar o bloquear en tiempo real.
- **Análisis de los registros del cortafuegos**, idealmente centralizados en un **SIEM**, para detectar ICMP externo entrante desde direcciones IP no confiables.
- Supervisión continua del tráfico, distinguiendo entre usuarios autorizados y no autorizados.

## Responder

- **Contención:** bloquear los paquetes ICMP entrantes y aislar o poner fuera de línea los servicios no críticos afectados.
- **Neutralización:** aplicar reglas del cortafuegos (rate limiting y bloqueo de la IP de origen) y el filtrado del IDS/IPS.
- **Análisis:** usar los registros del cortafuegos, las capturas de tráfico y las alertas del IDS/IPS para determinar origen, volumen y método del ataque.
- **Comunicación:** informar al equipo de TI y a la gerencia según los procedimientos.
- **Mejora:** actualizar reglas y procedimientos tras el incidente.

## Recuperar

- Restablecer primero los **servicios de red críticos** y luego volver a poner en línea los no críticos, una vez verificado que el tráfico malicioso cesó y que la red opera con normalidad.
- Como el impacto fue sobre la disponibilidad y no hubo pérdida de datos reportada, no se requirió restauración desde copias de seguridad; de haber datos afectados, se restaurarían desde el último respaldo.
- **Mejoras:** documentar el incidente, revisar periódicamente las reglas del cortafuegos y actualizar el plan de recuperación para gestionar mejor futuros incidentes.

---

*Trabajo propio basado en un escenario ficticio del Certificado Profesional de Ciberseguridad de Google (Curso 3 — Seguridad de redes). El análisis aplica el Marco de Ciberseguridad del NIST (NIST CSF), de dominio público.*
```
