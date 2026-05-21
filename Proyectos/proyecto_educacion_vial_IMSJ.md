# Proyecto UTU-Polo 2026

## Título: Proyecto Paraforma Educación Vial IMSJ

## Objetivos

* Proyecto de egreso para el grupo de 3º año
* Presentación del proyecto para los "Premios Nodo" en forma institucional

## Justificación pedagógica

Este trabajo integra competencias técnicas, metodológicas y ciudadanas alineadas al enfoque competencial del MCN 2025:

* Resolución de problemas reales.
* Trabajo colaborativo con trazabilidad.
* Diseño, desarrollo y documentación de sistemas.
* Tratamiento ético y responsable de datos personales.
* Gestión de agenda, publicación de contenidos y comunicación institucional.

## Público objetivo: IMSJ - Sección Tránsito y público general del departamento

## 1. Fundamentación del Proyecto

La IMSJ requiere una aplicación web que permita centralizar la comunicación pública de la sección tránsito, la agenda de trámites vinculados a la libreta de conducir y el acceso a materiales de estudio para aspirantes.

Actualmente, la información sobre noticias, anuncios, agendas, materiales y preguntas frecuentes puede encontrarse dispersa o depender de canales no integrados. El proyecto busca desarrollar una solución completa compuesta por dos interfaces diferenciadas y un backend centralizado que gestione la lógica del negocio.

La aplicación permitirá que el público general consulte anuncios vigentes, acceda a recursos de educación vial y se agende para la prueba de manejo o para la renovación de la libreta de conducir. A su vez, el personal de la IMSJ podrá administrar noticias, franjas de disponibilidad, agendas, materiales de estudio y preguntas frecuentes.

## 2. Arquitectura General del Sistema

### 2.1 Componentes

**Frontend Público General (diseño mobile-first)

Aplicación web simple para:

* Visualización de una cartelera de noticias y anuncios de la sección tránsito de la IMSJ.
* Barra superior con acceso a las funcionalidades principales:
  * Noticias / anuncios
  * Agenda para prueba de manejo
  * Renovación de libreta de conducir
  * Materiales de estudio
  * Preguntas frecuentes
* Consulta de noticias publicadas y vigentes:
  * Título
  * Imagen de portada
  * Galería de imágenes
  * Cuerpo de la noticia
  * Enlaces útiles a videos online u otros recursos
* Agenda para prueba de manejo para obtener la licencia de conducir.
* Agenda para trámite de renovación de libreta de conducir:
  * Modalidad normal con agenda
  * Modalidad urgente con agenda y costo especial
* Visualización de materiales de estudio.
* Consulta de preguntas frecuentes.

**Dashboard IMSJ (diseño desktop-first, responsive)

Panel de control administrativo para:

* Visualizar agenda de trámites:
  * Vista diaria
  * Vista semanal
  * Vista mensual
* Consultar trámites agendados de la semana en el cuerpo principal del dashboard.
* Barra superior con acceso a las funcionalidades principales:
  * Cartelera de anuncios
  * Agenda de trámites
  * Franjas de disponibilidad
  * Materiales de estudio
  * Preguntas frecuentes
* Publicar y administrar noticias para el público general:
  * Título
  * Imagen de portada
  * Imágenes en galería
  * Cuerpo de la noticia
  * Enlaces útiles a videos online u otros recursos
  * Vigencia de la noticia
  * Estado publicada / no-publicada
* Cargar franjas de disponibilidad para trámites de libreta de conducir:
  * Franjas para trámites normales
  * Franjas para trámites urgentes
  * Franjas para prueba de manejo
* Administrar materiales de estudio para aspirantes a obtener la libreta de conducir.
* Mantener la sección "Preguntas frecuentes":
  * Pregunta
  * Respuesta
  * Enlaces útiles a videos online u otros recursos
  * Estado visible / no-visible

**Backend

* Tecnologías

  * PHP / Laravel
  * MySQL
  * Almacenamiento en filesystem
  * API REST

* Endpoints mínimos:

* Autenticación
    POST /auth/login
    POST /auth/logout
    GET /auth/me
* Noticias
    POST /noticias
    GET /noticias/publicadas
    GET /noticias
    GET /noticias/{id}
    PATCH /noticias/{id}
    PATCH /noticias/{id}/publicar
    PATCH /noticias/{id}/despublicar
    DELETE /noticias/{id}
* Multimedia
    POST /noticias/{id}/media
    GET /media/{id}
    DELETE /media/{id}
* Agenda
    POST /franjas
    GET /franjas/disponibles
    GET /franjas
    PATCH /franjas/{id}
    DELETE /franjas/{id}
    POST /agendas
    GET /agendas/my
    GET /agendas
    PATCH /agendas/{id}/cancelar
    PATCH /agendas/{id}/confirmar
* Materiales de estudio
    POST /materiales
    GET /materiales/publicados
    GET /materiales
    PATCH /materiales/{id}
    DELETE /materiales/{id}
* Preguntas frecuentes
    POST /preguntas-frecuentes
    GET /preguntas-frecuentes/publicadas
    GET /preguntas-frecuentes
    PATCH /preguntas-frecuentes/{id}
    DELETE /preguntas-frecuentes/{id}

## 3. Modelo de Datos (mínimo requerido)

Tablas sugeridas:

* usuarios
* roles
* noticias
* noticias_multimedia
* franjas_disponibilidad
* agendas
* tipos_tramite
* materiales_estudio
* preguntas_frecuentes
* enlaces_utiles
* historial_actividad (cambios de estados y acciones administrativas)

Campos mínimos sugeridos:

* noticias
  * titulo
  * cuerpo
  * imagen_portada
  * fecha_inicio_vigencia
  * fecha_fin_vigencia
  * estado
  * usuario_id
* franjas_disponibilidad
  * tipo_tramite
  * fecha
  * hora_inicio
  * hora_fin
  * cupos
  * modalidad normal / urgente / prueba
* agendas
  * ciudadano_nombre
  * ciudadano_documento
  * ciudadano_email
  * ciudadano_telefono
  * tipo_tramite
  * modalidad
  * franja_id
  * estado
  * costo_especial
* materiales_estudio
  * titulo
  * descripcion
  * archivo
  * enlace
  * estado
* preguntas_frecuentes
  * pregunta
  * respuesta
  * estado

## 4. Requisitos No Funcionales

* Control de roles y permisos
* Validación de entradas
* Historial completo de acciones administrativas
* Protección de datos personales
* Usabilidad móvil (mobile first) ???
* Accesibilidad básica para público general
* Manejo de vigencia automática de noticias
* Prevención de doble reserva de agenda
* Confirmación visual de agenda para el ciudadano
* Separación clara entre contenidos publicados y contenidos no-publicados

## 5. Organización del Trabajo

**Roles minimos por equipo

* Equipo sugerido: 5 integrantes
  * Líder de proyecto
  * Desarrollador Backend
  * Desarrollador/es Frontend
  * Base de datos / Seguridad
  * Testing / Documentación

* Gestión Git / Entregas
  * 1 repositorio por grupo
  * Branch main + dev + feature branches
  * Pull Requests obligatorias
  * Reporte quincenal de actividad
  * Trazabilidad Git obligatoria

## 6. Entregables Obligatorios

* Documentación (Markdown)
  * README.md
  * 01-requerimientos.md
  * 02-modelado.md
  * 03-api.md
  * 04-seguridad.md
  * 05-planificacion.md
  * 06-testing.md

* Producto Funcional
  * 2 interfaces funcionando
  * Base de datos persistente
  * Cartelera pública con noticias vigentes
  * Agenda de prueba de manejo
  * Agenda de renovación normal y urgente
  * Dashboard IMSJ con vista diaria, semanal y mensual
  * Materiales de estudio publicados
  * Preguntas frecuentes publicadas
  * Control de roles implementado

## 7. Evaluación (100 puntos)

### 7.1 Entregables

* Requermientos (15)
* Modelado (15)
* Backend (20)
* Frontend (20)
* Git y trazabilidad (10)
* Testing (10)
* Ética y tratamiento de datos (10)

### 7.2 Defensa Final

* Demo de 15 minutos.
* Preguntas individuales.
* Justificación técnica de decisiones.

## 8. Plantillas para proyecto

### 8.1 Repositorio Git

educacion-vial-imsj/
│
├── backend/
│   ├── app/
│   ├── routes/
│   ├── database/
│   └── README.md
│
├── frontend-publico/
│   ├── index.html
│   ├── css/
│   ├── js/
│   └── manifest.json
│
├── frontend-imsj/
│   ├── index.html
│   ├── css/
│   ├── js/
│   └── manifest.json
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

### 8.2 Readme.md del repo

    # Proyecto Educación Vial IMSJ
    ## Intendencia Municipal de San José - Sección Tránsito

    Proyecto Egreso 2026

    ## Integrantes
    - Nombre 1 – Rol
    - Nombre 2 – Rol
    - Nombre 3 – Rol
    - Nombre 4 – Rol

    ## Tecnologías
    - Laravel
    - MySQL
    - Vanilla JS
    - Tailwind / Bootstrap

    ## Cómo ejecutar el proyecto

    ### Backend
    1. Clonar repositorio
    2. Configurar .env
    3. php artisan migrate
    4. php artisan serve

    ### Frontend
    Abrir index.html o ejecutar con servidor local

    ## Estructura del proyecto
    Ver carpeta /docs para documentación completa


## Apéndice 1: Consideraciones sobre agenda y datos personales

Como parte del proyecto, la agenda de trámites deberá manejar datos personales básicos del ciudadano, necesarios para identificar la reserva y permitir la comunicación administrativa.

Estos datos deberán utilizarse solamente para la finalidad del trámite seleccionado:

* Prueba de manejo para obtener licencia de conducir.
* Renovación normal de libreta de conducir.
* Renovación urgente de libreta de conducir con costo especial.

El sistema deberá evitar la exposición pública de datos personales y separar claramente la información visible para el público general de la información disponible para el personal de la IMSJ.

La agenda deberá controlar los cupos disponibles para cada franja, evitando reservas duplicadas o sobrecupos. En el caso de trámites urgentes, el sistema deberá identificar la modalidad y registrar el costo especial asociado al trámite.
