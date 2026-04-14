# Proyecto UTU-Polo 2026

## Título: Sistema de Control de Asistencia y Talleres en Convenio con INAU

## Objetivos

* Proyecto de egreso para el grupo de 3º año EMT 2026.
* Desarrollo de una solución informática completa para la gestión de talleres, participantes y asistencias en el marco de actividades realizadas en convenio con INAU.
* Aplicación integrada de competencias de análisis, modelado, desarrollo, documentación, testing y organización del trabajo.
* Presentación del proyecto en formato institucional, con documentación técnica y demostración funcional.

## Justificación pedagógica

Este proyecto integra competencias técnicas, metodológicas y organizativas alineadas con el enfoque competencial del MCN 2025 y con el perfil de egreso técnico-tecnológico de 3º EMT. Se plantea una situación auténtica de desarrollo de software vinculada a una necesidad real de organización, seguimiento y control de actividades socioeducativas.

El trabajo permite que los estudiantes:

* analicen requerimientos reales de una organización;
* modelen una solución informática con múltiples actores y permisos;
* diseñen interfaces diferenciadas según rol;
* desarrollen un backend con endpoints y persistencia de datos;
* implementen almacenamiento de adjuntos en filesystem;
* documenten decisiones técnicas;
* trabajen colaborativamente con trazabilidad;
* apliquen criterios de calidad, organización y ética en el manejo de datos personales.

Desde el punto de vista pedagógico, el proyecto favorece especialmente el desarrollo de competencias vinculadas al pensamiento computacional, pensamiento crítico, pensamiento científico, creatividad, comunicación, iniciativa y trabajo con otros, en concordancia con el MCN. Asimismo, se alinea con las competencias específicas de Ingeniería del Software y Administración de Sistemas Operativos del tramo 8, al requerir análisis de requerimientos, modelado, gestión del proyecto, implementación de una solución web y organización de despliegue y almacenamiento. 

## Público objetivo

INAU y equipo de talleristas

## 1. Fundamentación del Proyecto

El trabajo en talleres en convenio con INAU requiere una herramienta digital que permita registrar de forma ordenada los talleres desarrollados, los participantes asignados, la asistencia diaria y la comunicación interna entre talleristas y administración.

Actualmente, la necesidad de disponer de información confiable, trazable y centralizada sobre talleres, participantes y asistencias justifica el desarrollo de una plataforma específica. Esta solución permitirá mejorar el seguimiento de los procesos de participación, facilitar la generación de informes y asegurar una mejor coordinación entre quienes dictan los talleres y quienes administran la información.

El proyecto busca desarrollar un sistema compuesto por dos interfaces diferenciadas y un backend centralizado, capaz de gestionar usuarios, talleristas, participantes, talleres, asistencia, archivos adjuntos, mensajería interna e informes administrativos.

## 2. Arquitectura General del Sistema

### 2.1 Componentes

**Panel del Tallerista**

Interfaz web responsive, pensada para uso en computadora, tablet o celular durante el desarrollo del taller y el pasaje de lista.

Funciones principales:

* Inicio de sesión con usuario y contraseña.
* Creación de talleres.
* Edición de sus propios talleres.
* Registro de:
  * nombre del taller
  * descripción
  * temáticas a trabajar
  * lugar
  * documentos adjuntos
* Carga de archivos adjuntos permitidos:
  * PDF
  * imágenes
  * documentos de oficina
* Consulta de participantes asignados.
* Pasaje de lista día a día del taller.
* Registro de asistencia por participante y por fecha.
* Registro de observaciones por asistencia.
* Corrección de asistencias cargadas por el propio tallerista.
* Notificación automática al administrador cuando una asistencia es corregida por el tallerista.
* Consulta de informes de asistencia:
  * por participante
  * por rango de fechas
  * por taller
* Envío de mensajes internos al administrador para:
  * solicitud de registro de participantes
  * solicitud de insumos
  * solicitud de soporte

**Panel Administrador**

Interfaz administrativa para la gestión integral del sistema.

Funciones principales:

