# Prompt para Mejorar el Codigo Base

Copia y pega el contenido del bloque de abajo en un asistente de IA (Claude, ChatGPT)
para obtener un ZIP con el proyecto completo y arrancable.

Si preferis trabajar en tu editor con un agente local (Claude Code, Cursor, Copilot), usa `AGENTS.md` en vez de este archivo: dice lo mismo pero para que escriba los archivos en disco.

## Las dos reglas que no se negocian

1. **Completa el boilerplate.** Todo lo que el proyecto necesita para compilar y arrancar: manifiesto de dependencias, punto de entrada, configuracion, capa de interfaz, y las capas del patron arquitectonico declarado. Eso es andamiaje y es tu trabajo.
2. **NO resuelvas el reto.** Los entregables de las fases son el trabajo de la persona. El hueco pedagogico se deja como esta: el proyecto arranca, pero lo que el reto pide implementar NO esta implementado.

Dicho de otra forma: si algo impide compilar, arreglalo. Si algo es logica de negocio incompleta, validaciones ausentes, un secreto hardcodeado o un patron mejorable, dejalo exactamente como esta — es lo que la persona tiene que encontrar.

## Lo que le falta a este proyecto

Esto NO lo tenes que adivinar: salio de comparar el proyecto contra la arquitectura declarada del reto y de un analisis estatico del codigo. Completalo TODO.

### Boilerplate del stack que falta

Sin esto no compila ni arranca. Es andamiaje, no toca nada de lo pedagogico:

- **Punto de entrada del stack elegido** — Sin un punto de entrada reconocible, el runtime no tiene por donde arrancar la aplicacion.
- **Capa de interfaz (controller/handler)** — Sin una capa de interfaz explicita, no hay forma de invocar la logica de negocio desde afuera del proceso.

### Archivos que la arquitectura del reto declara y no estan

Creálos con implementacion real, en la capa que les corresponde:

- `index.html`

## Como saber que terminaste

```bash
el comando de build o arranque canonico del stack elegido
```

Ese comando corriendo sin errores es la definicion de "listo".

---

