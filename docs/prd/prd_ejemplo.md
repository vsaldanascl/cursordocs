

 

Contenido
1.	Introducción	2
2.	Objetivos del Proyecto	2
3.	Funcionalidades del Sistema	2
3.1 Registro y Acceso	2
3.2 Gestión de Datos de Productos	2
3.3 Comparación de Precios	2
3.4 Gestión de Órdenes de Compra	3
3.5 Reportes y Análisis	3
3.6 Gestión de Usuarios y Permisos	3
3.7 Integración con Proveedores	3
3.8 Sistema de Notificaciones	4
3.9 Seguridad	4
3.10 Facturación y Pagos	4
3.11 Auditoría y Registro	4
4. Requisitos No Funcionales	4
5. Tecnología Requerida	5
6. Entregables	5
7. Criterios de Evaluación de Propuestas	5
8. Modelos de Suscripción	5
4.	ANEXO: Especificación Detallada	6

 
1.	Introducción
Se requiere desarrollar una plataforma SaaS que permita a farmacias independientes comparar precios de diversos proveedores de fármacos, optimizando costos y tiempos de compra. Esta plataforma utilizará un portal web con un backend robusto capaz de procesar grandes volúmenes de datos eficientemente.
2.	Objetivos del Proyecto
•	Automatizar la comparación de precios de medicamentos entre múltiples proveedores
•	Optimizar la selección de proveedores según precio, tiempos de entrega y disponibilidad
•	Generar órdenes de compra automáticas y exportables
•	Proporcionar reportes de ahorro y análisis históricos de precios
•	Facilitar el uso para usuarios con bajo nivel de alfabetización digital
3.	Funcionalidades del Sistema
3.1 Registro y Acceso
•	Registro de farmacias: Formulario en línea con verificación de documentación oficial (licencia ISP/Seremi)
•	Autenticación segura: Login con credenciales y opción de autenticación de dos factores
•	Niveles de acceso: Administradores, farmacias y proveedores con permisos diferenciados
•	Verificación: Proceso de validación mediante correo electrónico seguido de aprobación manual por administrador
3.2 Gestión de Datos de Productos
•	Carga de catálogos: Soporte para Excel, CSV o integración vía API
•	Normalización de datos: Procesamiento automático de códigos de barras, SKUs, precios y stock
•	Validación: Detección y reporte de errores estructurales en los datos
•	Edición manual: Interfaz para ajustar datos antes de su confirmación final
•	Escaneo opcional: Lectura de códigos de barras mediante cámara de dispositivos móviles
3.3 Comparación de Precios
•	Algoritmo de optimización: Selección inteligente basada en precio, rapidez de entrega y disponibilidad
•	Filtros personalizables: Opciones para refinar búsquedas según necesidades específicas
•	Vista comparativa: Presentación clara de alternativas disponibles para cada producto
•	Selección manual o automática: Opción para elegir individualmente o permitir optimización automática
•	Alertas de mínimos de compra: Notificación cuando una orden no alcanza el mínimo requerido
3.4 Gestión de Órdenes de Compra
•	Generación automática: Creación de órdenes separadas por proveedor
•	Personalización: Edición de cantidades y productos antes de confirmar
•	Exportación: Formatos Excel y PDF disponibles
•	Envío automático: Distribución por correo electrónico a proveedores
•	Historial completo: Almacenamiento de todas las órdenes para consulta posterior
3.5 Reportes y Análisis
•	Dashboard interactivo: Visualización de KPIs y tendencias de compra
•	Historial de compras: Análisis por períodos (diario, semanal, mensual, anual)
•	Análisis de ahorro: Cálculo automático de beneficios generados por la plataforma
•	Exportación flexible: Descarga en Excel y PDF
•	Reportes programados: Envío automático según configuración del usuario
3.6 Gestión de Usuarios y Permisos
•	Roles definidos: Administrador, farmacia y proveedor con permisos específicos
•	Administración centralizada: Panel para gestión de usuarios y asignación de roles
•	Historial de cambios: Registro de modificaciones en permisos y accesos
•	Autenticación robusta: Credenciales únicas y seguras para cada usuario
3.7 Integración con Proveedores
•	Actualización automática: Sincronización periódica de catálogos vía API o archivos
•	Datos sincronizados: Precios, disponibilidad, códigos y nombres de productos
•	Alertas de cambios: Notificaciones ante modificaciones significativas de precios
•	Integración múltiple: Soporte para sincronización con diversos proveedores simultáneamente
3.8 Sistema de Notificaciones
•	Tipos de alertas: Cambios en precios, disponibilidad, estado de órdenes, pagos pendientes
•	Canales configurables: Correo electrónico, notificaciones en plataforma, SMS/WhatsApp (opcional)
•	Alertas personalizadas: Configuración de umbrales para notificaciones automáticas
•	Historial: Registro de todas las notificaciones enviadas
3.9 Seguridad
•	Autenticación segura: Contraseñas encriptadas y opción de MFA para administradores
•	Control de acceso por roles: Restricción de funcionalidades según permisos
•	Encriptación de datos: Protección en almacenamiento y tránsito
•	Auditoría de actividades: Monitoreo de accesos y acciones críticas
•	Protección contra ataques: Medidas contra SQL injection, XSS, fuerza bruta
3.10 Facturación y Pagos
•	Planes de suscripción: Básico, Pro y Business con diferentes niveles de servicio
•	Métodos de pago: Integración con WebPay, Khipu, transferencia electrónica
•	Facturación automática: Generación y envío de facturas por correo
•	Historial de pagos: Registro detallado de transacciones
•	Gestión de impagos: Notificaciones y suspensión temporal por falta de pago
3.11 Auditoría y Registro
•	Registro completo: Documentación de accesos, cambios y operaciones críticas
•	Información detallada: Fecha, hora, usuario, IP y detalles de cada acción
•	Panel de auditoría: Interfaz con filtros para administradores autorizados
•	Exportación segura: Generación de informes en CSV y PDF
•	Alertas de seguridad: Detección de actividades sospechosas
4. Requisitos No Funcionales
•	Interfaces responsivas: Diseño adaptable a diferentes dispositivos
•	Rendimiento óptimo: Tiempo máximo de procesamiento de 10 segundos para comparaciones grandes
•	Alta disponibilidad: Garantía de uptime del 99.9%
•	Escalabilidad: Arquitectura que permite crecimiento horizontal
•	Usabilidad: Interfaz intuitiva para usuarios con diferentes niveles de familiaridad tecnológica
5. Tecnología Requerida
•	Frontend: React.js o Vue.js
•	Backend: Python con Django o Node.js con Express
•	Base de Datos: PostgreSQL o DynamoDB
•	Infraestructura: AWS (Lambda, S3, API Gateway) o GCP
•	Seguridad: JWT para autenticación y encriptación de datos
6. Entregables
•	Diseño UI/UX (mockups y wireframes)
•	Desarrollo e implementación completa de frontend y backend
•	Documentación técnica y de usuario
•	Pruebas unitarias y de carga
•	Capacitación para usuarios finales
•	Soporte post-lanzamiento por 6 meses
7. Criterios de Evaluación de Propuestas
•	Experiencia demostrable en desarrollo de plataformas SaaS
•	Propuesta técnica alineada con los requisitos especificados
•	Plan detallado de ejecución y roadmap del proyecto
•	Estructura de costos transparente (desarrollo y mantenimiento)
•	Estrategia de escalabilidad y seguridad
8. Modelos de Suscripción
•	Plan Gratuito: Acceso limitado para prueba (ej. 10 productos por mes)
•	Plan Pro: Acceso completo a todas las funcionalidades
•	Plan Business: Soporte para farmacias con múltiples sucursales
 
