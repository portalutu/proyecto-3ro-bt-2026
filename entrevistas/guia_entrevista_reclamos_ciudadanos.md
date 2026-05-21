# Guía de entrevista - Sistema de Gestión de Reclamos Ciudadanos

## Objetivo de la entrevista

Relevar información con las autoridades o referentes de la comuna para comprender el uso esperado, funcionamiento real, alcance institucional, nivel de transparencia requerido y restricciones del proyecto.

La entrevista busca aclarar decisiones necesarias para analizar, modelar y desarrollar el sistema de gestión de reclamos ciudadanos, incluyendo la aplicación para ciudadanía, el dashboard administrativo y la interfaz para equipos o proveedores.

## Datos generales de la entrevista

* Fecha:
* Lugar / modalidad:
* Por UTU-Nodo: Esteban Pérez (Director), Andrea Valdez (docente, enlace con el proyecto), Diego Vera (docente, orientador de proyecto)
* Autoridades / referentes entrevistados:
* Área institucional: División Tránsito IMSJ
* Contacto de referencia:

## 1. Contexto institucional

* ¿Qué área de la comuna será responsable directa del sistema?
* ¿Qué problema concreto se busca resolver con la plataforma?
* ¿Cómo se reciben actualmente los reclamos ciudadanos?
* ¿Cómo se asignan actualmente los reclamos a equipos internos o proveedores?
* ¿Qué dificultades tiene el proceso actual?
* ¿Qué aspectos del proceso actual deberían mantenerse?
* ¿Qué áreas municipales intervienen en el ciclo de vida de un reclamo?
* ¿Existe alguna normativa interna, departamental o nacional que condicione el funcionamiento del sistema?

## 2. Público objetivo y usuarios

* ¿Quiénes podrán crear reclamos?
* ¿El sistema estará disponible para cualquier ciudadano o solamente para vecinos registrados?
* ¿Qué datos debe ingresar una persona para registrarse?
* ¿Será obligatorio validar la identidad del ciudadano?
* ¿Qué datos deben quedar asociados a cada reclamo?
* ¿Qué funcionarios utilizarán el dashboard administrativo?
* ¿Qué equipos internos o proveedores utilizarán la interfaz operativa?
* ¿Habrá roles con permisos diferentes?
* ¿Quién podrá ver todos los reclamos?
* ¿Quién podrá asignar, aprobar, rechazar o cerrar reclamos?

## 3. Tipos de reclamos y alcance funcional

* ¿Qué tipos de incidentes se recibirán inicialmente?
* ¿Qué categorías deberían existir? Por ejemplo: baches, alumbrado, arbolado, pérdidas de agua, cableado eléctrico.
* ¿Habrá categorías que no correspondan al sistema?
* ¿Qué información mínima debe tener un reclamo?
* ¿La descripción será obligatoria?
* ¿Las fotos o videos serán obligatorios u opcionales?
* ¿La ubicación geográfica será automática, manual o ambas?
* ¿El ciudadano podrá editar un reclamo luego de enviarlo?
* ¿El ciudadano podrá cancelar un reclamo?
* ¿Se permitirá crear reclamos anónimos?

## 4. Flujo de estados

* ¿Qué estados debe tener un reclamo?
* ¿El flujo propuesto es correcto? Ingreso, asignado, en proceso, pendiente de aprobación, resuelto, rechazado.
* ¿Qué significa exactamente cada estado?
* ¿Quién puede mover un reclamo de un estado a otro?
* ¿Qué datos deben registrarse en cada cambio de estado?
* ¿Qué ocurre cuando un reclamo es rechazado?
* ¿Qué ocurre cuando una solución no es aprobada?
* ¿El reclamo vuelve al mismo equipo o puede reasignarse?
* ¿Debe existir un plazo máximo para cada estado?
* ¿Debe registrarse la fecha de ingreso, asignación, inicio, finalización y aprobación?

## 5. Evidencias y documentación

* ¿Qué tipo de evidencia debe cargar el ciudadano?
* ¿Qué tipo de evidencia debe cargar el equipo o proveedor?
* ¿Se requieren fotos de antes y después?
* ¿Se permitirá video breve?
* ¿Cuál debería ser el tamaño máximo de archivos?
* ¿Quién podrá ver las evidencias?
* ¿Las evidencias serán públicas o solo internas?
* ¿Debe conservarse todo el historial multimedia?
* ¿Qué ocurre si una imagen contiene datos sensibles o información de terceros?

## 6. Dashboard administrativo

* ¿El tablero Kanban refleja correctamente la forma de trabajo esperada?
* ¿Qué columnas son indispensables?
* ¿Qué filtros necesita el dashboard?
* ¿Se debe filtrar por barrio, zona, tipo de reclamo, fecha, estado, equipo o proveedor?
* ¿Qué información debe verse en la tarjeta de cada reclamo?
* ¿Qué acciones rápidas debería permitir el tablero?
* ¿Se necesita una vista de mapa?
* ¿Se necesita una vista de lista además del Kanban?
* ¿Qué reportes serían útiles para la comuna?
* ¿Se requieren indicadores de reclamos vencidos, pendientes o sin asignar?