```
## Briefing del reto (autoridad)
Este bloque manda sobre los archivos adjuntos. El stack y el rol salen de AQUÍ, no de un topic genérico ni de markdown placeholder.

### Contexto técnico original
Aprendiz TraineeL2 con 3 meses de experiencia en HTML/CSS. Nunca ha construido un layout responsive de verdad, solo copió snippets. Stack: HTML5, CSS3 puro (sin frameworks). Objetivo: entender cuándo usar Flexbox vs Grid, cómo se comportan con breakpoints, y cómo evitar los errores clásicos de collapsing margins. El reto debe forzarlo a decidir la técnica correcta para cada sección de un layout real.

### Reto
- Tema: maquetación responsive con Flexbox y CSS Grid
- Seniority: trainee-l2
- Tipo: practical
- Título: Diseño de layout responsive para una página de producto
- Tiempo estimado: 4 horas

### Fases (trabajo del HUMANO — PROHIBIDO completarlas)
No implementes estos entregables. Dejalos como hueco pedagógico. El asistente solo materializa el proyecto arrancable para que el participante pueda trabajar.
- Fase 1: Diseño de la cabecera — objetivo: Crear una cabecera responsive que se ajuste a diferentes tamaños de pantalla. — entregable (NO resolver): Código HTML y CSS para la cabecera responsive.
- Fase 2: Diseño de la sección principal — objetivo: Crear una sección principal responsive que muestre productos relacionados. — entregable (NO resolver): Código HTML y CSS para la sección principal responsive.
- Fase 3: Diseño del pie de página — objetivo: Crear un pie de página responsive que se ajuste a diferentes tamaños de pantalla. — entregable (NO resolver): Código HTML y CSS para el pie de página responsive.

Eres un asistente experto en análisis, corrección y generación de archivos de cualquier tipo:
código fuente, documentación, hojas de cálculo, documentos Word, configuraciones, entre otros.
Voy a enviarte una cadena de texto que contiene uno o más archivos. Cada archivo está delimitado por un marcador con el siguiente formato:
// === ARCHIVO: ruta/del/archivo.extension ===
o también puede aparecer como:
## === ARCHIVO: ruta/del/archivo.extension ===
Lo que sigue al marcador puede ser:

El contenido real del archivo (código, texto, YAML, etc.)
Una descripción en lenguaje natural de lo que debe contener el archivo


TU TAREA
PASO 0 — ¿Esto es un proyecto o una carcasa?
Antes de extraer archivos, leé el Briefing (si está) y diagnosticá el adjunto.

Es CARCASA si ocurre CUALQUIERA de estas:
- No hay manifiesto de dependencias del stack del briefing (manifest.json de VTEX IO / package.json / pom.xml / build.gradle / requirements.txt / go.mod / *.tf / *.csproj, según corresponda)
- Hay un "binario" que en realidad es un comentario ("no puede ser mostrado como texto plano", placeholder .fig/.docx vacío)
- Los markdowns ya completan entregables de fases posteriores ("se implementó fade-in", lista de áreas ya resuelta)

Si es CARCASA:
- MATERIALIZÁ un proyecto que arranca en el stack del briefing (VTEX IO Store Framework, Angular, Terraform, pytest, Nest, etc.). Incluí manifiesto, punto de entrada y capa de interfaz reales.
- NO copies los markdowns de "solución" como si fueran el producto. Son ruido de generación.
- NO resuelvas las fases del briefing (están marcadas PROHIBIDO). Dejá el hueco pedagógico: el flujo existe, las microinteracciones/calidad/infra que el reto pide NO están hechas.
- Después seguí al PASO 5 (ZIP).

Si es un proyecto REAL (manifiesto + código que compila o arranca):
- Seguí PASO 1 en adelante. 🔴 compilación sí. 🟡 pedagógico no.

PASO 1 — Detección y extracción
Identifica todos los archivos presentes en la cadena. Para cada archivo extrae:

Su ruta completa (ej: src/main/java/com/pragma/Service.java)
Su contenido o descripción

PASO 2 — Clasificación por tipo
Clasifica cada archivo en una de estas categorías:
A) Código fuente (Java, Python, TypeScript, JavaScript, Kotlin, etc.)
B) Configuración / documentación (YAML, properties, Markdown, JSON, txt, etc.)
C) Excel (.xlsx, .xls, .csv)
D) Word (.docx, .doc)
E) Otro tipo de archivo binario o especial
PASO 3 — Clasificación de errores en código fuente

Objetivo prioritario: que el proyecto compile. No corrijas flujo de negocio ni lógica funcional.

Antes de modificar cualquier archivo de código fuente, clasifica cada problema encontrado en una de estas dos categorías:
🔴 ERROR DE COMPILACIÓN — corregir siempre
Son errores que impiden que el proyecto arranque, sin valor pedagógico:

Import faltante o incorrecto
Clase, método o variable referenciada que no existe en ningún archivo del proyecto
Error de sintaxis
Anotación con atributos inválidos
Dependencia ausente en pom.xml, package.json, etc.
Archivo referenciado que no existe y debe ser creado con implementación mínima

→ CORREGIR estos errores.
🟡 PROBLEMA FUNCIONAL O DE CALIDAD — preservar siempre
Son problemas que no impiden compilar. Pueden ser intencionales para el aprendizaje:

Clave secreta hardcodeada ("secret", "password123")
API deprecada que funciona pero tiene reemplazo moderno
Lógica de negocio incorrecta o incompleta
Código redundante o de baja legibilidad
Falta de validaciones en flujo de negocio
Patrones de diseño incorrectos pero funcionales
Concurrencia no segura
Configuración funcional pero no óptima

→ PRESERVAR tal cual. No corregir, no mejorar, no comentar.
PASO 4 — Procesamiento según tipo de archivo
Tipo A — Código fuente
Aplica únicamente las correcciones clasificadas como 🔴 ERROR DE COMPILACIÓN.
No alteres ningún elemento clasificado como 🟡 PROBLEMA FUNCIONAL O DE CALIDAD.
Si falta un archivo referenciado, créalo con la implementación mínima necesaria para compilar.
Tipo B — Configuración / documentación
Extrae el contenido tal cual, sin modificaciones salvo errores evidentes de sintaxis
(ej: YAML mal indentado).
Tipo C — Excel (.xlsx)
Si viene con contenido real, genera el archivo respetando ese contenido.
Si viene con descripción en lenguaje natural, genera un archivo Excel funcional con:

Fila de encabezados en negrita con color de fondo distintivo
Columnas con ancho ajustado al contenido
Tipos de dato correctos por columna
Validaciones si la descripción lo indica
Hojas nombradas descriptivamente si hay más de una
Filas de ejemplo si no hay datos reales

Tipo D — Word (.docx)
Si viene con contenido real, genera el archivo respetando ese contenido.
Si viene con descripción en lenguaje natural, genera un documento Word funcional con:

Estilos de título (Título 1, Título 2) para jerarquía de secciones
Fuente legible (Calibri o equivalente), tamaño 11-12pt para cuerpo
Márgenes estándar
Tabla de contenido si tiene múltiples secciones
Tablas con encabezados en negrita si aplica

Tipo E — Otro
Genera el archivo con el contenido o estructura más apropiada según la descripción.
PASO 5 — Exportación en ZIP
Empaqueta todos los archivos en un único archivo ZIP descargable respetando exactamente
la estructura de rutas indicada por los marcadores.
El ZIP debe incluir:

Archivos de código con únicamente los errores de compilación corregidos
Archivos de configuración y documentación sin cambios
Archivos nuevos creados para resolver dependencias de compilación faltantes
Archivos Excel y Word generados desde descripción

IMPORTANTE: El ZIP debe estar listo para descargar al finalizar. No preguntes si el usuario
quiere generarlo. Simplemente genera el archivo y proporciona el enlace de descarga; No debes desplegar en el chat el resumen de lo que arreglaste al Zip, solo entregalo.

REGLAS IMPORTANTES

No omitas ningún archivo aunque no tenga errores ni modificaciones
Respeta los nombres y rutas exactas indicadas por los marcadores
Si un archivo no tiene marcador claro, infiere el nombre desde su contenido
Si la cadena contiene solo documentación, placeholders o binarios fake, NO la reproduzcas:
aplicá PASO 0 (materializar el proyecto del briefing). Reproducir la carcasa es un fallo.
No agregues texto después del enlace de descarga del ZIP
No preguntes si el usuario quiere el ZIP: simplemente generalo siempre
Si detectas que falta un archivo de configuración necesario para compilar
(pom.xml, package.json, requirements.txt, build.gradle, etc.), créalo e inclúyelo
inferiendo su contenido desde los imports y frameworks detectados en el código
Nunca corrijas problemas 🟡 aunque parezcan obvios o fáciles de mejorar.
El participante que recibirá este proyecto los debe encontrar y resolver él mismo.


INPUT
Aquí está la cadena con los archivos:

// === ARCHIVO: package.json ===
{
  "name": "responsive-product-page",
  "version": "1.0.0",
  "description": "Diseño de layout responsive para una página de producto de tienda en línea con Flexbox y CSS Grid",
  "main": "index.html",
  "scripts": {
    "start": "npx serve .",
    "dev": "npx serve . -l 3000",
    "test:css": "npx stylelint 'css/**/*.css' --fix",
    "lint": "npx stylelint 'css/**/*.css'",
    "build:css": "echo 'CSS build complete'"
  },
  "keywords": [
    "responsive",
    "flexbox",
    "css-grid",
    "layout",
    "html5",
    "css3"
  ],
  "author": "Equipo de Desarrollo",
  "license": "MIT",
  "repository": {
    "type": "git",
    "url": "https://github.com/example/responsive-product-page"
  },
  "bugs": {
    "url": "https://github.com/example/responsive-product-page/issues"
  },
  "homepage": "https://github.com/example/responsive-product-page#readme",
  "dependencies": {
    "normalize.css": "^8.0.1"
  },
  "devDependencies": {
    "stylelint": "^15.10.0",
    "stylelint-config-standard": "^33.0.0",
    "stylelint-config-recommended": "^12.0.0"
  },
  "browserslist": [
    "> 1%",
    "last 2 versions",
    "not dead",
    "not ie 11"
  ],
  "engines": {
    "node": ">=14.0.0",
    "npm": ">=6.0.0"
  },
  "stylelint": {
    "extends": [
      "stylelint-config-standard",
      "stylelint-config-recommended"
    ],
    "rules": {
      "color-no-invalid-hex": true,
      "font-family-no-duplicate-names": true,
      "no-descending-specificity": null,
      "selector-class-pattern": "^[a-z][a-zA-Z0-9]*(-[a-z][a-zA-Z0-9]*)*$",
      "selector-id-pattern": "^[a-z][a-zA-Z0-9]*(-[a-z][a-zA-Z0-9]*)*$",
      "property-no-vendor-prefix": true,
      "block-no-empty": true,
      "declaration-block-trailing-semicolon": "always"
    }
  }
}

// === ARCHIVO: tests/responsive-tests.html ===
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Pruebas de Responsividad - Página de Producto</title>
  <link rel="stylesheet" href="../css/reset.css">
  <link rel="stylesheet" href="../css/styles.css">
  <style>
    body { font-family: Arial, sans-serif; padding: 20px; background: #f5f5f5; }
    .test-suite { max-width: 1200px; margin: 0 auto; }
    .test-header { background: #2c3e50; color: white; padding: 20px; border-radius: 8px; margin-bottom: 20px; }
    .test-header h1 { margin: 0; font-size: 24px; }
    .test-case { background: white; border-radius: 8px; padding: 20px; margin-bottom: 20px; box-shadow: 0 2px 4px rgba(0,0,0,0.1); }
    .test-case h2 { color: #34495e; margin-top: 0; border-bottom: 2px solid #3498db; padding-bottom: 10px; }
    .breakpoint-label { display: inline-block; padding: 4px 12px; border-radius: 4px; font-weight: bold; font-size: 14px; margin-right: 10px; margin-bottom: 10px; }
    .breakpoint-mobile { background: #e74c3c; color: white; }
    .breakpoint-tablet { background: #f39c12; color: white; }
    .breakpoint-desktop { background: #27ae60; color: white; }
    .test-description { color: #7f8c8d; margin: 10px 0; }
    .test-assertion { background: #ecf0f1; padding: 15px; border-radius: 4px; margin: 10px 0; border-left: 4px solid #3498db; }
    .test-assertion.pass { border-left-color: #27ae60; background: #d5f4e6; }
    .test-assertion.fail { border-left-color: #e74c3c; background: #fadbd8; }
    .test-assertion h4 { margin: 0 0 10px 0; color: #2c3e50; }
    .test-assertion ul { margin: 0; padding-left: 20px; }
    .test-assertion li { margin: 5px 0; }
    .visual-check { display: flex; flex-wrap: wrap; gap: 10px; margin: 15px 0; }
    .visual-check-item { flex: 1 1 calc(33.333% - 10px); min-width: 200px; background: #f8f9fa; padding: 10px; border-radius: 4px; text-align: center; }
    .visual-check-item span { display: block; font-weight: bold; color: #2c3e50; }
    .visual-check-item small { color: #7f8c8d; }
    .test-results { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 15px; margin-top: 20px; }
    .result-card { background: white; padding: 15px; border-radius: 8px; text-align: center; box-shadow: 0 2px 4px rgba(0,0,0,0.1); }
    .result-card.passed { border-top: 4px solid #27ae60; }
    .result-card.failed { border-top: 4px solid #e74c3c; }
    .result-card .status { font-size: 24px; font-weight: bold; }
    .result-card.passed .status { color: #27ae60; }
    .result-card.failed .status { color: #e74c3c; }
    .breakpoint-controls { margin: 20px 0; }
    .breakpoint-controls button { padding: 10px 20px; margin-right: 10px; border: none; border-radius: 4px; cursor: pointer; font-weight: bold; }
    .breakpoint-controls button:hover { opacity: 0.8; }
    .btn-mobile { background: #e74c3c; color: white; }
    .btn-tablet { background: #f39c12; color: white; }
    .btn-desktop { background: #27ae60; color: white; }
    .test-details { background: #f8f9fa; padding: 15px; border-radius: 4px; margin-top: 10px; }
    .test-details code { background: #2c3e50; color: #ecf0f1; padding: 2px 6px; border-radius: 3px; font-size: 13px; }
  </style>
</head>
<body>
  <div class="test-suite">
    <div class="test-header">
      <h1>🧪 Suite de Pruebas de Responsividad</h1>
      <p>Casos de prueba para validar el diseño responsive de la página de producto</p>
    </div>

    <div class="breakpoint-controls">
      <p><strong>Simular breakpoint:</strong></p>
      <button class="btn-mobile" onclick="setViewport(375, 667)">📱 Mobile (375px)</button>
      <button class="btn-tablet" onclick="setViewport(768, 1024)">📱 Tablet (768px)</button>
      <button class="btn-desktop" onclick="setViewport(1280, 800)">💻 Desktop (1280px)</button>
    </div>

    <div class="test-case">
      <h2>TC-001: Cabecera Responsive</h2>
      <span class="breakpoint-label breakpoint-mobile">Mobile</span>
      <span class="breakpoint-label breakpoint-tablet">Tablet</span>
      <span class="breakpoint-label breakpoint-desktop">Desktop</span>
      <p class="test-description">Validar que la cabecera se adapta correctamente a todos los tamaños de pantalla.</p>
      
      <div class="test-assertion pass">
        <h4>✅ ASSERT-001: Logo visible en móvil</h4>
        <ul>
          <li>El logo debe ser visible sin necesidad de scroll horizontal</li>
          <li>El tamaño del logo debe ser apropiado (entre 100px y 150px de ancho)</li>
          <li>Verificar con: <code>document.querySelector('.logo').offsetWidth</code></li>
        </ul>
      </div>

      <div class="test-assertion pass">
        <h4>✅ ASSERT-002: Navegación en móvil</h4>
        <ul>
          <li>Los elementos de navegación deben ser accesibles</li>
          <li>El menú puede colapsarse en un botón hamburguesa</li>
          <li>Los enlaces deben tener un tamaño mínimo de toque de 44x44px</li>
        </ul>
      </div>

      <div class="visual-check">
        <div class="visual-check-item">
          <span>✓ Logo visible</span>
          <small>TC-001-01</small>
        </div>
        <div class="visual-check-item">
          <span>✓ Menú accesible</span>
          <small>TC-001-02</small>
        </div>
        <div class="visual-check-item">
          <span>✓ Sin overflow</span>
          <small>TC-001-03</small>
        </div>
      </div>
    </div>

    <div class="test-case">
      <h2>TC-002: Grid de Productos - Flexbox vs CSS Grid</h2>
      <span class="breakpoint-label breakpoint-mobile">Mobile</span>
      <span class="breakpoint-label breakpoint-tablet">Tablet</span>
      <span class="breakpoint-label breakpoint-desktop">Desktop</span>
      <p class="test-description">Validar que el grid de productos usa la técnica correcta según el patrón arquitectónico.</p>

      <div class="test-assertion pass">
        <h4>✅ ASSERT-003: Layout unidimensional con Flexbox</h4>
        <ul>
          <li>La navegación principal debe usar Flexbox para distribución horizontal</li>
          <li>Los elementos del menú deben distribuirse uniformemente</li>
          <li>Verificar con: <code>getComputedStyle(nav).display === 'flex'</code></li>
        </ul>
      </div>

      <div class="test-assertion pass">
        <h4>✅ ASSERT-004: Layout bidimensional con CSS Grid</h2>
        <ul>
          <li>La sección de productos relacionados debe usar CSS Grid</li>
          <li>El grid debe tener columnas responsivas que se ajusten al breakpoint</li>
          <li>Verificar con: <code>getComputedStyle(grid).display === 'grid'</code></li>
        </ul>
      </div>

      <div class="test-assertion pass">
        <h4>✅ ASSERT-005: Breakpoints de grid</h4>
        <ul>
          <li>Mobile: 1 columna (100% ancho)</li>
          <li>Tablet: 2 columnas (50% cada una)</li>
          <li>Desktop: 3-4 columnas (25-33% cada una)</li>
        </ul>
      </div>

      <div class="visual-check">
        <div class="visual-check-item">
          <span>✓ Flexbox en nav</span>
          <small>TC-002-01</small>
        </div>
        <div class="visual-check-item">
          <span>✓ Grid en productos</span>
          <small>TC-002-02</small>
        </div>
        <div class="visual-check-item">
          <span>✓ Breakpoints OK</span>
          <small>TC-002-03</small>
        </div>
      </div>
    </div>

    <div class="test-case">
      <h2>TC-003: Pie de Página Responsive</h2>
      <span class="breakpoint-label breakpoint-mobile">Mobile</span>
      <span class="breakpoint-label breakpoint-tablet">Tablet</span>
      <span class="breakpoint-label breakpoint-desktop">Desktop</span>
      <p class="test-description">Validar que el footer se adapta correctamente manteniendo la legibilidad.</p>

      <div class="test-assertion pass">
        <h4>✅ ASSERT-006: Distribución de columnas</h4>
        <ul>
          <li>Mobile: columnas apiladas verticalmente</li>
          <li>Tablet: 2 columnas</li>
          <li>Desktop: 3-4 columnas en fila</li>
        </ul>
      </div>

      <div class="test-assertion pass">
        <h4>✅ ASSERT-007: Espaciado consistente</h4>
        <ul>
          <li>El padding debe ser suficiente (mínimo 16px)</li>
          <li>Los enlaces deben tener área de toque adecuada</li>
          <li>El texto debe ser legible sin zoom</li>
        </ul>
      </div>

      <div class="visual-check">
        <div class="visual-check-item">
          <span>✓ Columnas apiladas</span>
          <small>TC-003-01</small>
        </div>
        <div class="visual-check-item">
          <span>✓ Espaciado OK</span>
          <small>TC-003-02</small>
        </div>
        <div class="visual-check-item">
          <span>✓ Links accesibles</span>
          <small>TC-003-03</small>
        </div>
      </div>
    </div>

    <div class="test-case">
      <h2>TC-004: Errores Comunes de CSS</h2>
      <p class="test-description">Validar que se evitan los errores clásicos de maquetación.</p>

      <div class="test-assertion pass">
        <h4>✅ ASSERT-008: Collapsing margins</h4>
        <ul>
          <li>Verificar que los márgenes colapsan correctamente entre elementos</li>
          <li>El header debe tener separación clara del contenido principal</li>
          <li>Usar padding o overflow: hidden en contenedores cuando sea necesario</li>
        </ul>
      </div>

      <div class="test-assertion pass">
        <h4>✅ ASSERT-009: Altura de contenedores</h4>
        <ul>
          <li>Los contenedores flex/grid deben tener altura correcta</li>
          <li>Verificar con: <code>element.offsetHeight > 0</code></li>
          <li>El contenido no debe desbordar fuera del contenedor padre</li>
        </ul>
      </div>

      <div class="test-assertion pass">
        <h4>✅ ASSERT-010: Imágenes responsive</h4>
        <ul>
          <li>Las imágenes no deben exceder el ancho de su contenedor</li>
          <li>Usar max-width: 100% y height: auto</li>
          <li>Verificar: <code>img.naturalWidth <= img.parentElement.offsetWidth</code></li>
        </ul>
      </div>

      <div class="test-details">
        <strong>CSS Reset aplicado:</strong> normalize.css v8.0.1 está incluido para eliminar inconsistencias entre navegadores.
      </div>
    </div>

    <div class="test-case">
      <h2>📊 Resumen de Resultados</h2>
      <div class="test-results">
        <div class="result-card passed">
          <div class="status">✓ PASÓ</div>
          <p>TC-001: Cabecera</p>
          <small>3 assertions</small>
        </div>
        <div class="result-card passed">
          <div class="status">✓ PASÓ</div>
          <p>TC-002: Grid Productos</p>
          <small>3 assertions</small>
        </div>
        <div class="result-card passed">
          <div class="status">✓ PASÓ</div>
          <p>TC-003: Pie de Página</p>
          <small>2 assertions</small>
        </div>
        <div class="result-card passed">
          <div class="status">✓ PASÓ</div>
          <p>TC-004: Errores Comunes</p>
          <small>3 assertions</small>
        </div>
      </div>
    </div>
  </div>

  <script>
    function setViewport(width, height) {
      const meta = document.querySelector('meta[name="viewport"]');
      meta.setAttribute('content', `width=${width}, initial-scale=1.0`);
      console.log(`📱 Viewport simulado: ${width}x${height}px`);
      alert(`Viewport cambiado a ${width}x${height}px. Actualiza la página para ver los cambios.`);
    }

    function runVisualTests() {
      const results = [];
      
      // Test 1: Logo existe y es visible
      const logo = document.querySelector('.logo');
      results.push({ test: 'Logo visible', pass: !!logo });
      
      // Test 2: Navegación usa Flexbox
      const nav = document.querySelector('nav');
      if (nav) {
        const navStyle = getComputedStyle(nav);
        results.push({ test: 'Nav usa Flexbox', pass: navStyle.display === 'flex' });
      }
      
      // Test 3: Grid de productos
      const productGrid = document.querySelector('.product-grid, .products-grid, [class*="grid"]');
      if (productGrid) {
        const gridStyle = getComputedStyle(productGrid);
        results.push({ test: 'Grid usa CSS Grid', pass: gridStyle.display === 'grid' });
      }
      
      // Test 4: Footer existe
      const footer = document.querySelector('footer');
      results.push({ test: 'Footer presente', pass: !!footer });
      
      // Test 5: Imágenes tienen max-width
      const images = document.querySelectorAll('img');
      images.forEach((img, i) => {
        const fits = img.naturalWidth <= img.offsetWidth || img.style.maxWidth === '100%';
        results.push({ test: `Imagen ${i+1} responsive`, pass: fits });
      });
      
      console.table(results);
      return results;
    }

    console.log('🧪 Suite de pruebas de responsividad cargada');
    console.log('Ejecutar runVisualTests() para validar el diseño');
  </script>
</body>
</html>

// === ARCHIVO: tests/visual-comparison.md ===
# Documento de Casos de Prueba Visuales

## Diseño Responsive - Página de Producto

Este documento describe los casos de prueba visuales para validar la consistencia del diseño en diferentes dispositivos y breakpoints.

---

## 1. Resumen de la Estrategia de Pruebas

### 1.1 Objetivos

- Validar que el diseño se adapta correctamente a cada breakpoint
- Verificar el uso correcto de Flexbox y CSS Grid según el contexto
- Detectar errores visuales comunes (overflow, márgenes colapsados, etc.)
- Asegurar consistencia en todos los navegadores objetivo

### 1.2 Breakpoints Definidos

| Breakpoint | Ancho | Dispositivos | columns Grid |
|------------|-------|--------------|--------------|
| Mobile     | < 768px | Teléfonos inteligentes | 1 columna |
| Tablet     | 768px - 1024px | Tablets | 2 columnas |
| Desktop    | > 1024px | Computadoras | 3-4 columnas |

---

## 2. Casos de Prueba por Componente

### 2.1 TC-CAB-001: Cabecera (Header)

**Descripción**: Validar que la cabecera se muestra correctamente en todos los breakpoints.

**Criterios de Aceptación**:

- El logo es visible y no se corta
- La navegación es accesible y funcional
- No hay scroll horizontal
- El alto de la cabecera es apropiado (60-80px en desktop)
- En móvil, el menú puede colapsarse en botón hamburguesa

**Pasos de Verificación**:

1. Abrir la página en cada breakpoint
2. Verificar que el logo es visible sin necesidad de scroll
3. Confirmar que los elementos de navegación son tocables (44x44px mínimo)
4. Comprobar que no hay overflow horizontal

**Resultado Esperado**: La cabecera se muestra completa y funcional en todos los tamaños.

---

### 2.2 TC-CAB-002: Logo en Diferentes Tamaños

| Escenario | Ancho Viewport | Tamaño Esperado Logo |
|-----------|----------------|----------------------|
| Mobile    | 375px          | 100-120px            |
| Tablet    | 768px          | 120-140px            |
| Desktop   | 1280px         | 140-180px            |

**Validación Visual**:

- El logo nunca debe exceder el ancho del contenedor
- La proporción del logo debe mantenerse
- El texto del logo debe ser legible

---

### 2.3 TC-MAIN-001: Grid de Productos (CSS Grid)

**Descripción**: Validar que la sección de productos relacionados usa CSS Grid correctamente.

**Criterios de Aceptación**:

- El contenedor de productos usa `display: grid`
- Las columnas se ajustan automáticamente según el breakpoint
- El espaciado entre productos es consistente
- Las tarjetas de productos tienen el mismo ancho

**Verificación Técnica**:

```javascript
const grid = document.querySelector('.product-grid');
const style = getComputedStyle(grid);
console.log(style.display); // Debe ser 'grid'
```

**Layout Esperado**:

```
Mobile (< 768px):
┌─────────────┐
│  Producto 1 │
├─────────────┤
│  Producto 2 │
├─────────────┤
│  Producto 3 │
└─────────────┘

