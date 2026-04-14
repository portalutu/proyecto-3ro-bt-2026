# Proyecto UTU-Polo 2026

## Título: Sistema de Cobros a Socios para Club Ciclista Maragato

## Objetivos

* Proyecto de egreso para el grupo de 3º año EMT 2026.
* Desarrollo de una solución informática completa para la gestión de cuotas sociales, cobranzas y seguimiento de socios del Club Ciclista Maragato.
* Aplicación integrada de competencias de análisis, modelado, desarrollo, documentación, testing y organización del trabajo.
* Presentación del proyecto en formato institucional, con documentación técnica y demostración funcional.

## Justificación pedagógica

Este proyecto integra competencias técnicas, metodológicas y organizativas alineadas con el enfoque competencial del MCN 2025 y con el perfil de egreso técnico-tecnológico de 3º EMT. Se propone una situación auténtica de desarrollo de software, vinculada a una necesidad real de gestión administrativa y operativa de una institución local.  

El trabajo permite que los estudiantes:

* analicen requerimientos reales de un cliente;
* modelen una solución informática completa;
* diseñen interfaces diferenciadas según roles de usuario;
* implementen un backend con endpoints y persistencia de datos;
* documenten decisiones técnicas;
* trabajen colaborativamente con trazabilidad;
* apliquen criterios de calidad, organización y ética en el tratamiento de datos.

Desde el punto de vista pedagógico, el proyecto favorece especialmente el desarrollo de competencias vinculadas al pensamiento computacional, pensamiento crítico, pensamiento científico, creatividad, comunicación, iniciativa y trabajo con otros, en concordancia con el MCN. Asimismo, se alinea con las competencias específicas de Ingeniería del Software y Administración de Sistemas Operativos del tramo 8, al requerir análisis de requerimientos, modelado, gestión del proyecto, implementación de una solución web y despliegue organizado del sistema.   

## Público objetivo

Club Ciclista Maragato

## 1. Fundamentación del Proyecto

El Club Ciclista Maragato requiere una solución digital que permita gestionar de manera ordenada, trazable y eficiente el cobro de cuotas sociales de sus socios. Actualmente, la necesidad de controlar socios activos, cuotas pendientes, tareas de cobranza a domicilio, informes administrativos y comunicación interna con los socios justifica la construcción de una plataforma centralizada.

El proyecto busca desarrollar un sistema compuesto por tres interfaces diferenciadas y un backend centralizado, capaz de gestionar usuarios, socios, recibos virtuales, pagos, notificaciones y reportes administrativos.

La propuesta contempla la operativa habitual del club, donde al inicio del año se generan automáticamente los recibos mensuales de cuota para cada socio activo. A lo largo del año, dichos recibos se irán cancelando a medida que el socio realice sus pagos, ya sea directamente o mediante cobranza a domicilio. El sistema también permitirá que el cobrador disponga de listados actualizados para recorrer a los socios con cuotas pendientes, y que la administración pueda consultar indicadores de cobranza, ingresos y morosidad.

## 2. Arquitectura General del Sistema

### 2.1 Componentes

**Portal del Socio**

Interfaz web para el socio autenticado, orientada a la consulta y autogestión básica.

Funciones principales:

* Inicio de sesión con usuario y contraseña.
* Consulta de cuotas pendientes.
* Visualización del historial de recibos.
* Descarga de recibos.
* Confirmación de pagos realizados.
* Actualización de datos personales básicos.
* Envío de consultas a la administración.
* Recepción de notificaciones internas del sistema.

**Panel del Cobrador**

Interfaz web responsive orientada al trabajo operativo del cobrador, especialmente pensada para uso móvil.

Funciones principales:

* Inicio de sesión con usuario y contraseña.
* Consulta de socios con recibos pendientes o en estado de morosidad.
* Visualización de datos relevantes para la cobranza:
  * nombre del socio
  * dirección
  * teléfono
  * cantidad de recibos pendientes
* Registro de cobros realizados a domicilio.
* Posibilidad de cancelar uno o varios recibos en una misma visita.
* Registro de resultado de visita:
  * no estaba en domicilio
  * no quiso pagar
  * dirección incorrecta
  * volver a visitar

**Panel Administrador**

Interfaz administrativa para la gestión integral del sistema.

Funciones principales:

* Gestión de usuarios del sistema.
* Alta y gestión de cobradores.
* Asignación de carteras de socios a cobradores.
* CRUD de socios.
* Cambio de estado de socios:
  * activo
  * inactivo
  * moroso
* Generación automática anual de 12 recibos mensuales por cada socio activo.
* Registro manual de pagos.
* Anulación o corrección de pagos.
* Consulta de ingresos por cobros.
* Consulta de socios morosos.
* Consulta de porcentaje de cobranza por mes a una fecha dada.
* Envío de notificaciones internas a socios.
* Seguimiento general de la actividad del sistema.

**Backend**

Backend centralizado encargado de la lógica del negocio, la persistencia de datos y la exposición de endpoints para las tres interfaces.

Tecnologías:

* PHP / Laravel
* MySQL
* Almacenamiento en filesystem
* API REST

## 3. Reglas funcionales principales del sistema

### 3.1 Gestión de usuarios

La plataforma admite tres tipos de usuario:

* administrador
* socio
* cobrador

Cada usuario accede únicamente a las funciones correspondientes a su rol.

### 3.2 Gestión de socios

El sistema permitirá administrar socios mediante operaciones de alta, baja lógica, modificación y consulta.

