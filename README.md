# Diseño de layout responsive para una página de producto

Debes diseñar un layout responsive para una página de producto de una tienda en línea. La página debe mostrar una sección de cabecera, una sección principal con productos relacionados y una sección de pie de página. Debes decidir cuándo usar Flexbox y cuándo usar CSS Grid para lograr un diseño que se adapte a diferentes tamaños de pantalla sin problemas. Evita los errores clásicos de collapsing margins y asegura que el diseño sea consistente en todos los dispositivos.

## Informacion General

| Campo | Valor |
|-------|-------|
| **Tema** | maquetación responsive con Flexbox y CSS Grid |
| **Nivel** | trainee-l2 |
| **Tipo** | practical |
| **Tiempo estimado** | 4 horas |

## Fases del Reto

### Fase 0: Configuración del Proyecto

**Objetivo:** Obtener el proyecto base funcional enviando el Código Base a un asistente de IA, que lo analizará, corregirá errores y generará un ZIP listo para usar.

**Tiempo estimado:** 15-30 minutos

**Instrucciones:**

- Asegúrate de tener instalado para ejecutar el proyecto: Node.js 18+, npm, VS Code o similar.
- Copia todo el contenido del campo **Código Base** de este reto — incluyendo el texto de instrucciones que aparece al inicio.
- Abre un asistente de IA (Claude en claude.ai, ChatGPT o Gemini — se recomienda Claude), pega el contenido copiado en el chat y envíalo.
- El asistente analizará los archivos, corregirá errores y generará un archivo ZIP descargable. Descárgalo y extráelo en la carpeta donde quieras trabajar.
- Ejecuta `npm install && npm run build` (o `npm start`). Si no hay errores, estás listo.

**Entregable:** El proyecto compila/arranca sin errores.

<details>
<summary>Pistas de conocimiento</summary>

- Copia el Código Base completo incluyendo el texto de instrucciones al inicio — esas instrucciones le indican al asistente exactamente qué hacer con los archivos.
- Si el asistente no genera el ZIP automáticamente al terminar el análisis, escríbele: "genera el ZIP ahora".
- Si el proyecto tiene errores al arrancar, comparte el mensaje de error con el mismo asistente para que lo corrija.

</details>

### Fase 1: Diseño de la cabecera

**Objetivo:** Crear una cabecera responsive que se ajuste a diferentes tamaños de pantalla.

**Tiempo estimado:** 1 hora

**Instrucciones:**

- Identifica los elementos que deben estar en la cabecera (logo, menú de navegación, botón de carrito).
- Decide si usar Flexbox o CSS Grid para organizar estos elementos.
- Asegura que la cabecera se adapte a diferentes tamaños de pantalla sin problemas.

**Entregable:** Código HTML y CSS para la cabecera responsive.

<details>
<summary>Pistas de conocimiento</summary>

- Considera el orden de los elementos y cómo cambia en diferentes dispositivos.
- Piensa en cómo mantener la consistencia visual a lo largo de diferentes breakpoints.

</details>

### Fase 2: Diseño de la sección principal

**Objetivo:** Crear una sección principal responsive que muestre productos relacionados.

**Tiempo estimado:** 2 horas

**Instrucciones:**

- Identifica los elementos que deben estar en la sección principal (imágenes de productos, títulos, precios).
- Decide si usar Flexbox o CSS Grid para organizar estos elementos.
- Asegura que la sección principal se adapte a diferentes tamaños de pantalla sin problemas.

**Entregable:** Código HTML y CSS para la sección principal responsive.

<details>
<summary>Pistas de conocimiento</summary>

- Considera la disposición de los productos y cómo cambia en diferentes dispositivos.
- Piensa en cómo mantener la consistencia visual a lo largo de diferentes breakpoints.

</details>

### Fase 3: Diseño del pie de página

**Objetivo:** Crear un pie de página responsive que se ajuste a diferentes tamaños de pantalla.

**Tiempo estimado:** 1 hora

**Instrucciones:**

- Identifica los elementos que deben estar en el pie de página (enlaces de redes sociales, información de contacto).
- Decide si usar Flexbox o CSS Grid para organizar estos elementos.
- Asegura que el pie de página se adapte a diferentes tamaños de pantalla sin problemas.

**Entregable:** Código HTML y CSS para el pie de página responsive.

<details>
<summary>Pistas de conocimiento</summary>

- Considera el orden de los elementos y cómo cambia en diferentes dispositivos.
- Piensa en cómo mantener la consistencia visual a lo largo de diferentes breakpoints.

</details>

## Dimensiones Evaluadas

- **queEs**: ¿Qué es Flexbox y qué es CSS Grid?
- **paraQueSirve**: ¿Para qué se usa Flexbox y para qué se usa CSS Grid?
- **comoSeUsa**: ¿Cómo se usa Flexbox y cómo se usa CSS Grid para crear layouts responsive?
- **erroresComunes**: ¿Cuáles son los errores comunes al usar Flexbox y CSS Grid para crear layouts responsive?

## Criterios de Evaluacion

- Uso correcto de Flexbox y CSS Grid para crear layouts responsive.
- Evitar errores comunes como collapsing margins.
- Consistencia visual en diferentes dispositivos.

## Como trabajar con un asistente de IA

Hay dos caminos, elegi uno:

- **AGENTS.md** (recomendado) — instrucciones nativas del repo. Abri esta carpeta con tu agente local (Claude Code, Cursor, Codex, Copilot, Gemini) y las carga solo. Sabe que archivos faltan y con que comando se verifica, y completa el scaffold escribiendo en disco.
- **PROMPT_MEJORA.md** — para copiar y pegar en un chat (claude.ai, ChatGPT). Devuelve un ZIP con el proyecto. Sirve si no tenes un agente en el IDE.

Ninguno de los dos resuelve las fases del reto: eso es tu trabajo.

## Verificacion

El proyecto esta listo para trabajar cuando este comando corre sin errores:

```bash
el comando de build o arranque canonico del stack elegido
```

---

*Reto generado automaticamente por Challenge Generator - Pragma*
