# Tarea 015: Configuración del Despliegue (Deployment)

- **Descripción**: Preparar la aplicación para el despliegue en un entorno de producción.
- **Criterios de Aceptación**:
  - Se crea un `Dockerfile` para contenerizar la aplicación.
  - Se configura un servidor WSGI como Gunicorn para ejecutar la aplicación Flask.
  - Se prepara un script de inicio (`entrypoint.sh`) que ejecute la aplicación en modo de producción.
  - La documentación de despliegue (`docs/DEPLOYMENT.md`) explica los pasos para poner la aplicación en producción.
- **Archivos Afectados**:
  - `Dockerfile`
  - `entrypoint.sh`
  - `docs/DEPLOYMENT.md`
- **Dependencias**: Todas las demás tareas.
- **Tiempo Estimado**: 8 horas.
- **Notas Técnicas**:
  - El `Dockerfile` debe estar optimizado para producción (ej. usando una imagen base slim, no instalando dependencias de desarrollo).
  - Se debe considerar la configuración de un reverse proxy (como Nginx) por delante de Gunicorn para servir archivos estáticos y manejar terminación SSL.
  - La documentación debe ser clara y concisa. 