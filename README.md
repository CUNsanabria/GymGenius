# GymGenius
Gym Genius soft

# casos de usuario 
historias de usuario para el proyecto Gym Genius:

1. **Como usuario, quiero poder registrarme en el sistema para acceder a los servicios del gimnasio.**
   - Descripción: Los usuarios deben poder crear una cuenta en Gym Genius proporcionando información básica como nombre, dirección de correo electrónico y número de teléfono.
   - Criterios de Aceptación:
     - Debe haber un formulario de registro en la interfaz de usuario.
     - El formulario debe validar la dirección de correo electrónico y no permitir registros duplicados.
     - Después del registro exitoso, el usuario debe recibir un correo electrónico de confirmación.

2. **Como usuario, quiero poder iniciar sesión en mi cuenta para acceder a las funciones del gimnasio.**
   - Descripción: Los usuarios registrados deben poder iniciar sesión en Gym Genius utilizando sus credenciales previamente proporcionadas durante el registro.
   - Criterios de Aceptación:
     - Debe haber un formulario de inicio de sesión en la interfaz de usuario.
     - El sistema debe autenticar al usuario utilizando la dirección de correo electrónico y la contraseña.
     - Después del inicio de sesión exitoso, el usuario debe ser redirigido al panel de control.

3. **Como personal del gimnasio, quiero tener un ID único para acceder al sistema y realizar tareas administrativas.**
   - Descripción: El personal del gimnasio debe tener la capacidad de iniciar sesión en Gym Genius utilizando un ID único proporcionado por el sistema.
   - Criterios de Aceptación:
     - Se debe asignar un ID único a cada miembro del personal del gimnasio.
     - El personal debe poder iniciar sesión en el sistema utilizando su ID único y una contraseña.

4. **Como personal del gimnasio, quiero poder registrar la asistencia de los usuarios en el ingreso principal del gimnasio.**
   - Descripción: El personal del gimnasio debe poder registrar la entrada de los usuarios al gimnasio utilizando el ingreso principal.
   - Criterios de Aceptación:
     - Debe haber una opción en la interfaz para registrar la entrada de los usuarios.
     - El personal debe poder buscar y seleccionar al usuario por su ID único.
     - El sistema debe registrar la hora de entrada del usuario.

5. **Como personal del gimnasio, quiero poder verificar si los usuarios están al día con sus pagos al registrar su entrada.**
   - Descripción: El personal del gimnasio debe poder verificar rápidamente si un usuario tiene pagos pendientes al registrar su entrada.
   - Criterios de Aceptación:
     - Debe haber una indicación visual clara que muestre el estado de pago del usuario.
     - El sistema debe mostrar un mensaje de alerta si el usuario tiene pagos pendientes.
     - El personal debe poder ver el historial de pagos del usuario para obtener más detalles si es necesario.

Estas historias de usuario cubren algunas de las funcionalidades básicas del proyecto Gym Genius, desde el registro de usuarios hasta la gestión de la asistencia y la verificación de pagos.

# Documento de Requisitos

##1. Introducción

1.1 Propósito del Documento
Este documento describe los requisitos funcionales y no funcionales para el desarrollo de Gym Genius, una aplicación web destinada a la inscripción de personas para entrenar en un gimnasio, la gestión del personal, el control de accesos y la administración de pagos de membresías.

1.2 Alcance del Proyecto
Gym Genius permitirá a los administradores del gimnasio inscribir a los usuarios y al personal, controlar el acceso al gimnasio y gestionar los pagos de membresías. Las funcionalidades no incluyen la integración con otros sistemas externos ni la gestión avanzada de inventarios de equipo.

##2. Requisitos Funcionales

2.1 Gestión de Usuarios
- **Inscripción de Usuarios**:
  - El sistema permitirá registrar nuevos usuarios proporcionando datos como nombre, dirección, correo electrónico, número de teléfono, y detalles de pago.
  - Los usuarios podrán actualizar su información personal.

- **Inscripción de Personal**:
  - El sistema permitirá registrar al personal del gimnasio con información como nombre, cargo, horario de trabajo, y datos de contacto.
  - El personal podrá actualizar su información personal.

2.2 Control de Accesos
- **Verificación de Acceso**:
  - El sistema controlará el acceso de los usuarios mediante tarjetas de acceso, códigos QR o huellas dactilares.
  - Los usuarios deberán estar al día con los pagos de sus membresías para acceder al gimnasio.
  - Se enviarán alertas automáticas a los administradores si un usuario intenta acceder con una membresía vencida.

