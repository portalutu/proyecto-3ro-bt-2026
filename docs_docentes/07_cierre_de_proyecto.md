# 7. Documento de Cierre de Proyecto (Acta de Cierre)

## ¿Para qué sirve este documento?

El acta de cierre formaliza que el proyecto terminó: qué se entregó, qué requerimientos
se cumplieron, qué quedó pendiente, qué se aprendió y que el cliente/referente aceptó
la entrega. Es el último documento del proyecto y es especialmente importante para la
defensa final: resume en un solo lugar todo el recorrido del equipo.

---

## Plantilla

**Nombre del proyecto:**
**Fecha de cierre:**
**Equipo:**

**Resumen de sprints:**

| Sprint | Objetivo | Incremento entregado | Resultado |
| --- | --- | --- | --- |
| | | | |

**Actividades de cierre realizadas:**
1.

**Requerimientos cumplidos al cierre:**

| Área / requerimiento | Estado |
| --- | --- |
| | |

**Alcance excluido / pendiente para etapas futuras:**
-

**Lecciones aprendidas (retrospectiva general):**

| Lección | Explicación |
| --- | --- |
| | |

**Aceptación del cliente/sponsor:**
> (cita textual o resumen de la aprobación final)

**Firmas / aprobación:**

---

## Ejemplo desarrollado (caso TamboTrace)

**Nombre del proyecto:** TamboTrace — Sistema de trazabilidad para establecimiento lechero

**Fecha de cierre:** fin de Sprint 4 (semana 8)

**Equipo:** Líder/Scrum Master + 3 desarrolladores

### Resumen de sprints

| Sprint | Objetivo | Incremento entregado | Resultado |
| --- | --- | --- | --- |
| Sprint 1 | Base del sistema y animales | Login, roles, registro y búsqueda de vacas | Aprobado |
| Sprint 2 | Ordeñes y participación de vacas | Registro de ordeñe, selección y exclusión de vacas | Requirió corrección (ver [CC-02](06_control_de_cambios.md)) |
| Sprint 3 | Lotes y calidad | Creación de lote, datos productivos y análisis | Requirió corrección (ver [CC-03](06_control_de_cambios.md)) |
| Sprint 4 | Trazabilidad y cierre | Estados, cierre, consulta, reporte y guía | Aprobado |

### Actividades de cierre realizadas

1. Presentación final al cliente.
2. Validación de los requerimientos cumplidos frente al backlog inicial.
3. Entrega de acceso al sistema (usuarios y roles configurados).
4. Entrega de guía básica de uso.
5. Capacitación breve a usuarios principales (encargado y operarios).
6. Revisión de pendientes y mejoras futuras junto al cliente.
7. Registro de lecciones aprendidas.
8. Cierre formal del proyecto y firma de aceptación.

### Requerimientos cumplidos al cierre

| Área | Estado |
| --- | --- |
| Usuarios y roles | Cumplido |
| Registro de vacas | Cumplido |
| Estados de vacas | Cumplido |
| Registro de ordeñes | Cumplido, con mejora de selección rápida (HU19) |
| Exclusión de animales | Cumplido |
| Creación de lotes | Cumplido |
| Propiedades de calidad | Cumplido en carga manual |
| Estados de lote | Cumplido como corrección del Sprint 3 (HU20) |
| Cierre de lote | Cumplido con validación mínima (HU21) |
| Reporte de trazabilidad | Cumplido en versión básica |
| Historial de cambios | Cumplido en cambios críticos |
| Módulo veterinario completo | Pendiente para fase futura |
| Integración con laboratorio | Pendiente para fase futura |
| Sincronización offline completa | Pendiente para fase futura |

### Alcance excluido / pendiente para etapas futuras

- Integración automática con sensores de ordeñe y caravanas RFID.
- Aplicación móvil nativa y sincronización offline completa.
- Integración directa con laboratorios externos.
- Módulo veterinario completo (más allá de observaciones simples por vaca).

### Lecciones aprendidas (retrospectiva general)

| Lección | Explicación |
| --- | --- |
| La necesidad inicial no alcanza para construir el sistema | El cliente comenzó con una idea general; la entrevista permitió descubrir procesos, restricciones y prioridades reales. |
| Los usuarios reales modifican el diseño | La selección manual de vacas parecía correcta en el diseño, pero resultó poco práctica en la operación diaria. |
| Los requerimientos cambian al ver el producto | Los estados de lote surgieron recién cuando el cliente vio funcionando la carga de calidad. |
| Scrum permite correcciones controladas | Los cambios se incorporaron al backlog y se priorizaron sin reiniciar el proyecto (ver [control de cambios](06_control_de_cambios.md)). |
| No todo entra en la primera versión | Algunas ideas útiles quedaron fuera para respetar plazo y presupuesto. |
| El cierre no significa que el producto no pueda evolucionar | El sistema queda operativo y se documentan mejoras futuras. |

### Aceptación del cliente/sponsor

> "Ahora el sistema refleja mejor cómo trabajamos. Podemos registrar vacas, ordeñes,
> lotes, datos de calidad y consultar la trazabilidad. El reporte básico nos sirve para
> empezar. Aprobamos la entrega final y dejamos para una segunda etapa el módulo
> veterinario más completo y la integración con laboratorio."

**Resultado final:** proyecto aceptado por el cliente. Cierre formal.

### Firmas / aprobación

| Rol | Nombre | Firma / fecha |
| --- | --- | --- |
| Sponsor | | |
| Director del proyecto | | |
| Equipo de desarrollo | | |
