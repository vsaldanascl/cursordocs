# Tarea 009: Feature - Reportes y Análisis

- **Descripción**: Implementar el dashboard de reportes y las herramientas de análisis de datos de compras.
- **Criterios de Aceptación**:
  - Un dashboard interactivo muestra KPIs clave (ahorro, volumen de compra).
  - Se pueden generar reportes de historial de compras por diferentes períodos.
  - El análisis de ahorro calcula los beneficios generados por la plataforma.
  - Los reportes se pueden exportar a Excel y PDF.
- **Archivos Afectados**:
  - `app/routes/reports/web.py`
  - `app/routes/reports/api.py`
  - `app/services/reporting_service.py`
  - `templates/reports/`
- **Dependencias**: `008_feature_purchase_orders.md`
- **Tiempo Estimado**: 8 horas.
- **Notas Técnicas**:
  - Para los gráficos del frontend, se utilizará `Chart.js` como se especifica en la arquitectura.
  - El backend debe proporcionar endpoints de API eficientes que agreguen los datos para los reportes.
  - Las consultas complejas para los reportes pueden optimizarse con vistas materializadas o funciones RPC en Supabase. 