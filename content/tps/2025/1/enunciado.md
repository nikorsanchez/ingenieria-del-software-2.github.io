---

title: "2025C - EduSnap"
subtitle: "Grupal"
------------------

# EduSnap

## Índice

1. [Descripción](#descripción)
2. [Condiciones de aprobación](#condiciones-de-aprobación)
3. [Requisitos](#requisitos)
   1. [Épicas](#Épicas)
      1. [Usuarios](#usuarios)
      2. [Gestión de Clases](#gestión-de-clases)
      3. [Asignaciones y Evaluaciones](#asignaciones-y-evaluaciones)
      4. [Comunicación y Notificaciones](#comunicación-y-notificaciones)
      5. [Métricas y Análisis](#métricas-y-análisis)
      6. [Administración de la Plataforma](#administración-de-la-plataforma)
   2. [Historias de Usuario](#historias-de-usuario)
4. [Historias requeridas y optativas](#historias-requeridas-y-optativas)

## Descripción

EduSnap es una plataforma de gestión educativa diseñada para facilitar la enseñanza y el aprendizaje en entornos digitales. Su propósito es permitir que docentes y estudiantes interactúen de manera efectiva mediante la creación de clases, asignaciones, exámenes, y recursos educativos en línea. La plataforma integrará un modelo LLM para mejorar la generación de contenido educativo, automatizar correcciones y proporcionar asistencia personalizada a estudiantes y docentes.

## Condiciones de aprobación

El trabajo se aprobará al cumplir con una cantidad mínima de puntos obtenidos a partir de las historias de usuario implementadas. Habrá historias obligatorias y opcionales, permitiendo a los equipos elegir cómo completar los puntos necesarios.

## Requisitos

### Épicas

#### [Usuarios](#usuarios)

 - [Registro de usuarios](#registro-de-usuarios)
 - [Login con email y contraseña](#login-de-usuarios-con-usuario-y-contraseña)
 - [Login con datos biométricos](#login-con-datos-biométricos)
 - [Login con proveedor de identidad federada](#login-de-usuarios-con-proveedores-de-identidad-federada)
 - [Recupero de contraseña](#recupero-de-contraseña)
 - [Registro Administradores](#registro-de-administradores)
 - [Login Administradores](#login-de-administradores)
 - [Notificación de PIN en proceso de registro](#notificación-de-pin-en-proceso-de-registro)

#### [Gestión de perfiles](#gestión-de-perfiles)

 - [Edición de perfil](#edición-de-perfil)
 - [Visualización de perfil propio](#visualización-de-perfil-propio)
 - [Visualización de perfil de otros usuarios](#visualización-de-perfil-de-otros-usuarios)

#### [Gestión de Clases](#gestión-de-clases)

- [Creación y gestión de cursos](#creación-y-gestión-de-cursos)
- [Inscripción de estudiantes](#inscripción-de-estudiantes)
- [Organización de módulos y recursos](#organización-de-módulos-y-recursos)
- [Visualización de cursos](#visualización-de-cursos)
- [Cursos favoritos](#cursos-favoritos)
- [Visualización de cursos favoritos](#visualización-de-cursos-favoritos)
- [Feedback de cursos](#feedback-de-cursos)
- [Feedback de alumnos](#feedback-de-alumnos)
- [Visualización de feedbacks como alumno](#visualización-de-feedbacks-como-alumno)
- [Visualización de feedbacks del curso](#visualización-de-feedbacks-del-curso)

#### [Asignaciones y Evaluaciones](#asignaciones-y-evaluaciones)

- [Creación de tareas y exámenes](#creación-de-tareas-y-exámenes)
- [Completar tarea/rendir examen](#completar-tarea-rendir-examen)
- [Listado de tareas/exámenes (docente)](#listado-de-tareasexámenes-docente)
- [Listado de tareas/exámenes (alumno)](#listado-de-tareasexámenes-alumno)
- [Corrección automática con IA](#corrección-automática-con-ia)
- [Retroalimentación y notas](#retroalimentación-y-notas)

#### [Comunicación y Notificaciones](#comunicación-y-notificaciones)

- [Foro de preguntas y respuestas](#foro-de-preguntas-y-respuestas)
- [Chat de asistencia](#chat-de-asistencia)
- [Notificaciones push y email](#notificaciones-push-y-email)

#### [Métricas y Análisis](#métricas-y-análisis)

- [Estadísticas de desempeño estudiantil](#estadísticas-de-desempeño-estudiantil)
- [Análisis de tendencias de aprendizaje](#análisis-de-tendencias-de-aprendizaje)
- [Detección de plagio con IA](#detección-de-plagio-con-ia)

#### [Administración de la Plataforma](#administración-de-la-plataforma)

- [Gestión de usuarios y permisos](#gestión-de-usuarios-y-permisos)
- [Configuración de reglas y normativas](#configuración-de-reglas-y-normativas)
- [Monitoreo de actividad y rendimiento](#monitoreo-de-actividad-y-rendimiento)


### Historias de Usuario


#### Registro de usuarios

**Descripción**

- Como usuario no registrado quiero registrarme en la plataforma para acceder a las funcionalidades del sistema. 

_En el resto de los CA se utilizará la nomenclatura Usuario como un usuario registrado_

**Criterios de aceptación**

- CA 1: Registro exitoso
  - Cuando el registro del usuario es correcto.
  - Entonces el sistema creará un nuevo usuario con su perfil. Luego permitirá el ingreso al sistema.
- CA 2: Obtención de ubicación
  - Cuando el registro del usuario es correcto.
  - Entonces el sistema deberá solicitarle al usuario una ubicación predeterminada
- CA 3: Falta uno o más campos obligatorios
  - Cuando el registro del usuario es incorrecto debido a un ingreso erróneo o faltante de campos. 
  - Entonces el sistema indicará los campos faltantes y/o erróneos y no permitirá el ingreso al sistema.
- CA 4: Registro fallido
  - Cuando el registro del usuario falla debido a un error del servicio.
  - Entonces el sistema indicará un mensaje de error acorde al usuario.

___

#### Login de usuarios con usuario y contraseña

**Descripción**

- Como Usuario quiero ingresar a mi cuenta en la plataforma utilizando usuario y contraseña para acceder a las funcionalidades del sistema

**Criterios de aceptación**

- CA 1: Login exitoso con correo electrónico y contraseña
  - Cuando el login del usuario utilizando correo electrónico y contraseña es correcto
  - Entonces el sistema permitirá el ingreso al sistema
  - En caso contrario se deberá mostrar un mensaje de error acorde al usuario.
- CA 2: Login fallido
  - Cuando el login del usuario falla debido a un error del servicio.
  - Entonces el sistema indicará un mensaje de error acorde al usuario.
- CA 3: Sesión expirada
  - Cuando la sesión del usuario excede el tiempo de expiración
  - Entonces el sistema solicitará al usuario nuevamente el login
- CA 4: Usuario bloqueado
  - Cuando la cuenta del usuario se encuentra bloqueada por los administradores
  - Entonces el sistema no le permitirá loguearse al usuario
- CA 5: Bloqueo de cuenta por intentos fallidos
  - Cuando se detectan múltiples intentos fallidos de inicio de sesión en un corto período de tiempo,
  - Entonces el sistema bloqueará temporalmente la cuenta del usuario y mostrará un mensaje de advertencia, indicando la necesidad de esperar o contactar soporte para desbloquearla.

___

#### Login de usuarios con proveedores de identidad federada

**Descripción**

- Como usuario, quiero poder iniciar sesión en la plataforma utilizando proveedores de identidad federada (por ejemplo, Google, Facebook, etc.) para acceder de forma rápida y segura sin necesidad de registrar manualmente mis datos.

**Criterios de aceptación**

- CA 1: Inicio de sesión exitoso mediante identidad federada  
  - Cuando el usuario selecciona un proveedor de identidad federada y autoriza el acceso,  
  - Entonces el sistema recibirá y validará el token proporcionado; si el token es válido, se iniciará la sesión y se redirigirá al usuario a la plataforma.

- CA 2: Manejo de errores de autenticación  
  - Cuando el proveedor federado devuelve un error (por ejemplo, token inválido, expirado o problemas de conexión),  
  - Entonces el sistema mostrará un mensaje de error claro, indicando que la autenticación ha fallado, y ofrecerá la opción de reintentar o utilizar otro método de autenticación.

- CA 3: Sincronización de datos de perfil  
  - Cuando el usuario inicia sesión mediante un proveedor federado,  
  - Entonces el sistema extraerá y sincronizará la información básica del perfil (nombre, correo electrónico, foto de perfil) para crear o actualizar la cuenta en la plataforma, permitiendo que el usuario modifique estos datos posteriormente si lo desea.

- CA 4: Seguridad en el manejo de tokens  
  - Cuando el sistema recibe un token de identidad federada,  
  - Entonces dicho token será validado mediante el proveedor correspondiente y almacenado de forma segura para garantizar la integridad y confidencialidad de la sesión del usuario.

___

#### Login con datos biométricos

**Descripción**

- Como Usuario quiero ingresar con mi cuenta en la plataforma utilizando mis datos biométricos

**Criterios de aceptación**

- CA 1: Login exitoso con datos biométricos
  - Cuando el login del usuario utilizando datos biométricos, tales como identificación por rostro o huella dactilar, es correcto
  - Entonces el sistema permitirá el ingreso al sistema
  - En caso contrario se deberá mostrar un mensaje de error acorde al usuario.
- CA 2: Login fallido
  - Cuando el login del usuario falla debido a un error del servicio.
  - Entonces el sistema indicará un mensaje de error acorde al usuario.
- CA 3: Sesión expirada
  - Cuando la sesión del usuario excede el tiempo de expiración
  - Entonces el sistema solicitará al usuario nuevamente el login
- CA 4: Usuario bloqueado
  - Cuando la cuenta del usuario se encuentra bloqueada por los administradores
  - Entonces el sistema no le permitirá loguearse al usuario
___

#### Recupero de contraseña

**Descripción**

- Como Usuario quiero poder recuperar mi contraseña en caso de que no la recuerde

**Criterios de aceptación**
- CA 1: Recupero de contraseña exitoso
  - Cuando se realice un recupero de contraseña
  - Entonces se deberá enviar un email con un link de recupero de contraseña, el cual tiene solo un uso y un tiempo de expiración

___

#### Registro de administradores

**Descripción**

- Como administrador quiero poder dar de alta a otros administradores en la plataforma para acceder a las funcion

**Criterios de aceptación**

- CA 1: Registro exitoso
  - Cuando el registro del administrador es correcto.
  - Entonces el sistema registrará un nuevo administrador con sus respectivas credenciales y permitirá el ingreso al sistema.
- CA 2: Falta uno o más campos obligatorios
  - Cuando el registro del administrador es incorrecto debido a un ingreso erróneo o faltante de campos. 
  - Entonces el sistema indicará los campos faltantes y/o erróneos y no permitirá el ingreso al sistema
- CA 3: Registro fallido
  - Cuando el registro del administrador falla debido a un error del servicio.
  - Entonces el sistema indicará un mensaje de error acorde al usuario.

___


#### Login de administradores

**Descripción**

- Como Administrador quiero ingresar con mi cuenta en la plataforma para acceder a las funcionalidades del sistema

**Criterios de aceptación**


- CA 1: Login exitoso 
  - Cuando el login del administrador utilizando sus credenciales es correcto
  - Entonces el sistema permitirá el ingreso al sistema
  - En caso contrario se deberá mostrar un mensaje de error acorde al usuario.
- CA 2: Login fallido
  - Cuando el login del usuario falla debido a un error del servicio.
  - Entonces el sistema indicará un mensaje de error acorde al usuario.

___


#### Notificación de PIN en proceso de registro

**Descripción**

- Como usuario que se ha registrado en la plataforma, quiero recibir un PIN de verificación vía correo electrónico o mediante WhatsApp/SMS para confirmar mi cuenta, de modo que se valide la autenticidad de mi registro y se active mi cuenta de forma segura.

**Criterios de aceptación**

- CA 1: Envío de PIN de verificación  
  - Cuando el usuario se registra exitosamente completando todos los campos obligatorios,  
  - Entonces el sistema generará un PIN único y lo enviará al medio seleccionado (correo electrónico, WhatsApp o SMS), mostrando un mensaje informativo que indique que se ha enviado el PIN.

- CA 2: Validación del PIN ingresado  
  - Cuando el usuario ingrese el PIN recibido en el formulario de verificación,  
  - Entonces el sistema comparará el PIN ingresado con el generado; si es correcto y se ingresa dentro del tiempo de expiración (por ejemplo, 10 minutos), la cuenta se activará y el usuario podrá acceder a la plataforma.  
  - Si el PIN es incorrecto o ha expirado, se mostrará un mensaje de error y se ofrecerá la opción de reenviar un nuevo PIN.

- CA 3: Seguridad y uso único del PIN  
  - Cuando se genera el PIN, este debe ser válido solo para un único intento de verificación y tener un tiempo de expiración definido,  
  - Entonces, una vez utilizado o vencido, el sistema invalidará el PIN para evitar reutilización y asegurar el proceso.

___


#### Edición de perfil

**Descripción**

- Como Usuario, quiero poder editar los datos de mi perfil de usuario (por ejemplo, nombre, correo, foto de perfil y otros detalles relevantes) para mantener actualizada mi información personal y reflejar mis cambios a lo largo del tiempo.

**Criterios de aceptación**

- CA 1: Edición de datos exitosa  
  - Cuando el usuario modifica y guarda sus datos de perfil de forma correcta,  
  - Entonces el sistema actualizará la información y mostrará una confirmación de éxito.

- CA 2: Validación de campos  
  - Cuando el usuario introduce información no válida o deja campos obligatorios vacíos,  
  - Entonces el sistema mostrará mensajes de error claros indicando qué datos necesitan corrección antes de guardar.

- CA 3: Retroalimentación en tiempo real  
  - Cuando el usuario realiza cambios en su perfil,  
  - Entonces el sistema mostrará una vista previa o confirmación de los cambios realizados antes de la actualización final.

- CA 4: Manejo de errores del servidor  
  - Cuando ocurre un error durante el proceso de actualización (por ejemplo, problemas de conexión),  
  - Entonces el sistema mostrará un mensaje de error informativo y sugerirá reintentar la operación.


___


#### Visualización de perfil propio

**Descripción**

- Como Usuario, quiero poder visualizar los datos de mi perfil de usuario para revisar mi información personal, de modo que pueda confirmar que es correcta y actualizarla si es necesario.

**Criterios de aceptación**

- CA 1: Visualización correcta del perfil  
  - Cuando el usuario accede a la sección "Mi Perfil",  
  - Entonces el sistema mostrará de forma organizada tanto los datos públicos como privados asociados a su cuenta.

- CA 2: Manejo de errores  
  - Cuando ocurre un error al cargar el perfil (por ejemplo, fallo en la conexión),  
  - Entonces el sistema mostrará un mensaje de error adecuado e indicará opciones para reintentar la carga.

___

#### Visualización de perfil de otros usuarios

**Descripción**

- Como Usuario, quiero poder visualizar los datos de otros usuarios para conocer su información de contacto y detalles públicos, de modo que pueda decidir si interactúo o me conecto con ellos en la plataforma.

**Criterios de aceptación**

- CA 1: Visualización de datos públicos  
  - Cuando el usuario accede al perfil de otro usuario,  
  - Entonces el sistema mostrará únicamente los datos públicos configurados por el propietario, como nombre, foto de perfil y biografía.

- CA 2: Restricción de datos privados  
  - Cuando se visualiza el perfil de otro usuario,  
  - Entonces el sistema no mostrará información privada o sensible que no esté destinada a ser pública.

- CA 3: Manejo de perfiles inexistentes  
  - Cuando el usuario intenta acceder a un perfil que no existe o ha sido eliminado,  
  - Entonces el sistema mostrará un mensaje adecuado indicando que el perfil no está disponible.

___

#### Creación y gestión de cursos

**Descripción**

- Como docente, quiero poder crear y gestionar cursos en la plataforma para estructurar el proceso de enseñanza y organizar los contenidos de forma efectiva. Esto incluye la creación, edición y eliminación de cursos, así como la definición de criterios de elegibilidad para las inscripciones.

**Criterios de aceptación**

- **CA 1: Creación exitosa de curso**  
  - Cuando el docente ingresa la información requerida (nombre, descripción, fechas, etc.) para crear un curso,  
  - Entonces el sistema debe guardar el curso y mostrar un mensaje de éxito.

- **CA 2: Edición de curso**  
  - Cuando el docente modifica la información de un curso existente,  
  - Entonces el sistema debe actualizar el curso con los nuevos datos y confirmar la actualización.

- **CA 3: Eliminación de curso**  
  - Cuando el docente decide eliminar un curso,  
  - Entonces el sistema debe solicitar confirmación antes de eliminar y, tras confirmarla, eliminar el curso de manera logica.

- **CA 4: Validación de datos**  
  - Cuando el docente ingresa datos incompletos o erróneos al crear o editar un curso,  
  - Entonces el sistema mostrará mensajes de error indicando qué campos deben corregirse.

- **CA 5: Configuración de criterios de elegibilidad**  
  - Cuando el docente crea o edita un curso,  
  - Entonces el sistema debe permitir definir y almacenar criterios de elegibilidad (prerrequisitos, nivel académico, etc.) que serán utilizados para verificar si un estudiante cumple con los requisitos durante el proceso de inscripción.


___

#### Inscripción de estudiantes

**Descripción**

- Como estudiante, quiero poder inscribirme en los cursos disponibles en la plataforma para acceder a su contenido y participar en el proceso de aprendizaje.

**Criterios de aceptación**

- **CA 1: Inscripción exitosa**  
  - Cuando el estudiante selecciona un curso y proporciona la información requerida,  
  - Entonces el sistema debe registrar su inscripción y mostrar una confirmación.

- **CA 2: Verificación de elegibilidad**  
  - Cuando un curso requiere ciertos prerrequisitos o condiciones,  
  - Entonces el sistema verificará que el estudiante cumpla con dichos requisitos antes de permitir la inscripción.

- **CA 3: Manejo de inscripciones duplicadas**  
  - Cuando un estudiante intenta inscribirse en el mismo curso más de una vez,  
  - Entonces el sistema mostrará un mensaje indicando que ya está inscrito en ese curso.

- **CA 4: Notificaciones de inscripción**  
  - Cuando un estudiante se inscribe exitosamente,  
  - Entonces el sistema enviará una notificación (por email o a través de la plataforma) confirmando su inscripción.

___


#### Organización de módulos y recursos

**Descripción**

- Como docente, quiero poder organizar los módulos y recursos dentro de un curso para estructurar el contenido de manera coherente y facilitar el acceso a los materiales de estudio.

**Criterios de aceptación**

- **CA 1: Creación de módulos**  
  - Cuando el docente crea un nuevo módulo dentro de un curso,  
  - Entonces el sistema debe permitir ingresar un título, descripción y establecer el orden de los módulos, guardándolos correctamente.

- **CA 2: Asignación de recursos a módulos**  
  - Cuando el docente agrega recursos (videos, documentos, enlaces, etc.) a un módulo,  
  - Entonces el sistema debe permitir subir o vincular dichos recursos y mostrarlos en el módulo correspondiente.

- **CA 3: Edición y reordenamiento de módulos y recursos**  
  - Cuando el docente edita la estructura de un curso,  
  - Entonces el sistema debe permitir modificar la información de los módulos y cambiar el orden de los recursos, actualizando la organización en tiempo real.

- **CA 4: Validación y manejo de errores**  
  - Cuando se ingresan datos incompletos o erróneos en la creación o edición de módulos y recursos,  
  - Entonces el sistema mostrará mensajes de error adecuados e indicará las correcciones necesarias.


___


#### Visualización de cursos

**Descripción**

- Como alumno, quiero poder ver los cursos en los que estoy inscrito (tanto los actuales como los previos) para gestionar mi aprendizaje y revisar mi historial académico.

**Criterios de aceptación**

- CA 1: Visualización de cursos actuales y previos  
  - Cuando el alumno accede a la sección "Mis Cursos",  
  - Entonces el sistema mostrará una lista diferenciada de cursos activos y finalizados.

- CA 2: Filtro de cursos  
  - Cuando el alumno utiliza la funcionalidad de filtrado (por estado, fecha, nombre del curso, etc.),  
  - Entonces el sistema mostrará únicamente los cursos que cumplan con el criterio seleccionado.

- CA 3: Paginación  
  - Cuando el alumno visualiza la lista de cursos,  
  - Entonces el sistema presentará los cursos paginados para una mejor experiencia de usuario.


___


#### Cursos favoritos

**Descripción**

- Como alumno, quiero tener la posibilidad de guardar cursos como favoritos para acceder rápidamente a aquellos cursos que considero importantes o de interés.

**Criterios de aceptación**

- CA 1: Marcar curso como favorito  
  - Cuando el alumno visualiza un curso y selecciona la opción "Guardar como favorito",  
  - Entonces el sistema marcará el curso como favorito y lo añadirá a su lista de favoritos.

- CA 2: Confirmación de acción  
  - Cuando un curso es marcado como favorito,  
  - Entonces el sistema mostrará una notificación o indicador visual confirmando que el curso ha sido guardado.


___


#### Visualización de cursos favoritos

**Descripción**

- Como alumno, quiero poder ver mis cursos favoritos para acceder de manera rápida a ellos, con la posibilidad de filtrarlos y verlos en una lista paginada.

**Criterios de aceptación**

- CA 1: Visualización de lista de cursos favoritos  
  - Cuando el alumno accede a la sección "Cursos Favoritos",  
  - Entonces el sistema mostrará una lista de todos los cursos marcados como favoritos.

- CA 2: Filtro de cursos favoritos  
  - Cuando el alumno utiliza la funcionalidad de filtrado en la sección de cursos favoritos (por nombre, categoría, fecha, etc.),  
  - Entonces el sistema mostrará únicamente los cursos que cumplan con el criterio seleccionado.

- CA 3: Paginación  
  - Cuando el alumno visualiza la lista de cursos favoritos,  
  - Entonces el sistema presentará los resultados paginados para facilitar la navegación.


___


#### Feedback al curso

**Descripción**

- Como alumno, quiero tener la posibilidad de dar feedback a un curso, tanto en forma escrita como mediante una puntuación, para expresar mi opinión sobre la calidad del curso y ayudar a mejorar el proceso de enseñanza.

**Criterios de aceptación**

- CA 1: Envío de feedback escrito y puntuado  
  - Cuando el alumno envía su feedback para un curso,  
  - Entonces el sistema deberá permitirle ingresar un comentario y seleccionar una puntuación (por ejemplo, de 1 a 5) y registrar ambos datos.

- CA 2: Confirmación de envío  
  - Cuando el alumno envía el feedback,  
  - Entonces el sistema mostrará una notificación confirmando que su feedback ha sido registrado correctamente.

- CA 3: Validación de entrada  
  - Cuando el alumno envía feedback con información incompleta o errónea,  
  - Entonces el sistema mostrará mensajes de error indicando qué datos faltan o deben corregirse.

___


#### Feedback al alumno

**Descripción**

- Como docente, quiero tener la posibilidad de dar feedback a un alumno en el contexto de un curso, para proporcionar retroalimentación constructiva sobre su desempeño y ayudarlo a mejorar.

**Criterios de aceptación**

- CA 1: Envío de feedback al alumno  
  - Cuando el docente ingresa feedback para un alumno en un curso,  
  - Entonces el sistema deberá permitir ingresar tanto un comentario escrito como asignar una puntuación o evaluación cuantitativa.

- CA 2: Notificación al alumno  
  - Cuando el docente envía feedback,  
  - Entonces el sistema notificará al alumno sobre el nuevo feedback recibido.

- CA 3: Validación y actualización  
  - Cuando el docente envía feedback con campos obligatorios (comentario y/o puntuación),  
  - Entonces el sistema validará la información y registrará el feedback correctamente; en caso de errores, se mostrará un mensaje de advertencia.


___



#### Visualización de feedbacks como alumno

**Descripción**

- Como alumno, quiero poder ver los feedbacks que he recibido en mis cursos para conocer mi desempeño y áreas de mejora, presentados de manera filtrable y paginada.

**Criterios de aceptación**

- CA 1: Visualización de feedbacks recibidos  
  - Cuando el alumno accede a la sección "Mis Feedbacks",  
  - Entonces el sistema mostrará una lista de todos los feedbacks recibidos en los cursos en los que ha participado.

- CA 2: Filtro de feedbacks  
  - Cuando el alumno utiliza la funcionalidad de filtrado (por curso, fecha, tipo de feedback, etc.),  
  - Entonces el sistema mostrará únicamente los feedbacks que cumplan con el criterio seleccionado.

- CA 3: Paginación  
  - Cuando el alumno visualiza la lista de feedbacks,  
  - Entonces el sistema presentará los resultados paginados para mejorar la navegación.

- CA 4: Resumen de feedbacks generado por IA  
  - Cuando el alumno solicita o el sistema detecta la necesidad de un resumen,  
  - Entonces el sistema utilizará un modelo de IA para generar un resumen conciso que destaque los puntos clave de los feedbacks recibidos (fortalezas, áreas de mejora, tendencias generales), presentándolo de manera clara y accesible.

___


#### Visualización de feedbacks del curso

**Descripción**

- Como docente, quiero poder ver los feedbacks proporcionados para un curso en particular, para evaluar la percepción y satisfacción de los estudiantes respecto al curso, presentados de forma filtrable y paginada.

**Criterios de aceptación**

- CA 1: Visualización de feedbacks del curso  
  - Cuando el docente accede a la sección de feedbacks de un curso,  
  - Entonces el sistema mostrará una lista de todos los feedbacks asociados a ese curso.

- CA 2: Filtro de feedbacks del curso  
  - Cuando el docente utiliza la funcionalidad de filtrado (por fecha, tipo de feedback, puntuación, etc.),  
  - Entonces el sistema mostrará únicamente los feedbacks que cumplan con el criterio seleccionado.

- CA 3: Paginación  
  - Cuando se visualiza la lista de feedbacks del curso,  
  - Entonces el sistema presentará los resultados paginados para facilitar la revisión.

- CA 4: Resumen de feedbacks del curso generado por IA  
  - Cuando el docente solicita un resumen de los feedbacks,  
  - Entonces el sistema empleará un modelo de IA para generar un resumen que resalte las tendencias generales, aspectos positivos y áreas de mejora, facilitando una visión rápida y global de la satisfacción y desempeño en el curso.


___


  #### Creación de tareas y exámenes

**Descripción**

- Como docente, quiero poder crear tareas y exámenes en la plataforma para evaluar el conocimiento de mis estudiantes de forma estructurada y automatizar, en la medida de lo posible, el proceso de corrección y retroalimentación.

**Criterios de aceptación**

- **CA 1: Creación exitosa**  
  - Cuando el docente completa todos los campos obligatorios (título, descripción, fecha de entrega, instrucciones, etc.) para una tarea o examen,  
  - Entonces el sistema debe crear y almacenar la actividad correctamente, mostrando un mensaje de confirmación.

- **CA 2: Validación de campos obligatorios**  
  - Cuando el docente intenta crear una tarea o examen sin completar uno o más campos esenciales,  
  - Entonces el sistema mostrará mensajes de error específicos indicando qué información falta o es incorrecta, impidiendo la creación hasta que se corrijan.

- **CA 3: Configuración de fecha y condiciones de entrega**  
  - Cuando el docente establece una fecha y hora de entrega para la tarea o examen,  
  - Entonces el sistema debe permitir configurar estos parámetros y, de ser necesario, definir condiciones adicionales (como tiempo de tolerancia o reglas de entrega).

- **CA 4: Edición y actualización**  
  - Cuando el docente decide modificar los detalles de una tarea o examen ya creada,  
  - Entonces el sistema deberá permitir la edición de los campos correspondientes y actualizar la información de forma inmediata, mostrando una notificación de éxito.

- **CA 5: Eliminación de tareas y exámenes**  
  - Cuando el docente decide eliminar una tarea o examen,  
  - Entonces el sistema solicitará una confirmación de la acción y, una vez confirmada, eliminará la actividad de la plataforma.

- **CA 6: Publicación y visibilidad para estudiantes**  
  - Cuando una tarea o examen se crea y se publica,  
  - Entonces el sistema deberá mostrarla en la sección de actividades de los estudiantes inscritos en el curso, asegurando que sólo los usuarios autorizados puedan visualizarla.



___


#### Completar tarea/rendir examen

**Descripción**

- Como alumno, quiero poder completar tareas y rendir exámenes asignados para evaluar mi aprendizaje, de modo que pueda ingresar mis respuestas y recibir retroalimentación de forma estructurada.

**Criterios de aceptación**

- **CA 1: Acceso a la tarea/examen**  
  - Cuando el alumno accede a la sección "Mis Actividades" o "Tareas y Exámenes",  
  - Entonces el sistema mostrará las actividades asignadas, incluyendo instrucciones, fecha límite y estado (pendiente, en curso, etc.).

- **CA 2: Registro y entrada de respuestas**  
  - Cuando el alumno interactúa con una tarea o examen,  
  - Entonces el sistema deberá permitirle ingresar respuestas (texto, selección múltiple, subida de archivos, etc.) según el tipo de actividad.

- **CA 3: Envío y confirmación de entrega**  
  - Cuando el alumno finaliza la actividad y hace clic en "Enviar",  
  - Entonces el sistema registrará la entrega con la marca de tiempo correspondiente y mostrará un mensaje de confirmación de envío exitoso.

- **CA 4: Validación del plazo de entrega**  
  - Cuando el alumno envía la actividad,  
  - Entonces el sistema verificará que se entregue dentro del plazo establecido; si se envía fuera del plazo, se notificará que la entrega es tardía y se aplicará la política correspondiente.


___


#### Listado de tareas/exámenes (docente)

**Descripción**

- Como docente, quiero poder ver un listado de todas las tareas y exámenes que he creado para gestionar y monitorear la actividad de mis estudiantes, permitiéndome filtrar y navegar los registros de manera organizada.

**Criterios de aceptación**

- **CA 1: Visualización del listado**  
  - Cuando el docente accede a la sección "Mis Tareas/Exámenes",  
  - Entonces el sistema mostrará una lista de todas las actividades creadas, con información resumida como título, fecha de entrega, estado y cantidad de envíos.

- **CA 2: Filtro de actividades**  
  - Cuando el docente utiliza opciones de filtrado (por curso, fecha, estado, etc.),  
  - Entonces el sistema mostrará únicamente las actividades que cumplan con los criterios seleccionados.

- **CA 3: Paginación**  
  - Cuando existen muchas actividades,  
  - Entonces el sistema presentará el listado paginado para facilitar la navegación.

- **CA 4: Acceso a detalles de la actividad**  
  - Cuando el docente selecciona una tarea o examen del listado,  
  - Entonces el sistema mostrará los detalles completos de la actividad, incluyendo las respuestas de los estudiantes y opciones para editar o eliminar la actividad.


___



#### Listado de tareas/exámenes (alumno)

**Descripción**

- Como alumno, quiero poder ver un listado de las tareas y exámenes asignados para gestionar mis actividades académicas, conocer cuáles debo completar y revisar mi historial, de forma filtrable y paginada.

**Criterios de aceptación**

- **CA 1: Visualización del listado**  
  - Cuando el alumno accede a la sección "Mis Tareas/Exámenes",  
  - Entonces el sistema mostrará una lista de todas las actividades asignadas, con detalles como título, fecha límite, estado (pendiente, completada, atrasada), etc.

- **CA 2: Filtro de actividades**  
  - Cuando el alumno utiliza opciones de filtrado (por estado, fecha, curso, etc.),  
  - Entonces el sistema mostrará únicamente las actividades que cumplan con los criterios seleccionados.

- **CA 3: Paginación**  
  - Cuando existen numerosos registros,  
  - Entonces el sistema presentará los resultados paginados para una navegación eficiente.

- **CA 4: Acceso a detalles de la actividad**  
  - Cuando el alumno selecciona una tarea o examen del listado,  
  - Entonces el sistema mostrará la información completa de la actividad, incluyendo instrucciones, recursos adjuntos y la opción para iniciar o revisar la actividad.

___


#### Corrección automática con IA

**Descripción**

- Como docente, quiero que el sistema corrija automáticamente las respuestas de tareas y exámenes utilizando inteligencia artificial, para agilizar el proceso evaluativo y proporcionar calificaciones objetivas y consistentes sin intervención manual para respuestas de formato compatible.

**Criterios de aceptación**

- **CA 1: Procesamiento de respuestas**  
  - Cuando el alumno envía una tarea o examen con respuestas en formatos compatibles (por ejemplo, selección múltiple o verdadero/falso),  
  - Entonces el sistema enviará las respuestas al motor de IA para su evaluación.

- **CA 2: Asignación de calificaciones automáticas**  
  - Cuando la IA procesa las respuestas,  
  - Entonces el sistema asignará una nota numérica basada en criterios de evaluación predefinidos y mostrará el resultado tanto al docente como al alumno.

- **CA 3: Manejo de respuestas ambiguas o no evaluables**  
  - Cuando la IA detecte respuestas que no puedan evaluarse automáticamente (por ejemplo, respuestas abiertas o ambiguas),  
  - Entonces el sistema marcará dichas respuestas para revisión manual por parte del docente.

- **CA 4: Notificación de resultados**  
  - Cuando se complete el proceso de corrección automática,  
  - Entonces el sistema enviará una notificación informando a los usuarios que la evaluación ha finalizado y los resultados están disponibles.

___

#### Retroalimentación y notas

**Descripción**

- Como docente, quiero poder proporcionar retroalimentación detallada y asignar notas a las tareas y exámenes, ya sea de forma manual o complementada por la IA, para orientar a los alumnos sobre su desempeño y áreas de mejora.

**Criterios de aceptación**

- **CA 1: Envío de retroalimentación escrita**  
  - Cuando el docente agrega comentarios a una tarea o examen evaluado,  
  - Entonces el sistema deberá permitir la entrada de texto de retroalimentación junto con la calificación asignada.

- **CA 2: Visualización de retroalimentación y notas**  
  - Cuando el alumno revisa una actividad evaluada,  
  - Entonces el sistema mostrará la nota asignada y la retroalimentación detallada proporcionada por el docente.

- **CA 3: Edición de retroalimentación**  
  - Cuando el docente necesita modificar la retroalimentación antes de finalizar la evaluación,  
  - Entonces el sistema deberá permitir la edición de los comentarios y la actualización de la nota correspondiente.

- **CA 4: Generación de resumen de retroalimentación por IA**  
  - Cuando el docente opta por complementar su retroalimentación,  
  - Entonces el sistema podrá utilizar un modelo de IA para generar un resumen conciso que destaque los puntos clave de la evaluación.

- **CA 5: Seguridad y confidencialidad**  
  - Cuando se almacena la retroalimentación y las notas,  
  - Entonces el sistema asegurará que dicha información sea accesible únicamente para el docente y el alumno involucrado, cumpliendo con las normativas de privacidad.


___


#### Foro de preguntas y respuestas

**Descripción**

- Como usuario, quiero poder acceder a un foro de preguntas y respuestas dentro de la plataforma para interactuar con docentes y compañeros, resolver dudas y compartir conocimientos de manera colaborativa.

**Criterios de aceptación**

- **CA 1: Creación de preguntas**  
  - Cuando un usuario desea publicar una pregunta en el foro,  
  - Entonces el sistema deberá permitir la creación de una pregunta que incluya un título, una descripción detallada y la asignación de etiquetas o categorías relevantes.

- **CA 2: Publicación de respuestas**  
  - Cuando un usuario responde a una pregunta,  
  - Entonces el sistema deberá permitir la publicación de respuestas en formato de texto (y opcionalmente con recursos multimedia) que se adjunten a la pregunta original.

- **CA 3: Edición y eliminación de publicaciones**  
  - Cuando el autor de una pregunta o respuesta desea modificar o eliminar su publicación,  
  - Entonces el sistema deberá permitir la edición o eliminación de dicha publicación, siempre y cuando se cumplan las políticas de tiempo y moderación definidas.

- **CA 4: Votación y aceptación de respuestas**  
  - Cuando un usuario considera útil una pregunta o respuesta,  
  - Entonces el sistema deberá permitir que se emitan votos (positivos o negativos) y que el autor de la pregunta marque una respuesta como aceptada para resaltar la solución más adecuada.

- **CA 5: Filtrado y búsqueda de contenido**  
  - Cuando un usuario utiliza la funcionalidad de búsqueda o aplica filtros (por etiquetas, fecha, popularidad, etc.),  
  - Entonces el sistema deberá mostrar únicamente las preguntas y respuestas que cumplan con los criterios de búsqueda o filtro seleccionados.

- **CA 6: Notificaciones de actividad**  
  - Cuando se produzca actividad relevante en una pregunta (nuevas respuestas, comentarios o votos),  
  - Entonces el sistema deberá enviar notificaciones a los usuarios involucrados (autor de la pregunta, usuarios que han respondido o comentado).

- **CA 7: Paginación**  
  - Cuando existan numerosas preguntas en el foro,  
  - Entonces el sistema presentará los resultados paginados para facilitar la navegación y la carga eficiente de contenidos.

___


#### Chat de asistencia

**Descripción**

- Como usuario, quiero disponer de un chat de asistencia completamente gestionado por inteligencia artificial para resolver mis dudas en tiempo real, obtener información precisa y recibir recomendaciones automatizadas sin intervención humana, asegurando respuestas consistentes y rápidas.

**Criterios de aceptación**

- **CA 1: Acceso al chat IA**  
  - Cuando el usuario accede a la sección "Chat de Asistencia IA",  
  - Entonces el sistema mostrará una interfaz de chat interactiva exclusivamente gestionada por un bot de IA.

- **CA 2: Procesamiento de lenguaje natural**  
  - Cuando el usuario envía una consulta en lenguaje natural,  
  - Entonces el bot de IA interpretará la pregunta utilizando técnicas avanzadas de procesamiento de lenguaje natural para comprender la intención y el contexto.

- **CA 3: Respuestas inteligentes y contextualizadas**  
  - Cuando el usuario realiza una consulta,  
  - Entonces el bot de IA deberá proporcionar respuestas precisas, relevantes y adaptadas al contexto de la plataforma, incluyendo sugerencias y recursos adicionales cuando sea pertinente.

- **CA 4: Aprendizaje continuo**  
  - Cuando el bot de IA se enfrente a consultas desconocidas o ambiguas,  
  - Entonces registrará la interacción para análisis y mejora, permitiendo un proceso de aprendizaje continuo que optimice la calidad de sus respuestas futuras.

- **CA 5: Evaluación y feedback de las respuestas**  
  - Cuando el bot de IA responde a una consulta,  
  - Entonces el sistema ofrecerá al usuario la opción de calificar la respuesta y dejar comentarios, permitiendo así retroalimentación para ajustar y mejorar el desempeño del bot.


___


#### Notificaciones push y email

**Descripción**

- Como usuario, quiero recibir notificaciones push y correos electrónicos para estar informado de eventos importantes (por ejemplo, nuevas asignaciones, mensajes, recordatorios y actualizaciones) de manera oportuna, de modo que no me pierda información relevante y pueda actuar en consecuencia.

**Criterios de aceptación**

- **CA 1: Envío de notificaciones push**  
  - Cuando ocurre un evento relevante (como asignación de una nueva tarea, recepción de un mensaje o recordatorio de fecha límite),  
  - Entonces el sistema enviará una notificación push en tiempo real al dispositivo del usuario.

- **CA 2: Envío de notificaciones por correo electrónico**  
  - Cuando ocurre un evento relevante,  
  - Entonces el sistema enviará un correo electrónico con los detalles correspondientes a la dirección de correo registrada del usuario.

- **CA 3: Configuración de notificaciones**  
  - Cuando el usuario accede a la configuración de notificaciones,  
  - Entonces el sistema permitirá personalizar sus preferencias, pudiendo activar o desactivar notificaciones push y/o por email para distintos tipos de eventos.

- **CA 4: Seguridad y privacidad en el envío**  
  - Cuando se envían notificaciones,  
  - Entonces el sistema garantizará que la transmisión se realice de forma segura y que se respeten la integridad y privacidad de los datos del usuario.

- **CA 5: Registro y confirmación de envíos**  
  - Cuando se envía una notificación,  
  - Entonces el sistema registrará el evento de envío y, opcionalmente, mostrará una confirmación en la sección de configuración o mediante un log de actividad.