4.	ANEXO: Especificación Detallada
3.1. Acceso y Registro
Especificación de Requerimientos:
Requerimiento 1: Registro de Farmacias
Descripción:
El sistema debe permitir el registro de farmacias independientes mediante un formulario en línea. Para validar el registro, se requerirá la carga de documentos de autorización oficial.
Criterios de Aceptación:
1.	Un usuario debe poder registrarse proporcionando la siguiente información: 
o	Nombre de la farmacia
o	Nombre del responsable
o	RUT de la farmacia
o	Teléfono de contacto
o	Correo electrónico
o	Ubicación (región y comuna)
o	Documento de licencia (PDF o imagen)
2.	El sistema debe enviar un correo de verificación al usuario.
3.	Una vez verificado, el usuario debe ser aprobado manualmente por un administrador.
4.	Solo farmacias con validación manual pueden acceder a las funcionalidades de comparación de precios y generación de órdenes de compra.
Restricciones:
•	El correo electrónico debe ser único en la base de datos.
•	El documento de licencia debe ser legible y aprobado por un administrador.
•	Si el usuario no verifica su correo en 24 horas, su cuenta será eliminada automáticamente.
Interacciones con otros sistemas:
•	Integración con servicio de correo (ejemplo: AWS SES o SendGrid) para el envío del correo de validación.
•	Panel de administración para la revisión y aprobación de registros.
Casos de Uso:
1.	Un dueño de farmacia accede a la plataforma y completa el formulario de registro.
2.	Recibe un correo de verificación con un enlace de activación.
3.	Al hacer clic en el enlace, el estado de su cuenta cambia a "pendiente de aprobación".
4.	Un administrador revisa la solicitud y aprueba o rechaza el registro.
5.	Si es aprobado, el usuario recibe un correo de confirmación y puede iniciar sesión.

