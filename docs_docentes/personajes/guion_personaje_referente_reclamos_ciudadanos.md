# Andrea, notas para la entrevista (reclamos ciudadanos)

Guía del personaje Andrea, esto no es la guía de preguntas de los estudiantes, es para tener claro el personaje y no resolverles el relevamiento sin querer.

La gracia acá es que no hay resistencia a la tecnología, hay optimismo de más. Andrea no complica nada porque para ella nada es complicado, así que el grupo se va a tener que enfocar para que se detenga a pensar en detalles que da por resueltos o que directamente ni se le cruzan por la cabeza.

Proyecto: [sistema_gestion_reclamos_ciudadanos.md](../Proyectos/sistema_gestion_reclamos_ciudadanos.md)

## De dónde viene todo esto

Atención Ciudadana es un área nueva dentro de la IMSJ, armada después del cambio de signo político en las últimas elecciones departamentales. Andrea quedó a cargo. La que figura como sponsor formal del proyecto es la Intendente, pero en los hechos no va a aparecer nunca por la entrevista ni por ninguna reunión, confía en el criterio de Andrea y le delega todo.

Eso pone a Andrea en una posición particular: tiene autoridad real para decidir, pero también tiene mucho interés en acertar, porque la nueva administración necesita mostrar resultados pronto y ella no quiere ser la que atrasa las cosas ni la que le hace quedar mal a la Intendente. Si el proyecto sale bien, es una carta a favor de las dos, de ahí que tienda a mostrarlo todo fácil, para no sembrar dudas sobre si fue buena idea encargarle esto a ella.

## Cómo habla el personaje

Alegre, informal, cercana. Nunca se tensa, ni cuando el grupo le marca problemas grandes, todo lo minimiza con una sonrisa: "esto para ustedes debe ser cosa fácil", "che, pero esto no es largo, lo sacan en un día o dos", "ustedes son los expertos, a mí no me pregunten cómo se hace, yo solo les digo lo que necesitamos". Tira algún chiste liviano de vez en cuando, tipo "yo de sistemas entiendo lo mismo que de arreglar un auto: prendo las balizas y llamo a alguien".

No hay desconfianza en ella, al contrario: confía de más, y esa confianza mal puesta es lo que el grupo tiene que aprender a manejar. Nunca le dice que no a un pedido de información, pero tampoco se toma el trabajo de pensarlo antes de contestar, así que a veces responde rápido y después se contradice sin darse cuenta.

## Lo que dice que quiere

Un sistema que "resuelva todo", que la gente pueda hacer un reclamo y listo, sin vueltas. No entra en detalles de roles, de estados, de qué pasa si un reclamo se rechaza, para ella eso "lo ven ustedes, son detalles técnicos". Quiere algo prolijo para mostrar, pensando sobre todo en los Premios Nodo y en la imagen de la nueva gestión departamental.

## Lo que en realidad hace falta (esto el grupo lo tiene que sacar con preguntas, Andrea no lo va a plantear sola)

* Todo el flujo de estados de un reclamo bien definido, con claridad sobre quién puede moverlo de un estado a otro. Andrea da por hecho que "eso se entiende solo".
* Roles diferenciados entre ciudadanía, comuna y equipos o proveedores externos que resuelven los reclamos,  ella no distingue bien entre "el sistema" y "quién hace qué adentro del sistema".
* Validación de identidad del ciudadano al registrarse (la API docente de validación de CI), porque si no, cualquiera podría cargar un reclamo con datos falsos o a nombre de otra persona, y eso, políticamente, sería un problema serio para la imagen de la gestión.
* Manejo cuidado de evidencias fotográficas y de video: quién las puede ver, si son públicas, qué pasa si una foto muestra algo sensible de un vecino.
* Reportes e indicadores para mostrar resultados, reclamos resueltos, tiempos de resolución, desempeño de equipos o proveedores. Los va a pedir en algún momento de la entrevista, casi como si se le ocurriera de repente, sin conectar que para tener esos números después hace falta que el sistema registre bien los datos desde el principio.
* Protección de los datos personales de la ciudadanía, algo que a ella ni se le cruza espontáneamente, pero que si el grupo no lo menciona puede terminar apareciendo como una exigencia tardía, "porque en la intendencia seguro me lo preguntan".
* Qué pasa con el sistema después del proyecto educativo: quién lo mantiene, quién carga los proveedores, quién actualiza los datos. A Andrea esto le resulta lejano, "eso lo vemos cuando llegue el momento".

## La tensión que hay que sostener

Con Andrea no hay resistencia contra innovación, todo lo contrario: exceso de confianza contra la complejidad real de lo que se está pidiendo. Andrea no pone trabas, pero tampoco entrega información precisa si no se la sacan con preguntas concretas, no por desconfianza, sino porque ella misma está muy enfocada en su rol y no se paró a pensarlo. Y de fondo siempre está la necesidad política: que el proyecto quede bien parado ante la Intendente y ayude a consolidar el área nueva de cara a la continuidad de la gestión.

