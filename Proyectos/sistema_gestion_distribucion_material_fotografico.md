# Proyecto Polo 2026

## Título: Sistema de Gestión y Distribución de Material Fotográfico

## Objetivos

* Proyecto de egreso para el grupo de 3º año EMT 2026.
* Desarrollo de una solución informática completa para la gestión, organización y distribución de material fotográfico mediante colecciones digitales.
* Aplicación integrada de competencias de análisis, modelado, desarrollo, documentación, testing y organización del trabajo.
* Presentación del proyecto en formato institucional, con documentación técnica y demostración funcional.

## Justificación pedagógica

Este proyecto integra competencias técnicas, metodológicas y organizativas alineadas con el enfoque competencial del MCN 2025 y con el perfil de egreso técnico-tecnológico de 3º EMT. Se plantea una situación auténtica de desarrollo de software vinculada a la gestión de contenido digital y distribución controlada de archivos multimedia.

El trabajo permite que los estudiantes:

* analicen requerimientos de gestión de contenido digital;
* modelen una solución con control de acceso por roles;
* diseñen interfaces diferenciadas para administración y clientes;
* desarrollen un backend con endpoints y persistencia de datos;
* implementen almacenamiento de archivos en filesystem;
* documenten decisiones técnicas;
* trabajen colaborativamente con trazabilidad;
* apliquen criterios de seguridad y control en la distribución de archivos;
* implementen una relación many-to-many entre clientes y colecciones para gestionar visibilidad.

Desde el punto de vista pedagógico, el proyecto favorece el desarrollo de competencias vinculadas al pensamiento computacional, pensamiento crítico, creatividad, comunicación, iniciativa y trabajo en equipo, en concordancia con el MCN. Asimismo, se alinea con las competencias específicas de Ingeniería del Software y Administración de Sistemas Operativos del tramo 8, al requerir modelado, implementación de backend, control de acceso, gestión de archivos y organización del despliegue.

## Público objetivo

Clientes registrados y administradores de contenido fotográfico.

## 1. Fundamentación del Proyecto

Se requiere un sistema digital que permita la gestión, visualización y descarga controlada de material fotográfico por parte de usuarios registrados.

El sistema estará orientado a la organización de imágenes en colecciones temáticas, facilitando su acceso, consulta y descarga de manera ordenada. Todas las imágenes deberán pertenecer a una colección, ya que las colecciones funcionarán como unidad principal de organización y control de acceso.

A su vez, permitirá a los administradores gestionar el contenido disponible, organizar imágenes y definir qué colecciones serán públicas y cuáles estarán disponibles únicamente para clientes específicos.

La visibilidad de una colección se determinará mediante su relación con clientes:

* si una colección no tiene clientes asociados, será pública;
* si una colección tiene uno o más clientes asociados, será privada y solo podrán acceder los clientes vinculados.

El proyecto propone el desarrollo de una aplicación web con autenticación de usuarios, diferenciación de roles y gestión de archivos multimedia, incorporando mecanismos de control, visibilidad por colección y registro de descargas para asegurar trazabilidad del uso del sistema.

## 2. Arquitectura General del Sistema

### 2.1 Componentes

**Portal del Cliente**

Interfaz web responsive orientada a usuarios registrados.

Funciones principales:

* Inicio de sesión con usuario y contraseña.
* Visualización de colecciones disponibles para el cliente.
* Visualización de imágenes pertenecientes a una colección accesible.
* Descarga de:
  * imagen individual;
  * múltiples imágenes seleccionadas;
  * colección completa en archivo comprimido.
* Consulta de historial de descargas propias.
* Marcado de imágenes favoritas.

**Panel Administrador**

Interfaz administrativa para la gestión del sistema.

Funciones principales:

* CRUD de clientes.
* CRUD de colecciones.
* Subida de imágenes dentro de colecciones.
* Baja lógica de imágenes.
* Modificación de datos básicos de imágenes.
* Gestión de visibilidad de colecciones:
  * colecciones públicas;
  * colecciones privadas para uno o varios clientes.
* Asignación de clientes autorizados a colecciones privadas.
* Consulta de estadísticas de descargas.
* Consulta de imágenes más descargadas.
* Consulta de historial de descargas por usuario.

**Backend**

Backend centralizado encargado de la lógica del sistema y la exposición de endpoints.

Tecnologías:

* PHP
* MySQL
* API REST
* Almacenamiento en filesystem

Responsabilidades:

* Autenticación y manejo de sesiones.
* Control de roles.
* Gestión de clientes, colecciones e imágenes.
* Gestión de visibilidad de colecciones.
* Registro de descargas.
* Gestión de favoritos.
* Entrega segura de archivos.