## 7. Equipos internos y proveedores

* ¿Los trabajos serán realizados por funcionarios, cuadrillas internas, empresas proveedoras o una combinación?
* ¿Qué datos se deben registrar de cada equipo o proveedor?
* ¿Cómo se asigna un reclamo a un equipo?
* ¿Un reclamo puede tener más de un equipo asignado?
* ¿Qué información debe ver un equipo al recibir una tarea?
* ¿El equipo debe poder marcar inicio y finalización?
* ¿Qué materiales utilizados deben registrarse?
* ¿Las observaciones de los equipos serán visibles para el ciudadano?
* ¿Qué ocurre si el equipo no puede resolver el reclamo?

## 8. Transparencia y comunicación ciudadana

* ¿Qué información del reclamo debe poder consultar el ciudadano?
* ¿El ciudadano verá solamente sus reclamos o también reclamos públicos de otros vecinos?
* ¿Se publicará un mapa general de reclamos?
* ¿Qué datos deben ocultarse para proteger privacidad?
* ¿El ciudadano podrá ver el equipo asignado?
* ¿El ciudadano podrá ver fechas estimadas de resolución?
* ¿El ciudadano recibirá notificaciones por cambios de estado?
* ¿Por qué medios se notificaría? Email, web, celular, otro.
* ¿El ciudadano podrá valorar la solución?
* ¿El ciudadano podrá comentar o responder luego de la resolución?

## 9. Sponsors, responsables y sostenibilidad

* ¿Quiénes son los sponsors o autoridades que respaldan el proyecto?
* ¿Existe un referente funcional para responder dudas durante el desarrollo?
* ¿Existe un referente técnico de la comuna?
* ¿Quién validará los avances del proyecto?
* ¿Quién aprobará la versión final?
* ¿La comuna espera utilizar el sistema luego del proyecto educativo o será un prototipo?
* ¿Dónde se alojaría el sistema si se implementa realmente?
* ¿Quién mantendría usuarios, categorías, equipos, proveedores y datos luego de la entrega?

## 10. Seguridad y datos personales

* ¿Qué datos personales del ciudadano son imprescindibles?
* ¿Durante cuánto tiempo deberían conservarse los datos personales y los reclamos?
* ¿Quién puede acceder a los datos personales?
* ¿Se necesita registrar consentimiento del ciudadano?
* ¿El sistema debe permitir eliminar o anonimizar datos?
* ¿Qué controles mínimos de seguridad espera la comuna?
* ¿Qué nivel de auditoría se requiere sobre acciones de funcionarios y proveedores?
* ¿Qué ocurre si un funcionario o proveedor deja de trabajar con la comuna?
* ¿Se requiere integración con algún sistema de autenticación existente?

## 11. Integraciones y validación de identidad

* ¿La validación de identidad será obligatoria en un sistema real?
* ¿Qué datos debería validar la comuna antes de permitir el alta de un ciudadano?
* ¿La API docente de validación de CI alcanza para el prototipo?
* ¿Qué debería ocurrir si la validación falla?
* ¿Se necesita integración con correo electrónico?
* ¿Se necesita integración con mapas o servicios de geolocalización?
* ¿Se necesita exportar información a otros sistemas municipales?

## 12. Reportes, indicadores y gestión

* ¿Qué indicadores necesita la autoridad para evaluar el funcionamiento del sistema?
* ¿Se medirá tiempo promedio de resolución?
* ¿Se medirá cantidad de reclamos por zona?
* ¿Se medirá cantidad de reclamos por tipo?
* ¿Se medirá desempeño por equipo o proveedor?
* ¿Se necesitan reportes exportables?
* ¿Con qué frecuencia se revisarían los reportes?
* ¿Qué datos son importantes para presentar públicamente?

## 13. Alcance del prototipo

* ¿Qué funcionalidades son imprescindibles para una primera versión?
* ¿Qué funcionalidades pueden quedar para una etapa posterior?
* ¿Qué flujo completo debería demostrarse en la defensa del proyecto?
* ¿Qué datos de prueba puede aportar la comuna?
* ¿Se pueden usar nombres, documentos, imágenes, ubicaciones y reclamos ficticios?
* ¿Hay restricciones de identidad visual o uso de logos institucionales?
* ¿Qué criterios usarán las autoridades para decir que el prototipo es útil?

## 14. Preguntas de cierre

* ¿Hay algún proceso importante que no hayamos mencionado?
* ¿Qué errores debería evitar el equipo al diseñar el sistema?
* ¿Qué expectativa principal tiene la comuna sobre este proyecto?
* ¿Qué documentación o material institucional puede compartirse con el equipo?
* ¿Quién será el contacto para consultas posteriores?

## 15. Acuerdos y próximos pasos

* Información pendiente de recibir:
* Decisiones tomadas durante la entrevista:
* Funcionalidades confirmadas:
* Funcionalidades descartadas:
* Riesgos detectados:
* Próxima reunión:

