# Proyecto UTU-Polo 2026

## Título: Sistema de Gestión de Reclamos Ciudadanos

## Objetivos

* Proyecto de egreso para el grupo de 3º año
* Presentación del proyecto para los "Premios Nodo" en forma institucional

## Justificación pedagógica

Este trabajo integra competencias técnicas, metodológicas y ciudadanas alineadas al enfoque competencial del MCN 2025:

* Resolución de problemas reales.
* Trabajo colaborativo con trazabilidad.
* Diseño, desarrollo y documentación de sistemas.
* Tratamiento ético y responsable de datos personales.

## Público objetivo: Comuna Maragata(???)

## 1. Fundamentación del Proyecto

La comuna requiere un sistema digital que permita gestionar de forma transparente y eficiente los reclamos ciudadanos relacionados con infraestructura urbana (baches, alumbrado, arbolado, pérdidas de agua, cableado eléctrico, etc.).

El proyecto busca desarrollar una solución completa compuesta por tres interfaces diferenciadas y un backend centralizado que gestione la lógica del negocio.

## 2. Arquitectura General del Sistema

### 2.1 Componentes

**PWA Ciudadanía

Aplicación móvil progresiva para:

* Registro y validación inicial (email + endpoint docente de validación CI).
* Creación de reclamos:
  * Tipo de incidente
  * Descripción
  * Fotos / video breve
  * Geolocalización (automática)
  * Seguimiento del estado
  * Recepción de notificaciones

**Dashboard Comuna (Kanban)

* Panel de control administrativo con columnas:

  * Ingreso
  * Asignado
  * En proceso
  * Pendiente de aprobación
  * Resuelto
  * Rechazado / Reclamos

* Funciones:
  * Asignación a equipos o proveedores
  * Visualización de evidencias antes/después
  * Aprobación o rechazo
  * Reportes estadísticos básicos (duración de trabajos, trabajos sin resolver, plazos, incumplimientos, cantidad de reclamos x equipo/proveedor, etc.)

**Frontend Equipos / Proveedores

* Interfaz simple para:

  * Visualizar tareas asignadas
  * Marcar inicio
    * Registrar finalización con:
      * Materiales utilizados
      * Observaciones
      * Evidencias fotográficas
    * Solucionar tareas rechazadas con prioridad

**Backend

* Tecnologías

  * PHP / Laravel
  * MySQL
  * Almacenamiento en filesystem
  * API REST

* Endpoints mínimos

* Autenticación
    POST /auth/register
    POST /auth/login
    POST /auth/verify-ci
* Reclamos
    POST /reclamos
    GET /reclamos/my
    GET /reclamos
    PATCH /reclamos/{id}/assign
    PATCH /reclamos/{id}/start
    PATCH /reclamos/{id}/finish
    PATCH /reclamos/{id}/approve
    PATCH /reclamos/{id}/reject
* Evidencias
    POST /reclamos/{id}/media
    GET /media/{id}

## 3. Modelo de Datos (mínimo requerido)

Tablas sugeridas:

* usuarios
* reclamos
* historial_actividad (cambios de estados)
* multimedia (documentos vinculados a cada reclamo)
* proveedores (o equipos internos de trabajo)
* materiales (opcional)

## 4. Requisitos No Funcionales

* Control de roles y permisos
* Validación de entradas
* Historial completo de estados
* Protección de datos personales
* Usabilidad móvil (mobile first) ???

## 5. Organización del Trabajo

**Roles minimos por equipo

* Equipo sugerido: 5 integrantes
  * Líder de proyecto
  * Desarrollador Backend
  * Desarrollador/es Frontend
  * Seguridad / Frontend

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
  * 3 interfaces funcionando
  * Base de datos persistente
  * Evidencias almacenadas
  * Flujo completo de estados implementado

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

reclamos-comuna-maragata/
│
├── backend/
│   ├── app/
│   ├── routes/
│   ├── database/
│   └── README.md
│
├── frontend-ciudadania/
│   ├── index.html
│   ├── css/
│   ├── js/
│   └── manifest.json
│
├── frontend-proveedores/
│   ├── index.html
│   ├── css/
│   ├── js/
│   └── manifest.json
│
├── frontend-comuna/
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
│   └──  06-testing.md
│
├── .gitignore
├── LICENSE
└── README.md

### 8.2 Readme.md del repo

    # Sistema de Gestión de Reclamos Ciudadanos
    ## Comuna Maragata

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
