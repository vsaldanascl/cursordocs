# 🛠️ Prompt Mejorado: Generador de Archivos de Tareas con Dependencias

A partir de la siguiente documentación de entrada:

- **PRD (Product Requirements Document)**: `prd.md`
- **Diseño de Arquitectura Técnica**: `arquitectura.md`
- **Especificaciones de Frontend**: `frontend.md`
- **Documentos en /docs/tasks que ya esten marcados como completados**: `NNN_NombreFuncionalidad.md`

Genera una serie de archivos de tareas organizados por funcionalidad, teniendo en cuenta lo siguiente:

---

## 📁 Ejemplo Estructura Esperada de Archivos (ubicación: `docs/tasks/`):

```
docs/tasks/
├── 001_project_setup.md
├── 002_dependencies.md
├── 003_environment_config.md
├── 004_feature_authentication.md
├── 005_feature_payments.md
├── 006_feature_dashboard.md
├── 007_ui_components.md
├── 008_styling_guide.md
├── 009_integration_tests.md
├── 010_build_process.md
└── 011_deployment_config.md
```

Cada archivo representa una unidad de trabajo atómica, coherente y ejecutable.

---

## 📄 Formato de Cada Archivo de Tarea:

- **Título**: Nombre breve y claro de la tarea.
- **Descripción**: Explicación detallada del objetivo y alcance de la tarea.
- **Directriz de Implementación**: Antes de iniciar, es **obligatorio** consultar `@arquitectura.md` y `@frontend.md` para alinear la implementación con las decisiones de diseño establecidas. El objetivo es asegurar la coherencia y evitar regresiones en la funcionalidad existente.
- **Uso de Herramientas**: Cuando la tarea involucre testing de interfaz de usuario o interacciones con la base de datos, se debe priorizar el uso de los MCP (Managed Code Plugins) de Playwright y Supabase.
- **Criterios de Aceptación**: Lista clara y verificable de condiciones necesarias para considerar la tarea completada.
- **Plan de Verificación**: Al finalizar la implementación, se deben detallar las pruebas automatizadas (unitarias, de integración o E2E) que **Cursor ejecutará automáticamente** mediante scripts de testing, comandos npm/yarn, o MCPs disponibles (Playwright, Supabase) para validar que la tarea cumple con los criterios de aceptación y no introduce regresiones.
- **Archivos Afectados**: Archivos que serán creados o modificados.
- **Dependencias**: Otras tareas que deben completarse previamente (referenciadas por número o nombre de archivo).
- **Tiempo Estimado**: Duración estimada para completar la tarea.
- **Notas Técnicas**: Detalles técnicos relevantes, decisiones arquitectónicas, frameworks/librerías involucradas, consideraciones de seguridad, rendimiento o diseño.
- **Checklist de Verificación**: Lista de elementos marcables (checkboxes) que se deben completar secuencialmente después de ejecutar las pruebas automatizadas, incluyendo verificaciones de funcionalidad, rendimiento, seguridad y compatibilidad según corresponda.

---

## 🧠 Consideraciones Especiales:

- **Interdependencias**: Ten en cuenta las dependencias técnicas y lógicas derivadas de `arquitectura.md` y `frontend.md` para establecer el orden correcto de ejecución de tareas.
- **Modularidad**: Divide funcionalidades grandes en subtareas manejables, preferentemente una por archivo.
- **Coherencia entre documentos**: Valida que las decisiones técnicas y de interfaz estén alineadas con las definiciones de producto y arquitectura.
- **Orden de ejecución**: Asigna los números de archivo según el orden lógico de implementación y no simplemente por funcionalidad.
- **Considerar implementación actual**: Si en /docs/tasks o en la implementacion misma ya se encuentran desarrollados funcionalidades, considerar aquello para la creacion o modificacion de las tasks por crear o modificar las existentes