3.2. Carga de Datos
Especificación de Requerimientos:
Requerimiento 2: Carga de Catálogos de Productos
Descripción:
El sistema debe permitir a los usuarios cargar catálogos de productos de proveedores en distintos formatos para facilitar la comparación de precios. La plataforma debe normalizar estos datos para garantizar la correcta asociación de productos y precios.
Criterios de Aceptación:
1.	Los usuarios deben poder subir archivos en los siguientes formatos:
o	Excel (.xlsx, .xls)
o	CSV (.csv)
o	API (en caso de integración con proveedores que la soporten)
2.	El sistema debe procesar y normalizar los siguientes datos:
o	Código de barras del producto (clave primaria)
o	Nombre del producto (puede variar entre proveedores)
o	Precio unitario
o	SKU interno del proveedor (opcional)
3.	El sistema debe validar que los datos cargados no contengan errores estructurales (celdas vacías, formatos incorrectos, duplicados).
4.	El usuario debe recibir una notificación con un resumen de los datos procesados y errores detectados.
5.	El sistema debe permitir la edición manual de datos cargados antes de su confirmación.
Restricciones:
•	No se aceptarán archivos mayores a 10 MB.
•	Los archivos deben contener al menos las columnas de código de barras y precio para ser procesados.
•	Si un producto no tiene código de barras, no podrá ser incluido en la base de datos.
Interacciones con otros sistemas:
•	Integración con bases de datos de productos para la validación de códigos de barras.
•	Opción de carga masiva mediante API para proveedores que lo permitan.
Casos de Uso:
1.	Un usuario accede a la plataforma y elige la opción de "Carga de catálogo".
2.	Selecciona el archivo desde su dispositivo y lo sube al sistema.
3.	El sistema valida el archivo y muestra un resumen de los datos cargados.
4.	Si hay errores, el usuario recibe un reporte detallado y opciones de corrección.
5.	Si los datos son correctos, el usuario confirma la carga y los datos quedan almacenados en la base de datos.

