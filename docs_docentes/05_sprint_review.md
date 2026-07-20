# 5. Sprint Review

## ¿Para qué sirve este documento?

El Sprint Review es la reunión al final de cada sprint donde el equipo muestra el
incremento funcional al cliente/referente y recoge su feedback. Documentarlo permite:

- Dejar constancia de qué se mostró y qué funcionó.
- Registrar textualmente el feedback del cliente (aprobación u observaciones).
- Detectar correcciones o nuevas necesidades, que después se formalizan en el
  [control de cambios](06_control_de_cambios.md) y se incorporan al
  [backlog](04_backlog_por_sprint.md).

Se redacta **un documento por sprint** (Sprint Review 1, 2, 3...), inmediatamente
después de la reunión con el cliente.

---

## Plantilla

**Sprint N — [nombre del sprint]**
**Fecha:**
**Participantes:** (equipo + cliente/referentes presentes)

**Incremento demostrado:**
(Qué funcionalidades se mostraron en vivo)

**Feedback del cliente:**
> (cita textual o resumen fiel de lo que dijo el cliente)

**Observaciones o correcciones solicitadas:**
-

**Resultado del sprint:** (Aprobado / Aprobado con observaciones / Requiere corrección)

**Impacto en el backlog:** (historias nuevas o modificadas, referencia al control de cambios)

---

## Ejemplo desarrollado (caso TamboTrace)

### Sprint Review 1 — Base del sistema y registro de animales

**Participantes:** equipo de desarrollo; Sr. ARRR (sponsor); encargado del tambo.

**Incremento demostrado:** inicio de sesión, creación de usuarios y roles, registro de
vacas, búsqueda de vacas, cambio de estado de vaca.

**Feedback del cliente:**
> "Esto está bien para empezar. La carga de vacas es clara y la búsqueda por caravana
> nos sirve mucho. Aprobamos este avance."

**Observaciones o correcciones solicitadas:** ninguna.

**Resultado del sprint:** Aprobado sin correcciones mayores.

**Impacto en el backlog:** ninguno.

---

### Sprint Review 2 — Registro de ordeñes y participación de animales

**Participantes:** equipo de desarrollo; encargado del tambo; operaria de ordeñe.

**Incremento demostrado:** creación de ordeñe con fecha, turno, tanque y responsable;
selección de vacas participantes; exclusión de vacas con motivo.

**Feedback del cliente:**
> "La función está bien, pero seleccionar vaca por vaca nos lleva demasiado tiempo. En
> un ordeñe participan muchas vacas. Necesitamos una forma de cargar rápidamente todas
> las vacas en producción y después excluir solo las que no participaron."

**Observaciones o correcciones solicitadas:**
- Agregar un botón "Agregar todas las vacas en producción" al crear un ordeñe.
- Permitir luego quitar o excluir animales específicos de esa selección.

**Resultado del sprint:** Funcional, pero requiere corrección.

**Impacto en el backlog:** se agrega HU19 ("Como operario, quiero agregar
automáticamente todas las vacas en producción a un ordeñe, para no seleccionarlas una
por una", 5 puntos, prioridad Alta). Ver [CC-01 en control de cambios](06_control_de_cambios.md).

---

### Sprint Review 3 — Lotes de leche y propiedades de calidad

**Participantes:** equipo de desarrollo; encargado del tambo; administración.

**Incremento demostrado:** selección rápida de vacas en producción (HU19), creación de
lote desde un ordeñe, registro de litros estimados y tanque, carga de propiedades de
calidad.

**Feedback del cliente:**
> "Ahora crear el lote funciona, pero necesitamos diferenciar entre datos cargados en
> el momento del ordeñe y datos que llegan después del laboratorio. Si alguien mira el
> lote antes de cargar los análisis, debería quedar claro que está incompleto."

**Observaciones o correcciones solicitadas:**
- Agregar estados de lote: Borrador, Pendiente de análisis, Completo, Cerrado.
- Impedir el cierre de un lote si faltan datos obligatorios.

**Resultado del sprint:** Funcional, pero requiere ajustes antes de la entrega final.

**Impacto en el backlog:** se agregan HU20 ("ver el estado de un lote", 5 puntos,
Alta) y HU21 ("impedir cerrar un lote si faltan datos", 3 puntos, Alta). Ver
[CC-02 en control de cambios](06_control_de_cambios.md).

---

### Sprint Review 4 — Trazabilidad, reportes, cierre y entrega

**Participantes:** equipo de desarrollo; Sr. ARRR (sponsor); encargado del tambo; administración.

**Incremento demostrado:** estados de lote, validación de datos mínimos antes de
cerrar, cierre de lote, consulta de trazabilidad completa por lote, exportación de
reporte básico, historial de cambios críticos, guía breve de uso.

**Feedback del cliente:**
> "Ahora el sistema refleja mejor cómo trabajamos. Podemos registrar vacas, ordeñes,
> lotes, datos de calidad y consultar la trazabilidad. El reporte básico nos sirve para
> empezar. Aprobamos la entrega final y dejamos para una segunda etapa el módulo
> veterinario más completo y la integración con laboratorio."

**Observaciones o correcciones solicitadas:** ninguna que bloquee la entrega; quedan
registradas como mejoras futuras (módulo veterinario completo, integración con
laboratorio) en el [documento de cierre de proyecto](07_cierre_de_proyecto.md).

**Resultado del sprint:** Aprobado. Producto aceptado para cierre de proyecto.

**Impacto en el backlog:** ninguno adicional; se cierra el Product Backlog de la
primera versión.
