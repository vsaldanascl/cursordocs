# Tarea 006: Feature - Gestión de Catálogos de Productos

- **Descripción**: Desarrollar la funcionalidad para que los usuarios (proveedores/administradores) puedan cargar y gestionar los catálogos de productos de los proveedores.
- **Criterios de Aceptación**:
  - Se puede cargar un catálogo de productos desde archivos Excel o CSV.
  - El sistema normaliza los datos del producto (códigos, nombres, precios, stock).
  - El sistema valida los datos y reporta errores.
  - Existe una interfaz para editar manualmente los datos cargados.
  - Se desarrollan los endpoints de API necesarios para la gestión de productos.
- **Archivos Afectados**:
  - `app/routes/products/web.py`
  - `app/routes/products/api.py`
  - `app/services/product_importer.py`
  - `templates/products/`
- **Dependencias**: `005_feature_authentication.md`
- **Tiempo Estimado**: 10 horas.
- **Notas Técnicas**:
  - Se utilizará una librería como `pandas` para la lectura y procesamiento de los archivos Excel/CSV.
  - La carga de archivos grandes debe manejarse de forma asíncrona para no bloquear la interfaz.
  - Se debe definir un modelo de datos claro para los productos que permita la normalización a pesar de las diferencias entre proveedores. 