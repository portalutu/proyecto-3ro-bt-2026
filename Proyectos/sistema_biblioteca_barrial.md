# Proyecto UTU-Polo 2026

## Título: Sistema de Gestión de Biblioteca Barrial

## Objetivos

* Proyecto de egreso para el grupo de 3º año EMT 2026.
* Desarrollo de una solución informática completa para la gestión de socios, catálogo, préstamos, devoluciones y seguimiento administrativo de una biblioteca barrial.
* Aplicación integrada de competencias de análisis, modelado, desarrollo, documentación, testing y organización del trabajo.
* Presentación del proyecto en formato institucional, con documentación técnica y demostración funcional.

## Justificación pedagógica

Este proyecto integra competencias técnicas, metodológicas y organizativas alineadas con el enfoque competencial del MCN 2025 y con el perfil de egreso técnico-tecnológico de 3º EMT. Se propone una situación auténtica de desarrollo de software, vinculada a una necesidad real de organización cultural y gestión comunitaria.

El trabajo permite que los estudiantes:

* analicen requerimientos reales de una institución;
* modelen una solución informática completa;
* diseñen interfaces diferenciadas según roles de usuario;
* implementen un backend con endpoints y persistencia de datos;
* documenten decisiones técnicas;
* trabajen colaborativamente con trazabilidad;
* apliquen criterios de calidad, organización y ética en el tratamiento de datos personales.

Desde el punto de vista pedagógico, el proyecto favorece especialmente el desarrollo de competencias vinculadas al pensamiento computacional, pensamiento crítico, pensamiento científico, creatividad, comunicación, iniciativa y trabajo con otros, en concordancia con el MCN. Asimismo, se alinea con las competencias específicas de Ingeniería del Software y Administración de Sistemas Operativos del tramo 8, al requerir análisis de requerimientos, modelado, gestión del proyecto, implementación de una solución web y despliegue organizado del sistema.

## Público objetivo (Donación del Polo Tecnológico San José)

Biblioteca barrial o comunitaria

## 1. Fundamentación del Proyecto

Las bibliotecas barriales cumplen un rol social y cultural importante, pero con frecuencia gestionan sus préstamos, devoluciones, registro de socios y control del catálogo mediante planillas dispersas, cuadernos o procedimientos manuales. Esta situación dificulta el seguimiento de ejemplares disponibles, los vencimientos de préstamo, la detección de retrasos y la obtención de información confiable para la toma de decisiones.

El proyecto busca desarrollar un sistema compuesto por tres interfaces diferenciadas y un backend centralizado, capaz de gestionar usuarios, socios, libros, ejemplares, préstamos, reservas, multas simples, notificaciones y reportes administrativos.

La propuesta contempla la operativa habitual de una biblioteca de pequeña o mediana escala, donde una persona socia puede consultar el catálogo y sus préstamos vigentes, el personal bibliotecario puede registrar préstamos y devoluciones, y la administración puede mantener el catálogo, controlar morosidad, generar reportes y supervisar la actividad general del sistema.

## 2. Arquitectura General del Sistema

### 2.1 Componentes

**Portal del Socio**

Interfaz web responsive para socios autenticados, orientada a la consulta y autogestión básica.

Funciones principales:

* Inicio de sesión con usuario y contraseña.
* Consulta del catálogo disponible.
* Búsqueda de libros por título, autor, categoría o palabra clave.
* Visualización de préstamos vigentes e historial personal.
* Consulta de fecha de vencimiento de cada préstamo.
* Solicitud de reserva de libros disponibles para reserva.
* Consulta de notificaciones del sistema.
* Actualización de datos personales básicos.

**Panel del Bibliotecario**

Interfaz web responsive orientada al trabajo operativo diario de atención y registro.

Funciones principales:

* Inicio de sesión con usuario y contraseña.
* Búsqueda rápida de socios y libros.
* Registro de préstamos.
* Registro de devoluciones.
* Renovación de préstamos según reglas definidas.
* Visualización de reservas pendientes.
* Confirmación de entrega de un libro reservado.
* Registro de observaciones sobre ejemplares:
  * deteriorado
  * extraviado
  * fuera de circulación
* Consulta de préstamos vencidos.

**Panel Administrador**

Interfaz administrativa para la gestión integral del sistema.

Funciones principales:

