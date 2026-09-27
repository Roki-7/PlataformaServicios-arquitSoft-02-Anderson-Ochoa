# Requisitos funcionales

## 1. Descripción

Los requisitos funcionales especifican las capacidades que debe proporcionar la plataforma para satisfacer las necesidades identificadas en las historias de usuario.

Cada requisito posee un identificador único, una descripción funcional, un actor principal y un criterio básico de aceptación que permitirá verificar posteriormente su cumplimiento.

## 2. Requisitos funcionales

| ID | Requisito | Descripción | Actor principal | Criterio de aceptación |
|---|---|---|---|---|
| RF01 | Registro de usuarios | El sistema debe permitir crear cuentas de usuario con los roles de cliente y prestador de servicios. | Cliente / Prestador | El usuario puede registrar una cuenta válida y el sistema almacena correctamente su información y rol. |
| RF02 | Autenticación | El sistema debe permitir iniciar sesión, cerrar sesión y recuperar el acceso a una cuenta. | Cliente / Prestador / Administrador | El sistema permite el acceso únicamente cuando las credenciales son válidas y permite recuperar una cuenta mediante un mecanismo autorizado. |
| RF03 | Gestión de perfil | El sistema debe permitir consultar y actualizar los datos del perfil, ubicación, descripción y datos de contacto autorizados. | Cliente / Prestador | El usuario puede modificar los datos permitidos y visualizar la información actualizada. |
| RF04 | Perfil del prestador | El sistema debe permitir registrar experiencia, especialidades, disponibilidad y evidencias de trabajos realizados. | Prestador de servicios | El prestador puede completar y actualizar su información profesional y esta puede ser consultada por los clientes. |
| RF05 | Gestión de categorías | El sistema debe permitir crear, actualizar, activar y desactivar categorías y subcategorías de servicios. | Administrador | El administrador puede gestionar categorías sin necesidad de modificar el código fuente del sistema. |
| RF06 | Publicación de servicios | El sistema debe permitir al prestador publicar, editar, pausar y retirar los servicios que ofrece. | Prestador de servicios | Los servicios publicados aparecen disponibles para búsqueda cuando se encuentran activos. |
| RF07 | Búsqueda y filtros | El sistema debe permitir buscar y filtrar prestadores y servicios por categoría, ubicación, disponibilidad y calificación. | Cliente | El sistema muestra resultados que coinciden con los criterios seleccionados por el cliente. |
| RF08 | Publicación de trabajos | El sistema debe permitir al cliente publicar una necesidad de trabajo indicando descripción, categoría, ubicación, fecha y demás información relevante. | Cliente | Una solicitud válida queda registrada y disponible para los prestadores correspondientes. |
| RF09 | Consulta de trabajos | El sistema debe permitir a los prestadores consultar oportunidades de trabajo compatibles con sus categorías o criterios de búsqueda. | Prestador de servicios | El prestador puede visualizar solicitudes disponibles y consultar su detalle. |
| RF10 | Propuestas y cotizaciones | El sistema debe permitir al prestador enviar una propuesta indicando monto, descripción, condiciones y otros datos relacionados. | Prestador de servicios | La propuesta queda asociada al trabajo y puede ser consultada por el cliente que realizó la publicación. |
| RF11 | Comparación de propuestas | El sistema debe permitir al cliente revisar y comparar las propuestas recibidas para un trabajo publicado. | Cliente | El cliente puede visualizar las propuestas recibidas y sus principales condiciones antes de seleccionar una. |
| RF12 | Contratación | El sistema debe registrar la aceptación de una propuesta y crear la contratación correspondiente. | Cliente | Al aceptar una propuesta válida, el sistema genera una contratación vinculada con el cliente, prestador y trabajo. |
| RF13 | Comunicación | El sistema debe permitir la comunicación entre cliente y prestador asociada a una propuesta o contratación. | Cliente / Prestador | Los participantes de una contratación pueden intercambiar mensajes relacionados con el servicio. |
| RF14 | Estados del trabajo | El sistema debe gestionar estados del trabajo como solicitado, propuesto, contratado, en ejecución, finalizado y cancelado. | Cliente / Prestador | El sistema registra el estado actual y controla las transiciones permitidas durante el proceso de contratación. |
| RF15 | Notificaciones | El sistema debe generar notificaciones ante nuevas propuestas, aceptación, cambios de estado y finalización de trabajos. | Cliente / Prestador | Los usuarios reciben avisos cuando ocurre un evento relevante asociado a sus operaciones. |
| RF16 | Calificaciones y comentarios | El sistema debe permitir al cliente calificar y comentar un servicio después de que la contratación haya finalizado. | Cliente | Solo una contratación finalizada puede ser calificada y la valoración queda asociada al prestador. |
| RF17 | Pagos | El sistema debe registrar y, cuando corresponda, procesar pagos mediante una pasarela de pago externa. | Cliente | El sistema registra el resultado de la operación y actualiza el estado del pago según la respuesta de la pasarela. |
| RF18 | Comisiones | El sistema debe calcular y registrar la comisión correspondiente a la plataforma de acuerdo con las reglas configuradas. | Sistema / Administrador | La comisión se calcula automáticamente a partir de la contratación o pago correspondiente. |
| RF19 | Historial | El sistema debe permitir consultar el historial de solicitudes, propuestas, contrataciones y servicios asociados a un usuario. | Cliente / Prestador | El usuario puede visualizar sus operaciones anteriores de forma organizada. |
| RF20 | Administración | El sistema debe permitir gestionar usuarios, publicaciones, categorías, incidencias y contenido reportado. | Administrador | El administrador puede consultar y ejecutar las operaciones de gestión autorizadas desde su panel. |
| RF21 | Reportes | El sistema debe permitir consultar reportes relacionados con usuarios, servicios, contrataciones, transacciones y comisiones. | Administrador | El administrador puede visualizar información consolidada según los criterios disponibles. |
| RF22 | Denuncias e incidencias | El sistema debe permitir reportar una publicación, usuario o contratación para su posterior revisión administrativa. | Cliente / Prestador / Administrador | Una denuncia queda registrada con su motivo, origen, estado y datos necesarios para su seguimiento. |

