# 4. Backlog por Sprint

## ¿Para qué sirve este documento?

El **Product Backlog** es la lista completa y priorizada de historias de usuario del
proyecto. El **Sprint Backlog** es el subconjunto de historias que el equipo se
compromete a entregar en un sprint concreto, elegido en el Sprint Planning.

Este documento tiene dos partes:
1. El Product Backlog priorizado, con una estimación de en qué sprint entra cada historia.
2. El detalle de cada sprint: objetivo, historias seleccionadas, puntos totales e
   incremento esperado.

Se actualiza durante todo el proyecto: al cierre de cada sprint se revisa qué quedó
pendiente y qué historias nuevas se agregaron (ver
[control de cambios](06_control_de_cambios.md)).

---

## Plantilla

### Product Backlog priorizado

| Orden | ID | Historia | Puntos | Sprint estimado |
| --- | --- | --- | --- | --- |
| 1 | | | | |

### Sprint N: [nombre del sprint]

**Objetivo del sprint:**

**Historias seleccionadas:**

| ID | Historia | Puntos |
| --- | --- | --- |
| | | |
| **Total** | | |

**Incremento esperado:** (qué podrá hacer el cliente al terminar el sprint)

---

## Ejemplo desarrollado (caso TamboTrace)

Velocidad estimada del equipo: **20 puntos por sprint**, en sprints de 2 semanas.
Proyecto planificado en **4 sprints** (8 semanas).

### Product Backlog priorizado

| Orden | ID | Historia | Puntos | Sprint estimado |
| --- | --- | --- | --- | --- |
| 1 | HU1 | Inicio de sesión | 3 | Sprint 1 |
| 2 | HU2 | Gestión de usuarios y roles | 5 | Sprint 1 |
| 3 | HU3 | Registro de vacas | 5 | Sprint 1 |
| 4 | HU4 | Búsqueda de vacas | 3 | Sprint 1 |
| 5 | HU5 | Cambio de estado de vaca | 3 | Sprint 1 |
| 6 | HU6 | Registro de ordeñe | 5 | Sprint 2 |
| 7 | HU7 | Selección de vacas participantes | 8 | Sprint 2 |
| 8 | HU8 | Exclusión de vacas con motivo | 5 | Sprint 2 |
| 9 | HU9 | Creación de lote desde ordeñe | 8 | Sprint 3 |
| 10 | HU10 | Datos productivos básicos del lote | 3 | Sprint 3 |
| 11 | HU11 | Resultados de calidad | 5 | Sprint 3 |
| 12 | HU12 | Cierre de lote | 5 | Sprint 3 |
| 13 | HU13 | Consulta de trazabilidad por lote | 8 | Sprint 4 |
| 14 | HU14 | Exportación de reporte | 5 | Sprint 4 |
| 15 | HU16 | Historial de cambios críticos | 5 | Sprint 4 |
| 16 | HU17 | Respaldos automáticos | 3 | Sprint 4 |
| 17 | HU15 | Observaciones sanitarias | 5 | Sprint 4, si hay capacidad |
| 18 | HU18 | Guía básica de uso | 2 | Sprint 4 |

---

### Sprint 1: Base del sistema y registro de animales

**Objetivo del sprint:** construir la base inicial del sistema: acceso seguro, roles
básicos y gestión inicial de vacas.

| ID | Historia | Puntos |
| --- | --- | --- |
| HU1 | Inicio de sesión | 3 |
| HU2 | Gestión de usuarios y roles | 5 |
| HU3 | Registro de vacas | 5 |
| HU4 | Búsqueda de vacas | 3 |
| HU5 | Cambio de estado de vaca | 3 |
| **Total** | | **19** |

**Incremento esperado:** el cliente puede iniciar sesión, crear usuarios, asignar
roles, registrar vacas, buscarlas y cambiar su estado.

---

### Sprint 2: Registro de ordeñes y participación de animales

**Objetivo del sprint:** permitir registrar ordeñes y asociar vacas participantes o excluidas.

| ID | Historia | Puntos |
| --- | --- | --- |
| HU6 | Registro de ordeñe | 5 |
| HU7 | Selección de vacas participantes | 8 |
| HU8 | Exclusión de vacas con motivo | 5 |
| Ajuste técnico | Mejora de interfaz para selección rápida | 2 |
| **Total** | | **20** |

**Incremento esperado:** el cliente puede crear un ordeñe, indicar fecha, turno,
tanque y responsable, seleccionar vacas participantes y excluir animales con motivo.

---

### Sprint 3: Lotes de leche y propiedades de calidad

**Objetivo del sprint:** crear lotes de leche a partir de ordeñes y registrar sus
propiedades principales.

| ID | Historia | Puntos |
| --- | --- | --- |
| HU19 *(agregada tras Sprint 2, ver control de cambios)* | Agregar automáticamente vacas en producción al ordeñe | 5 |
| HU9 | Creación de lote desde ordeñe | 8 |
| HU10 | Datos productivos básicos del lote | 3 |
| HU11 | Resultados de calidad | 5 |
| **Total** | | **21** |

> El equipo acepta 21 puntos (por encima de la velocidad promedio) porque HU19 es una
> corrección prioritaria surgida en el Sprint Review 2.

**Incremento esperado:** el cliente puede agregar rápidamente vacas en producción a un
ordeñe, crear un lote desde un ordeñe, registrar litros estimados y tanque, y cargar
propiedades de calidad del lote.

---

### Sprint 4: Trazabilidad, reportes, cierre y entrega

**Objetivo del sprint:** completar la trazabilidad por lote, aplicar correcciones
solicitadas y preparar el cierre del proyecto.

| ID | Historia | Puntos |
| --- | --- | --- |
| HU20 *(agregada tras Sprint 3)* | Estados de lote | 5 |
| HU21 *(agregada tras Sprint 3)* | Validación para cierre de lote | 3 |
| HU12 | Cierre de lote | 5 |
| HU13 | Consulta de trazabilidad por lote | 8 |
| HU14 | Exportación de reporte | 5 |
| HU16 | Historial de cambios críticos | 5 |
| HU18 | Guía básica de uso | 2 |
| **Total** | | **33** |

> El total supera la velocidad normal del equipo. Para mantener el plazo se recortan
> alcances: HU17 (respaldos automáticos) se resuelve con la configuración básica del
> hosting en lugar de una pantalla propia, HU15 (observaciones sanitarias) queda como
> mejora futura, y el reporte se entrega en PDF básico sin personalización avanzada.
> Ver detalle en el [control de cambios](06_control_de_cambios.md).

**Incremento esperado:** el cliente puede ver estados de lote, validar datos mínimos
antes de cerrar, cerrar lotes, consultar trazabilidad completa por lote, exportar un
reporte básico, revisar cambios críticos y contar con una guía breve de uso.

---

### Resumen general de sprints

| Sprint | Objetivo | Resultado |
| --- | --- | --- |
| Sprint 1 | Base del sistema y animales | Aprobado |
| Sprint 2 | Ordeñes y participación de vacas | Requiere corrección |
| Sprint 3 | Lotes y calidad | Requiere corrección |
| Sprint 4 | Trazabilidad y cierre | Aprobado |