3.3. Comparación de Precios y Generación de Órdenes
Especificación de Requerimientos:
Requerimiento 3: Comparación de Precios
Descripción:
El sistema debe permitir a los usuarios comparar los precios de los productos cargados en la base de datos según los proveedores con los que tienen acuerdos. La comparación debe realizarse en base al precio, tiempos de entrega y stock disponible.
Criterios de Aceptación:
1.	El usuario debe poder seleccionar los productos que desea cotizar.
2.	El sistema debe listar los proveedores disponibles para cada producto.
3.	Los proveedores deben ser ordenados según los criterios seleccionados por el usuario: 
o	Precio más bajo
o	Entrega más rápida
o	Stock disponible
4.	El usuario debe poder seleccionar un proveedor por producto o permitir que el sistema optimice la selección.
5.	Se debe generar una orden de compra automática basada en la comparación y selección.
6.	El usuario debe poder modificar la selección antes de confirmar la orden de compra.
Restricciones:
•	Solo se mostrarán precios de proveedores con los que el usuario tenga un acuerdo activo.
•	Si dos proveedores tienen el mismo precio y tiempos de entrega, se debe elegir al proveedor con mejor historial de disponibilidad.
•	Los datos deben actualizarse cada vez que el usuario realice una nueva consulta.
Interacciones con otros sistemas:
•	Integración con la base de datos de proveedores y sus catálogos de precios.
•	Algoritmo de optimización para selección de proveedor basado en criterios personalizados.
•	Generación de órdenes de compra automáticas basadas en los resultados de la comparación.
Casos de Uso:
1.	Un usuario accede a la plataforma y selecciona los productos que desea cotizar.
2.	El sistema realiza la comparación de precios y muestra los resultados ordenados según el criterio seleccionado.
3.	El usuario revisa los proveedores disponibles y realiza ajustes manuales si es necesario.
4.	Se genera una orden de compra automática con la selección final del usuario.
5.	El usuario confirma la orden y se notifica a los proveedores correspondientes.

3.4. Generación y Gestión de Órdenes de Compra
Especificación de Requerimientos:
Requerimiento 4: Generación de Órdenes de Compra
Descripción:
El sistema debe permitir la generación automática de órdenes de compra basadas en la comparación de precios y selección de proveedores. Cada orden de compra debe ser específica para cada proveedor y debe incluir los detalles de los productos seleccionados, cantidad, precio unitario, precio total y plazos de entrega.
Criterios de Aceptación:
1.	El usuario debe poder revisar y modificar la orden de compra antes de su confirmación.
2.	La orden de compra debe contener la siguiente información: 
o	Nombre del proveedor
o	Lista de productos seleccionados con su código de barras
o	Cantidad por producto
o	Precio unitario y precio total por producto
o	Fecha estimada de entrega
o	Total de la orden de compra
3.	Se debe permitir la descarga de la orden de compra en formato Excel y PDF.
4.	La orden de compra debe ser enviada automáticamente al proveedor vía correo electrónico.
5.	El sistema debe almacenar un historial de órdenes de compra para referencia futura.
Restricciones:
•	Una orden de compra solo puede contener productos de un solo proveedor.
•	Si una orden de compra no alcanza el mínimo requerido por el proveedor, se debe ofrecer la opción de agregar productos adicionales o dividir la compra entre otros proveedores.
•	Solo usuarios con permisos adecuados pueden generar órdenes de compra.
Interacciones con otros sistemas:
•	Integración con la base de datos de proveedores para validar información.
•	Sistema de notificaciones para alertar sobre órdenes generadas y enviadas.
•	Panel de administración para monitorear el estado de las órdenes de compra.
Casos de Uso:
1.	Un usuario revisa la lista de productos y selecciona los que desea comprar.
2.	El sistema genera automáticamente una orden de compra optimizada según los criterios elegidos.
3.	El usuario revisa la orden, realiza ajustes si es necesario y la confirma.
4.	La orden de compra se genera en formato PDF/Excel y se envía automáticamente al proveedor correspondiente.
5.	El sistema almacena la orden de compra en el historial para futuras consultas.