2.3 Gestión de Pagos
- **Procesamiento de Pagos**:
  - El sistema aceptará pagos mediante tarjeta de crédito, débito y otros métodos electrónicos.
  - Los usuarios podrán ver el estado de sus pagos y su historial de transacciones.

- **Notificaciones de Pago**:
  - Se enviarán notificaciones automáticas por correo electrónico y SMS a los usuarios para recordarles los pagos pendientes.
  - Se generarán alertas automáticas para los administradores sobre pagos vencidos.

##3. Requisitos No Funcionales

3.1 Seguridad
- Los datos de los usuarios se almacenarán de manera segura utilizando cifrado.
- Se implementará autenticación multifactor para los administradores y el personal del gimnasio.

3.2 Usabilidad
- La interfaz de usuario será intuitiva y fácil de navegar.
- La aplicación será accesible desde dispositivos móviles y computadoras de escritorio.

3.3 Rendimiento
- El sistema deberá soportar hasta 500 usuarios concurrentes sin degradación significativa en el rendimiento.
- Los tiempos de respuesta del sistema no deberán exceder los 2 segundos para cualquier operación.

##4. Otros Requisitos

4.1 Integración con Otros Sistemas
- Actualmente, no se requiere integración con otros sistemas externos.

4.2 Regulaciones y Cumplimiento
- El sistema cumplirá con las normativas locales de protección de datos y privacidad, incluyendo la GDPR si es aplicable.

 4.3 Soporte y Mantenimiento
- Se proporcionará soporte técnico durante el horario laboral.
- Las actualizaciones y parches de seguridad se implementarán de manera regular.


# Modelo de Datos

Entidades Principales:

    Usuario:
        Atributos:
            ID (identificador único)
            Nombre
            Correo electrónico
            Contraseña
            Fecha de registro
            Estado de membresía (activo, inactivo)
        Relaciones:
            Un usuario puede tener múltiples inscripciones en clases de entrenamiento.
            Un usuario puede tener múltiples registros de acceso al gimnasio.
            Un usuario puede tener múltiples pagos de membresía.

    Clase de Entrenamiento:
        Atributos:
            ID (identificador único)
            Nombre
            Descripción
            Instructor
            Horario
        Relaciones:
            Una clase de entrenamiento puede tener múltiples inscripciones de usuarios.

    Registro de Acceso:
        Atributos:
            ID (identificador único)
            ID de usuario (clave externa)
            Fecha y hora de acceso
            Estado (entrada, salida)
        Relaciones:
            Un registro de acceso está asociado a un usuario.

    Pago de Membresía:
        Atributos:
            ID (identificador único)
            ID de usuario (clave externa)
            Fecha de pago
            Monto
        Relaciones:
            Un pago de membresía está asociado a un usuario.

    Personal del Gimnasio:
        Atributos:
            ID (identificador único)
            Nombre
            Cargo
            Correo electrónico
            Contraseña
        Relaciones:
            El personal del gimnasio puede estar asociado a múltiples registros de acceso al gimnasio.

            # Diagrama de Relaciones
            
+--------------+     +------------------------+     +---------------------+
|   Usuario    |     | Clase de Entrenamiento |     | Registro de Acceso  |
+--------------+     +------------------------+     +---------------------+
| ID           |     | ID                     |     | ID                  |
| Nombre       |     | Nombre                 |     | ID de usuario       |
| Correo       |     | Descripción            |     | Fecha y hora acceso |
| Contraseña   |     | Instructor             |     | Estado              |
| Fecha registro |   | Horario                |     +---------------------+
| Estado membresía |  +------------------------+
+--------------+     | Inscripción             |
                     +------------------------+
                     | ID                     |
                     | ID de usuario          |
                     | ID de clase            |
                     +------------------------+

+------------------------+     +--------------------------+
|   Pago de Membresía    |     |   Personal del Gimnasio  |
+------------------------+     +--------------------------+
| ID                     |     | ID                       |
| ID de usuario          |     | Nombre                   |
| Fecha de pago          |     | Cargo                    |
| Monto                  |     | Correo electrónico       |
+------------------------+     | Contraseña               |
                                +--------------------------+