* Gestión de usuarios del sistema.
* CRUD de talleristas.
* CRUD de participantes.
* Alta de cuentas de talleristas.
* Asignación de participantes a talleres.
* Visualización y modificación de cualquier taller registrado.
* Visualización y modificación de cualquier dato o adjunto cargado por un tallerista.
* Registro de trazabilidad cuando el administrador modifica información creada por un tallerista.
* Envío de mensajes internos a cualquier tallerista.
* Consulta y modificación de registros de asistencia.
* Consulta de informes de asistencia:
  * por participante
  * por rango de fechas
  * por taller
* Consulta de informes de talleristas:
  * por rango de fechas y taller
  * por taller
  * talleristas que trabajaron con un participante determinado

**Backend**

Backend centralizado encargado de la lógica del negocio, la persistencia de datos y la exposición de endpoints para las dos interfaces.

Tecnologías:

* PHP / Laravel
* MySQL
* Almacenamiento en filesystem
* API REST

## 3. Reglas funcionales principales del sistema

### 3.1 Gestión de usuarios

La plataforma admite dos tipos de usuario:

* administrador
* tallerista

Los participantes no acceden al sistema.

Cada usuario accede únicamente a las funciones correspondientes a su rol.

### 3.2 Gestión de talleristas

El sistema permitirá administrar talleristas mediante operaciones de alta, baja lógica, modificación y consulta.

Cada tallerista tendrá cuenta de acceso con usuario y contraseña, creada por el administrador.

### 3.3 Gestión de participantes

El sistema permitirá administrar participantes mediante operaciones de alta, baja lógica, modificación y consulta.

Campos mínimos sugeridos:

* nombre y apellido
* cédula de identidad
* fecha de nacimiento
* teléfono
* dirección
* email
* referente adulto
* observaciones
* centro o programa de referencia
* situación de derivación
* fecha de ingreso

Un participante podrá estar asignado a más de un taller.

La asignación de participantes a talleres será realizada exclusivamente por el administrador.

El tallerista podrá visualizar la ficha completa del participante, pero no podrá registrarlo directamente en el sistema.

### 3.4 Gestión de talleres

Los talleres podrán ser creados por:

* talleristas
* administradores

Cada taller podrá estar asociado a uno o más talleristas.

El sistema deberá permitir registrar como mínimo:

* nombre del taller
* descripción
* temáticas a trabajar
* lugar
* documentos adjuntos

Tipos de archivo admitidos:

* PDF
* imágenes
* documentos de oficina

Estados posibles del taller:

* planificado
* en curso
* finalizado
* suspendido

El administrador podrá reasignar talleres a otros talleristas.

### 3.5 Control de asistencia

El pasaje de lista se realizará por:

* fecha
* taller
* participante
* estado de asistencia

Estados posibles de asistencia:

* presente
* ausente
* justificado
* tardanza

Cada registro de asistencia podrá incluir observaciones.

Solo podrá existir un registro de asistencia por participante, por fecha y por taller.

El tallerista podrá corregir asistencias registradas por él mismo. Cuando esto suceda, la plataforma deberá:

* marcar el registro como corregido;
* conservar trazabilidad de la corrección;
* enviar un mensaje interno al administrador informando la modificación.

El administrador podrá modificar cualquier asistencia. Si modifica un registro originalmente cargado por un tallerista, deberá quedar explícitamente registrado que fue modificado por el administrador.

### 3.6 Informes

El sistema deberá permitir la generación de informes de asistencia con los siguientes datos:

**Por participante**

* cantidad de asistencias
* cantidad de inasistencias
* porcentaje de asistencia
* detalle por fechas

**Por rango de fechas**

* posibilidad de filtrar por tallerista
* detalle de asistencias e inasistencias dentro del rango indicado

**Por taller**

* cantidad de participantes
* porcentaje general de asistencia
* detalle de cada encuentro

### 3.7 Informes de talleristas

El sistema deberá permitir informes de talleristas:

* por rango de fechas y taller
* por taller
* talleristas que trabajaron con un participante determinado

En este último caso, el informe deberá listar como mínimo:

* nombre del tallerista
* taller
* fechas en las que el participante asistió o tuvo actividad vinculada al taller

### 3.8 Mensajería interna

