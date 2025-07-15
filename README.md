# Lineamientos de Desarrollo - CursorDocs

## 📐 Lineamientos de Arquitectura y Organización de Código

- Mantener una arquitectura modular y simple, alineada con el archivo `arquitectura.md`
- Ningún archivo debe superar las **1000 líneas de código**. Al sobrepasar, refactorizar
- Seguir patrones claros y repetibles en estructura de carpetas y nombres
- El proyecto debe estar organizado en directorios por funcionalidad (`app/api`, `app/services`, etc.)
- Separar las funcionalidades clave como el bot de automatización en carpetas propias
- Evitar código "spaghetti" o mezcla de lógica en múltiples capas

## 🤖 Lineamientos para Desarrollo Asistido por IA (Claude, Gemini)

### Gestión de Tareas
- Priorizar tareas pequeñas y atómicas, definidas en archivos `.md` en `docs/tasks/`

### Estructura de Tareas
Incluir en cada tarea:
- **Título, descripción, directriz de implementación**
- **Criterios de aceptación**
- **Plan de verificación**
- **Dependencias técnicas**
- **Consideraciones especiales**

### MCPs (Model Connected Plugins)
Usar MCPs cuando se trabaje con:
- **Base de datos**: Supabase o equivalente
- **Automatización de navegador**: Playwright

### Distribución de Modelos
- **Claude 4**: principal (~85%)
- **Gemini 2.5 Pro**: para contexto amplio, documentación, PRD y entendimiento del proyecto general (~10%)
- **Claude 4 Thinking**: para tareas más complejas, o errores que Claude 4 no logra resolver (~5%)

> **Nota**: Cuando existan inconsistencias entre PRD y arquitectura, prevalece la arquitectura.

## 🧪 Testing y Validación

- Todas las tareas deben incluir **plan de verificación automático**
- Priorizar el uso de tests automatizados (unitarios, integración, UI)
- Checklist de verificación debe estar marcado como completado por el modelo

## 📄 Documentación y Comunicación

- Documentar el sistema en archivos `PRD.md`, `arquitectura.md`, `frontend.md`, etc.
- **Evitar README o archivos de demo genéricos**
- Todos los miembros deben tener acceso al repo para revisar especificaciones y tareas
- Los archivos generados deben ser coherentes y consistentes entre sí