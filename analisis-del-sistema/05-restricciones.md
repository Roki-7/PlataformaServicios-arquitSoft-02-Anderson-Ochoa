# Restricciones del sistema

## 1. Descripción

Las restricciones representan condiciones, limitaciones o decisiones que deben respetarse durante el diseño, desarrollo y evolución de la plataforma.

Estas restricciones pueden ser tecnológicas, arquitectónicas, de integración, de seguridad o relacionadas con el alcance del proyecto.

## 2. Restricciones identificadas

| ID | Restricción | Tipo | Descripción | Impacto en la arquitectura |
|---|---|---|---|---|
| RC01 | Aplicación web responsive | Tecnológica | La primera versión del sistema deberá ser accesible mediante un navegador web y adaptarse a computadoras, tabletas y teléfonos móviles. | Condiciona el diseño de la capa de presentación y requiere una interfaz adaptable a diferentes tamaños de pantalla. |
| RC02 | Control de versiones | Organizacional / Tecnológica | El proyecto deberá utilizar Git para el control de versiones y GitHub como repositorio remoto. | Obliga a mantener un historial de cambios, ramas y commits organizados durante el desarrollo. |
| RC03 | API REST | Arquitectónica | La comunicación entre la interfaz web y el backend deberá realizarse mediante una API REST. | Define el mecanismo principal de comunicación entre la capa de presentación y los servicios del sistema. |
| RC04 | Persistencia de información | Tecnológica | La información de usuarios, servicios, solicitudes, propuestas, contrataciones, pagos y demás operaciones deberá almacenarse de forma persistente. | Requiere una capa de datos y mecanismos de acceso controlado a la base de datos. |
| RC05 | Pasarela de pago externa | Integración | El procesamiento de pagos deberá realizarse mediante una pasarela de pago externa. | Requiere una integración desacoplada que permita gestionar solicitudes, respuestas, errores y confirmaciones de pago. |
| RC06 | Servicio de ubicación / mapas | Integración | Las funcionalidades geográficas podrán utilizar un proveedor externo de mapas o geolocalización. | Requiere encapsular la integración para evitar dependencia directa con un proveedor específico. |
| RC07 | Servicio de notificaciones | Integración | Las notificaciones externas podrán gestionarse mediante un servicio especializado independiente del núcleo del sistema. | Requiere que el módulo de notificaciones esté desacoplado de las funcionalidades principales. |
| RC08 | Privacidad y alcance del sistema | Seguridad / Negocio | El sistema deberá limitar la exposición de datos personales y únicamente admitir servicios que se encuentren dentro del alcance autorizado de la plataforma. | Condiciona el manejo de información personal, permisos, visibilidad de datos y control administrativo del contenido publicado. |

## 3. Restricciones tecnológicas

Las principales restricciones tecnológicas son:

- La solución inicial será una aplicación web responsive.
- El proyecto utilizará Git y GitHub para control de versiones.
- La comunicación entre frontend y backend se realizará mediante una API REST.
- La información del sistema deberá almacenarse de manera persistente.

Estas decisiones establecen una base tecnológica mínima para la primera versión de la plataforma.

## 4. Restricciones de integración

La plataforma deberá interactuar con servicios externos para determinadas funcionalidades:

- Pasarela de pago.
- Servicio de ubicación o mapas.
- Servicio de notificaciones.

Estas integraciones deberán implementarse de forma desacoplada para evitar que el núcleo funcional del sistema dependa directamente de un proveedor específico.

## 5. Restricciones de seguridad y privacidad

La plataforma deberá proteger los datos personales y controlar qué información puede visualizar cada usuario.

El acceso a las funcionalidades deberá depender del rol y los permisos correspondientes.

Los datos sensibles no deberán exponerse innecesariamente a otros usuarios.

Las publicaciones y actividades realizadas dentro de la plataforma deberán respetar el alcance funcional definido para servicios técnicos, profesionales y de oficios.

## 6. Relación con las decisiones arquitectónicas

Las restricciones identificadas influyen directamente en el diseño de la solución.

La utilización de una API REST condiciona la comunicación entre presentación y lógica de negocio.

La persistencia exige una capa de datos claramente definida.

Las integraciones externas requieren servicios especializados que reduzcan el acoplamiento con proveedores.

Las restricciones de privacidad y seguridad influyen en autenticación, autorización, manejo de datos y control de acceso.

Estas restricciones serán consideradas posteriormente al identificar los drivers arquitectónicos del sistema.