# 1. Project Charter (Acta de Constitución del Proyecto)

## ¿Para qué sirve este documento?

El Project Charter es el primer documento formal del proyecto. Autoriza su existencia,
define de forma breve qué se va a construir, quién lo pide, quién lo hace y qué se
considera éxito. No entra en detalle técnico: eso se desarrolla después en épicas,
requerimientos e historias de usuario.

Se redacta **una sola vez**, al inicio, luego de la primera reunión o entrevista con el
cliente/referente institucional. Si el alcance cambia drásticamente durante el proyecto,
el cambio se documenta en el [control de cambios](06_control_de_cambios.md), no
reescribiendo el charter.

---

## Plantilla

**Nombre del proyecto:**
**Cliente / patrocinador (sponsor):**
**Director del proyecto / Scrum Master:**
**Equipo:**
**Fecha de inicio:**
**Duración estimada:**

**Situación inicial del cliente:**
(Rubro, tamaño, contexto, nivel tecnológico actual, cómo resuelve hoy el problema)

**Necesidad planteada por el cliente:**
(Cita textual o resumen de lo que el cliente pidió en la primera reunión)

**Objetivo del proyecto:**
(Qué problema de negocio resuelve el sistema, en una o dos frases)

**Justificación del proyecto:**
(Por qué vale la pena hacerlo, qué pasa si no se hace)

**Visión del producto:**
(Descripción breve de la solución propuesta)

**Alcance incluido (primera versión):**
1. ...

**Alcance excluido (queda para etapas futuras):**
1. ...

**Stakeholders principales:**

| Rol | Persona / referente | Responsabilidad |
| --- | --- | --- |
| | | |

**Riesgos iniciales:**

| Riesgo | Impacto posible |
| --- | --- |
| | |

**Plazo y metodología:**
(Cantidad de sprints, duración de cada sprint, fecha estimada de entrega final)

**Presupuesto / esfuerzo estimado:**

**Criterios de éxito:**
(Cómo se sabe que el proyecto cumplió su objetivo)

---

## Ejemplo desarrollado (caso TamboTrace)

**Nombre del proyecto:** TamboTrace — Sistema de trazabilidad para establecimiento lechero

**Cliente / patrocinador (sponsor):** Sr. Antonio Romualdo Rogelio Roldán, dueño de la Estancia "MuchaTeta"

**Director del proyecto / Scrum Master:** Líder del equipo de desarrollo

**Equipo:** 1 Líder/Scrum Master, 3 desarrolladores (frontend y backend)

**Fecha de inicio:** semana 1 del proyecto

**Duración estimada:** 8 semanas (4 sprints de 2 semanas)

**Situación inicial del cliente:**
Establecimiento lechero mediano (aprox. 280 vacas), producción de leche cruda para
industria local con intención de mejorar procesos para exportación. Nivel tecnológico
medio-bajo: registro actual en planillas, cuadernos y archivos dispersos.

**Necesidad planteada por el cliente:**
> "Queremos un sistema que nos ayude a tener trazabilidad. La idea es poder identificar
> cada lote de leche, saber qué vacas participaron, registrar datos importantes de
> producción y calidad, y tener reportes que nos sirvan para demostrar orden y control
> si avanzamos hacia ventas más exigentes o exportación."

**Objetivo del proyecto:**
Desarrollar una aplicación web que permita registrar animales, ordeñes y lotes de leche,
y consultar la trazabilidad completa de cada lote producido.

**Justificación del proyecto:**
Hoy la información está dispersa en papel y planillas separadas. Reconstruir de qué
animales salió un lote, en qué fecha se ordeñó y qué controles tuvo es lento y poco
confiable, lo que dificulta responder ante controles de calidad o exportación.

**Visión del producto:**
Aplicación web responsive para registrar vacas, controlar ordeñes, generar lotes de
leche, asociar animales a cada lote, cargar propiedades de calidad y obtener reportes
de trazabilidad. La primera versión resuelve el circuito básico de producción y
trazabilidad, sin funcionalidades avanzadas que aumenten costo o plazo.

**Alcance incluido (primera versión):**
1. Gestión de usuarios y roles.
2. Registro de vacas y su estado (producción, secado, tratamiento, baja).
3. Registro de ordeñes por fecha, turno y responsable, con vacas participantes/excluidas.
4. Creación de lotes de leche a partir de un ordeñe.
5. Registro de propiedades de calidad del lote.
6. Cierre de lote para evitar modificaciones no autorizadas.
7. Consulta de trazabilidad por lote y reporte exportable.
8. Capacitación básica y manual breve.

**Alcance excluido (queda para etapas futuras):**
1. Integración automática con sensores de ordeñe o caravanas RFID.
2. Aplicación móvil nativa y sincronización offline completa.
3. Integración directa con laboratorios externos.
4. Módulo veterinario completo, facturación y control de alimentación.

**Stakeholders principales:**

| Rol | Persona / referente | Responsabilidad |
| --- | --- | --- |
| Sponsor | Sr. ARRR, dueño del establecimiento | Aprueba presupuesto, alcance y prioridades |
| Usuario experto | Encargado del tambo | Explica el proceso de ordeñe y registro diario |
| Usuario operativo | Operaria de ordeñe | Carga datos en el campo |
| Equipo de desarrollo | Líder/SM + desarrolladores FE/BE | Releva necesidades y construye el producto |

**Riesgos iniciales:**

| Riesgo | Impacto posible |
| --- | --- |
| Conectividad irregular en la sala de ordeñe | Dificultad para cargar datos en el momento |
| Baja adopción por parte de operarios | Datos incompletos o cargados fuera de tiempo |
| Alcance mayor a la capacidad del equipo en 4 sprints | Necesidad de recortar funcionalidades |

**Plazo y metodología:**
Scrum, 4 sprints de 2 semanas (8 semanas totales), con revisión del incremento junto
al cliente al final de cada sprint.

**Presupuesto / esfuerzo estimado:**
240 horas de equipo, estimadas en USD 6.600.

**Criterios de éxito:**
El sistema permite registrar vacas, ordeñes y lotes, y responder una consulta de
trazabilidad completa por lote (animales, fecha, turno, propiedades de calidad) en
menos de 3 segundos, con el cliente aceptando la entrega final.