3.5. Reportes y Análisis de Datos
Especificación de Requerimientos:
Requerimiento 5: Generación de Reportes y Análisis de Datos
Descripción:
El sistema debe proporcionar herramientas de reportería y análisis que permitan a los usuarios evaluar su historial de compras, tendencias de precios y ahorros generados. Los reportes deben poder visualizarse en el sistema y exportarse en formatos Excel y PDF.
Criterios de Aceptación:
1.	El usuario debe poder acceder a un panel de reportes con la siguiente información: 
o	Historial de compras por período (diario, semanal, mensual, anual).
o	Comparación de precios históricos por producto.
o	Análisis de ahorro generado por la plataforma.
o	Reporte de proveedores más utilizados y rendimiento en tiempos de entrega.
2.	Los reportes deben incluir filtros por fechas, proveedores y productos específicos.
3.	Se debe permitir la exportación de reportes en formato Excel y PDF.
4.	Los gráficos y tablas de reportes deben ser dinámicos e interactivos.
5.	El sistema debe enviar reportes automáticos por correo electrónico a los usuarios que lo soliciten.
Restricciones:
•	Solo usuarios con permisos administrativos pueden acceder a reportes avanzados.
•	Los reportes deben generarse en un tiempo máximo de 5 segundos para optimizar la experiencia del usuario.
•	El almacenamiento de reportes históricos debe limitarse a un período configurable por el administrador.
Interacciones con otros sistemas:
•	Integración con la base de datos de compras y órdenes de compra para generación de reportes.
•	Herramientas de visualización de datos (ejemplo: librerías gráficas en frontend como Chart.js o D3.js).
•	Sistema de notificaciones para alertar sobre reportes generados y programados.
Casos de Uso:
1.	Un usuario accede al panel de reportes y selecciona el tipo de análisis que desea visualizar.
2.	El sistema genera el reporte solicitado y lo muestra en pantalla con gráficos interactivos.
3.	El usuario aplica filtros según su necesidad (fechas, proveedores, productos, etc.).
4.	El usuario decide exportar el reporte en formato Excel o PDF.
5.	Si el usuario ha programado reportes automáticos, recibe un correo con el reporte adjunto en el formato seleccionado.

3.6. Gestión de Usuarios y Permisos
Especificación de Requerimientos:
Requerimiento 6: Gestión de Usuarios y Permisos
Descripción:
El sistema debe permitir la administración de usuarios con distintos niveles de permisos y roles. Cada usuario tendrá acceso a funciones específicas de acuerdo con su rol dentro de la plataforma.
Criterios de Aceptación:
1.	El sistema debe permitir la creación, edición y eliminación de usuarios por parte de administradores autorizados.
2.	Se deben definir los siguientes roles de usuario con sus respectivos permisos: 
o	Administrador: Acceso completo al sistema, gestión de usuarios, configuración y reportería avanzada.
o	Farmacia: Acceso a comparación de precios, generación de órdenes de compra y reportes básicos.
o	Proveedor: Acceso a la carga y actualización de catálogos de productos.
3.	Los administradores deben poder asignar y modificar los roles de los usuarios.
4.	El sistema debe registrar un historial de cambios en permisos y accesos.
5.	Cada usuario debe autenticarse con credenciales únicas y seguras.
Restricciones:
•	Un usuario no puede cambiar su propio rol.
•	Solo los administradores pueden gestionar usuarios y permisos.
•	El sistema debe implementar autenticación segura con encriptación de contraseñas.
Interacciones con otros sistemas:
•	Integración con un sistema de autenticación (OAuth 2.0, JWT o similar).
•	Registro de logs de acceso y cambios en roles para auditoría.
Casos de Uso:
1.	Un administrador accede al panel de gestión de usuarios.
2.	Crea un nuevo usuario y le asigna un rol específico.
3.	Un usuario intenta acceder a una función restringida y el sistema valida sus permisos.
4.	Un administrador modifica los permisos de un usuario existente.
5.	Se genera un registro de auditoría cada vez que se cambia un rol o se accede al sistema.

