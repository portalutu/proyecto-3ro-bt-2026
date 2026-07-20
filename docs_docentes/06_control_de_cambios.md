# 6. Control de Cambios

## ¿Para qué sirve este documento?

En Scrum es normal y esperable que el alcance se ajuste durante el proyecto: el
Product Backlog es flexible por diseño. Pero que sea flexible no significa que los
cambios queden sin registro. El control de cambios es una bitácora que deja constancia
de **qué cambió, por qué, quién lo pidió o lo detectó, y qué impacto tuvo** en alcance,
tiempo, costo o backlog.

Este documento es distinto del [Sprint Review](05_sprint_review.md): el Sprint Review
es el acta de la reunión donde surge el cambio; el control de cambios es el registro
consolidado y trazable de todas las decisiones de cambio del proyecto, sin importar su
origen (una reunión, un hallazgo técnico, un pedido fuera de sprint).

---

## Plantilla

| ID | Fecha | Origen | Descripción del cambio | Impacto | Decisión | Estado |
| --- | --- | --- | --- | --- | --- | --- |
| CC-01 | | | | | | |

Donde:
- **Origen:** de dónde surge (Sprint Review N, pedido directo del cliente, hallazgo
  técnico del equipo, restricción externa, etc.)
- **Impacto:** en alcance (historias agregadas/quitadas), tiempo, costo o prioridades.
- **Decisión:** qué resolvió el equipo (aceptar, rechazar, postergar, dividir en fases).
- **Estado:** Propuesto / Aceptado / Rechazado / Aplicado / Postergado.

---

## Ejemplo desarrollado (caso TamboTrace)

| ID | Fecha | Origen | Descripción del cambio | Impacto | Decisión | Estado |
| --- | --- | --- | --- | --- | --- | --- |
| CC-01 | Fin de Sprint 1 | Estimación de épicas | La estimación total del backlog (92 pts) supera la capacidad del equipo para 4 sprints (80 pts). | Alcance: se reduce sincronización offline a "fuera de alcance"; auditoría se limita a cambios críticos; veterinario queda con rol de consulta, sin módulo completo. | Aceptado: se ajusta el alcance inicial antes de comenzar el desarrollo. | Aplicado |
| CC-02 | [Sprint Review 2](05_sprint_review.md) | Feedback del cliente | Seleccionar vacas una por una en cada ordeñe es demasiado lento en la operación real. | Alcance: se agrega HU19 (agregar automáticamente vacas en producción al ordeñe, 5 pts). Backlog: HU19 se prioriza como Alta y entra al Sprint 3. | Aceptado. | Aplicado |
| CC-03 | [Sprint Review 3](05_sprint_review.md) | Feedback del cliente | No queda claro si un lote tiene todos sus datos cargados (algunos llegan después del laboratorio). | Alcance: se agregan HU20 (estados de lote, 5 pts) y HU21 (validación para impedir cierre con datos faltantes, 3 pts). Backlog: ambas entran al Sprint 4. | Aceptado. | Aplicado |
| CC-04 | Planificación de Sprint 4 | Capacidad del equipo | El Sprint 4 acumula 33 puntos (HU20, HU21 sumadas a lo ya planificado), muy por encima de la velocidad promedio (20 pts). | Alcance: HU17 (respaldos automáticos) se resuelve con configuración básica del hosting en vez de pantalla propia; HU15 (observaciones sanitarias) se posterga a una fase futura; exportación de reporte se limita a PDF básico sin personalización. | Aceptado: se recorta alcance para proteger el objetivo del sprint y la fecha de entrega. | Aplicado |
| CC-05 | [Sprint Review 4](05_sprint_review.md) | Feedback del cliente | El cliente pide para una segunda etapa un módulo veterinario completo y la integración automática con laboratorio. | Alcance: no se incorpora al proyecto actual. Se documenta como mejora futura. | Postergado: queda registrado en el [documento de cierre](07_cierre_de_proyecto.md) como trabajo futuro, fuera del alcance de esta primera versión. | Postergado |

> **Nota:** todo cambio con impacto en alcance, tiempo o costo debe quedar
> registrado aquí, aunque el equipo lo haya "resuelto" verbalmente en una reunión. Esto
> evita discusiones futuras sobre qué se acordó y por qué, y es evidencia concreta del
> trabajo de gestión del proyecto para la defensa final.
