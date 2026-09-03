ll# Resumen para autoridades - Sistema de Gestión de Reclamos Ciudadanos

## Presentación general

El proyecto propone desarrollar un sistema digital para gestionar reclamos ciudadanos relacionados con infraestructura urbana y servicios comunales.

La propuesta busca que la ciudadanía pueda registrar reclamos de forma simple y que la comuna pueda recibirlos, asignarlos, hacer seguimiento del trabajo realizado y mantener trazabilidad de todo el proceso.

## Objetivo principal

Crear una plataforma que permita ordenar el ciclo completo de un reclamo ciudadano, desde su ingreso hasta su resolución, incorporando evidencias, estados, responsables y reportes básicos para la gestión.

## Usuarios previstos

El sistema contempla tres tipos de usuarios:

* Ciudadanía
* Personal administrativo de la comuna
* Equipos internos o proveedores

La ciudadanía utilizará una aplicación web móvil o PWA para registrar reclamos, adjuntar evidencias y consultar el estado.

El personal administrativo utilizará un dashboard tipo Kanban para gestionar, asignar, aprobar o rechazar reclamos.

Los equipos internos o proveedores utilizarán una interfaz simple para consultar tareas asignadas, registrar avances, materiales utilizados y evidencias de finalización.

## Funcionalidades para la ciudadanía

* Registrarse y validar datos básicos.
* Crear reclamos indicando tipo de incidente, descripción y ubicación.
* Adjuntar fotos o video breve como evidencia.
* Consultar el estado de sus reclamos.
* Recibir notificaciones sobre cambios de estado.

## Funcionalidades para la comuna

* Visualizar reclamos ingresados en un tablero de gestión.
* Asignar reclamos a equipos internos o proveedores.
* Cambiar estados del reclamo durante el proceso.
* Revisar evidencias antes y después del trabajo.
* Aprobar o rechazar la resolución de un reclamo.
* Obtener reportes básicos sobre tiempos, pendientes, incumplimientos y carga de trabajo.

## Funcionalidades para equipos o proveedores

* Consultar tareas asignadas.
* Marcar inicio del trabajo.
* Registrar finalización.
* Indicar materiales utilizados.
* Agregar observaciones.
* Adjuntar evidencias fotográficas del trabajo realizado.
* Atender tareas rechazadas o devueltas para corrección.

## Aspectos a validar con las autoridades

Durante la entrevista será importante aclarar:

* Qué tipos de reclamos se gestionarán inicialmente.
* Cómo se reciben y asignan los reclamos hoy.
* Qué estados debe tener un reclamo.
* Quién puede aprobar, rechazar o cerrar reclamos.
* Qué información podrá ver el ciudadano.
* Qué información debe mantenerse interna.
* Qué nivel de transparencia se espera para el seguimiento.
* Qué datos personales se necesitan y cómo deben protegerse.
* Si participarán equipos internos, proveedores externos o ambos.
* Qué reportes serían útiles para la gestión comunal.
* Si la propuesta será un prototipo educativo o si podría proyectarse como sistema real.

## Valor esperado

El sistema permitiría mejorar la trazabilidad de los reclamos, ordenar el trabajo interno, facilitar la comunicación con la ciudadanía y generar información útil para la toma de decisiones.

Para el proyecto educativo, representa un caso completo de desarrollo web con roles diferenciados, gestión de estados, evidencias multimedia, geolocalización, reportes, seguridad y tratamiento responsable de datos personales.

---
---

## Desafío en el mercado (Jul 2026)

La comuna acaba de liberar un chatbot llamado "Clara" basado en whatsapp para centralizar los reclamos en una sola plataforma, para brindar a la ciudadanía una forma unificada de reclamo con posibilidades de recibir feedback o consultas adicionales.  Este desarrollo ocurrió en un espacio temporal paralelo a la concepción y desarrollo inicial de nuestra plataforma.  Al ser un desarrollo interno de la propia comuna, el valor de innovación de nuestra plataforma se vé disminuído.

Noticia original:
```
La Intendencia de San José presentó el nuevo servicio de atención ciudadana. Se trata de un bot denominado “Clara” que funciona como asistente virtual.

La plataforma ya está operativa y los ciudadanos pueden plantear reclamos vinculados a todas las áreas de la Intendencia por WhatsApp, a través del celular 4342 9000.

Martín Ponzetti, coordinador del Área de Innovación y Tecnología, aseguró que el servicio permite “tener toda la información centralizada y hacer el seguimiento” de las solicitudes.

Los reclamos son derivados a la dirección de la Intendencia correspondiente o al organismo competente y se notifica el avance del proceso, a través del número celular del ciudadano.

Ponzetti agregó que el bot permite facilitar y evitar demoras. Asimismo, el sistema mantiene la posibilidad de comunicarse con agentes humanos para tener asesoramiento.

El asistente también deriva a los servicios de pago de tributos online y consulta de expedientes.
```

