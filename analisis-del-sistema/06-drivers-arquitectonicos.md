# Drivers arquitectónicos

## 1. Descripción

Los drivers arquitectónicos son requisitos, atributos de calidad o restricciones que tienen una influencia significativa en la forma en que se diseña la arquitectura del sistema.

Estos elementos permiten justificar decisiones relacionadas con organización de módulos, comunicación entre componentes, seguridad, integración con servicios externos, persistencia, escalabilidad y mantenimiento.

## 2. Drivers arquitectónicos identificados

| ID | Driver arquitectónico | Origen | Influencia en la arquitectura |
|---|---|---|---|
| DA01 | Soportar el crecimiento de usuarios, publicaciones, categorías y zonas geográficas. | AC03 - Escalabilidad | Influye en la forma de desplegar, dimensionar y organizar los componentes para permitir un crecimiento progresivo sin rediseñar completamente el sistema. |
| DA02 | Mantener tiempos de respuesta adecuados en búsquedas y consultas frecuentes. | AC01 - Rendimiento | Puede influir en índices de base de datos, optimización de consultas, acceso a datos y utilización de mecanismos de caché para lecturas frecuentes. |
| DA03 | Proteger datos personales, credenciales, permisos y operaciones de los usuarios. | AC04 - Seguridad | Influye en los mecanismos de autenticación, autorización por roles, protección de credenciales, control de sesiones y auditoría de operaciones. |
| DA04 | Integrarse con una pasarela de pago externa. | RC05 - Pasarela de pago | Condiciona las interfaces de integración, manejo de errores, confirmación de transacciones y desacoplamiento respecto al proveedor externo. |
| DA05 | Utilizar una API REST entre la aplicación web y el backend. | RC03 - API REST | Define el mecanismo principal de comunicación entre la capa de presentación y la lógica de negocio. |
| DA06 | Evitar que fallas de servicios secundarios afecten las funciones principales. | AC02 - Disponibilidad / AC07 - Resiliencia | Influye en el manejo de errores, tolerancia a fallos y desacoplamiento de servicios externos como notificaciones o ubicación. |
| DA07 | Facilitar cambios y nuevas funcionalidades sin afectar innecesariamente otros módulos. | AC05 - Mantenibilidad | Impulsa una organización modular, responsabilidades claras y dependencias controladas entre los componentes. |

## 3. Justificación de los drivers

### DA01 - Escalabilidad

La plataforma podrá incrementar progresivamente la cantidad de usuarios, servicios publicados, solicitudes de trabajo y zonas geográficas atendidas.

Por este motivo, la arquitectura deberá permitir ampliar la capacidad del sistema sin modificar completamente su estructura.

### DA02 - Rendimiento

Las operaciones de búsqueda, consulta de servicios, perfiles y trabajos serán utilizadas de forma frecuente.

La arquitectura deberá considerar mecanismos que permitan mantener tiempos de respuesta adecuados, como optimización de consultas, índices y, cuando sea necesario, caché para información de lectura frecuente.

### DA03 - Seguridad

La plataforma administrará información personal, credenciales, perfiles, contrataciones y operaciones económicas.

Por ello, la arquitectura deberá considerar autenticación, autorización, manejo seguro de credenciales y control de acceso según el rol del usuario.

### DA04 - Integración con pasarela de pago

La plataforma no procesará directamente las transacciones financieras.

El sistema deberá comunicarse con un proveedor externo de pagos mediante un componente de integración que controle solicitudes, respuestas, errores y confirmaciones de transacción.

### DA05 - API REST

La aplicación web utilizará una API REST para comunicarse con el backend.

Esto permite separar la interfaz de usuario de las reglas de negocio y facilita que el backend pueda ser utilizado posteriormente por otros clientes, como una aplicación móvil.

### DA06 - Resiliencia

Las funcionalidades principales no deberán depender completamente de servicios secundarios.

Por ejemplo, si temporalmente falla el servicio de notificaciones, un usuario debería poder continuar utilizando funcionalidades independientes como consultar servicios o revisar su perfil.

### DA07 - Mantenibilidad

El sistema deberá permitir incorporar nuevas categorías, funcionalidades o integraciones sin modificar innecesariamente otras partes.

Para ello, los módulos deberán mantener responsabilidades claramente definidas y dependencias controladas.

## 4. Priorización arquitectónica

Los drivers que tienen mayor influencia en la arquitectura inicial son:

1. **Seguridad**, debido al manejo de cuentas, permisos, datos personales y transacciones.
2. **Escalabilidad**, debido al posible crecimiento de usuarios, servicios y zonas geográficas.
3. **Rendimiento**, especialmente en búsquedas y consultas frecuentes.
4. **Mantenibilidad**, para permitir la evolución progresiva del sistema.
5. **Integración con servicios externos**, principalmente pagos, ubicación y notificaciones.

La priorización no elimina los demás drivers, sino que ayuda a identificar qué aspectos deberán recibir mayor atención durante el diseño arquitectónico.

## 5. Relación con la arquitectura inicial

Los drivers identificados justifican varias decisiones de la arquitectura:

- La aplicación web y el backend estarán separados mediante una API REST.
- Las reglas del negocio se concentrarán en una capa independiente de la interfaz.
- El acceso a la base de datos se realizará mediante componentes especializados.
- La caché podrá utilizarse para optimizar consultas frecuentes cuando sea necesario.
- Los servicios externos se integrarán mediante componentes desacoplados.
- La autenticación y autorización se gestionarán de forma centralizada.
- Los módulos se organizarán por responsabilidades para facilitar el mantenimiento y crecimiento del sistema.