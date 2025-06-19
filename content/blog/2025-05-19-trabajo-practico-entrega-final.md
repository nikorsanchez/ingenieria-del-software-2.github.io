---
date: "2025-06-19T19:45:00Z"
subtitle: Una nueva dinámica de evaluación final.
tags:
- evaluacion
- opcional
- beta
- 2025-1C
title: Propuesta Opcional (Beta) de Evaluación para la Entrega Final - 1C 2025
---

Para la instancia de entrega final, queremos proponerles una nueva dinámica de evaluación que estamos probando en formato **beta**. Este modelo se implementará de manera estándar en los próximos cuatrimestres, y **estamos buscando grupos pioneros que deseen participar este semestre.**

Creemos que esta experiencia les sumará un valor diferencial, ya que busca enriquecer el feedback que reciben sobre su trabajo, simulando una presentación ante un stakeholder con una perspectiva completamente nueva.

### ¿En qué consiste esta Modalidad?

La propuesta es que la **segunda parte de su presentación (la Demo Funcional) sea evaluada por un docente diferente** (acompañado del ayudante asignado al grupo) al que los ha acompañado durante todo el proyecto. El objetivo es simple: eliminar cualquier sesgo y obtener una evaluación fresca y objetiva del producto final que han construido.

Por esta razón, la primera parte de la presentación se vuelve crucial, ya que su propósito es **poner en contexto a este nuevo evaluador** sobre las decisiones de arquitectura, tecnología y diseño que tomaron, justificando el porqué de la solución que van a presentar.

A continuación, les detallamos la estructura recomendada para los equipos que decidan optar por esta modalidad.

---

### **Parte 1: Presentación de Contexto y Arquitectura (Duración estimada: 15-20 minutos)**

Este bloque inicial sirve para contextualizar el proyecto, las decisiones técnicas que tomaron y el rol de cada integrante en el proceso.

#### **Diapositiva 1: Portada y Presentación del Grupo**
* **Título:** "Proyecto ClassConnect - Presentación Final"
* **Integrantes:** Listen los nombres completos de todos los miembros del equipo.
* **Materia/Cátedra:** Nombre de la materia.
* **Fecha:** 26/06/2025

#### **Rol y Contribuciones Individuales (1 a 2 diapositivas por integrante)**
Cada integrante debe tener un espacio en esta diapositiva para presentarse brevemente.
* **¿Qué deben explicar?** (Elegir una o dos opciones):
    * **Feature Clave:** ¿Cuál fue la funcionalidad (historia de usuario o épica) más desafiante o que más te gustó implementar? Describe brevemente el desafío técnico (ej. "Implementar el login federado con Google me obligó a investigar sobre OAuth 2.0 y la gestión segura de tokens JWT").
    * **Contribución Principal:** ¿En qué área del sistema te enfocaste más? (Ej: "Mi foco principal fue el backend, específicamente en el desarrollo del microservicio de Gestión de Clases, usando FastAPI y asegurando la comunicación con el servicio de Usuarios").
    * **Aporte Técnico:** ¿Implementaste alguna parte crítica de los requisitos no funcionales? (Ej: "Fui responsable de configurar el pipeline de CI/CD con GitHub Actions, incluyendo los steps de testing, linting y el reporte de coverage a Codecov").
* **Apoyo Visual:** Es altamente recomendable usar un diagrama simple de alto nivel para ilustrar la feature o el componente en el que trabajaron.

#### **Arquitectura y Diseño del Sistema (4 Diapositivas)**
El objetivo aquí es demostrar que tienen una visión integral de la solución que construyeron. Deben presentar y explicar los siguientes diagramas:
* **Diagrama de Arquitectura General:**
    * Muestren una vista de pájaro de ClassConnect.
    * Identifiquen los componentes principales: Aplicación Móvil, Backoffice Web, Servicios Backend (microservicios), Bases de Datos y Servicios Externos (Firebase, Twilio, etc.).
    * Ilustren cómo se comunican estos componentes entre sí (ej. REST APIs, WebSockets).
* **Diagrama de Microservicios:**
    * Hagan foco en la arquitectura backend.
    * Detallen cada microservicio (ej. Usuarios, Cursos, Evaluaciones, Notificaciones).
    * Expliquen la responsabilidad principal de cada uno y cómo interactúan (comunicación síncrona/asíncrona).