## Oportunidad de colaboración con la comuna

### Propuesta de asociación: Clara + plataforma de gestión personalizada (similar a Tool Use Pattern en AI)

Se propone establecer una asociación con la Intendencia de San José para integrar nuestra plataforma como una **capa complementaria de personalización, gestión operativa y seguimiento** del servicio Clara. La iniciativa no busca sustituir el chatbot ni crear un canal paralelo de reclamos: Clara continuaría siendo el punto de contacto principal con la ciudadanía mediante WhatsApp, mientras que nuestra plataforma ampliaría las capacidades disponibles para gestionar cada caso una vez recibido.

El enfoque permitiría preservar la inversión y la identidad institucional de Clara, a la vez que ofrecería a la Intendencia una herramienta adaptable a las necesidades específicas de sus direcciones, equipos internos y proveedores. Para el proyecto educativo, la asociación permitiría trabajar sobre un problema real, demostrar capacidad de integración y dar visibilidad al trabajo realizado por los estudiantes.

### Valor aportado por nuestra plataforma

La capa adicional podría incorporar:

* Formularios y recorridos personalizados según el tipo de reclamo, solicitando ubicación, fotografías, videos u otros datos relevantes.
* Un tablero de gestión para clasificar, priorizar, asignar y controlar reclamos por dirección, zona, urgencia o responsable.
* Flujos de trabajo configurables, con estados, permisos y criterios de aprobación diferentes para cada área de la Intendencia.
* Una interfaz específica para cuadrillas y proveedores, desde la cual puedan registrar avances, materiales utilizados y evidencias de finalización.
* Historial completo del caso, con responsables, fechas, cambios de estado, observaciones y evidencias.
* Notificaciones hacia Clara para que el ciudadano pueda recibir novedades por el mismo canal en el que inició su gestión.
* Reportes e indicadores sobre tiempos de respuesta y resolución, reclamos recurrentes, distribución geográfica, carga de trabajo e incumplimientos.
* Una experiencia personalizada para el ciudadano, utilizando los datos ya aportados para evitar preguntas repetidas y ofrecer información relevante según su reclamo.

### Modelo de integración propuesto

El funcionamiento esperado sería el siguiente:

1. El ciudadano inicia el reclamo mediante Clara.
2. Clara recopila los datos básicos y, cuando corresponda, deriva el caso a nuestra plataforma mediante un mecanismo acordado con la Intendencia.
3. La plataforma completa la información necesaria, clasifica el reclamo y lo incorpora al flujo de trabajo del área responsable.
4. El personal administrativo, las cuadrillas o los proveedores gestionan el caso y registran sus actuaciones.
5. Los cambios relevantes se comunican nuevamente a Clara, que informa al ciudadano y mantiene una experiencia de atención unificada.

La integración debería definirse con el equipo técnico de la Intendencia. Según las capacidades disponibles, podría implementarse mediante una API, webhooks, intercambio controlado de archivos o, en una primera etapa, una carga asistida. De esta forma, la viabilidad del piloto no dependería de que Clara cuente desde el inicio con una interfaz de integración completa.

### Piloto sugerido

Se recomienda comenzar con un piloto acotado a una categoría de alto volumen y proceso claramente identificable, por ejemplo alumbrado, calles, residuos o espacios públicos. El piloto podría desarrollarse en las siguientes etapas:

1. Relevamiento conjunto del proceso actual, actores, datos, estados y reglas de derivación.
2. Diseño de la experiencia integrada y definición de responsabilidades entre Clara y nuestra plataforma.
3. Construcción de un prototipo funcional con datos de prueba, sin acceder inicialmente a información personal real.
4. Prueba controlada con personal de una dirección y un número reducido de casos.
5. Evaluación de resultados, ajustes y decisión sobre una eventual ampliación a otras áreas.

Para medir el resultado se propone comparar, antes y durante el piloto, el tiempo de asignación, el tiempo de resolución, el porcentaje de reclamos con información suficiente, la cantidad de casos reabiertos, el cumplimiento de plazos y la satisfacción de ciudadanos y funcionarios.

### Condiciones de gobernanza y protección de datos