* Gestión de usuarios del sistema.
* Alta y gestión de bibliotecarios.
* CRUD de socios.
* CRUD de libros y categorías.
* Gestión de ejemplares físicos por libro.
* Cambio de estado de ejemplares:
  * disponible
  * prestado
  * reservado
  * extraviado
  * fuera de circulación
* Configuración de plazos básicos de préstamo.
* Consulta de préstamos activos, vencidos y devueltos.
* Registro o anulación de multas simples por atraso o pérdida.
* Consulta de reportes:
  * préstamos por período
  * libros más prestados
  * socios con retrasos
  * disponibilidad del catálogo
* Envío de notificaciones internas a socios.

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
* bibliotecario
* socio

Cada usuario accede únicamente a las funciones correspondientes a su rol.

### 3.2 Gestión de socios

El sistema permitirá administrar socios mediante operaciones de alta, baja lógica, modificación y consulta.

Campos mínimos sugeridos:

* número de socio
* foto
* nombre y apellido
* cédula de identidad
* dirección
* teléfono
* email
* fecha de alta
* estado del socio

Estados posibles:

* activo
* suspendido
* inactivo

Un socio suspendido no podrá registrar nuevos préstamos hasta regularizar su situación.

### 3.3 Gestión del catálogo

El sistema permitirá registrar libros y sus ejemplares físicos.

Cada libro deberá incluir como mínimo:

* título
* autor
* editorial
* año de edición
* ISBN, si corresponde
* categoría
* descripción breve
* foto portada

Cada ejemplar deberá incluir como mínimo:

* código interno
* libro asociado
* estado
* ubicación física

Un mismo libro podrá tener varios ejemplares.

### 3.4 Préstamos

Los préstamos serán registrados por bibliotecario o administrador.

Cada préstamo deberá registrar:

* socio
* ejemplar prestado
* fecha de préstamo
* fecha de vencimiento
* estado
* usuario que registró la operación

Estados posibles del préstamo:

* activo
* vencido
* devuelto
* anulado

Un ejemplar no podrá estar asociado a más de un préstamo activo al mismo tiempo.

### 3.5 Devoluciones y renovaciones

Cuando un ejemplar sea devuelto, el sistema deberá registrar la fecha de devolución y actualizar su disponibilidad.

La renovación de un préstamo será posible únicamente si:

* el préstamo no está vencido; y
* el ejemplar no tiene una reserva pendiente de otro socio.

La cantidad máxima de renovaciones podrá definirse como una regla simple del sistema.

### 3.6 Reservas

El sistema permitirá registrar reservas de libros o ejemplares según la lógica definida por el equipo.

Reglas mínimas sugeridas:

* un socio solo podrá reservar si está activo;
* no podrá tener más de una reserva activa para el mismo libro;
* cuando un ejemplar reservado quede disponible, el sistema deberá marcarlo como pendiente de retiro;
* si la reserva no se concreta dentro del plazo definido, podrá ser cancelada.

### 3.7 Morosidad y multas simples

A efectos de este proyecto, se considerará en atraso a todo socio que mantenga préstamos vencidos.

El sistema podrá registrar multas simples por:

* devolución fuera de fecha;
* pérdida de ejemplar;
* deterioro grave del material.

No es necesario integrar pasarela de pago. El registro de multa podrá manejarse como deuda administrativa interna.

### 3.8 Notificaciones

El sistema incluirá notificaciones internas visibles para el socio dentro de su portal.

El administrador podrá enviar notificaciones individuales.

También podrán generarse notificaciones automáticas por:

* préstamo próximo a vencer;
* préstamo vencido;
* reserva disponible para retiro.

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

### 4.4 Bibliotecarios

* GET /bibliotecarios
* POST /bibliotecarios
* GET /bibliotecarios/{id}
* PUT /bibliotecarios/{id}
* DELETE /bibliotecarios/{id}

### 4.5 Libros

* GET /libros
* POST /libros
* GET /libros/{id}
* PUT /libros/{id}
* DELETE /libros/{id}

### 4.6 Ejemplares

* GET /ejemplares
* POST /ejemplares
* GET /ejemplares/{id}
* PUT /ejemplares/{id}
* PATCH /ejemplares/{id}/estado
* DELETE /ejemplares/{id}

### 4.7 Préstamos

* GET /prestamos
* POST /prestamos
* GET /prestamos/{id}
* PATCH /prestamos/{id}/devolver
* PATCH /prestamos/{id}/renovar
* PATCH /prestamos/{id}/anular