3.7. Integración con Proveedores y Sincronización de Datos
Especificación de Requerimientos:
Requerimiento 7: Integración con Proveedores
Descripción:
El sistema debe permitir la integración con proveedores de medicamentos para la actualización automática de catálogos de productos y precios. La sincronización debe realizarse mediante API o carga de archivos automatizada.
Criterios de Aceptación:
1.	El sistema debe permitir la integración con proveedores a través de: 
o	API REST para la obtención de datos en tiempo real.
o	Carga de archivos en formatos CSV o Excel de manera programada.
2.	Los datos sincronizados deben incluir: 
o	Código de barras del producto.
o	Nombre del producto.
o	Precio unitario actualizado.
o	Disponibilidad y stock.
o	SKU interno del proveedor.
3.	La actualización de precios y disponibilidad debe realizarse de manera periódica, configurable por el usuario.
4.	El sistema debe generar alertas cuando un proveedor modifique significativamente los precios o disponibilidad de productos.
5.	Se debe permitir la integración con múltiples proveedores simultáneamente.
Restricciones:
•	Solo proveedores registrados y autorizados pueden sincronizar datos con el sistema.
•	Si un proveedor no proporciona datos estructurados correctamente, su información no se sincronizará.
•	Las actualizaciones masivas deben ejecutarse en horarios programados para evitar interrupciones en el sistema.
Interacciones con otros sistemas:
•	API de proveedores para la obtención y actualización de información.
•	Base de datos de productos para almacenamiento y comparación de precios.
•	Sistema de notificaciones para alertas de cambios en precios y disponibilidad.
Casos de Uso:
1.	Un administrador configura la integración con un proveedor mediante API o carga de archivos.
2.	El sistema sincroniza automáticamente la información de productos según la programación establecida.
3.	Un usuario revisa los datos actualizados en la plataforma y verifica cambios en precios y stock.
4.	Se genera una alerta automática si hay modificaciones significativas en los precios de un proveedor.
5.	El usuario utiliza los datos sincronizados para generar órdenes de compra optimizadas.

3.8. Notificaciones y Alertas
Especificación de Requerimientos:
Requerimiento 8: Sistema de Notificaciones y Alertas
Descripción:
El sistema debe contar con un módulo de notificaciones que informe a los usuarios sobre eventos relevantes dentro de la plataforma, como cambios en precios, disponibilidad de productos, generación de órdenes de compra y alertas personalizadas.
Criterios de Aceptación:
1.	El sistema debe enviar notificaciones en los siguientes casos: 
o	Cambios significativos en precios de productos.
o	Baja disponibilidad o agotamiento de productos en stock.
o	Confirmación y estado de órdenes de compra.
o	Recordatorios de pago de suscripción.
o	Alertas personalizadas configuradas por el usuario.
2.	Los usuarios deben poder configurar sus preferencias de notificación: 
o	Correo electrónico.
o	Notificación dentro de la plataforma.
o	Notificación por SMS o WhatsApp (opcional para futuro desarrollo).
3.	Las notificaciones deben incluir información detallada sobre el evento y enlaces directos a la acción correspondiente en la plataforma.
4.	Se debe permitir la configuración de umbrales para alertas automáticas (por ejemplo, notificar si un producto baja un 10% en precio o si el stock cae por debajo de un nivel definido).
5.	El sistema debe registrar todas las notificaciones enviadas para referencia y auditoría.
Restricciones:
•	Los usuarios solo pueden recibir notificaciones relacionadas con los productos y proveedores con los que tienen acuerdos.
•	Se debe evitar el envío excesivo de notificaciones para no saturar al usuario.
•	La frecuencia de las notificaciones automáticas debe ser configurable.
Interacciones con otros sistemas:
•	Integración con sistema de correo (AWS SES, SendGrid, etc.) para envío de notificaciones por email.
•	Integración con servicios de mensajería (Twilio, WhatsApp Business API) para notificaciones móviles.
•	Base de datos de usuarios y proveedores para personalizar alertas.
Casos de Uso:
1.	Un usuario recibe una notificación sobre una variación en el precio de un producto clave y revisa la nueva oferta en la plataforma.
2.	El sistema envía una alerta cuando un producto en la orden de compra está agotado en el proveedor seleccionado.
3.	Un administrador configura una alerta para recibir notificaciones sobre cambios en la disponibilidad de ciertos productos.
4.	Un usuario recibe un recordatorio de pago de suscripción y accede al portal para realizar la transacción.
5.	El sistema almacena un historial de notificaciones enviadas para revisión en cualquier momento.