**Sistema de almacenamiento**

* Uso de filesystem para almacenamiento de imágenes.
* Organización recomendada:
  * `/uploads/{coleccion}/{imagen}`
* Posible implementación de estructura tipo “bucket”:
  * separación lógica por colecciones;
  * mejora en organización y escalabilidad.

## 3. Reglas funcionales principales del sistema

### 3.1 Gestión de usuarios

La plataforma admite dos tipos de usuario:

* administrador;
* cliente.

Cada usuario accede únicamente a las funciones correspondientes a su rol.

### 3.2 Gestión de colecciones

El sistema permitirá:

* crear colecciones de imágenes;
* modificar datos de colecciones;
* consultar colecciones disponibles;
* eliminar o desactivar colecciones según el criterio definido por el equipo;
* gestionar la visibilidad de cada colección mediante la asignación de clientes autorizados.

Toda colección podrá funcionar de dos formas:

#### Colección pública

Una colección será considerada pública cuando no tenga clientes asociados en la tabla de visibilidad.

Las colecciones públicas podrán ser visualizadas por todos los clientes autenticados.

#### Colección privada

Una colección será considerada privada cuando tenga uno o más clientes asociados en la tabla de visibilidad.

Las colecciones privadas únicamente podrán visualizarse por los clientes autorizados.

Una colección privada podrá estar asignada a:

* un único cliente;
* varios clientes.

A su vez, un cliente podrá tener acceso a:

* una única colección privada;
* varias colecciones privadas.

Esto implica una relación many-to-many entre clientes y colecciones.

### 3.3 Gestión de imágenes

El sistema permitirá:

* subir imágenes;
* asociar cada imagen obligatoriamente a una colección;
* modificar datos básicos de imágenes;
* aplicar baja lógica de imágenes;
* listar imágenes por colección.

Las imágenes no tendrán visibilidad propia.

La visibilidad de una imagen dependerá completamente de la colección a la que pertenece:

* si la colección es pública, sus imágenes podrán ser vistas por todos los clientes autenticados;
* si la colección es privada, sus imágenes solo podrán ser vistas por los clientes autorizados para esa colección.

Solo el administrador podrá subir, modificar o desactivar imágenes.

### 3.4 Descargas

El sistema permitirá:

* descarga de imágenes individuales;
* descarga múltiple de imágenes seleccionadas;
* descarga completa de una colección.

Toda descarga deberá validar previamente que el usuario tenga acceso a la colección correspondiente.

Cada descarga deberá ser registrada.

### 3.5 Registro de actividad

El sistema deberá registrar:

* usuario que realiza la descarga;
* imagen o colección descargada;
* fecha y hora;
* cantidad de archivos descargados.

Esta información será accesible para el administrador.

El cliente podrá visualizar únicamente su propio historial de descargas.

### 3.6 Favoritos

El cliente podrá marcar imágenes como favoritas para facilitar su acceso posterior.

Solo podrán marcarse como favoritas imágenes pertenecientes a colecciones que el cliente tenga permiso de visualizar.

### 3.7 Seguridad de archivos

Los archivos no deberán ser accesibles directamente mediante URL.

El acceso deberá estar controlado por el backend, validando:

* autenticación;
* rol del usuario;
* acceso a la colección correspondiente;
* disponibilidad de la imagen.

## 4. Endpoints mínimos del Backend

### 4.1 Autenticación

* POST /auth/login
* POST /auth/logout
* GET /auth/session

### 4.2 Usuarios

* GET /users
* POST /users
* GET /users/{id}
* PUT /users/{id}
* DELETE /users/{id}

### 4.3 Colecciones

* GET /collections
* POST /collections
* GET /collections/{id}
* PUT /collections/{id}
* DELETE /collections/{id}

Comportamiento esperado de `GET /collections`:

* para administrador: devuelve todas las colecciones;
* para cliente: devuelve únicamente:
  * colecciones públicas;
  * colecciones privadas a las que tenga acceso.

### 4.4 Imágenes

* GET /collections/{id}/images
* POST /collections/{id}/images
* GET /images/{id}
* PUT /images/{id}
* DELETE /images/{id}

Comportamiento esperado de `GET /collections/{id}/images`:

* para administrador: devuelve las imágenes activas de la colección;
* para cliente: devuelve las imágenes únicamente si tiene acceso a la colección solicitada.

### 4.5 Visibilidad de colecciones

* GET /collections/{id}/visibility
* POST /collections/{id}/visibility
* DELETE /collections/{id}/visibility/{client_id}

Funcionamiento esperado:

