# Tarea 003: Core Backend y Application Factory

- **Descripción**: Implementar la estructura fundamental del backend, incluyendo el Application Factory de Flask, la configuración del logging y la inicialización de los blueprints principales.
- **Criterios de Aceptación**:
  - `app/__init__.py` contiene la función `create_app`.
  - El sistema de logging (`core_logging.py`) está configurado para escribir en archivos y en la consola.
  - Se registran los blueprints básicos del sistema (main, health check).
  - La aplicación puede iniciarse sin errores.
- **Archivos Afectados**:
  - `app/__init__.py`
  - `app/core_logging.py`
  - `app/api_main.py`
  - `app.py` (Punto de entrada)
- **Dependencias**: `002_environment_config.md`
- **Tiempo Estimado**: 4 horas.
- **Notas Técnicas**:
  - El Application Factory (`create_app`) debe manejar la carga de configuración y el registro de blueprints.
  - El logging debe ser configurable por entorno (más verboso en desarrollo).
  - `api_main.py` contendrá rutas básicas como `/` y `/api/health`. 