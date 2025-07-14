# Tarea 012: Frontend - Estructura y Layout Base

- **Descripción**: Crear la estructura base de los templates del frontend, incluyendo el layout principal, la navegación y el pie de página.
- **Criterios de Aceptación**:
  - Se crea un archivo `base.html` que sirve como plantilla principal para todas las páginas.
  - El layout utiliza Bootstrap 5 y es completamente responsivo.
  - Se incluye una barra de navegación principal y un pie de página estándar.
  - La estructura de archivos estáticos (CSS, JS) está organizada por módulo.
- **Archivos Afectados**:
  - `templates/base.html`
  - `templates/partials/_navbar.html`
  - `templates/partials/_footer.html`
  - `static/css/main.css`
  - `static/js/main.js`
- **Dependencias**: `003_core_backend.md`
- **Tiempo Estimado**: 5 horas.
- **Notas Técnicas**:
  - Se seguirá estrictamente la filosofía de "Bootstrap Puro", sin CSS personalizado que altere los componentes de Bootstrap.
  - El JavaScript será minimalista (ES6+), enfocado en la interactividad necesaria.
  - Se usarán bloques de Jinja (`{% block content %}`) para que las páginas hijas puedan heredar del `base.html`. 