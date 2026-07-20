# 2. Épicas y Requerimientos

## ¿Para qué sirve este documento?

Antes de escribir historias de usuario hay que entender **qué debe hacer el sistema**
(requerimientos funcionales), **con qué calidad** (requerimientos no funcionales) y
**cómo se organiza ese trabajo en bloques grandes** (épicas). Este documento se
construye después de la entrevista con el cliente/referente y antes del Product Backlog.

- Los **requerimientos funcionales (RF)** describen acciones concretas que el sistema
  debe permitir.
- Los **requerimientos no funcionales (RNF)** describen condiciones de calidad,
  seguridad, rendimiento, usabilidad o restricciones técnicas.
- Las **épicas** agrupan RF relacionados en grandes bloques de trabajo, que luego se
  dividen en historias de usuario más pequeñas.

---

## Plantilla

### Requerimientos funcionales

| Código | Requerimiento funcional |
| --- | --- |
| RF1 | |

### Requerimientos no funcionales

| Código | Requerimiento no funcional |
| --- | --- |
| RNF1 | |

### Épicas

| Código | Épica | Descripción |
| --- | --- | --- |
| EP1 | | |

### Estimación por épica

| Código | Épica | Estimación en puntos |
| --- | --- | --- |
| EP1 | | |
| **Total** | | |

---

## Ejemplo desarrollado (caso TamboTrace)

### Requerimientos funcionales

| Código | Requerimiento funcional |
| --- | --- |
| RF1 | El sistema debe permitir iniciar sesión con usuario y contraseña. |
| RF2 | El sistema debe permitir gestionar usuarios con diferentes roles. |
| RF3 | El sistema debe permitir registrar vacas con número de caravana, nombre opcional, raza, fecha de nacimiento, estado y observaciones. |
| RF4 | El sistema debe permitir modificar el estado de una vaca: en producción, secado, tratamiento o baja. |
| RF5 | El sistema debe permitir registrar ordeñes indicando fecha, turno, responsable y tanque asociado. |
| RF6 | El sistema debe permitir seleccionar las vacas participantes en cada ordeñe. |
| RF7 | El sistema debe permitir excluir vacas de un ordeñe indicando motivo. |
| RF8 | El sistema debe permitir crear lotes de leche a partir de un ordeñe. |
| RF9 | El sistema debe permitir registrar propiedades del lote: litros estimados, temperatura, grasa, proteína, células somáticas, resultado de antibióticos y observaciones. |
| RF10 | El sistema debe permitir completar propiedades de calidad después de creado el lote. |
| RF11 | El sistema debe permitir cerrar un lote para evitar modificaciones no autorizadas. |
| RF12 | El sistema debe permitir consultar la trazabilidad de un lote, mostrando fecha, turno, tanque, responsable, vacas incluidas, vacas excluidas y propiedades registradas. |
| RF13 | El sistema debe permitir buscar vacas por caravana, nombre o estado. |
| RF14 | El sistema debe permitir generar reportes exportables en PDF o planilla. |
| RF15 | El sistema debe registrar un historial de cambios sobre lotes cerrados o datos críticos. |

### Requerimientos no funcionales

| Código | Requerimiento no funcional |
| --- | --- |
| RNF1 | El sistema debe ser usable desde computadora, tablet o celular mediante navegador web. |
| RNF2 | La interfaz de carga de ordeñe debe ser simple y rápida para uso en sala de ordeñe. |
| RNF3 | El sistema debe responder las consultas principales en menos de 3 segundos bajo carga normal. |
| RNF4 | El sistema debe permitir acceso mediante roles: administrador, encargado, operario y veterinario. |
| RNF5 | Los datos sensibles deben protegerse mediante autenticación y autorización por rol. |
| RNF6 | El sistema debe realizar respaldos automáticos diarios. |
| RNF7 | El sistema debe registrar fecha, hora y usuario en cambios críticos. |
| RNF8 | El sistema debe tener disponibilidad suficiente para operar durante los horarios de ordeñe. |
| RNF9 | La solución debe poder desplegarse en hosting externo, ya que el cliente no posee servidor propio. |
| RNF10 | El sistema debe permitir crecer en cantidad de animales y lotes sin rediseñar la base de datos. |
| RNF11 | Los reportes deben ser claros, imprimibles y comprensibles para auditorías internas. |
| RNF12 | La primera versión debe considerar conectividad irregular, evitando pantallas pesadas o procesos largos en la carga diaria. |

### Épicas

| Código | Épica | Descripción |
| --- | --- | --- |
| EP1 | Gestión de usuarios y seguridad | Acceso al sistema, roles, permisos y control básico de seguridad. |
| EP2 | Gestión de animales | Registro, consulta y actualización de datos de vacas lecheras. |
| EP3 | Registro de ordeñes | Registro de ordeñes por fecha, turno, tanque, responsable y animales participantes. |
| EP4 | Gestión de lotes de leche | Creación, edición, cierre y consulta de lotes de leche. |
| EP5 | Propiedades de calidad del lote | Registro de datos productivos y resultados de análisis de calidad. |
| EP6 | Trazabilidad y reportes | Consulta integral de trazabilidad por lote y generación de reportes. |
| EP7 | Auditoría básica y respaldo | Historial de cambios críticos y respaldo periódico de la información. |
| EP8 | Capacitación y cierre | Manual básico, capacitación de usuarios y cierre formal del proyecto. |

### Estimación por épica

| Código | Épica | Estimación en puntos |
| --- | --- | --- |
| EP1 | Gestión de usuarios y seguridad | 12 |
| EP2 | Gestión de animales | 14 |
| EP3 | Registro de ordeñes | 16 |
| EP4 | Gestión de lotes de leche | 16 |
| EP5 | Propiedades de calidad del lote | 10 |
| EP6 | Trazabilidad y reportes | 14 |
| EP7 | Auditoría básica y respaldo | 6 |
| EP8 | Capacitación y cierre | 4 |
| **Total** | | **92 puntos** |

> **Nota:** la estimación total (92 puntos) supera la capacidad estimada del
> equipo para 4 sprints (80 puntos, a 20 puntos por sprint). Esto es normal en Scrum: el
> Product Backlog se prioriza por valor y riesgo, y el equipo negocia con el cliente qué
> se ajusta o se posterga (ver [historias de usuario](03_historias_de_usuario.md) y
> [backlog por sprint](04_backlog_por_sprint.md)).