3.9. Seguridad y Control de Acceso
Especificación de Requerimientos:
Requerimiento 9: Seguridad y Control de Acceso
Descripción:
El sistema debe garantizar la seguridad de los datos de los usuarios y proveedores mediante controles de acceso adecuados, encriptación de datos y autenticación robusta.
Criterios de Aceptación:
1.	Implementar autenticación segura mediante: 
o	Autenticación por correo y contraseña con encriptación.
o	Autenticación multifactor (MFA) opcional para usuarios administrativos.
o	Integración con OAuth 2.0 o SAML para login con terceros.
2.	Control de acceso basado en roles: 
o	Los usuarios solo pueden acceder a funcionalidades según sus permisos.
o	Separación de roles entre administradores, farmacias y proveedores.
3.	Protección de datos sensibles: 
o	Encriptación de datos almacenados (Base de datos con AES-256 o equivalente).
o	Encriptación de datos en tránsito mediante HTTPS/TLS 1.2 o superior.
4.	Registro de actividad y auditoría: 
o	Monitoreo de accesos y acciones críticas dentro del sistema.
o	Historial de cambios en órdenes de compra y precios.
5.	Protección contra ataques cibernéticos: 
o	Prevención de ataques de inyección SQL y XSS.
o	Implementación de políticas de seguridad en headers HTTP.
o	Protección contra fuerza bruta y bloqueo de intentos fallidos de inicio de sesión.
Restricciones:
•	Solo los administradores pueden modificar configuraciones de seguridad.
•	El sistema debe cumplir con normativas de protección de datos (Ej. GDPR, ISO 27001).
•	Las contraseñas deben cumplir con requisitos mínimos de seguridad (longitud, caracteres especiales, etc.).
Interacciones con otros sistemas:
•	Integración con servicios de autenticación externos (Ejemplo: Google Identity, Okta, Auth0).
•	Monitoreo de eventos de seguridad mediante herramientas SIEM.
•	Generación de logs de seguridad almacenados de manera segura.
Casos de Uso:
1.	Un usuario intenta acceder a la plataforma y se autentica con MFA.
2.	Un administrador revisa el historial de accesos y detecta intentos de ingreso fallidos.
3.	Un usuario intenta acceder a una funcionalidad restringida y el sistema lo bloquea.
4.	Un proveedor cambia el precio de un producto y se registra la acción en el historial de auditoría.
5.	Se detecta un intento de ataque por fuerza bruta y el sistema bloquea el IP temporalmente.