El sistema incluirá una bandeja simple de mensajes internos entre administrador y talleristas.

Características:

* mensajes con estado de leído;
* el estado cambia automáticamente cuando el usuario abre el mensaje;
* el tallerista solo podrá visualizar sus propios mensajes;
* el administrador podrá enviar mensajes a cualquier tallerista;
* el tallerista podrá enviar mensajes al administrador.

Tipos de mensaje sugeridos para uso de talleristas:

* solicitud de registro de participante
* solicitud de insumos
* solicitud de soporte

En esta etapa, estas solicitudes funcionarán como mensajes internos comunes.

## 4. Endpoints mínimos del Backend

### 4.1 Autenticación

* POST /auth/login
* POST /auth/logout
* GET /auth/me

### 4.2 Usuarios

* GET /usuarios
* POST /usuarios
* GET /usuarios/{id}
* PUT /usuarios/{id}
* DELETE /usuarios/{id}

### 4.3 Talleristas

* GET /talleristas
* POST /talleristas
* GET /talleristas/{id}
* PUT /talleristas/{id}
* DELETE /talleristas/{id}

### 4.4 Participantes

* GET /participantes
* POST /participantes
* GET /participantes/{id}
* PUT /participantes/{id}
* DELETE /participantes/{id}

### 4.5 Talleres

* GET /talleres
* POST /talleres
* GET /talleres/{id}
* PUT /talleres/{id}
* DELETE /talleres/{id}
* PATCH /talleres/{id}/estado
* POST /talleres/{id}/adjuntos
* GET /talleres/{id}/adjuntos

### 4.6 Asignación de participantes

* GET /talleres/{id}/participantes
* POST /talleres/{id}/participantes
* DELETE /talleres/{id}/participantes/{participanteId}

### 4.7 Asistencias

* GET /asistencias
* POST /asistencias
* GET /asistencias/{id}
* PUT /asistencias/{id}
* PATCH /asistencias/{id}/corregir
* DELETE /asistencias/{id}

### 4.8 Mensajes internos

* GET /mensajes
* POST /mensajes
* GET /mensajes/{id}
* PATCH /mensajes/{id}/leer
* POST /mensajes/{id}/responder

### 4.9 Reportes

* GET /reportes/asistencia-participante
* GET /reportes/asistencia-rango-fechas
* GET /reportes/asistencia-taller
* GET /reportes/talleristas-rango-fechas
* GET /reportes/talleristas-por-taller
* GET /reportes/talleristas-por-participante

## 5. Modelo de Datos (mínimo requerido)

Tablas sugeridas:

* usuarios
* roles
* talleristas
* participantes
* talleres
* taller_participante
* asistencias
* mensajes_internos
* historial_actividad
* adjuntos

### 5.1 Descripción general de tablas

**usuarios**

Almacena credenciales y datos básicos de acceso de administradores y talleristas.

**roles**

Define el rol de cada usuario del sistema.

**talleristas**

Contiene la información específica de los talleristas.

**participantes**

Contiene la ficha de cada participante registrado.

**talleres**

Almacena la información general de cada taller.

**taller_participante**

Resuelve la relación entre talleres y participantes, permitiendo que un participante esté en varios talleres.

**asistencias**

Registra la asistencia de cada participante por fecha y por taller, con trazabilidad de creación y modificación.

**mensajes_internos**

Almacena mensajes entre administrador y talleristas, con estado de lectura.

**historial_actividad**

Permite conservar trazabilidad de acciones relevantes del sistema, como creación de talleres, edición de adjuntos, corrección de asistencias y modificaciones administrativas.

**adjuntos**

Almacena la referencia a archivos asociados a talleres, guardados físicamente en el filesystem del backend.

## 6. Requisitos No Funcionales

* Control de roles y permisos.
* Validación de entradas en formularios y endpoints.
* Persistencia confiable de datos.
* Diseño responsive, con especial atención a la interfaz del tallerista.
* Usabilidad clara para carga rápida de asistencia.
* Protección de datos personales de participantes.
* Trazabilidad de modificaciones realizadas por talleristas y administradores.
* Restricción de formatos de adjuntos permitidos.
* Separación entre frontend y backend.
* Organización del sistema bajo arquitectura de endpoints REST.

