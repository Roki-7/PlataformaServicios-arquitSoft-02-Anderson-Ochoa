# Atributos de calidad

## 1. Descripción

Los atributos de calidad establecen cómo debe comportarse la plataforma, además de las funcionalidades que proporciona.

Estos atributos influyen directamente en las decisiones arquitectónicas, tecnológicas y de diseño del sistema.

## 2. Atributos de calidad

| ID | Atributo de calidad | Escenario de calidad | Criterio de verificación propuesto |
|---|---|---|---|
| AC01 | Rendimiento | Las búsquedas de servicios, perfiles y trabajos deben responder con rapidez aun cuando existan múltiples usuarios concurrentes. | Las consultas frecuentes deberán responder en un tiempo adecuado para el usuario y deberán evaluarse mediante pruebas de carga y medición de tiempos de respuesta. |
| AC02 | Disponibilidad | Las funciones principales de consulta, publicación y contratación deben permanecer disponibles durante la operación normal de la plataforma. | Una falla en una funcionalidad secundaria no deberá impedir el acceso a las operaciones principales que no dependan de ella. |
| AC03 | Escalabilidad | La solución debe poder crecer en cantidad de usuarios, publicaciones, categorías y zonas geográficas sin requerir un rediseño completo. | La arquitectura deberá permitir aumentar recursos o capacidad de procesamiento sin modificar las reglas principales del negocio. |
| AC04 | Seguridad | Los datos personales, credenciales, permisos y transacciones deben estar protegidos frente a accesos no autorizados. | El sistema deberá aplicar autenticación, autorización por roles, protección de credenciales y comunicaciones seguras. |
| AC05 | Mantenibilidad | Los módulos deben poseer responsabilidades claras y bajo acoplamiento para facilitar correcciones, pruebas y modificaciones. | Los cambios en un módulo deberán producir el menor impacto posible sobre otras funcionalidades del sistema. |
| AC06 | Usabilidad | La interfaz debe ser comprensible y usable desde computadoras, tabletas y teléfonos móviles. | Las funciones principales deberán poder utilizarse mediante una interfaz web responsive y mantener una navegación consistente en diferentes tamaños de pantalla. |
| AC07 | Resiliencia | La falla temporal de un servicio secundario, como notificaciones, no debe inutilizar funciones principales que no dependan directamente de dicho servicio. | El sistema deberá controlar errores de integraciones externas y permitir que las operaciones independientes continúen funcionando. |

## 3. Escenarios principales

### AC01 - Rendimiento

**Fuente del estímulo:** clientes y prestadores de servicios.

**Estímulo:** múltiples usuarios realizan búsquedas, consultas y operaciones simultáneamente.

**Respuesta esperada:** el sistema procesa las solicitudes manteniendo tiempos de respuesta adecuados.

**Componentes relacionados:** API REST, lógica de negocio, base de datos y mecanismos de optimización de consultas.

### AC02 - Disponibilidad

**Fuente del estímulo:** usuario de la plataforma.

**Estímulo:** un usuario intenta acceder a una funcionalidad principal durante la operación normal del sistema.

**Respuesta esperada:** las funciones principales permanecen disponibles siempre que sus dependencias esenciales estén operativas.

### AC03 - Escalabilidad

**Fuente del estímulo:** crecimiento de la plataforma.

**Estímulo:** aumenta la cantidad de usuarios, servicios publicados, solicitudes de trabajo y zonas geográficas atendidas.

**Respuesta esperada:** el sistema incrementa su capacidad sin requerir modificar completamente su arquitectura.

### AC04 - Seguridad

**Fuente del estímulo:** usuario autorizado o intento de acceso no autorizado.

**Estímulo:** se solicita acceso a información o funcionalidades protegidas.

**Respuesta esperada:** el sistema valida la identidad y los permisos antes de permitir la operación.

### AC05 - Mantenibilidad

**Fuente del estímulo:** equipo de desarrollo.

**Estímulo:** se requiere corregir, modificar o incorporar una funcionalidad.

**Respuesta esperada:** el cambio puede realizarse de forma localizada sin afectar innecesariamente otros módulos.

### AC06 - Usabilidad

**Fuente del estímulo:** cliente, prestador o administrador.

**Estímulo:** el usuario accede desde una computadora, tableta o teléfono móvil.

**Respuesta esperada:** la interfaz se adapta al dispositivo y mantiene una navegación comprensible.

### AC07 - Resiliencia

**Fuente del estímulo:** falla de un servicio externo.

**Estímulo:** el servicio de notificaciones, ubicación u otra integración secundaria deja de responder temporalmente.

**Respuesta esperada:** la plataforma controla la falla y permite continuar utilizando las funciones principales que no dependan de dicho servicio.

## 4. Relación con la arquitectura

Los atributos de calidad identificados condicionarán diferentes decisiones arquitectónicas del sistema.

El rendimiento y la escalabilidad influirán en el acceso a datos, optimización de consultas y posible utilización de mecanismos de caché.

La seguridad influirá en los mecanismos de autenticación, autorización, protección de credenciales y control de acceso.

La mantenibilidad impulsará una separación clara de responsabilidades y dependencias controladas entre los componentes.

La resiliencia requerirá que las integraciones externas se encuentren desacopladas del núcleo de la plataforma para evitar que una falla secundaria afecte innecesariamente otras funciones.