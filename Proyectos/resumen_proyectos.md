# Resumen de Proyectos

## Sistema de Control de Asistencia y Talleres en Convenio con INAU

Este proyecto propone desarrollar una plataforma web para gestionar los talleres realizados en convenio con INAU, permitiendo registrar talleres, participantes y asistencia diaria de forma centralizada. Cuenta con dos interfaces —un panel del tallerista para crear talleres, pasar lista y cargar adjuntos, y un panel administrador para gestionar talleristas, participantes, asignaciones e informes— sobre un backend en PHP/MySQL con API REST. Incluye reglas de trazabilidad (correcciones de asistencia notificadas al administrador), mensajería interna entre tallerista y administración, e informes de asistencia por participante, fecha o taller.

## Proyecto Paraforma Educación Vial IMSJ

Este proyecto plantea una aplicación web para la Sección Tránsito de la IMSJ, centralizando noticias, agenda de trámites (prueba de manejo y renovación de libreta, normal o urgente) y materiales de estudio para aspirantes. Se compone de un frontend público para consulta y autogestión de agenda, y un dashboard IMSJ para publicar noticias, administrar franjas de disponibilidad y mantener materiales y preguntas frecuentes, todo sobre un backend Laravel/MySQL con API REST. Pone énfasis en el manejo responsable de datos personales del ciudadano y en evitar reservas duplicadas o sobrecupos en la agenda.

## Sistema de Gestión de Biblioteca Barrial

Este proyecto busca digitalizar la operativa de una biblioteca barrial, reemplazando planillas y registros manuales por un sistema de gestión de socios, catálogo, préstamos, devoluciones y reservas. Contempla tres interfaces —portal del socio para consultar catálogo y préstamos, panel del bibliotecario para operar préstamos/devoluciones diarios, y panel administrador para el catálogo, multas y reportes— sobre un backend Laravel/MySQL. Incluye reglas de negocio como límite de renovaciones, control de reservas, multas simples por atraso o pérdida y notificaciones automáticas de vencimientos.

## Sistema de Cobros a Socios para Club Ciclista Maragato

Este proyecto propone una plataforma para gestionar el cobro de cuotas sociales del Club Ciclista Maragato, con generación automática de 12 recibos anuales por socio activo y seguimiento de pagos y morosidad. Tiene tres interfaces: un portal del socio para consultar cuotas y recibos, un panel del cobrador orientado a uso móvil para registrar cobros a domicilio y resultados de visita, y un panel administrador para gestionar socios, cobradores, carteras e informes de ingresos y morosidad, todo sobre un backend Laravel/MySQL con API REST.

## Sistema de Gestión y Distribución de Material Fotográfico

Este proyecto plantea una plataforma para organizar y distribuir material fotográfico en colecciones, con control de acceso mediante una relación many-to-many entre clientes y colecciones (una colección es pública si no tiene clientes asociados, o privada si tiene uno o más). Incluye un portal del cliente para visualizar, descargar (individual, múltiple o por colección completa) y marcar favoritos, y un panel administrador para gestionar clientes, colecciones, imágenes y visibilidad, sobre un backend PHP/MySQL que sirve los archivos de forma controlada (sin acceso directo por URL) y registra cada descarga para trazabilidad.

## Sistema de Gestión de Reclamos Ciudadanos

Este proyecto propone una solución para que la comuna gestione de forma transparente los reclamos ciudadanos sobre infraestructura urbana (baches, alumbrado, arbolado, etc.), mediante tres interfaces: una PWA de ciudadanía para crear reclamos con fotos, video y geolocalización; un dashboard tipo Kanban para la comuna que permite asignar, aprobar o rechazar reclamos y ver reportes; y un frontend para equipos/proveedores que reciben y resuelven las tareas asignadas. Un aspecto distintivo es la integración obligatoria, solo en el alta de un nuevo ciudadano, con una API docente simulada de validación de identidad (al estilo GUB.UY) que verifica la autenticidad del documento y detecta intentos fraudulentos de registro.
