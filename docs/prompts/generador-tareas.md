
# 🛠️ Prompt Mejorado: Generador de Archivos de Tareas con Dependencias

A partir de la siguiente documentación de entrada:

- **PRD (Product Requirements Document)**: `prd.md`
- **Diseño de Arquitectura Técnica**: `arquitectura.md`
- **Especificaciones de Frontend**: `frontend.md`

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
- **Criterios de Aceptación**: Lista clara y verificable de condiciones necesarias para considerar la tarea completada.
- **Archivos Afectados**: Archivos que serán creados o modificados.
- **Dependencias**: Otras tareas que deben completarse previamente (referenciadas por número o nombre de archivo).
- **Tiempo Estimado**: Duración estimada para completar la tarea.
- **Notas Técnicas**: Detalles técnicos relevantes, decisiones arquitectónicas, frameworks/librerías involucradas, consideraciones de seguridad, rendimiento o diseño.

---

## 🧠 Consideraciones Especiales:

- **Interdependencias**: Ten en cuenta las dependencias técnicas y lógicas derivadas de `arquitectura.md` y `frontend.md` para establecer el orden correcto de ejecución de tareas.
- **Modularidad**: Divide funcionalidades grandes en subtareas manejables, preferentemente una por archivo.
- **Coherencia entre documentos**: Valida que las decisiones técnicas y de interfaz estén alineadas con las definiciones de producto y arquitectura.
- **Orden de ejecución**: Asigna los números de archivo según el orden lógico de implementación y no simplemente por funcionalidad.
