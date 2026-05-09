# Sistemas Distribuidos 

---

## Unidad V: Seguridad en sistemas distribuidos

### Proyecto Final - Sistema de Citas y Expedientes Médicos

##### Integrantes del equipo 

- Jesús Virgilio Ayala Gaspar 

- Maricarmen Buenfil Perez 

---

### Sistema Distribuido para la Gestión de Citas de un Consultorio Médico

#### Objetivo. 
Diseñar e implementar una solución robusta que resuelva los desafíos inherentes a la concurrencia, la transparencia de red y la integridad de los datos en un entorno de servicios médicos. Se desarrollará una aplicación distribuida basada en un modelo de tres capas (presentación, lógica de negocio, datos) que permita a pacientes reservar una cita de consulta con un médico, y al médico llevar el historial de cada paciente. En este sistema se deben incluir mecanismos de exclusión mutua distribuida para la gestión de concurrencia de reservas sobre un mismo horario y mecanismos de seguridad para la autenticación de usuarios y operaciones en la base de datos, utilizando servicios web como medio de comunicación entre las capas del sistema.

La aplicación deberá implementar las siguientes funcionalidades:

1. Gestión de pacientes. Permitir el registro de nuevos pacientes, incluyendo al menos los siguientes datos: nombre, dirección, correo electrónico, teléfono, edad, sexo. Para la identificación única de cada paciente y su validación al acceder al sistema se deberá implementar el registro de un nombre de usuario y contraseña. Permitir la consulta, modificación y eliminación de la información de los pacientes registrados.

2. Gestión de Reservas de citas médicas. Permitir el registro de una nueva cita seleccionando el día y la hora. Permitir la consulta, modificación y eliminación de la información registrada tanto por parte del paciente, como por parte del médico (administrador), en este caso se puede generar algún tipo de notificación al paciente de la eliminación de su registro de cita (puede ser un servicio web que envíe un correo o se puede llevar un registro de notificaciones por usuario que se desplieguen cuando ingrese al sistema). El médico también puede registrar una nueva cita para un paciente y, en este caso, también se generará un aviso para el paciente.

3. Registro de la historia clínica. Generar un registro de relatoría por parte del médico sobre lo que ocurre en la consulta con el paciente (diagnóstico, resultados de análisis clínicos, prescripciones, etc.). Todas las consultas inician con el registro de temperatura corporal, peso, altura y presión arterial. Esta información se deberá almacenar encriptada.

4. Generación de Reportes (requiere autenticación).

    * a) Lista de Pacientes (Médico)
    * b) Calendario de citas. (Médico)
    * c) Historial clínico de un paciente (Encabezado: Datos generales del paciente, Cuerpo: los datos recabados de cada consulta. (Médico y el paciente)

#### Arquitectura del sistema

La aplicación deberá implementarse utilizando una arquitectura de tres capas:

1. Capa de Presentación: Interfaz de usuario (web) para la interacción con el sistema. Deberá permitir a los usuarios realizar todas las operaciones de gestión y visualización de la información.

2. Capa de Lógica de Negocio: Implementará la lógica de la aplicación, incluyendo el control de la concurrencia en el registro de citas, los mecanismos de seguridad y la generación de los reportes. Esta capa deberá exponer sus funcionalidades a través de servicios web para favorecer la heterogeneidad de dispositivos.

3. Capa de Datos: Responsable del almacenamiento y la gestión de la información. Se podrá utilizar un sistema de gestión de bases de datos (SGBD) para la persistencia de los datos.

#### Entregar:

1. Documento de Diseño: Descripción detallada de la arquitectura del sistema, el diseño de la base de datos, la especificación de los servicios web (parámetros, formatos de datos), la descripción de la interfaz de usuario, el mecanismo de control de concurrencia y los mecanismos de seguridad implementados.

2. Código Fuente: Código completo y documentado de las tres capas de la aplicación.

3. Manual de Usuario: Guía para la instalación y el uso de la aplicación.

4. Pruebas de Concurrencia: reporte de pruebas donde se demuestre que el mecanismo de exclusión mutua evita efectivamente la "condición de carrera" en la reserva de citas.

5. Presentación: Exposición del proyecto, demostración de la funcionalidad y explicación de las decisiones de diseño.

---

### Criterios de Evaluación


| **Criterio**                                      | **Porcentaje**  |
| ------------------------------------------------- | :-------------: |
| Cumplimiento de requisitos funcionales            | 35%             |
| Implementación técnica (seguridad y concurrencia) | 35%             |
| Documentación                                     | 20%             |
| Presentación final del proyecto                   | 10%             |
| **Total**                                         | 100%            |