La Intendencia mantendría la titularidad y el control de los datos y definiría qué información puede consultar cada perfil. La asociación debería acordar formalmente el alcance del piloto, las responsabilidades de las partes, los criterios de acceso, la conservación de la información, la seguridad, la trazabilidad de acciones y el tratamiento de datos personales y evidencias multimedia.

También debería preverse el consentimiento o aviso correspondiente al ciudadano, especialmente cuando el reclamo pase de Clara a la plataforma complementaria. Para reducir riesgos, el prototipo educativo debería trabajar con datos ficticios o anonimizados hasta contar con autorización institucional y controles técnicos adecuados.

### Beneficio para ambas partes y difusión del proyecto

La Intendencia obtendría una extensión flexible para experimentar con procesos personalizados, tableros internos y analítica sin alterar el canal ciudadano ya consolidado. El equipo del proyecto accedería a validación con usuarios reales, aprendizaje aplicado y una referencia institucional que aumentaría la relevancia y visibilidad de su trabajo.

Como parte del acuerdo se propone que la Intendencia reconozca públicamente la colaboración, siempre con autorización previa, mediante una mención en comunicaciones del piloto, una demostración conjunta, una presentación institucional o una publicación de resultados. La difusión debería identificar claramente a Clara como servicio oficial de atención y a nuestra plataforma como solución complementaria desarrollada en el marco del proyecto educativo, evitando confusión sobre la autoría, el respaldo institucional o el grado de madurez del producto.

### Propuesta de siguiente paso

Solicitar una reunión de trabajo con el Área de Innovación y Tecnología y con la dirección seleccionada para el piloto. El objetivo sería validar el recorrido actual de los reclamos, conocer las posibilidades técnicas de integración con Clara, seleccionar el caso de uso inicial y acordar un piloto de alcance reducido con responsables, cronograma, indicadores de éxito y reglas de comunicación pública.

## Oportunidad de colaboración con la comuna: frontend dual con Clara

### Propuesta de asociación: dos canales de acceso y un único proceso institucional (similar a Router Pattern en AI)

Se propone una segunda modalidad de colaboración en la que **Clara y nuestra aplicación funcionen como frontends complementarios para la ciudadanía**, sin reemplazar ni duplicar el sistema interno de la Intendencia. Clara mantendría su canal de atención por WhatsApp y continuaría recibiendo, derivando y procesando institucionalmente las solicitudes. Nuestra aplicación ofrecería una experiencia web alternativa, más visual, guiada y personalizada, para preparar el reclamo y transferirlo a Clara en un formato estructurado.

En este modelo, nuestra solución utilizaría principalmente su frontend y solamente la parte mínima de su backend necesaria para validar, organizar y transferir la información. No administraría el ciclo interno del reclamo ni actuaría como un segundo sistema de expedientes. La fuente oficial del estado, la derivación y la resolución seguiría siendo Clara y la infraestructura definida por la Intendencia.

### Experiencia propuesta para la ciudadanía

La aplicación permitiría que el ciudadano:

* Seleccione el tipo de reclamo mediante categorías, ejemplos y ayudas visuales.
* Indique la ubicación en un mapa o mediante geolocalización, con posibilidad de corregirla antes del envío.
* Adjunte fotografías u otras evidencias admitidas y complete únicamente los datos necesarios para el caso elegido.
* Revise un resumen claro del reclamo, conozca qué información será transferida y confirme su consentimiento.
* Envíe la solicitud a Clara sin tener que volver a escribir o cargar los mismos datos.
* Continúe la interacción y reciba el número de solicitud, las consultas adicionales y las novedades a través de Clara.

De esta forma, quienes prefieran WhatsApp podrán utilizar Clara directamente, mientras que quienes necesiten una experiencia guiada, accesible o con mayor apoyo visual podrán comenzar en nuestra aplicación. Ambos recorridos convergerían en el mismo canal institucional de procesamiento.

### Flujo funcional propuesto

1. El ciudadano accede a nuestra aplicación y selecciona el tipo de reclamo.
2. La aplicación solicita y valida los datos correspondientes a esa categoría, como descripción, ubicación y evidencias.
3. Antes del envío, se presenta un resumen y se informa que la solicitud será transferida a Clara para su gestión oficial.
4. Con la confirmación del ciudadano, el backend intermediario transforma los datos al formato acordado y los remite a Clara, identificando el origen de la solicitud.
5. Clara registra el reclamo, aplica sus reglas de derivación y devuelve una confirmación o identificador oficial.
6. La conversación, las solicitudes de información adicional y las notificaciones posteriores continúan por Clara y mediante los mecanismos definidos por la Intendencia.

