# Tarea 005: Feature - Autenticación y Gestión de Usuarios

- **Descripción**: Implementar el sistema completo de registro, autenticación y gestión de usuarios, incluyendo roles y permisos.
- **Criterios de Aceptación**:
  - Los usuarios pueden registrarse a través de un formulario web.
  - El registro incluye verificación por correo electrónico y aprobación manual por un administrador.
  - Los usuarios pueden iniciar y cerrar sesión de forma segura (usando JWT).
  - Existen roles (Administrador, Farmacia, Proveedor) con permisos diferenciados.
  - Se crean los endpoints de API (`/api/users`) y las rutas web (`/users`) para la gestión de usuarios.
- **Archivos Afectados**:
  - `app/api_users.py`
  - `app/routes/users/web.py` (o similar)
  - `templates/auth/` (login.html, register.html)
  - `templates/users/` (profile.html, user_list.html)
- **Dependencias**: `004_database_setup.md`
- **Tiempo Estimado**: 8 horas.
- **Notas Técnicas**:
  - La autenticación se basará en tokens JWT. Supabase Auth puede ser una opción a investigar.
  - La lógica de negocio para la gestión de usuarios se encapsulará en un `service_users.py` si la complejidad lo requiere.
  - Se debe implementar el control de acceso basado en roles para proteger las rutas. 