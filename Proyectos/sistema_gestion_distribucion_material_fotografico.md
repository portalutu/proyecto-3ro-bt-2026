# Proyecto UTU-Polo 2026

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
* apliquen criterios de seguridad y control en la distribución de archivos.

Desde el punto de vista pedagógico, el proyecto favorece el desarrollo de competencias vinculadas al pensamiento computacional, pensamiento crítico, creatividad, comunicación, iniciativa y trabajo en equipo, en concordancia con el MCN. Asimismo, se alinea con las competencias específicas de Ingeniería del Software y Administración de Sistemas Operativos del tramo 8, al requerir modelado, implementación de backend, control de acceso, gestión de archivos y organización del despliegue.

## Público objetivo

Clientes registrados y administradores de contenido fotográfico.

## 1. Fundamentación del Proyecto

Se requiere un sistema digital que permita la gestión, visualización y descarga controlada de material fotográfico por parte de usuarios registrados.

El sistema estará orientado a la organización de imágenes en colecciones temáticas, facilitando su acceso, consulta y descarga de manera ordenada. A su vez, permitirá a los administradores gestionar el contenido disponible, controlar su visibilidad y mantener una estructura organizada de archivos.

El proyecto propone el desarrollo de una aplicación web con autenticación de usuarios, diferenciación de roles y gestión de archivos multimedia, incorporando mecanismos de control y registro de descargas para asegurar trazabilidad del uso del sistema.

## 2. Arquitectura General del Sistema

### 2.1 Componentes

**Portal del Cliente**

Interfaz web responsive orientada a usuarios registrados.

Funciones principales:

* Inicio de sesión con usuario y contraseña.
* Visualización de colecciones de imágenes disponibles.
* Visualización de imágenes individuales.
* Selección de imágenes.
* Descarga de:
  * imagen individual
  * múltiples imágenes seleccionadas
  * colección completa (archivo comprimido)
* Acceso restringido según permisos.

**Panel Administrador**

Interfaz administrativa para la gestión del sistema.

Funciones principales:

* Gestión de usuarios.
* Creación de colecciones.
* Subida de imágenes.
* Asignación de imágenes a colecciones.
* Configuración de visibilidad de imágenes y colecciones.
* Consulta de estadísticas de descargas.
* Control general del contenido.

**Backend**

Backend centralizado encargado de la lógica del sistema y la exposición de endpoints.

Tecnologías:

* PHP (vanilla)
* MySQL
* API REST
* Almacenamiento en filesystem

Responsabilidades:

* Autenticación y manejo de sesiones.
* Control de roles (administrador / cliente).
* Gestión de imágenes y colecciones.
* Registro de descargas.
* Entrega segura de archivos.

**Sistema de almacenamiento**

* Uso de filesystem para almacenamiento de imágenes.
* Organización recomendada:
  * `/uploads/{coleccion}/{imagen}`
* Posible implementación de estructura tipo “bucket”:
  * separación lógica por colecciones o usuarios
  * mejora en organización y escalabilidad

## 3. Reglas funcionales principales del sistema

### 3.1 Gestión de usuarios

La plataforma admite dos tipos de usuario:

* administrador
* cliente

Cada usuario accede únicamente a las funciones correspondientes a su rol.

### 3.2 Gestión de colecciones

El sistema permitirá:

* crear colecciones de imágenes;
* modificar datos de colecciones;
* definir visibilidad (visible / no visible).

Las colecciones visibles podrán ser accedidas por los clientes.

### 3.3 Gestión de imágenes

El sistema permitirá:

* subir imágenes;
* asociarlas a una colección;
* configurar visibilidad;
* listar imágenes por colección.

Solo el administrador podrá realizar estas acciones.

### 3.4 Descargas

El sistema permitirá:

* descarga de imágenes individuales;
* descarga múltiple de imágenes seleccionadas;
* descarga completa de una colección.

Cada descarga deberá ser registrada.

### 3.5 Registro de actividad

El sistema deberá registrar:

* usuario que realiza la descarga;
* imagen o colección descargada;
* fecha y cantidad de descargas.

Esta información será accesible para el administrador.

### 3.6 Seguridad de archivos

Los archivos no deberán ser accesibles directamente mediante URL.

El acceso deberá estar controlado por el backend, validando permisos antes de permitir la descarga.

## 4. Endpoints mínimos del Backend

### 4.1 Autenticación

* POST /auth/login
* POST /auth/logout
* GET /auth/session

### 4.2 Usuarios

* GET /users
* POST /users

### 4.3 Colecciones

* GET /collections
* POST /collections
* GET /collections/{id}

### 4.4 Imágenes

* POST /images
* GET /images?collection_id=
* PATCH /images/{id}/visibility

### 4.5 Descargas

* POST /downloads
* GET /downloads

### 4.6 Archivos

* GET /files/{id}

## 5. Modelo de Datos (mínimo requerido)

Tablas sugeridas:

* usuarios
* colecciones
* imagenes
* descargas

### 5.1 Descripción general de tablas

**usuarios**  
Almacena credenciales y datos básicos de acceso.

**colecciones**  
Agrupa imágenes en conjuntos organizados.

**imagenes**  
Almacena la información de cada archivo y su relación con colecciones.

**descargas**  
Registra las descargas realizadas por los usuarios, permitiendo trazabilidad.

## 6. Requisitos No Funcionales

* Autenticación segura (hash de contraseñas).
* Control de roles y permisos.
* Validación de archivos (tipo, tamaño, seguridad).
* Protección de acceso a archivos.
* Registro de actividad de descargas.
* Diseño responsive básico.
* Organización eficiente del filesystem.
* Separación entre frontend y backend.
* Arquitectura basada en endpoints REST.

## 7. Organización del Trabajo

### 7.1 Roles mínimos por equipo

Equipo sugerido: 5 integrantes

* Líder de proyecto
* Desarrollador Backend
* Desarrollador Frontend
* Responsable de almacenamiento y archivos
* Responsable de Base de Datos, Testing y Documentación

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
  * panel administrador
  * portal cliente
* Base de datos persistente.
* Gestión de colecciones e imágenes.
* Descarga controlada de archivos.
* Registro de descargas operativo.

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

## 10. Plantillas para proyecto

### 10.1 Repositorio Git

gestion-fotografias/
│  
├── backend/  
├── frontend/  
├── docs/  
├── .gitignore  
├── LICENSE  
└── README.md  

## 11. Posibles mejoras a futuro

* soporte para videos;
* sistema de etiquetas o búsqueda avanzada;
* permisos por colección;
* sistema de favoritos;
* generación automática de thumbnails;
* almacenamiento en la nube;
* límite de descargas por usuario;
* estadísticas avanzadas de uso.