El flujo deberá contemplar una confirmación inequívoca de recepción. Hasta que Clara no devuelva dicha confirmación, la aplicación no deberá presentar el reclamo como ingresado oficialmente.

### Alternativas técnicas para la transferencia

La opción preferida sería una integración autorizada mediante API, webhook u otra interfaz provista por la Intendencia, con autenticación, validación de campos y respuesta de recepción. Si esa capacidad no estuviera disponible durante el piloto, podría evaluarse un mecanismo de transición en el que la aplicación genere un mensaje estructurado y abra la conversación oficial de Clara en WhatsApp para que el propio ciudadano revise y confirme el envío.

La alternativa definitiva deberá ser validada por el equipo responsable de Clara. No se recomienda automatizar mensajes mediante mecanismos no oficiales ni operar una cuenta de WhatsApp en nombre del ciudadano, ya que ello podría afectar la seguridad, la trazabilidad y las condiciones de uso del canal.

### Alcance del backend intermediario

El backend de nuestra plataforma se limitaría a:

* Mantener catálogos, formularios y reglas de validación acordados con la Intendencia.
* Preparar y transformar la información al formato requerido por Clara.
* Gestionar de forma segura la transferencia y su confirmación técnica.
* Registrar datos mínimos de auditoría, como fecha, resultado del envío e identificador de correlación.
* Evitar reenvíos y reclamos duplicados mediante claves de idempotencia o controles equivalentes.
* Eliminar o anonimizar la información temporal una vez confirmada la recepción, de acuerdo con la política que se establezca.

Quedarían fuera de este componente la asignación a direcciones, la gestión de cuadrillas, los cambios de estado, la resolución y el repositorio oficial de reclamos. Esta delimitación reduce la complejidad, evita mantener información divergente y preserva a Clara como núcleo del servicio institucional.

### Beneficios de la propuesta

Para la ciudadanía, la propuesta amplía las formas de acceso, reduce errores y omisiones, facilita el ingreso de ubicación y evidencias y permite elegir el canal más cómodo sin perder la continuidad del servicio oficial.

Para la Intendencia, aporta solicitudes más completas y normalizadas, mejora la calidad de los datos de entrada y amplía la cobertura digital sin modificar su esquema interno de procesamiento. También permite evaluar qué recorridos, ayudas y validaciones disminuyen la necesidad de consultas posteriores.

Para nuestro proyecto, permite demostrar capacidades de experiencia de usuario, accesibilidad, validación de información e interoperabilidad con un servicio público real. La solución se presenta como una puerta de entrada complementaria a Clara y no como una plataforma competidora.

### Piloto y criterios de éxito

Se propone comenzar con una o dos categorías de reclamos que requieran ubicación y evidencia fotográfica. El piloto debería probarse primero con datos ficticios y luego, si existe autorización institucional, con un grupo controlado de usuarios.

Los principales indicadores serían:

* Porcentaje de transferencias recibidas y confirmadas correctamente por Clara.
* Porcentaje de reclamos que llegan con todos los datos obligatorios.
* Reducción de consultas posteriores por información faltante.
* Tiempo necesario para completar y registrar una solicitud.
* Cantidad de duplicados o transferencias fallidas.
* Satisfacción y facilidad de uso percibida por la ciudadanía.
* Uso relativo de la aplicación y del acceso directo por WhatsApp, sin establecer una competencia entre ambos canales.

### Condiciones para la asociación y difusión

Antes del piloto deberán acordarse el mecanismo de integración, los campos obligatorios, la responsabilidad ante fallas, la retención de datos, la seguridad de las evidencias, el consentimiento ciudadano, la accesibilidad y el uso de la identidad visual de Clara y de la Intendencia. La aplicación deberá indicar con claridad cuándo está preparando la solicitud y cuándo esta fue aceptada oficialmente por Clara.

Como contrapartida por el desarrollo y la evaluación del frontend alternativo, se propone que la Intendencia reconozca la colaboración en la presentación o comunicación del piloto, con enlaces o referencias al proyecto y al equipo responsable. Toda difusión deberá contar con aprobación previa y explicar que nuestra aplicación es un canal complementario de preparación y transferencia, mientras que Clara es el servicio oficial que recibe y procesa el reclamo.

### Próximo paso recomendado

Realizar un taller técnico y funcional con el Área de Innovación y Tecnología y las personas responsables de Clara. El taller debería confirmar si existe una interfaz oficial de integración, definir el contrato de datos y la confirmación de recepción, seleccionar las categorías del piloto y acordar responsabilidades, controles de privacidad, indicadores y criterios para comunicar públicamente la colaboración.
