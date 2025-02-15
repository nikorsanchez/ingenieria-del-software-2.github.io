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

#### [Gestión de Clases](#gestión-de-clases)

- [Creación y gestión de cursos](#creación-y-gestión-de-cursos)
- [Inscripción de estudiantes](#inscripción-de-estudiantes)
- [Organización de módulos y recursos](#organización-de-módulos-y-recursos)

#### [Asignaciones y Evaluaciones](#asignaciones-y-evaluaciones)

- [Creación de tareas y exámenes](#creación-de-tareas-y-exámenes)
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


- Gestión de perfiles de docentes y estudiantes
- Recuperación de cuenta
- Creación y gestión de cursos
- Inscripción de estudiantes
- Organización de módulos y recursos
- Creación de tareas y exámenes
- Corrección automática con IA
- Retroalimentación y notas
- Foro de preguntas y respuestas
- Chat de asistencia
- Notificaciones push y email
- Estadísticas de desempeño estudiantil
- Análisis de tendencias de aprendizaje
- Detección de plagio con IA
- Gestión de usuarios y permisos
- Configuración de reglas y normativas
- Monitoreo de actividad y rendimiento


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
- CA 5: Registro fallido
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