## 7. Organización del Trabajo

### 7.1 Roles mínimos por equipo

Equipo sugerido: 5 integrantes

* Líder de proyecto
* Desarrollador Backend
* Desarrollador Frontend Administrador
* Desarrollador Frontend Tallerista
* Responsable de Base de Datos, Testing y Documentación

### 7.2 Gestión Git / Entregas

* 1 repositorio por grupo.
* Uso obligatorio de Git para trazabilidad.
* Pull Requests obligatorias.
* Registro claro y consistente de commits.
* Reporte quincenal de avance.
* Documentación técnica obligatoria dentro del repositorio.

> Nota: aunque el trabajo se desarrollará sobre un único repositorio sin estrategia formal de ramas, se exigirá igualmente orden en la trazabilidad, revisión de cambios y control de versiones.

## 8. Entregables Obligatorios

### 8.1 Documentación (Markdown)

* README.md
* 01-requerimientos.md
* 02-modelado.md
* 03-api.md
* 04-seguridad.md
* 05-planificacion.md
* 06-testing.md

### 8.2 Producto funcional

* 2 interfaces funcionando:
  * panel administrador
  * panel tallerista
* Base de datos persistente.
* Gestión completa de talleristas y participantes.
* Gestión de talleres con adjuntos.
* Flujo completo de control de asistencia implementado.
* Mensajería interna operativa.
* Informes de asistencia y de talleristas funcionando.

## 9. Evaluación (100 puntos)

### 9.1 Entregables

* Requerimientos (15)
* Modelado (15)
* Backend (20)
* Frontend (20)
* Git y trazabilidad (10)
* Testing (10)
* Documentación y presentación técnica (10)

### 9.2 Defensa Final

* Demo de 15 minutos.
* Preguntas individuales.
* Justificación técnica de decisiones.
* Explicación del modelo funcional implementado.
* Defensa del reparto de tareas y aportes individuales.

## 10. Plantillas para proyecto

### 10.1 Repositorio Git

control-asistencia-talleres-inau/
│
├── backend/
│   ├── app/
│   ├── routes/
│   ├── database/
│   └── README.md
│
├── frontend-admin/
│   ├── index.html
│   ├── css/
│   ├── js/
│   └── README.md
│
├── frontend-tallerista/
│   ├── index.html
│   ├── css/
│   ├── js/
│   └── README.md
│
├── docs/
│   ├── 01-requerimientos.md
│   ├── 02-modelado.md
│   ├── 03-api.md
│   ├── 04-seguridad.md
│   ├── 05-planificacion.md
│   └── 06-testing.md
│
├── .gitignore
├── LICENSE
└── README.md

### 10.2 README.md del repo

# Sistema de Control de Asistencia y Talleres en Convenio con INAU

Proyecto Egreso 2026

## Integrantes
- Nombre 1 – Líder de proyecto
- Nombre 2 – Backend
- Nombre 3 – Frontend Administrador
- Nombre 4 – Frontend Tallerista
- Nombre 5 – Base de datos, testing y documentación

## Tecnologías
- Laravel
- MySQL
- Vanilla JS
- Tailwind / Bootstrap

## Cómo ejecutar el proyecto

### Backend
1. Clonar repositorio
2. Configurar .env
3. Ejecutar migraciones
4. Levantar servidor Laravel

### Frontend
Abrir cada frontend con servidor local o integrarlo al entorno definido por el equipo.

## Estructura del proyecto
Ver carpeta /docs para documentación completa.

## 11. Posibles mejoras a futuro

El proyecto base no contempla algunas funcionalidades que podrían proponerse como ampliación o evolución posterior. Entre ellas:

* panel estadístico con gráficos;
* exportación de informes a PDF o Excel;
* portal para participantes o referentes;
* firma digital o validación avanzada de asistencia;
* notificaciones automáticas;
* solicitudes formales procesables en lugar de mensajes simples;
* control de insumos por taller;
* múltiples niveles de permisos administrativos;
* seguimiento más detallado de intervenciones socioeducativas.