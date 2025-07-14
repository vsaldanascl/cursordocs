# Tarea 007: Feature - Motor de Comparación de Precios

- **Descripción**: Implementar el algoritmo principal de la plataforma para comparar precios de productos entre diferentes proveedores.
- **Criterios de Aceptación**:
  - Un usuario puede seleccionar productos y ver una comparación de precios de los proveedores disponibles.
  - El algoritmo de optimización puede sugerir la mejor combinación de compra basada en precio, tiempo de entrega y disponibilidad.
  - La vista comparativa es clara y permite la selección manual o automática.
  - Se implementan filtros para refinar la búsqueda.
- **Archivos Afectados**:
  - `app/routes/comparison/web.py`
  - `app/routes/comparison/api.py`
  - `app/services/comparison_engine.py`
  - `templates/comparison/`
- **Dependencias**: `006_feature_product_catalog.md`
- **Tiempo Estimado**: 12 horas.
- **Notas Técnicas**:
  - El motor de comparación (`comparison_engine.py`) será el núcleo de esta funcionalidad. Debe ser eficiente y escalable.
  - Se pueden usar funciones RPC de PostgreSQL (`call_rpc`) para realizar cálculos complejos directamente en la base de datos y mejorar el rendimiento.
  - La interfaz de usuario es crítica aquí; debe ser intuitiva y fácil de usar para personas con baja alfabetización digital. 