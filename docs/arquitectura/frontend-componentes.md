# Componentes de UI y Experiencia de Usuario

Este documento describe los componentes de UI reutilizables y las estrategias de navegación y experiencia de usuario.

## 📋 Índice

1. [Componentes Bootstrap Utilizados](#componentes-bootstrap-utilizados)
2. [Componentes Personalizados](#componentes-personalizados)
3. [Navegación y UX](#navegación-y-ux)
4. [Experiencia de Usuario (UX)](#experiencia-de-usuario-ux)

---

## 1. Componentes Bootstrap Utilizados

El sistema aprovecha la robusta librería de componentes de Bootstrap para garantizar consistencia y rapidez en el desarrollo.

- **Navegación**: `Navbar`, `Nav`, `Breadcrumb`
- **Contenedores**: `Container`, `Card`, `Accordion`
- **Formularios**: `Form`, `Input Group`, `Select`, `Datalist`
- **Tablas**: `Table`, `Pagination`, `Badge`
- **Modales y Alertas**: `Modal`, `Alert`, `Toast`
- **Botones y Controles**: `Button`, `Button Group`, `Dropdown`

---

## 2. Componentes Personalizados

Son abstracciones construidas sobre componentes Bootstrap para encapsular lógica repetitiva.

#### Sistema de Mensajes (Toasts)
```javascript
// Implementación de toast notifications reutilizable
function showToast(type, message, duration = 5000) {
    const toastContainer = document.getElementById('toastContainer') || createToastContainer();
    
    const toast = document.createElement('div');
    toast.className = `toast align-items-center text-white bg-${type} border-0`;
    toast.setAttribute('role', 'alert');
    // ... (resto de la implementación) ...
    
    toastContainer.appendChild(toast);
    const bsToast = new bootstrap.Toast(toast, { delay: duration });
    bsToast.show();
}
```

#### Estados de Carga (Spinners y Skeletons)
```javascript
// Muestra un spinner de carga centralizado
function showLoadingState(containerId) {
    const container = document.getElementById(containerId);
    container.innerHTML = `
        <div class="d-flex justify-content-center align-items-center" style="min-height: 200px;">
            <div class="spinner-border text-primary" role="status">
                <span class="visually-hidden">Cargando...</span>
            </div>
        </div>
    `;
}

// Muestra un esqueleto de carga para tablas
function showSkeletonTable(containerId, rows = 5) {
    const container = document.getElementById(containerId);
    // ... (lógica para generar filas de esqueleto) ...
}
```

---

## 3. Navegación y UX

### Estructura de Navegación

#### Navegación Principal (Sidebar)
La navegación lateral es el principal medio para moverse entre los módulos de la aplicación. Utiliza el componente `Collapse` de Bootstrap para submenús.

#### Navegación Contextual (Tabs)
Dentro de un módulo, se utilizan `Nav-tabs` para cambiar entre diferentes secciones o funcionalidades relacionadas, manteniendo al usuario en el contexto actual.

### Gestión de Estado de Navegación

#### Activación de Elementos de Navegación
Un script de JavaScript se encarga de resaltar el enlace activo en la navegación lateral basándose en la URL actual, mejorando la orientación del usuario.

```javascript
// Navigation State Management
document.addEventListener('DOMContentLoaded', function() {
    const currentPath = window.location.pathname;
    const activeLink = document.querySelector(`.list-group-item-action[href='${currentPath}']`);

    if (activeLink) {
        activeLink.classList.add('active');
        const parentCollapse = activeLink.closest('.collapse');
        if (parentCollapse) {
            parentCollapse.classList.add('show');
            const dropdownToggle = document.querySelector(`[data-bs-target="#${parentCollapse.id}"]`);
            if (dropdownToggle) {
                dropdownToggle.classList.add('active');
            }
        }
    }
});
```
---

## 4. Experiencia de Usuario (UX)

### Principios de Diseño UX

1.  **Consistencia**: Elementos similares se comportan de manera similar.
2.  **Feedback**: Respuesta inmediata y clara a las acciones del usuario.
3.  **Eficiencia**: Minimizar el número de clics para tareas comunes.
4.  **Claridad**: Información presentada de forma limpia y comprensible.
5.  **Accesibilidad**: La interfaz debe ser usable por todos.

### Patrones de Interacción

##### Carga Asíncrona con Feedback
```javascript
// Patrón de carga asíncrona con feedback visual
async function loadDataWithFeedback(loadFunction, containerId) {
    showLoadingState(containerId);
    try {
        const data = await loadFunction();
        if (data.success) {
            displayData(data.data, containerId);
            showToast('success', 'Datos cargados exitosamente');
        } else {
            throw new Error(data.message);
        }
    } catch (error) {
        showErrorState(containerId, error.message);
        showToast('error', `Error al cargar datos: ${error.message}`);
    }
}
```

##### Confirmación de Acciones Destructivas
Se utiliza un `Modal` de Bootstrap para solicitar confirmación antes de realizar acciones irreversibles, como eliminar un registro. Esto previene errores costosos.

##### Búsqueda en Tiempo Real con Debouncing
Para evitar peticiones excesivas a la API en campos de búsqueda, se aplica un `debounce`. La búsqueda solo se ejecuta después de que el usuario ha dejado de escribir por un breve período (ej. 300ms). 