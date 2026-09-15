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