## 3. Relación entre historias de usuario y requisitos funcionales

| Historia de usuario | Necesidad principal | Requisitos funcionales relacionados |
|---|---|---|
| HU01 | Registro y acceso | RF01, RF02 |
| HU02 | Gestión del perfil profesional | RF03, RF04 |
| HU03 | Gestión de servicios | RF05, RF06 |
| HU04 | Búsqueda y filtros | RF07 |
| HU05 | Publicación de trabajos | RF08 |
| HU06 | Consulta de trabajos y envío de propuestas | RF09, RF10 |
| HU07 | Comparación y contratación | RF11, RF12 |
| HU08 | Comunicación y seguimiento | RF13, RF14, RF15 |
| HU09 | Pago del servicio | RF17, RF18 |
| HU10 | Calificación del servicio | RF16 |
| HU11 | Consulta del historial | RF19 |
| HU12 | Administración de la plataforma | RF20, RF21, RF22 |

## 4. Reglas generales de los requisitos

Los requisitos funcionales deberán cumplir las siguientes condiciones generales:

- Las operaciones deben respetar los permisos asignados al rol del usuario.
- Las acciones que modifiquen información deben validar los datos antes de almacenarlos.
- Las contrataciones deben mantener trazabilidad desde la solicitud inicial hasta su finalización.
- Las operaciones de pago deberán conservar el estado informado por la pasarela externa.
- Las calificaciones solo podrán registrarse sobre contrataciones finalizadas.
- Las operaciones administrativas deberán estar restringidas a usuarios con rol de administrador.
- Las categorías y subcategorías deberán administrarse dinámicamente.
- Los estados de las solicitudes, propuestas y contrataciones deberán conservar un historial coherente.