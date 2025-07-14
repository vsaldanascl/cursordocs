# Tarea 002: Configuración de Entornos

- **Descripción**: Crear y configurar los archivos y variables de entorno necesarios para los entornos de desarrollo, testing y producción.
- **Criterios de Aceptación**:
  - Archivo `.env.example` creado con todas las variables de entorno requeridas (sin valores sensibles).
  - El archivo `core_config.py` implementa las clases de configuración para `development` y `production`.
  - La aplicación Flask carga la configuración correcta según la variable `FLASK_ENV`.
- **Archivos Afectados**:
  - `.env` (a ser creado por el desarrollador a partir del ejemplo)
  - `.env.example`
  - `app/core_config.py`
  - `app/__init__.py`
- **Dependencias**: `001_project_setup.md`
- **Tiempo Estimado**: 3 horas.
- **Notas Técnicas**:
  - Las variables de entorno deben incluir las de Flask, Supabase y cualquier otra API externa.
  - La configuración debe ser cargada usando `python-dotenv`.
  - Se debe asegurar que las claves secretas y otros datos sensibles no se suban al repositorio. 