Frase ancla, para sostener el tono en toda la entrevista:

> "Ay, no se compliquen tanto, esto para ustedes debe ser cosa fácil. Yo confío en lo que ustedes decidan, eh, totalmente. Eso sí, lo necesitamos andando y quedando bien, porque a la Intendente esto le importa mucho, y si queda lindo, quedamos bien todos."

## Respuestas para tener a mano

**Por qué se hace el proyecto**, "Atención Ciudadana es un área nueva, la armamos apenas asumimos, y queremos que se note el cambio, que la gente vea que ahora los reclamos se atienden en serio. Además esto va para los Premios Nodo, así que cuanto más profesional se vea, mejor para todos."

**Sobre roles y permisos**, "¿Roles? Mirá, no sé, ¿no es que cada uno entra y hace lo suyo nomás? Ustedes definan eso, que seguro tienen más idea que yo." Si el grupo insiste con un ejemplo concreto, ¿puede un vecino cerrar su propio reclamo?, ¿puede un proveedor ver los reclamos de otro proveedor?, ahí recién empieza a pensarlo en serio.

**Sobre validación de identidad**, "¿Hace falta pedir cédula y todo eso? Yo pensé que con el nombre y el teléfono alcanzaba." Si le explican el riesgo de reclamos falsos o de alguien haciéndose pasar por otro vecino, cambia el tono: "no, eso no, imaginate que después sale en la prensa que cualquiera podía inventar un reclamo con el nombre de otro."

**Sobre evidencias y fotos**, "Que suban fotos, sí, eso está bueno, se ve prolijo el antes y el después." Si preguntan quién puede verlas o qué pasa si aparece algo privado de un vecino, se queda pensando: "mirá, no lo había pensado así, pero tenés razón, eso hay que cuidarlo."

**Sobre reportes**, "Ah, sí, reportes necesitamos seguro, para mostrarle a la Intendente cómo venimos, cantidad de reclamos, tiempos, esas cosas." No conecta que para tener esos números buenos el sistema tiene que registrar bien los datos desde el arranque, lo da por garantizado.

**Sobre datos personales**, "¿Seguridad de los datos? Y, supongo que sí, como cualquier sistema, ¿no?" Recién si el grupo menciona una filtración real en otra intendencia, se pone seria un momento: "no, eso no nos puede pasar, menos ahora que recién arrancamos la gestión."

**Sobre qué pasa después del proyecto**, "Y bueno, eso lo vemos cuando se termine el año, ¿no? Ahora priorizamos que funcione para la presentación." Si insisten en quién va a mantener el sistema en producción, recién ahí admite que todavía no está definido.

**Si preguntan directamente qué necesita del equipo**, "Necesito que esto salga bien y que se note el cambio. No hace falta que sea complicado, al contrario, cuanto más simple mejor. Ustedes saben de esto, yo confío, solo les pido que no se me atrasen mucho, que yo también tengo que rendir cuentas para arriba."

## Cosas de las que no hay que ceder fácil

Andrea no va a discutir nada técnico, va a estar de acuerdo con casi todo lo que le propongan. El desafío para el grupo no es convencerla, es lograr que se detenga a definir las cosas antes de decir que sí a todo. Si le dan una lista de opciones sin pedirle una decisión concreta, va a elegir "lo que sea más rápido" sin pensarlo demasiado. Conviene no dejarla escapar con un "ustedes decidan" cuando la decisión es algo que solo ella puede tomar, por ejemplo, qué tan estricta debe ser la validación de identidad, o qué tan público debe ser el mapa de reclamos.

## Cuándo se pone seria

Cuando el grupo conecta el pedido con la interna política: el riesgo de quedar mal ante la Intendente, la posibilidad de que algo termine en la prensa, o que el área nueva quede mal parada frente a otras direcciones de la comuna. Ahí Andrea deja el chiste por un momento, aunque enseguida vuelve a aflojar el ambiente con algún comentario optimista.

* Validación de identidad: cede rápido si se lo conecta con fraude o suplantación de identidad.
* Privacidad de evidencias: cede si se lo conecta con un caso de filtración o escándalo mediático.
* Reportes: los pide todos, sin medir el esfuerzo que implica generarlos.
* Sostenibilidad después del proyecto: es lo que más le cuesta tomar en serio, casi no hay argumento que la haga pensarlo a fondo durante la entrevista, queda como algo para una reunión futura.

## Cierre

Algo en esta línea, en personaje:

> "¡Pero esto salió redondo! Ustedes tranquilos que lo van a hacer bárbaro, yo les tengo fe. Cualquier cosa que necesiten, me avisan y seguimos para adelante. ¡Vamo'arriba con esto!"

Después de esto, salir del personaje y comentar con el grupo qué cosas quedaron sin definir porque Andrea las dio por sentado, y en qué momentos deberían haber insistido más para sacarle una respuesta concreta.
