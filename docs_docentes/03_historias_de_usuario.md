# 3. Historias de Usuario

## ¿Para qué sirve este documento?

Las historias de usuario (HU) traducen los requerimientos y épicas en unidades de
trabajo chicas, estimables y priorizables, escritas desde el punto de vista de quien
usa el sistema. Son la base del Product Backlog (ver
[backlog por sprint](04_backlog_por_sprint.md)).

**Formato:**

> Como **[tipo de usuario]**, quiero **[acción o necesidad]**, para **[beneficio o resultado esperado]**.

Cada historia debe tener:
- Un **ID** único (HU1, HU2, ...).
- **Criterios de aceptación**: condiciones concretas que indican cuándo la historia
  está terminada.
- Una **estimación** en puntos de historia.
- Una **prioridad** (Alta / Media / Baja).

---

## Plantilla

### Escala de estimación sugerida

- 1 punto: tarea muy pequeña.
- 3 puntos: tarea simple, con cierta lógica.
- 5 puntos: tarea media.
- 8 puntos: tarea compleja.
- 13 puntos: tarea grande o riesgosa.

### Historia detallada

**ID:**
**Historia:** Como [rol], quiero [acción], para [beneficio].
**Criterios de aceptación:**
- [ ]
- [ ]
**Puntos:**
**Prioridad:**

### Listado de historias

| ID | Historia de usuario | Puntos | Prioridad |
| --- | --- | --- | --- |
| HU1 | | | |

---

## Ejemplo desarrollado (caso TamboTrace)

### Historias detalladas (ejemplo de nivel de detalle esperado)

**ID:** HU7
**Historia:** Como operario, quiero seleccionar las vacas participantes en un ordeñe,
para saber qué animales aportaron a la producción.
**Criterios de aceptación:**
- [ ] Puedo ver el listado de vacas activas (en producción) al crear un ordeñe.
- [ ] Puedo marcar/desmarcar vacas individualmente como participantes.
- [ ] El ordeñe no se puede guardar sin al menos una vaca participante.
- [ ] El sistema guarda la lista de vacas asociadas al ordeñe para consultas posteriores.
**Puntos:** 8
**Prioridad:** Alta

---

**ID:** HU12
**Historia:** Como encargado, quiero cerrar un lote, para evitar modificaciones
accidentales.
**Criterios de aceptación:**
- [ ] Solo un usuario con rol encargado o administrador puede cerrar un lote.
- [ ] Un lote cerrado no permite editar vacas, litros ni propiedades de calidad.
- [ ] El sistema muestra un mensaje de confirmación antes de cerrar.
- [ ] El sistema registra fecha, hora y usuario responsable del cierre.
**Puntos:** 5
**Prioridad:** Alta

---

**ID:** HU13
**Historia:** Como administración, quiero consultar un lote y ver vacas incluidas,
excluidas y propiedades, para responder consultas de trazabilidad.
**Criterios de aceptación:**
- [ ] La consulta muestra fecha, turno, tanque y responsable del lote.
- [ ] La consulta lista las vacas incluidas y las excluidas, con motivo de exclusión.
- [ ] La consulta muestra las propiedades de calidad cargadas (o indica cuáles faltan).
- [ ] La consulta responde en menos de 3 segundos con datos de un lote típico.
**Puntos:** 8
**Prioridad:** Alta

### Listado completo de historias

| ID | Historia de usuario | Puntos | Prioridad |
| --- | --- | --- | --- |
| HU1 | Como administrador, quiero iniciar sesión en el sistema, para acceder de forma segura. | 3 | Alta |
| HU2 | Como administrador, quiero crear usuarios y asignar roles, para controlar qué puede hacer cada persona. | 5 | Alta |
| HU3 | Como encargado, quiero registrar una vaca con sus datos principales, para mantener actualizado el rodeo. | 5 | Alta |
| HU4 | Como encargado, quiero buscar vacas por caravana o estado, para encontrarlas rápidamente. | 3 | Alta |
| HU5 | Como encargado, quiero cambiar el estado de una vaca, para indicar si está en producción, secado, tratamiento o baja. | 3 | Alta |
| HU6 | Como operario, quiero registrar un ordeñe con fecha, turno, tanque y responsable, para documentar la producción diaria. | 5 | Alta |
| HU7 | Como operario, quiero seleccionar las vacas participantes en un ordeñe, para saber qué animales aportaron a la producción. | 8 | Alta |
| HU8 | Como operario, quiero excluir vacas de un ordeñe indicando motivo, para evitar incluir animales en tratamiento. | 5 | Alta |
| HU9 | Como encargado, quiero crear un lote de leche a partir de un ordeñe, para identificar formalmente la producción. | 8 | Alta |
| HU10 | Como encargado, quiero cargar litros estimados y tanque asociado al lote, para registrar datos productivos básicos. | 3 | Alta |
| HU11 | Como administración, quiero cargar resultados de calidad del lote, para completar información recibida después del laboratorio. | 5 | Media |
| HU12 | Como encargado, quiero cerrar un lote, para evitar modificaciones accidentales. | 5 | Alta |
| HU13 | Como administración, quiero consultar un lote y ver vacas incluidas, excluidas y propiedades, para responder consultas de trazabilidad. | 8 | Alta |
| HU14 | Como administración, quiero exportar un reporte de trazabilidad, para presentarlo en auditorías o controles internos. | 5 | Media |
| HU15 | Como veterinario, quiero registrar observaciones sanitarias de una vaca, para documentar situaciones relevantes. | 5 | Media |
| HU16 | Como administrador, quiero ver historial de cambios críticos, para saber quién modificó información sensible. | 5 | Media |
| HU17 | Como administrador, quiero que el sistema realice respaldos automáticos, para reducir riesgo de pérdida de datos. | 3 | Media |
| HU18 | Como usuario nuevo, quiero recibir una guía básica de uso, para aprender el flujo principal del sistema. | 2 | Baja |

> **Nota:** las historias HU19, HU20 y HU21 no forman parte de este listado
> inicial: surgen durante el proyecto a partir del feedback del cliente en los
> [sprint reviews](05_sprint_review.md), y quedan registradas en el
> [control de cambios](06_control_de_cambios.md).
