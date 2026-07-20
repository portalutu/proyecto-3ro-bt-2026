# 9. Actas de Reuniones

## ¿Para qué sirve este documento?

Este documento es la bitácora de reuniones del proyecto. El líder/Scrum Master de cada
equipo registra aquí **cada reunión** que se realice (internas del equipo, con el
cliente/referente o con el docente): fecha, asistentes, modalidad, temas tratados, temas
pendientes, acuerdos y desacuerdos.

Es distinto del [Sprint Review](05_sprint_review.md): el Sprint Review es el acta
específica de la reunión de revisión de cada sprint con el cliente. Las actas de
reuniones registran **todas** las demás instancias (dailies relevantes, reuniones de
planificación, reuniones con el referente fuera del ciclo de sprint, etc.) y sirven como
evidencia del trabajo de gestión del equipo para la defensa final.

---

## Plantilla

| ID | Fecha | Modalidad | Asistentes | Temas tratados | Temas pendientes | Acuerdos | Desacuerdos |
| --- | --- | --- | --- | --- | --- | --- | --- |
| R-01 | | Presencial / Virtual | | | | | |

Donde:
- **Modalidad:** presencial, virtual o mixta.
- **Asistentes:** integrantes del equipo presentes y, si corresponde, referente/cliente
  o docente.
- **Temas tratados:** puntos discutidos en la reunión.
- **Temas pendientes:** puntos que quedaron sin resolver y deben retomarse en una
  próxima reunión.
- **Acuerdos:** decisiones tomadas en conjunto.
- **Desacuerdos:** puntos donde no hubo consenso, dejando registro de las distintas
  posturas (no es necesario resolverlos en el acta, pero sí registrarlos).

---

## Ejemplo desarrollado (caso TamboTrace)

| ID | Fecha | Modalidad | Asistentes | Temas tratados | Temas pendientes | Acuerdos | Desacuerdos |
| --- | --- | --- | --- | --- | --- | --- | --- |
| R-01 | Inicio de proyecto | Presencial | Equipo completo | Relevamiento de la idea inicial del cliente y primeras preguntas para la entrevista. | Confirmar fecha de entrevista con el cliente. | Se define agenda de entrevista y roles del equipo. | — |
| R-02 | Post-entrevista | Presencial | Equipo completo | Puesta en común de lo relevado en la entrevista con el sponsor. | Redacción del Project Charter. | Se define alcance inicial y prioridades del cliente. | — |
| R-03 | Planificación Sprint 1 | Virtual | Equipo completo | Selección de historias de usuario para el Sprint 1, estimación de puntos. | Ninguno. | Se prioriza login, roles y registro/búsqueda de vacas. | Dos integrantes no coincidían en si dejar sincronización offline dentro del Sprint 1; se resolvió excluirla (ver [CC-01](06_control_de_cambios.md)). |
| R-04 | Interna, mitad de Sprint 2 | Virtual | Equipo completo | Avance de registro de ordeñe, dificultades con la selección manual de vacas. | Validar con el cliente si la selección manual es aceptable en la operación real. | Se agenda reunión con el cliente para el Sprint Review 2. | — |
| R-05 | Seguimiento Sprint 4 | Presencial | Equipo completo | Revisión de pendientes antes del cierre, preparación de la demo final. | Confirmar disponibilidad del cliente para el acta de cierre. | Se distribuyen tareas de cierre entre los integrantes. | Desacuerdo sobre incluir o no una pantalla extra de reportes antes del cierre; se acuerda no incluirla para no arriesgar la fecha de entrega. |

> **Nota:** el acta no reemplaza al [Sprint Review](05_sprint_review.md) ni al
> [control de cambios](06_control_de_cambios.md). Si en una reunión surge un cambio de
> alcance, tiempo o costo, además de registrarlo aquí debe quedar asentado en el
> control de cambios correspondiente.
