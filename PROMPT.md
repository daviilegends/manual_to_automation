# PROMPT — QA Study Tracker

Construye una página web interactiva completa en un solo archivo `index.html`.
Es un tracker de estudio para aprender JavaScript + Playwright desde cero.
Lee el CLAUDE.md antes de escribir una línea de código.

---

## Lo que debe hacer la página

### Header
- Título: "QA Journey" con subtítulo "De manual tester a automation engineer"
- Progress bar horizontal que muestra % de días completados del total (80 días)
- Heatmap de actividad estilo GitHub: 16 semanas × 5 días = 80 celdas
  - Celda gris oscuro = no completado
  - Celda dorada (#F0A500) = completado
  - Celda con borde blanco = día de hoy (calculado con new Date())
  - Al hacer hover en una celda muestra tooltip "Semana X · Día Y · [título del tema]"

### Navegación lateral izquierda (sticky)
- Lista de las 16 semanas con su nombre y porcentaje de completado
- La semana activa está resaltada
- Click en semana → scroll suave a esa sección

### Contenido principal
16 secciones, una por semana. Cada sección tiene:
- Header de semana: número, título, concepto JS/Playwright, badge de fase
- 5 tarjetas de día, cada una contiene:
  - Número de día y fecha calculada desde el 10 de junio de 2025
  - Título del tema
  - Sección TEORÍA: explicación en español, simple, para alguien sin experiencia
    en programación. Usa analogías del mundo real. Máximo 3 párrafos cortos.
  - Sección EJEMPLO: bloque de código con syntax highlighting básico (spans con colores)
    mostrando el concepto aplicado a SauceDemo o QA real
  - Sección PRÁCTICA: una tarea concreta para hacer ese día ("Abre playcode.io y escribe...")
  - Botón "✓ Completado" — al hacer click cambia a estado completado (verde, ✓ guardado),
    actualiza el heatmap y la progress bar en tiempo real

### Sistema de logros (sidebar derecho o modal)
Al completar una semana entera aparece un badge:
- Semana 1-4: "JS Apprentice", "JS Practitioner", "JS Confident", "JS Ready"
- Semana 5-8: "PW Initiate", "PW Selector", "PW Tester", "PW Confident"
- Semana 9-13: "POM Builder" ×5
- Semana 14-16: "Portfolio Ready" ×3
Badge aparece con animación suave. Se guarda en localStorage.

---

## Contenido de las 16 semanas (genera TODO el contenido)

### FASE 1 — JavaScript esencial (semanas 1–4)

**Semana 1 — Variables y tipos de dato**
- Día 1 (Jun 10): ¿Qué es una variable? const vs let. Analogía: una caja con etiqueta.
- Día 2 (Jun 11): Tipos: string, number, boolean. Cómo JavaScript los diferencia.
- Día 3 (Jun 12): Template literals. Cómo construir texto dinámico con `${}`.
- Día 4 (Jun 13): Operadores básicos: +, -, *, /, ===, !==, &&, ||
- Día 5 (Jun 14): Práctica integradora: script que arma un reporte de QA con variables

**Semana 2 — Funciones**
- Día 6: ¿Qué es una función? Analogía: una receta que se puede reutilizar.
- Día 7: Parámetros y return. Cómo pasar información y recibir un resultado.
- Día 8: Arrow functions. La sintaxis corta que verás en todo Playwright.
- Día 9: Scope: dónde "vive" una variable. Por qué importa en tests.
- Día 10: Práctica: función `login(usuario, password)` que retorna un mensaje

**Semana 3 — Arrays y objetos**
- Día 11: Arrays — qué son, cómo crearlos, cómo acceder por índice.
- Día 12: Métodos de array: map, filter, find. Analogía: filtrar una lista de bugs.
- Día 13: Objetos — pares clave/valor. Un objeto es como un formulario.
- Día 14: Arrays de objetos — la estructura más común en datos de tests.
- Día 15: Práctica: array de productos de SauceDemo, filtrar por precio

**Semana 4 — Async / Await**
- Día 16: ¿Qué es asíncrono? Analogía: pedir comida y esperar sin bloquear la caja.
- Día 17: Promises — qué son, cómo funcionan. .then() y .catch()
- Día 18: async/await — la forma moderna. Por qué TODO Playwright lo usa.
- Día 19: try/catch — manejar errores en código async. Tests que fallan con gracia.
- Día 20: Práctica: función async que "simula" un login con await y maneja el error

### FASE 2 — Playwright desde cero (semanas 5–8)

**Semana 5 — Setup y primer test**
- Día 21: Instalar Node.js y VS Code. Verificar con `node --version`.
- Día 22: `npm init playwright@latest` — crear el proyecto. Qué genera cada archivo.
- Día 23: Estructura del proyecto Playwright. ¿Qué es playwright.config.ts?
- Día 24: Primer test: abrir SauceDemo y verificar el título de la página.
- Día 25: Correr tests con `npx playwright test` y ver el reporte HTML.

**Semana 6 — Selectores**
- Día 26: ¿Qué es un locator? Por qué es la habilidad #1 de Playwright.
- Día 27: getByRole — el selector más robusto. Roles ARIA explicados simple.
- Día 28: getByText, getByLabel, getByPlaceholder — selectores semánticos.
- Día 29: locator() con CSS: #id, .class, [attr]. Cuándo usarlos.
- Día 30: Codegen — grabar un test con el inspector de Playwright.

**Semana 7 — Acciones y assertions**
- Día 31: click(), fill(), press() — las acciones más comunes.
- Día 32: expect().toBeVisible(), toHaveText(), toHaveURL() — cómo verificar.
- Día 33: Assertions en formularios: toHaveValue(), toBeChecked(), toBeEnabled().
- Día 34: Soft assertions — seguir el test aunque falle una verificación.
- Día 35: Práctica: test completo de login en SauceDemo con 3 assertions.

**Semana 8 — Navegación y waits**
- Día 36: page.goto(), page.reload(), page.goBack() — navegar entre páginas.
- Día 37: Waits automáticos de Playwright. Por qué NO usar page.waitForTimeout().
- Día 38: waitForSelector, waitForURL, waitForLoadState — esperas inteligentes.
- Día 39: Screenshots y videos en tests fallidos. Configurar en playwright.config.
- Día 40: Práctica: test de flujo completo login → inventario → verificar productos.

### FASE 3 — Estructura profesional (semanas 9–13)

**Semana 9 — Page Object Model (POM)**
- Día 41: ¿Qué problema resuelve el POM? Test espagueti vs código limpio.
- Día 42: Crear la primera Page Object: LoginPage con sus locators y métodos.
- Día 43: Crear InventoryPage. Cómo las pages se llaman entre sí.
- Día 44: Refactorizar tests existentes para usar las Page Objects.
- Día 45: Práctica: crear CartPage y CheckoutPage para SauceDemo.

**Semana 10 — Fixtures y hooks**
- Día 46: beforeEach y afterEach — setup y limpieza automática.
- Día 47: beforeAll y afterAll — cuándo usarlos (y cuándo NO).
- Día 48: Fixtures de Playwright — reutilizar estado entre tests.
- Día 49: Fixture de login — no repetir el flujo de autenticación en cada test.
- Día 50: Práctica: suite de tests con fixture de login compartido.

**Semana 11 — Datos de prueba**
- Día 51: Data-driven testing — mismo test, múltiples conjuntos de datos.
- Día 52: test.describe y test.step — organizar tests con estructura.
- Día 53: Variables de entorno con .env — nunca hardcodear credenciales.
- Día 54: Faker.js — generar datos dinámicos (nombres, emails, etc.)
- Día 55: Práctica: test parametrizado con múltiples usuarios de SauceDemo.

**Semana 12 — API testing con Playwright**
- Día 56: ¿Qué es una API? REST explicado para QA.
- Día 57: request context en Playwright — hacer llamadas API desde tests.
- Día 58: Combinar API + UI: crear datos por API, verificar en UI.
- Día 59: Interceptar requests con page.route() — simular respuestas.
- Día 60: Práctica: test que verifica consistencia entre API y UI de SauceDemo.

**Semana 13 — CI/CD básico**
- Día 61: ¿Qué es CI/CD? Por qué los tests automáticos necesitan correr solos.
- Día 62: GitHub básico — init, commit, push. Subir el proyecto.
- Día 63: GitHub Actions — crear un workflow que corra tests en cada push.
- Día 64: Playwright en Docker — tests en contenedor (concepto, no implementación).
- Día 65: Allure Reports — instalar y generar reportes visuales del proyecto.

### FASE 4 — Portfolio (semanas 14–16)

**Semana 14 — Pulir el framework**
- Día 66: Code review del proyecto — eliminar código duplicado y magic strings.
- Día 67: Agregar tipos TypeScript explícitos a Page Objects.
- Día 68: Configurar múltiples browsers en playwright.config (Chrome, Firefox, Safari).
- Día 69: Tags de tests: @smoke, @regression — correr subconjuntos.
- Día 70: Práctica: suite @smoke que corre en menos de 2 minutos.

**Semana 15 — README y documentación**
- Día 71: Escribir un README.md profesional. Qué cubre, cómo instalar, cómo correr.
- Día 72: Documentar las Page Objects con JSDoc comments.
- Día 73: Diagrama de arquitectura del framework (texto ASCII o mermaid).
- Día 74: Grabar un video corto del framework corriendo (Loom o similar).
- Día 75: Práctica: README completo listo para mostrar en entrevista.

**Semana 16 — Deploy y showcase**
- Día 76: Publicar Allure Report en GitHub Pages.
- Día 77: Preparar respuestas para preguntas de entrevista sobre el framework.
- Día 78: Conectar el framework con Azure DevOps (concepto del Intelligent Bug Reporter).
- Día 79: Revisión final — correr todos los tests, limpiar el repo.
- Día 80 (Sep 27): ¡Celebración! Resumen de todo lo aprendido. Next steps.

---

## Requisitos técnicos de implementación

### Progress tracking
```javascript
// Estructura en localStorage
const progress = {
  completedDays: [1, 2, 3],          // array de números de día completados
  unlockedBadges: ['JS Apprentice'],  // badges ganados
  lastVisited: '2025-06-10',          // fecha de última visita
  startDate: '2025-06-10'             // siempre fijo
}
```

### Cálculo de fechas
- Día 1 = 10 de junio de 2025 (martes)
- Solo días de semana (lunes a viernes)
- Saltar fines de semana al calcular la fecha de cada día
- Mostrar la fecha en formato "Jun 10" o "10 jun"

### Heatmap
- Grid de 16 columnas (semanas) × 5 filas (días)
- Cada celda es 14×14px con 3px de gap
- Colores: #2C2840 (vacío) → #F0A500 (completado)
- Borde blanco de 1px en el día de hoy
- Tooltip al hover: posicionado con JavaScript, no con CSS title

### Syntax highlighting de código
No usar librerías externas. Hacer resaltado básico con spans:
- Keywords (const, let, async, await, function, return): color ámbar #F0A500
- Strings: color verde #00C49A
- Comentarios: color gris #6666AA
- Funciones: color azul claro #7EC8E3

### Responsive
- Desktop (>1200px): sidebar izquierdo + contenido principal + sidebar derecho (badges)
- Tablet (768-1200px): sidebar colapsable + contenido
- Mobile (<768px): todo en columna, sidebar como menú hamburguesa

### Animaciones
- Marcar día completado: celda del heatmap hace "pop" (scale 1.3 → 1) en 300ms
- Progress bar: transición suave width en 500ms
- Badge desbloqueado: slide-in desde arriba + glow dorado por 2 segundos
- Sin más animaciones — menos es más

---

## Tono del contenido en español

La teoría debe sonar como un amigo experto explicando, NO como documentación técnica.

MALO: "Las variables son contenedores de almacenamiento para valores de datos."
BUENO: "Una variable es como una caja con una etiqueta. Dentro guardas algo — un texto, un número, lo que sea. La etiqueta es el nombre que tú le das."

Cada ejemplo de código debe usar SauceDemo o un contexto de QA real.
Cada tarea práctica debe ser accionable: "Abre playcode.io, escribe esto, cambia X por Y, ve qué pasa."

---

Genera el archivo index.html completo con todo el contenido de las 16 semanas.