* **Diagrama de Infraestructura y Despliegue (Cloud & CI/CD):**
    * Muestren dónde y cómo está desplegada la aplicación (la PAAS que eligieron, ej. Heroku, AWS, etc.).
    * Ilustren el flujo de Integración y Despliegue Continuo (CI/CD). Desde que un desarrollador hace un push a una rama, hasta que los cambios se despliegan automáticamente. Destaquen las herramientas usadas (ej. GitHub Actions, Docker).
* **Diagrama del Modelo de Datos (Base de Datos):**
    * Presenten el esquema de la base de datos (o de las bases de datos si usan más de una).
    * Muestren las entidades principales (ej. Usuarios, Cursos, Inscripciones, Tareas, Entregas) y las relaciones entre ellas. No es necesario mostrar todos los campos, pero sí las claves primarias y foráneas más importantes.

---

### **Parte 2: Demo Funcional End-to-End (Duración estimada: 35-40 minutos)**

Este es el momento de mostrar la plataforma en acción. La demo debe ser fluida, guiada por 1 o 2 integrantes, mientras el resto del equipo está preparado para responder preguntas. El objetivo es demostrar que las funcionalidades core del sistema están completas y funcionan de manera integrada.

#### **Recomendación de Flujo para la Demo:**
Les sugiero seguir una narrativa lógica que muestre un ciclo de vida completo en la plataforma. Por ejemplo:

1.  **El Administrador prepara la plataforma:**
    * Login de Admin: Ingresar al Backoffice Web.
    * Gestión de Usuarios: Mostrar el listado de usuarios y quizás bloquear/desbloquear un usuario de prueba para que funcione.
2.  **El Docente crea su espacio de enseñanza:**
    * Registro y Login: Registrar un nuevo docente desde la app y hacer login (pueden mostrar el login con email/contraseña y el federado).
    * Gestión de Perfil: Editar su perfil para que se vea completo.
    * Creación de un Curso: Crear un curso desde cero (Creación y gestión de cursos).
    * Organización del Contenido: Agregar módulos y recursos (un PDF, un video) a ese curso.
    * Creación de una Evaluación: Crear una tarea o un examen para el curso recién creado (Creación de tareas y exámenes).
3.  **El Estudiante se une y participa:**
    * Registro y Login: Registrar un nuevo estudiante y hacer login.
    * Visualización y Búsqueda de Cursos: Mostrar el listado de cursos disponibles para inscripción.
    * Inscripción al Curso: Inscribirse al curso que creó el docente.
    * Exploración del Curso: Navegar por los módulos y recursos.
    * Realización de la Tarea: Acceder al listado de tareas, completar y entregar la tarea creada por el docente (Completar tarea/rendir examen).
4.  **El Ciclo de Feedback se completa:**
    * El Docente Evalúa: Volver al perfil del docente. Mostrar el listado de tareas, ver la entrega del alumno y asignarle una nota con retroalimentación (Retroalimentación y notas).
    * Notificaciones: Mostrar cómo le llega la notificación (push o email) al alumno informándole que su tarea fue corregida.
    * El Estudiante Revisa su Nota: Volver al perfil del alumno para que vea su calificación y el feedback.
    * Métricas para el Docente: Como docente, mostrar las Estadísticas de desempeño estudiantil del curso.

---

### **Claves para una Presentación Exitosa**

#### **Durante la Demo:**
* El ayudante hará preguntas en cualquier momento. Estas pueden ser sobre la funcionalidad que se está mostrando, la decisión de diseño detrás de ella, o cómo se resolvió un problema técnico en el frontend o backend.
* **¡Todos deben estar listos para responder!** Si quien presenta la demo no sabe una respuesta técnica específica, otro miembro del equipo debe poder intervenir y explicarlo. Esto demuestra el trabajo en equipo y el conocimiento compartido.

#### **Consejos Adicionales para el Éxito:**
* **Practiquen la demo:** Ensáyenla varias veces para asegurarse de que el flujo es lógico y no hay problemas técnicos inesperados. Tengan un "plan B" si algo falla (ej. un video corto de la feature funcionando).
* **Preparen el entorno:** Tengan la app instalada, el backoffice abierto y todos los servicios corriendo antes de empezar. Usen datos de prueba limpios y coherentes.
* **Documentación como apoyo:** Tengan a mano la documentación del proyecto (especificación de la API, Postmortem, etc.). Si surge una pregunta compleja, pueden referirse a ella para dar una respuesta más completa.
* **Sean concisos y claros:** Expliquen el "qué" y el "porqué" de cada acción. "Ahora, como docente, voy a crear un curso. Para esto, implementamos un endpoint POST en nuestro servicio de Cursos que valida estos campos...".