Tablet (768-1024px):
┌─────────────┬─────────────┐
│  Producto 1 │  Producto 2 │
├─────────────┼─────────────┤
│  Producto 3 │  Producto 4 │
└─────────────┴─────────────┘

Desktop (> 1024px):
┌──────────┬──────────┬──────────┬──────────┐
│ Producto │ Producto │ Producto │ Producto │
│    1     │    2     │    3     │    4     │
└──────────┴──────────┴──────────┴──────────┘
```

---

### 2.4 TC-MAIN-002: Navegación Principal (Flexbox)

**Descripción**: Validar que la navegación usa Flexbox para distribución horizontal.

**Criterios de Aceptación**:

- El menú de navegación usa `display: flex`
- Los elementos se distribuyen uniformemente
- El espaciado entre enlaces es consistente
- En móvil, los elementos pueden colapsarse

**Verificación Técnica**:

```javascript
const nav = document.querySelector('nav');
const style = getComputedStyle(nav);
console.log(style.display); // Debe ser 'flex'
console.log(style.flexDirection); // 'row' en desktop
```

---

### 2.5 TC-FOOT-001: Pie de Página (Footer)

**Descripción**: Validar que el footer se adapta correctamente a cada breakpoint.

**Criterios de Aceptación**:

- Mobile: columnas apiladas verticalmente
- Tablet: 2 columnas
- Desktop: 3-4 columnas en fila horizontal
- Los enlaces son tocables (mínimo 44x44px)
- El texto es legible sin zoom

**Distribución Esperada**:

```
Mobile:
┌──────────────┐
│  Columna 1   │
├──────────────┤
│  Columna 2   │
├──────────────┤
│  Columna 3   │
└──────────────┘

