# Calidad y Performance del Frontend

Este documento cubre temas transversales para asegurar un frontend de alta calidad, incluyendo responsive design, performance, accesibilidad y testing.

## 📋 Índice

1. [Responsive Design](#responsive-design)
2. [Interactividad y Eventos](#interactividad-y-eventos)
3. [Validación y Formularios](#validación-y-formularios)
4. [Visualización de Datos](#visualización-de-datos)
5. [Performance Frontend](#performance-frontend)
6. [Accesibilidad](#accesibilidad)
7. [Testing Frontend](#testing-frontend)
8. [Mejores Prácticas](#mejores-prácticas)

---

## 1. Responsive Design

### Filosofía Mobile-First
El frontend implementa un diseño **Mobile-First** utilizando el sistema de grillas y componentes responsivos de Bootstrap, garantizando una experiencia óptima en todos los dispositivos.

### Estrategias por Componente
- **Navegación**: El sidebar se oculta en pantallas pequeñas, accesible a través de un botón "toggle". El menú superior se colapsa en un menú de hamburguesa.
- **Tablas**: Se utiliza `.table-responsive` para habilitar el scroll horizontal en tablas anchas, evitando la deformación del layout.
- **Formularios**: El sistema de columnas de Bootstrap (`.row`, `.col-md-6`) permite que los campos de formulario se apilen verticalmente en pantallas pequeñas.
- **Gráficos**: Chart.js es responsive por defecto (`responsive: true`).

---

## 2. Interactividad y Eventos

### Event Delegation
Para manejar eventos en elementos dinámicos (ej. botones en una tabla que se carga por AJAX), se utiliza el patrón de delegación de eventos. Se asigna un único listener a un contenedor padre.

```javascript
document.getElementById('table-container').addEventListener('click', (e) => {
    if (e.target.closest('.btn-edit-item')) {
        const itemId = e.target.closest('.btn-edit-item').dataset.itemId;
        editItem(itemId);
    }
});
```

### Custom Events
Para comunicar entre módulos desacoplados, se pueden usar eventos personalizados. Por ejemplo, un módulo puede disparar `CustomEvent('item:created')` y otro módulo puede escucharlo para actualizar su vista.

---

## 3. Validación y Formularios

Se implementa una validación en **múltiples capas**:
1.  **Validación Client-Side (JavaScript)**: Feedback inmediato al usuario utilizando las clases `.is-valid` e `.is-invalid` de Bootstrap.
2.  **Atributos HTML5**: Uso de atributos como `required`, `type="email"`, `minlength`.
3.  **Validación Server-Side**: La validación definitiva y más segura, que se ejecuta en el backend.

---

## 4. Visualización de Datos

### Chart.js
Para la visualización de datos, se utiliza Chart.js por su simplicidad, flexibilidad y diseño responsive.

#### Fábrica de Gráficos
Se recomienda una `ChartFactory` para centralizar la configuración y creación de gráficos, asegurando un estilo visual consistente.

```javascript
class ChartFactory {
    static createTimeSeries(canvasId, data, label) {
        // ... configuración estandarizada para gráficos de serie temporal
    }
    static createBarChart(canvasId, data, label) {
        // ... configuración estandarizada para gráficos de barras
    }
}
```
---

## 5. Performance Frontend

- **Lazy Loading**: Carga diferida de imágenes (`loading="lazy"`) y módulos JS que no son críticos para el renderizado inicial.
- **Debouncing y Throttling**: Para eventos frecuentes como `resize`, `scroll` o `input` en búsquedas, para evitar la ejecución excesiva de funciones.
- **Minificación**: En un pipeline de producción, los archivos CSS y JS deben ser minificados para reducir su tamaño.
- **Uso de CDNs**: Para librerías comunes (Bootstrap, Chart.js), se aprovecha el cache del navegador del usuario.

---

## 6. Accesibilidad (a11y)

### Estándares WCAG
Se siguen las directrices WCAG 2.1 AA como base.
- **HTML Semántico**: Uso correcto de `<main>`, `<nav>`, `<header>`, `<section>`, etc.
- **Atributos ARIA**: Uso de `aria-label`, `aria-describedby`, `role` para componentes dinámicos como modales y dropdowns, para que sean comprensibles por lectores de pantalla.
- **Navegación por Teclado**: La aplicación debe ser completamente navegable y operable utilizando solo el teclado.
- **Gestión del Foco**: Mover el foco programáticamente a elementos relevantes, por ejemplo, al abrir un modal, el foco debe ir al primer elemento interactivo dentro de él.

---

## 7. Testing Frontend

### Estrategias de Testing

#### Unit Testing (con Jest o similar)
Ideal para probar funciones puras y lógica de negocio aislada (ej. una función de `utils.js`).

#### Integration Testing
Prueba cómo interactúan varios componentes. Por ejemplo, verificar que al hacer clic en un botón se abre un modal y se carga la información correcta.

#### End-to-End (E2E) Testing (con Playwright o Cypress)
Simula el flujo completo de un usuario en un navegador real.

```javascript
// Ejemplo de test E2E con Playwright
test('debería crear un nuevo item', async ({ page }) => {
    await page.goto('/module_a/feature_1');
    await page.click('#btnNewItem');
    await page.fill('[name="name"]', 'Nuevo Item');
    await page.click('button[type="submit"]');
    await expect(page.locator('.toast-success')).toBeVisible();
});
```

---

## 8. Mejores Prácticas

- **Organización del Código**: Mantener la estructura de archivos modular y consistente.
- **Nomenclatura**: Seguir convenciones claras (ej. `camelCase` para funciones JS, `PascalCase` para clases).
- **Gestión de Errores**: Envolver siempre las llamadas `fetch` y operaciones asíncronas en bloques `try/catch` para manejar errores de red o de API de forma controlada.
- **Seguridad**: Sanitizar cualquier dato del usuario antes de insertarlo en el DOM con `innerHTML` para prevenir ataques XSS. Preferir siempre `textContent`. 