* `GET /collections/{id}/visibility`
  * devuelve los clientes asociados a la colección;
  * si no existen clientes asociados, la colección se considera pública.

* `POST /collections/{id}/visibility`
  * asocia un cliente a una colección;
  * desde ese momento la colección pasa a ser privada.

* `DELETE /collections/{id}/visibility/{client_id}`
  * quita el acceso de un cliente a una colección privada;
  * si se eliminan todas las relaciones de visibilidad, la colección vuelve a ser pública.

### 4.6 Descargas

* POST /downloads
* GET /downloads

Comportamiento esperado:

* `POST /downloads`
  * permite registrar y procesar:
    * descarga de una imagen;
    * descarga múltiple de imágenes;
    * descarga completa de una colección;
  * valida que el cliente tenga acceso a la colección correspondiente.

* `GET /downloads`
  * para administrador: devuelve el historial general de descargas;
  * para cliente: devuelve únicamente su historial personal.

### 4.7 Archivos

* GET /files/{id}

Comportamiento esperado:

* permite servir un archivo solicitado;
* valida previamente que el usuario tenga acceso a la colección a la que pertenece la imagen;
* impide el acceso directo a archivos sin autorización.

### 4.8 Favoritos

* GET /favorites
* POST /images/{id}/favorite
* DELETE /images/{id}/favorite

## 5. Modelo de Datos (mínimo requerido)

Tablas sugeridas:

* usuarios
* roles
* clientes
* colecciones
* imagenes
* visibilidad_colecciones
* descargas
* favoritos
* historial_actividad

### 5.1 Descripción general de tablas

**usuarios**  
Almacena credenciales y datos básicos de acceso.

**roles**  
Define el rol del usuario dentro del sistema.

**clientes**  
Contiene los datos propios de cada cliente registrado.

**colecciones**  
Agrupa imágenes en conjuntos organizados y funciona como unidad principal de visibilidad.

**imagenes**  
Almacena la información de cada archivo y su relación obligatoria con una colección.

**visibilidad_colecciones**  
Tabla intermedia entre clientes y colecciones.

Define qué clientes tienen acceso a determinadas colecciones privadas.

Reglas principales:

* si una colección no tiene registros en esta tabla, se considera pública;
* si una colección tiene uno o más registros, se considera privada;
* un cliente puede estar asociado a muchas colecciones;
* una colección puede estar asociada a muchos clientes.

**descargas**  
Registra las descargas realizadas por los usuarios, permitiendo trazabilidad.

**favoritos**  
Permite almacenar imágenes marcadas como favoritas por usuarios.

**historial_actividad**  
Permite conservar trazabilidad de acciones relevantes del sistema, como:

* creación y modificación de colecciones;
* subida o baja lógica de imágenes;
* cambios en la visibilidad de colecciones;
* registros de descargas;
* acciones administrativas relevantes.

## 6. Requisitos No Funcionales

* Autenticación segura con hash de contraseñas.
* Control de roles y permisos.
* Validación de archivos:
  * tipo;
  * tamaño;
  * seguridad.
* Protección de acceso a archivos.
* Registro de actividad de descargas.
* Diseño responsive básico.
* Organización eficiente del filesystem.
* Separación entre frontend y backend.
* Arquitectura basada en endpoints REST.
* Persistencia confiable de datos.
* Control de acceso a colecciones desde el backend, no desde el frontend.

## 7. Organización del Trabajo

### 7.1 Roles mínimos por equipo

Equipo sugerido: 5 integrantes

* Líder de proyecto.
* Desarrollador Backend.
* Desarrollador Frontend Cliente.
* Desarrollador Frontend Administrador.
* Responsable de Base de Datos, Testing y Documentación.

### 7.2 Gestión Git / Entregas

* 1 repositorio por grupo.
* Uso obligatorio de Git.
* Pull Requests obligatorias.
* Registro claro de commits.
* Reporte quincenal de avance.
* Documentación técnica obligatoria.

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
  * panel administrador;
  * portal cliente.
* Base de datos persistente.
* Gestión de clientes.
* Gestión de colecciones.
* Gestión de imágenes dentro de colecciones.
* Sistema de visibilidad de colecciones mediante relación cliente-colección.
* Descarga controlada de archivos.
* Registro de descargas operativo.
* Sistema de favoritos operativo.

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
* Explicación del modelo implementado.
* Defensa del reparto de tareas y aportes individuales.

## 10. Plantillas para proyecto

### 10.1 Repositorio Git

```txt
gestion-fotografias/
│
├── backend/
│
├── frontend-cliente/
│
├── frontend-admin/
│
├── docs/
│
├── .gitignore
├── LICENSE
└── README.md