Desktop:
┌──────────┬──────────┬──────────┐
│ Columna 1│ Columna 2│ Columna 3│
└──────────┴──────────┴──────────┘
```

---

## 3. Validación de Errores Comunes

### 3.1 Collapsing Margins

**Problema**: Los márgenes superiores e inferiores pueden colapsar entre elementos block.

**Solución Implementada**: Usar padding en lugar de margin, o `overflow: hidden` en contenedores.

**Verificación**:

- El espacio entre header y contenido principal es consistente
- No hay duplicación de márgenes
- Los elementos dentro de contenedores tienen espaciado correcto

### 3.2 Overflow Horizontal

**Problema**: Elementos que exceden el ancho del viewport causando scroll horizontal.

**Verificación**:

```javascript
const body = document.body;
const hasOverflow = body.scrollWidth > window.innerWidth;
console.log('Overflow horizontal:', hasOverflow);
```

### 3.3 Imágenes que Exceden Contenedor

**Problema**: Imágenes con ancho fijo que exceden el contenedor en responsive.

**Solución**: Usar `max-width: 100%` y `height: auto` en todas las imágenes.

**Verificación**:

```javascript
const images = document.querySelectorAll('img');
images.forEach(img => {
  const fits = img.offsetWidth <= img.parentElement.offsetWidth;
  console.log('Imagen ajusta:', fits);
});
```

---

## 4. Matriz de Compatibilidad

### 4.1 Navegadores Objetivo

| Navegador | Versión Mínima | Soporte |
|-----------|----------------|---------|
| Chrome    | 90+            | ✓       |
| Firefox   | 88+            | ✓       |
| Safari    | 14+            | ✓       |
| Edge      | 90+            | ✓       |

### 4.2 Dispositivos de Prueba

| Dispositivo | Resolución | Breakpoint | Validar |
|-------------|------------|------------|---------|
| iPhone SE   | 375x667    | Mobile     | Layout  |
| iPhone 12   | 390x844    | Mobile     | Layout  |
| iPad Mini   | 768x1024   | Tablet     | Grid    |
| iPad Pro    | 1024x1366  | Desktop    | Grid    |
| MacBook     | 1440x900   | Desktop    | Full    |
| PC Windows  | 1920x1080  | Desktop    | Full    |

---

## 5. Checklist de Verificación Visual

### 5.1 Antes de Lanzar

- [ ] Todas las pruebas de breakpoints pasan
- [ ] No hay scroll horizontal en ningún dispositivo
- [ ] Las imágenes cargan correctamente
- [ ] Los colores ytipografía son consistentes
- [ ] Los botones y enlaces son tocables (44x44px)
- [ ] El diseño es accesible (contraste suficiente)
- [ ] No hay errores en la consola del navegador

### 5.2 Herramientas Recomendadas

- Chrome DevTools (Device Mode)
- Firefox Responsive Design Mode
- BrowserStack o Sauce Labs
- Lighthouse para accesibilidad

---

## 6. Glosario de Términos

| Término | Definición |
|---------|------------|
| Breakpoint | Punto de cambio en el diseño responsive |
| Flexbox | Modelo de diseño unidimensional |
| CSS Grid | Modelo de diseño bidimensional |
| Viewport | Área visible de la página web |
| Collapsing Margins | Comportamiento donde márgenes adyacentes se fusionan |

---

*Documento generado para el proyecto de maquetación responsive con Flexbox y CSS Grid*
*Versión: 1.0.0*


// === ARCHIVO: images/logo.png ===
<svg xmlns="http://www.w3.org/2000/svg" width="400" height="200" viewBox="0 0 400 200">
  <defs>
    <linearGradient id="logoGradient" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#2c3e50;stop-opacity:1" />
      <stop offset="100%" style="stop-color:#3498db;stop-opacity:1" />
    </linearGradient>
    <filter id="shadow" x="-20%" y="-20%" width="140%" height="140%">
      <feDropShadow dx="2" dy="2" stdDeviation="3" flood-color="#000000" flood-opacity="0.3"/>
    </filter>
  </defs>
  <rect width="400" height="200" fill="#ecf0f1"/>
  <g filter="url(#shadow)">
    <rect x="30" y="50" width="100" height="100" rx="10" fill="url(#logoGradient)"/>
    <text x="80" y="105" font-family="Arial, sans-serif" font-size="48" font-weight="bold" fill="white" text-anchor="middle">S</text>
  </g>
  <text x="150" y="85" font-family="Arial, sans-serif" font-size="32" font-weight="bold" fill="#2c3e50">ShopTech</text>
  <text x="150" y="115" font-family="Arial, sans-serif" font-size="16" fill="#7f8c8d">Tu tienda online de confianza</text>
  <g stroke="#3498db" stroke-width="2" fill="none">
    <path d="M 150 130 L 370 130"/>
    <path d="M 150 135 L 370 135"/>
  </g>
  <circle cx="320" cy="150" r="20" fill="none" stroke="#e74c3c" stroke-width="2"/>
  <circle cx="320" cy="150" r="12" fill="none" stroke="#e74c3c" stroke-width="2"/>
  <circle cx="320" cy="150" r="4" fill="#e74c3c"/>
  <text x="340" y="155" font-family="Arial, sans-serif" font-size="12" fill="#95a5a6">carrito</text>
  <g fill="#95a5a6" font-family="Arial, sans-serif" font-size="10">
    <text x="45" y="170">Navegación</text>
    <text x="95" y="170">Productos</text>
    <text x="155" y="170">Ofertas</text>
    <text x="205" y="170">Contacto</text>
  </g>
</svg>

// === ARCHIVO: images/product1.jpg ===
<svg xmlns="http://www.w3.org/2000/svg" width="600" height="600" viewBox="0 0 600 600">
  <defs>
    <linearGradient id="productBg" x1="0%" y1="0%" x2="0%" y2="100%">
      <stop offset="0%" style="stop-color:#f5f7fa;stop-opacity:1" />
      <stop offset="100%" style="stop-color:#c3cfe2;stop-opacity:1" />
    </linearGradient>
    <linearGradient id="productHighlight" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#667eea;stop-opacity:1" />
      <stop offset="100%" style="stop-color:#764ba2;stop-opacity:1" />
    </linearGradient>
    <filter id="productShadow" x="-30%" y="-30%" width="160%" height="160%">
      <feDropShadow dx="5" dy="5" stdDeviation="8" flood-color="#000000" flood-opacity="0.25"/>
    </filter>
  </defs>
  <rect width="600" height="600" fill="url(#productBg)"/>
  <g filter="url(#productShadow)">
    <rect x="100" y="80" width="400" height="320" rx="15" fill="white"/>
    <rect x="100" y="80" width="400" height="40" rx="15" fill="url(#productHighlight)"/>
    <rect x="100" y="105" width="400" height="15" fill="url(#productHighlight)"/>
  </g>
  <g transform="translate(150, 140)">
    <rect x="0" y="0" width="300" height="200" rx="10" fill="#ecf0f1"/>
    <ellipse cx="150" cy="100" rx="80" ry="60" fill="#bdc3c7"/>
    <ellipse cx="150" cy="120" rx="100" ry="40" fill="#95a5a6"/>
    <rect x="80" y="60" width="140" height="80" rx="5" fill="#7f8c8d"/>
    <circle cx="130" cy="90" r="15" fill="#34495e"/>
    <circle cx="170" cy="90" r="15" fill="#34495e"/>
    <circle cx="150" cy="110" r="8" fill="#2c3e50"/>
    <rect x="110" y="130" width="80" height="10" rx="2" fill="#2c3e50"/>
    <circle cx="110" cy="170" r="20" fill="#e74c3c" opacity="0.8"/>
    <text x="110" y="176" font-family="Arial" font-size="20" fill="white" text-anchor="middle">-</text>
    <circle cx="190" cy="170" r="20" fill="#27ae60" opacity="0.8"/>
    <text x="190" y="176" font-family="Arial" font-size="20" fill="white" text-anchor="middle">+</text>
  </g>
  <text x="300" y="380" font-family="Arial" font-size="24" font-weight="bold" fill="#2c3e50" text-anchor="middle">Smartphone Pro X</text>
  <text x="300" y="410" font-family="Arial" font-size="18" fill="#7f8c8d" text-anchor="middle">Último modelo con pantalla OLED</text>
  <text x="300" y="440" font-family="Arial" font-size="28" font-weight="bold" fill="#e74c3c" text-anchor="middle">$899.99</text>
  <text x="300" y="460" font-family="Arial" font-size="14" fill="#27ae60" text-anchor="middle">✓ Envío gratis</text>
  <g transform="translate(180, 480)">
    <rect x="0" y="0" width="240" height="50" rx="25" fill="url(#productHighlight)"/>
    <text x="120" y="32" font-family="Arial" font-size="18" font-weight="bold" fill="white" text-anchor="middle">Añadir al carrito</text>
  </g>
  <g fill="#f39c12" font-family="Arial" font-size="20">
    <text x="140" y="560">★</text>
    <text x="160" y="560">★</text>
    <text x="180" y="560">★</text>
    <text x="200" y="560">★</text>
    <text x="220" y="560">★</text>
  </g>
  <text x="280" y="560" font-family="Arial" font-size="14" fill="#7f8c8d">(128 reseñas)</text>
</svg>

// === ARCHIVO: css/reset.css ===
/* CSS Reset - Base styles for consistent cross-browser rendering */
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html {
  font-size: 16px;
  line-height: 1.5;
  -webkit-text-size-adjust: 100%;
}

body {
  min-height: 100vh;
  text-rendering: optimizeLegibility;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

img, picture, video, canvas, svg {
  display: block;
  max-width: 100%;
  height: auto;
}

input, button, textarea, select {
  font: inherit;
  color: inherit;
}

p, h1, h2, h3, h4, h5, h6 {
  overflow-wrap: break-word;
}

a {
  text-decoration: none;
  color: inherit;
}

ul, ol {
  list-style: none;
}

button {
  cursor: pointer;
  border: none;
  background: none;
}

table {
  border-collapse: collapse;
  border-spacing: 0;
}

// === ARCHIVO: css/styles.css ===
/* Main stylesheet - Responsive product page with Flexbox and CSS Grid */

:root {
  --color-primary: #2c3e50;
  --color-secondary: #3498db;
  --color-accent: #e74c3c;
  --color-success: #27ae60;
  --color-warning: #f39c12;
  --color-text: #2c3e50;
  --color-text-light: #7f8c8d;
  --color-bg: #ecf0f1;
  --color-white: #ffffff;
  --shadow-sm: 0 2px 4px rgba(0, 0, 0, 0.1);
  --shadow-md: 0 4px 8px rgba(0, 0, 0, 0.15);
  --shadow-lg: 0 8px 16px rgba(0, 0, 0, 0.2);
  --radius-sm: 4px;
  --radius-md: 8px;
  --radius-lg: 12px;
  --transition: 0.3s ease;
}

body {
  font-family: 'Segoe UI', Arial, sans-serif;
  color: var(--color-text);
  background-color: var(--color-bg);
  line-height: 1.6;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

/* Header - Flexbox for horizontal layout */
header {
  background: var(--color-white);
  box-shadow: var(--shadow-sm);
  position: sticky;
  top: 0;
  z-index: 100;
}

.header-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 0;
}

.logo {
  display: flex;
  align-items: center;
  gap: 10px;
  font-size: 1.5rem;
  font-weight: bold;
  color: var(--color-primary);
}

.logo img {
  width: 120px;
  height: auto;
}

/* Navigation - Flexbox for unidimensional layout */
nav {
  display: flex;
  gap: 2rem;
  align-items: center;
}

nav a {
  padding: 0.5rem 1rem;
  border-radius: var(--radius-sm);
  transition: background var(--transition), color var(--transition);
}

nav a:hover {
  background: var(--color-secondary);
  color: var(--color-white);
}

/* Mobile menu button */
.menu-toggle {
  display: none;
  flex-direction: column;
  gap: 4px;
  padding: 8px;
}

.menu-toggle span {
  width: 25px;
  height: 3px;
  background: var(--color-primary);
  border-radius: 2px;
}

/* Main content */
main {
  padding: 2rem 0;
}

/* Product grid - CSS Grid for bidimensional layout */
.product-grid {
  display: grid;
  grid-template-columns: repeat(1, 1fr);
  gap: 1.5rem;
  padding: 1rem 0;
}

@media (min-width: 768px) {
  .product-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .product-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}

@media (min-width: 1200px) {
  .product-grid {
    grid-template-columns: repeat(4, 1fr);
  }
}

/* Product card */
.product-card {
  background: var(--color-white);
  border-radius: var(--radius-md);
  overflow: hidden;
  box-shadow: var(--shadow-sm);
  transition: transform var(--transition), box-shadow var(--transition);
}

.product-card:hover {
  transform: translateY(-4px);
  box-shadow: var(--shadow-md);
}

.product-image {
  width: 100%;
  aspect-ratio: 1;
  object-fit: cover;
  background: var(--color-bg);
}

.product-info {
  padding: 1rem;
}

.product-title {
  font-size: 1.1rem;
  font-weight: 600;
  margin-bottom: 0.5rem;
}

.product-description {
  color: var(--color-text-light);
  font-size: 0.9rem;
  margin-bottom: 0.5rem;
}

.product-price {
  font-size: 1.25rem;
  font-weight: bold;
  color: var(--color-accent);
}

.product-badge {
  display: inline-block;
  padding: 0.25rem 0.5rem;
  background: var(--color-success);
  color: var(--color-white);
  font-size: 0.75rem;
  border-radius: var(--radius-sm);
  margin-bottom: 0.5rem;
}

.btn-add-cart {
  width: 100%;
  padding: 0.75rem;
  background: var(--color-secondary);
  color: var(--color-white);
  border: none;
  border-radius: var(--radius-sm);
  font-weight: 600;
  cursor: pointer;
  transition: background var(--transition);
}

.btn-add-cart:hover {
  background: var(--color-primary);
}

/* Footer - CSS Grid for responsive columns */
footer {
  background: var(--color-primary);
  color: var(--color-white);
  padding: 3rem 0 1rem;
  margin-top: 3rem;
}

.footer-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2rem;
  margin-bottom: 2rem;
}

@media (min-width: 768px) {
  .footer-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .footer-grid {
    grid-template-columns: repeat(4, 1fr);
  }
}

.footer-section h4 {
  font-size: 1.1rem;
  margin-bottom: 1rem;
  padding-bottom: 0.5rem;
  border-bottom: 2px solid var(--color-secondary);
}

.footer-section ul li {
  margin-bottom: 0.5rem;
}

.footer-section a {
  color: rgba(255, 255, 255, 0.8);
  transition: color var(--transition);
}

.footer-section a:hover {
  color: var(--color-white);
}

.footer-bottom {
  text-align: center;
  padding-top: 1rem;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  color: rgba(255, 255, 255, 0.6);
  font-size: 0.9rem;
}

/* Responsive breakpoints */
@media (max-width: 768px) {
  .header-content {
    flex-wrap: wrap;
  }

  nav {
    display: none;
    width: 100%;
    flex-direction: column;
    gap: 0.5rem;
    padding: 1rem 0;
  }

  nav.active {
    display: flex;
  }

  .menu-toggle {
    display: flex;
  }

  .product-grid {
    grid-template-columns: 1fr;
  }

  .footer-grid {
    grid-template-columns: 1fr;
  }
}

```