### 4.8 Reservas

* GET /reservas
* POST /reservas
* GET /reservas/{id}
* PATCH /reservas/{id}/confirmar
* PATCH /reservas/{id}/cancelar

### 4.9 Multas

* GET /multas
* POST /multas
* GET /multas/{id}
* PUT /multas/{id}
* DELETE /multas/{id}

### 4.10 Reportes

* GET /reportes/prestamos-por-periodo
* GET /reportes/libros-mas-prestados
* GET /reportes/socios-con-atrasos
* GET /reportes/disponibilidad-catalogo

### 4.11 Notificaciones

* GET /notificaciones
* POST /notificaciones
* GET /notificaciones/{id}
* PATCH /notificaciones/{id}/leer

## 5. Modelo de Datos (mínimo requerido)

Tablas sugeridas:

* usuarios
* roles
* socios
* bibliotecarios
* categorias
* libros
* ejemplares
* prestamos
* reservas
* multas
* notificaciones
* historial_actividad

### 5.1 Descripción general de tablas

**usuarios**

Almacena credenciales y datos básicos de acceso de administradores, bibliotecarios y socios.

**roles**

Define el rol de cada usuario del sistema.

**socios**

Contiene la información específica de las personas socias de la biblioteca.

**bibliotecarios**

Contiene la información específica del personal bibliotecario.

**categorias**

Permite clasificar los libros por temática o tipo de material.

**libros**

Almacena la información bibliográfica general de cada obra.

**ejemplares**

Representa cada unidad física disponible en la biblioteca y su estado actual.

**prestamos**

Registra los préstamos realizados, fechas relevantes, vencimientos, devoluciones y estado.

**reservas**

Almacena las solicitudes de reserva realizadas por los socios y su seguimiento.

**multas**

Permite registrar deudas administrativas simples vinculadas a atrasos, pérdidas o deterioros.

**notificaciones**

Almacena notificaciones manuales y automáticas dirigidas a los socios.

**historial_actividad**

Permite conservar trazabilidad de acciones relevantes del sistema, como altas, préstamos, devoluciones, renovaciones, reservas, cambios de estado y anulaciones.

## 6. Requisitos No Funcionales

* Control de roles y permisos.
* Validación de entradas en formularios y endpoints.
* Persistencia confiable de datos.
* Diseño responsive en las interfaces principales.
* Búsqueda ágil de socios y libros.
* Protección de datos personales.
* Trazabilidad de operaciones críticas.
* Separación entre frontend y backend.
* Organización del sistema bajo arquitectura de endpoints REST.
* Interfaz clara para tareas frecuentes de préstamo y devolución.

## 7. Organización del Trabajo

**Roles mínimos por equipo**

* Equipo sugerido: 5 integrantes
  * Líder de proyecto
  * Desarrollador Backend
  * Desarrollador/es Frontend
  * Seguridad / Frontend

**Gestión Git / Entregas**

* 1 repositorio por grupo
* Branch main + dev + feature branches
* Pull Requests obligatorias
* Reporte quincenal de actividad
* Trazabilidad Git obligatoria

## 8. Entregables Obligatorios

* Documentación (Markdown)
  * README.md
  * 01-requerimientos.md
  * 02-modelado.md
  * 03-api.md
  * 04-seguridad.md
  * 05-planificacion.md
  * 06-testing.md

* Producto Funcional
  * 3 interfaces funcionando
  * Base de datos persistente
  * Flujo completo de préstamos y devoluciones implementado
  * Gestión de catálogo y ejemplares operativa
  * Reportes básicos funcionando

## 9. Evaluación (100 puntos)

### 9.1 Entregables

* Requerimientos (15)
* Modelado (15)
* Backend (20)
* Frontend (20)
* Git y trazabilidad (10)
* Testing (10)
* Ética y tratamiento de datos (10)

### 9.2 Defensa Final

* Demo de 15 minutos.
* Preguntas individuales.
* Justificación técnica de decisiones.

## 10. Plantilla sugerida para repositorio

biblioteca-barrial/
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
│   └── manifest.json
│
├── frontend-bibliotecario/
│   ├── index.html
│   ├── css/
│   ├── js/
│   └── manifest.json
│
├── frontend-admin/
│   ├── index.html
│   ├── css/
│   └── js/
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