3.10. Facturación y Gestión de Pagos
Especificación de Requerimientos:
Requerimiento 10: Facturación y Gestión de Pagos
Descripción:
El sistema debe permitir la gestión de pagos y facturación para farmacias suscritas al servicio. Se debe ofrecer distintos planes de suscripción con métodos de pago seguros y emisión automática de facturas.
Criterios de Aceptación:
1.	El sistema debe permitir los siguientes métodos de pago: 
o	Tarjeta de crédito/débito (integración con pasarelas de pago como WebPay, PayPal, Stripe).
o	Transferencias bancarias manuales con confirmación administrativa.
2.	Los usuarios deben poder elegir entre diferentes planes de suscripción: 
o	Plan básico (X funcionalidades, X límite de productos comparados).
o	Plan avanzado (funcionalidades completas, sin límite de productos comparados).
o	Plan empresarial (planes personalizados para grandes farmacias o cadenas).
3.	El sistema debe generar facturas automáticas y enviarlas al usuario vía correo electrónico.
4.	Se debe mostrar un historial de pagos en el perfil del usuario, con detalles de cada transacción.
5.	Notificaciones automáticas para recordar pagos pendientes antes del vencimiento.
6.	Bloqueo temporal del acceso en caso de impago hasta regularización del mismo.
Restricciones:
•	Solo administradores pueden gestionar planes y tarifas de suscripción.
•	Si un usuario no paga dentro de X días tras el vencimiento, su acceso se suspenderá automáticamente.
•	Se deben cumplir regulaciones fiscales aplicables según la región del usuario.
Interacciones con otros sistemas:
•	Integración con pasarelas de pago para procesamiento seguro de transacciones.
•	Base de datos de usuarios y suscripciones para control de acceso y facturación.
•	Sistema de notificaciones para alertar sobre pagos pendientes y confirmaciones.
Casos de Uso:
1.	Un usuario selecciona un plan de suscripción y elige un método de pago.
2.	El sistema procesa el pago y genera una factura automática enviada al correo del usuario.
3.	Un usuario revisa su historial de pagos en el panel de administración.
4.	Un usuario recibe una notificación recordándole que su pago está próximo a vencer.
5.	Un usuario con pago vencido intenta acceder al sistema y se le muestra una alerta de suspensión.

3.11. Auditoría y Registro de Actividad
Especificación de Requerimientos:
Requerimiento 11: Auditoría y Registro de Actividad
Descripción:
El sistema debe contar con un módulo de auditoría que registre todas las acciones relevantes realizadas por los usuarios dentro de la plataforma. Esto permitirá un monitoreo detallado de cambios, accesos y modificaciones realizadas en órdenes de compra, precios y configuraciones del sistema.
Criterios de Aceptación:
1.	El sistema debe registrar las siguientes actividades: 
o	Inicio y cierre de sesión de usuarios.
o	Creación, modificación y eliminación de órdenes de compra.
o	Cambios en la configuración de seguridad y permisos de usuario.
o	Actualización de precios y disponibilidad por parte de los proveedores.
o	Pagos y cambios en planes de suscripción.
2.	Cada evento registrado debe incluir: 
o	Fecha y hora del evento.
o	Usuario que realizó la acción.
o	Dirección IP desde donde se realizó la acción.
o	Detalles específicos del cambio o acción ejecutada.
3.	Los administradores deben poder acceder a un panel de auditoría con filtros por usuario, fecha y tipo de acción.
4.	Se debe permitir la exportación de registros en formato CSV y PDF.
5.	Los registros deben almacenarse de manera segura y con acceso restringido a usuarios autorizados.
6.	El sistema debe permitir la configuración de alertas en caso de acciones sospechosas (ejemplo: múltiples intentos de inicio de sesión fallidos).
Restricciones:
•	Solo administradores y auditores autorizados pueden acceder al registro de actividad.
•	Los registros deben conservarse por un período configurable (ejemplo: 6 meses, 1 año).
•	No se debe permitir la manipulación o eliminación de registros de auditoría.
Interacciones con otros sistemas:
•	Base de datos de usuarios y actividad para almacenamiento de logs.
•	Sistema de notificaciones para alertar sobre eventos críticos.
•	Integración con herramientas SIEM para análisis avanzado de seguridad.
Casos de Uso:
1.	Un administrador revisa el historial de acceso de un usuario sospechoso.
2.	Se genera una alerta cuando un usuario intenta múltiples inicios de sesión fallidos.
3.	Un auditor exporta un informe detallado de cambios en precios y órdenes de compra.
4.	Un proveedor revisa sus propias acciones registradas en el sistema.
5.	Un usuario intenta eliminar un registro de auditoría y el sistema lo bloquea automáticamente.