Campos mínimos sugeridos:

* número de socio
* nombre y apellido
* cédula de identidad
* dirección
* teléfono
* email
* fecha de alta
* estado del socio

Estados posibles:

* activo
* inactivo
* moroso

### 3.3 Generación de recibos

Al inicio de cada año, el sistema deberá generar automáticamente 12 recibos virtuales mensuales para cada socio que se encuentre en estado activo.

Cada recibo deberá incluir como mínimo:

* número de recibo
* socio asociado
* período
* fecha de vencimiento
* importe
* estado
* fecha de pago, si corresponde

### 3.4 Cobro de recibos

Los pagos serán completos, no parciales.

Un pago podrá cancelar:

* un único recibo; o
* varios recibos, según lo registrado por el cobrador o el administrador.

El sistema deberá registrar quién realizó el cobro y en qué fecha.

### 3.5 Definición de morosidad

A efectos de este proyecto, se considerará moroso a todo socio que tenga más de un recibo pendiente.

### 3.6 Notificaciones

El sistema incluirá notificaciones internas visibles para el socio dentro de su portal.

El administrador podrá enviar notificaciones individuales.

Cuando el socio visualice una notificación, esta quedará marcada como leída automáticamente.

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

### 4.3 Socios

* GET /socios
* POST /socios
* GET /socios/{id}
* PUT /socios/{id}
* DELETE /socios/{id}
* PATCH /socios/{id}/estado

### 4.4 Recibos

* POST /recibos/generar-anuales
* GET /recibos
* GET /recibos/{id}
* GET /socios/{id}/recibos
* PATCH /recibos/{id}/cancelar
* PATCH /recibos/{id}/anular

### 4.5 Pagos

* GET /pagos
* POST /pagos
* GET /pagos/{id}
* PUT /pagos/{id}
* DELETE /pagos/{id}

### 4.6 Cobranza

* GET /cobranzas/pendientes
* GET /cobranzas/pendientes?fecha=AAAA-MM-DD
* POST /cobranzas/registrar
* POST /cobranzas/resultado-visita

### 4.7 Reportes

* GET /reportes/ingresos
* GET /reportes/morosos
* GET /reportes/cobranza-porcentaje

### 4.8 Notificaciones

* GET /notificaciones
* POST /notificaciones
* GET /notificaciones/{id}
* PATCH /notificaciones/{id}/leer

### 4.9 Consultas del socio

* GET /consultas
* POST /consultas
* GET /consultas/{id}

## 5. Modelo de Datos (mínimo requerido)

Tablas sugeridas:

* usuarios
* roles
* socios
* recibos
* pagos
* notificaciones
* historial_actividad

### 5.1 Descripción general de tablas

**usuarios**

Almacena las credenciales y datos básicos de acceso de administradores, socios y cobradores.

**roles**

Define el rol del usuario dentro del sistema.

**socios**

Contiene la información de cada socio registrado en el club.

**recibos**

Registra cada cuota mensual generada para un socio.

**pagos**

Registra cada pago efectuado, indicando quién lo registró, qué recibos canceló y en qué fecha.

**notificaciones**

Almacena las notificaciones internas enviadas a socios.

**historial_actividad**

Permite conservar trazabilidad de acciones relevantes del sistema, como creación de recibos, registro de pagos, cambios de estado y correcciones administrativas.

## 6. Requisitos No Funcionales

* Control de roles y permisos.
* Validación de entradas en formularios y endpoints.
* Persistencia confiable de datos.
* Diseño responsive, con especial atención a la interfaz del cobrador.
* Navegación clara y usabilidad básica para perfiles no técnicos.
* Protección de datos personales de socios.
* Registro trazable de operaciones relevantes.
* Separación entre frontend y backend.
* Organización del sistema bajo arquitectura de endpoints REST.

## 7. Organización del Trabajo

### 7.1 Roles mínimos por equipo

Equipo sugerido: 5 integrantes

* Líder de proyecto
* Desarrollador Backend
* Desarrollador Frontend Administrador / Socio
* Desarrollador Frontend Cobrador
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

* 3 interfaces funcionando:
  * panel administrador
  * portal del socio
  * panel del cobrador
* Base de datos persistente.
* Recibos generados automáticamente.
* Flujo completo de pagos implementado.
* Reportes administrativos operativos.
* Notificaciones internas funcionando.
* Gestión de socios y usuarios operativa.

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

cobros-club-ciclista-maragato/
│
├── backend/
│   ├── app/
│   ├── routes/
│   ├── database/
│   └── README.md
│
├── frontend-socios/
│   ├── index.html
│   ├── css/
│   ├── js/
│   └── README.md
│
├── frontend-cobrador/
│   ├── index.html
│   ├── css/
│   ├── js/
│   └── README.md
│
├── frontend-admin/
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

# Sistema de Cobros a Socios para Club Ciclista Maragato

Proyecto Egreso 2026

## Integrantes
- Nombre 1 – Líder de proyecto
- Nombre 2 – Backend
- Nombre 3 – Frontend Administrador / Socio
- Nombre 4 – Frontend Cobrador
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

* categorías de socios con cuotas diferenciales;
* recargos automáticos por mora;
* notificaciones masivas;
* notificaciones por grupos de morosos;
* exportación de reportes;
* panel estadístico con gráficos;
* asignación geográfica avanzada para cobranza;
* historial completo de cambios del socio;
* múltiples teléfonos o medios de contacto por socio.