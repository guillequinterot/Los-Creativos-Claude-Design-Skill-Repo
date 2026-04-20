# Skill: Los Creativos — Claude Design

## Propósito

Esta skill guía la generación de assets visuales, propuestas de diseño, materiales gráficos y decisiones estéticas para la marca Los Creativos. Úsala cuando el usuario pida diseñar, proponer o describir cualquier elemento visual de la marca.

---

## Identidad de Marca

**Nombre:** Los Creativos  
**Sitio:** loscreativos.co  
**Posicionamiento:** Agencia de marketing digital de resultados para empresas en LATAM y España  
**Industria:** Marketing B2B — SEO, Diseño Web, Pauta Digital  
**Mercados:** Colombia, México, Chile, Argentina, España, USA, Canadá, Australia

### Frase de marca
> "Hacemos que Google, ChatGPT, las AI Overviews y los usuarios entiendan por qué elegirte a ti."

### Adjetivos de estilo visual

| Adjetivo | Qué significa en diseño |
|----------|------------------------|
| **Bold** | Tipografía negra (900), headings en uppercase, sin timidez visual |
| **Limpio** | Abundante espacio en blanco, sin decoración innecesaria |
| **Alto contraste** | Texto oscuro sobre claro, nunca grises medios sobre blancos |
| **Conversion-focused** | Jerarquía visual clara que guía al CTA; el ojo siempre sabe a dónde ir |
| **Moderno-serio** | Redondeado sin ser juguetón; sofisticado sin ser frío |
| **Data-driven** | Los números son protagonistas: estadísticas grandes, métricas prominentes |
| **Latinoamericano-global** | Energía del mercado LATAM con estándares visuales internacionales |

### Mood board en palabras
Rojo de alta energía · Navy de autoridad · Blancos amplios · Tipografía apretada y fuerte · Bordes redondeados generosos · Sombras sutiles · Iconos lineales limpios · Fotografía real del equipo

---

## Paleta de Colores

### Colores de Marca

| Nombre semántico | Hex | Uso |
|-----------------|-----|-----|
| **Rojo Creativos** | `#FF2D46` | Color institucional. CTAs, botones primarios, isotipo, acento de identidad. Usa con moderación — impacto máximo. |
| **Navy Profundo** | `#0F172A` | Wordmark del logo, texto de headings, botón secundario. Color de autoridad. |
| **Navy Fondo** | `#0B1628` | Fondos de secciones hero oscuras, backgrounds de alto impacto. Ligeramente más azulado que Navy Profundo. |
| **Rojo Suave** | `#FFF1F2` | Fondos de banners de marca, highlights, secciones de acento. Casi blanco, levemente rosado. |
| **Rojo Pastel** | `#FFE9EC` | Fondos de icon chips en reposo. Más saturado que Rojo Suave. |

### Colores Neutros

| Nombre semántico | Hex | Uso |
|-----------------|-----|-----|
| **Gris Hielo** | `#F9FAFB` | Fondo base de toda la página/app. Nunca usar blanco puro como fondo de página. |
| **Blanco Superficie** | `#FFFFFF` | Cards, modales, paneles. Contraste con Gris Hielo. |
| **Pizarra** | `#1E2939` | Texto de lectura principal (párrafos, body text). Azul oscuro casi negro. |
| **Navy Texto** | `#0F172A` | Headings y texto de máxima jerarquía. Igual al Navy Profundo de marca. |
| **Gris Medio** | `#6A7282` | Texto secundario, metadatos, placeholders, subtítulos, captions. |
| **Gris Borde** | `#E0E0E0` | Líneas divisorias, bordes de inputs y cards. |

### Colores Semánticos

| Estado | Color principal | Fondo | Uso |
|--------|----------------|-------|-----|
| **Éxito** | `#16A34A` | `#ECFDF3` | Confirmaciones, métricas positivas, "publicado" |
| **Advertencia** | `#F59E0B` | `#FFFBEB` | Acciones de riesgo moderado, "en progreso" |
| **Error** | `#CF2E2E` | `#FFF1F2` | Validaciones fallidas, formularios con error. Distinto del Rojo Creativos. |
| **Información** | `#2563EB` | `#EFF6FF` | Banners informativos, tooltips, links de sistema |

> **Regla crítica de color:** El Rojo Creativos (`#FF2D46`) es de MARCA, no de error. El error usa `#CF2E2E` (rojo más oscuro y apagado). Confundirlos rompe la semántica visual.

---

## Tipografía

### Familia principal: Satoshi

**Descripción visual:** Geométrica sans-serif de trazo uniforme. Similar a Inter pero con más personalidad — las curvas tienen tensión propia. Muy legible en tamaños pequeños, impactante en display.

**Fallbacks web-safe ordenados por similitud:**
1. `Inter` — primera opción si Satoshi no carga (Google Fonts, siempre disponible)
2. `-apple-system` / `BlinkMacSystemFont` — sistema macOS/iOS
3. `'Segoe UI'` — sistema Windows
4. `system-ui` — sistema genérico
5. `sans-serif` — último recurso

**Stack completo:**
```
'Satoshi', 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', system-ui, sans-serif
```

### Pesos y usos

| Peso | Nombre | Uso típico |
|------|--------|------------|
| 300 Light | Delicado | Texto decorativo de gran tamaño, citas sutiles |
| 400 Regular | Neutro | Body text, párrafos, descripciones |
| 500 Medium | Equilibrado | Nav links, labels de formulario, overlines, subtítulos |
| 700 Bold | Fuerte | H2–H5, énfasis en texto, botones outline |
| 900 Black | Impactante | Display, H1, números estadísticos, botones CTA |

### Escala tipográfica

| Nivel | Tamaño | Peso | Leading | Tracking | Uso |
|-------|--------|------|---------|----------|-----|
| Display 2XL | 60px | 900 Black | 1.0 | -0.02em | Hero principal — UPPERCASE |
| Display XL | 48px | 900 Black | 1.1 | -0.02em | Display secundario |
| H1 | 40px | 900 Black | 1.2 | -0.02em | Título de página |
| H2 | 32px | 700 Bold | 1.2 | -0.01em | Sección principal |
| H3 | 28px | 700 Bold | 1.25 | -0.01em | Subsección |
| H4 | 22px | 700 Bold | 1.3 | 0 | Título de card, sidebar |
| H5 | 18px | 500 Medium | 1.35 | 0 | Label prominente |
| Body LG | 18px | 400 Regular | 1.6 | 0 | Párrafo introductorio |
| Body MD | 16px | 400 Regular | 1.6 | 0 | Texto estándar |
| Body SM | 14px | 400 Regular | 1.5 | 0 | Texto secundario, labels |
| Caption | 12px | 400 Regular | 1.4 | 0 | Metadata, badges, hints |
| Overline | 11px | 500 Medium | 1.3 | +0.08em | UPPERCASE, etiquetas de sección |

**Regla de headings en display:** H1 y display siempre en uppercase. H2 y H3: title case o uppercase según contexto. H4+ nunca uppercase.

---

## Escala de Espaciado

Base: **4px**. Todos los valores son múltiplos exactos.

| Token | Valor | Equivalente rem | Uso típico |
|-------|-------|-----------------|------------|
| sp-1 | 4px | 0.25rem | Micro-gaps (icono + texto) |
| sp-2 | 8px | 0.5rem | Gaps internos pequeños |
| sp-3 | 12px | 0.75rem | Gap entre elementos relacionados |
| sp-4 | 16px | 1rem | Padding de componentes pequeños |
| sp-5 | 20px | 1.25rem | Padding mobile, gaps moderados |
| sp-6 | 24px | 1.5rem | Grid gutter, separación de columnas |
| sp-7 | 30px | 1.875rem | Padding de cards |
| sp-8 | 40px | 2.5rem | Separación entre secciones internas |
| sp-9 | 60px | 3.75rem | Padding vertical de secciones |
| sp-10 | 80px | 5rem | Padding horizontal desktop, hero |
| Hero especial | 150px | 9.375rem | Solo para sección ATF principal |

**Ritmo vertical:** Las secciones respiran. Nunca menos de 60px entre secciones mayores.

---

## Geometría y Forma

### Border-radius

| Nombre | Valor | Forma | Elementos |
|--------|-------|-------|-----------|
| SM — Suave pequeño | 10px | Redondeado discreto | Inputs, chips pequeños, dropdowns |
| MD — Suave medio | 15px | Redondeado notable | Cards secundarias, textareas, tooltips |
| LG — Suave grande | 20px | Redondeado prominente | Cards principales, botones (canónico) |
| XL — Suave extra | 28px | Redondeado fuerte | Modales, containers de sección |
| FULL — Píldora | 9999px | Completamente circular/oval | Badges, avatares, chips de icono |

**Principio:** Nunca esquinas agudas (0px) en la UI pública. El sistema usa redondeo generoso como señal de modernidad B2B accesible.

### Sombras / Elevación

| Nivel | Sombra CSS | Cuándo |
|-------|-----------|--------|
| SM — Reposo | `0 1px 2px rgba(0,0,0,.05)` | Cards estáticas, elementos en reposo |
| MD — Hover | `0 4px 17px -8px rgba(0,0,0,.18)` | Cards en hover, dropdowns, tooltips |
| LG — Float | `0 12px 30px rgba(0,0,0,.14)` | Modales, drawers, elementos flotantes |

---

## Descripción visual de componentes

### Botón Primario
Rectángulo rojo `#FF2D46` con esquinas redondeadas 20px. Texto blanco, uppercase, bold, letter-spacing generoso. Sombra suave en reposo, sombra más pronunciada en hover. En active, se comprime ligeramente (scale 0.97). Es el único elemento que grita "acción" en la página.

### Botón Secundario  
Mismo shape que el primario pero en Navy `#0F172A`. Transmite autoridad y seriedad. Se usa cuando hay dos CTAs y el secundario es menos urgente pero igualmente importante.

### Botón Outline
Borde gris `#E0E0E0`, texto Navy, fondo transparente. En hover: borde se vuelve Navy. Visualmente ligero — ideal para acciones alternativas o de menor jerarquía junto a un botón primario.

### Input
Rectángulo de fondo `#F9FAFB` (casi blanco) con borde `#E0E0E0`. En focus: borde rojo `#FF2D46` con halo rgba rojo de baja opacidad. Border-radius 15px. Altura fija 48px. Label arriba en bold 14px navy, hint abajo en 12px gris.

### Card básica
Rectángulo blanco con borde `#E0E0E0` y sombra mínima. Border-radius 20px. Padding interno 30px. Contenido: título negro 22px bold, descripción gris 14px. Minimalista y legible.

### Card interactiva
Igual que la básica pero con chip de icono circular rojo suave arriba. En hover: levita 3px hacia arriba, borde se tiñe suavemente de rojo, icon chip cambia a rojo sólido con icono blanco, título cambia a rojo. Transición 300ms ease. Siempre es un `<a>` — es navegación.

### Card stat
Centrada. Número grande (48px, weight 900) —puede ser en rojo o navy. Label en 12px uppercase gris con tracking ancho debajo del número. Minimalista, el número es toda la comunicación.

### Card dark
Fondo `#172233` (navy suavizado). Texto blanco. Bordes semitransparentes. Padding 24px. Border-radius 15px. Usada en secciones con fondo `#0B1628`.

### Badge
Píldora con padding 5px/10px. Texto 12px bold. Las variantes de color tienen fondo pálido del mismo tono que el texto (ej. rojo muy claro con texto rojo). El badge dark es la excepción: fondo navy sólido con texto blanco.

### Alert
Banda horizontal con fondo pálido del color semántico, borde izquierdo del mismo color (o borde completo sutil), icono a la izquierda, texto a la derecha. Border-radius 15px. El alert de marca usa el rojo suave de fondo — es para comunicados positivos de la marca, no errores.

### Nav
Franja blanca sticky en top. Altura 68px. Logo a la izquierda. Links centrados en bold 16px navy. Botón rojo "Contacto" a la derecha. Separado del contenido por un borde `#E0E0E0` inferior muy sutil. El megamenu aparece como panel blanco full-width con borde superior cuando se hace hover.

### Footer
Franja blanca con `border-top: 1px solid #E0E0E0` en el top. 5 columnas: logo+tagline+social a la izquierda (más ancha), luego 4 columnas de links con títulos en uppercase gris. Bottom bar con copyright en gris y links legales a la derecha. **No es oscuro** — es el footer canónico del sitio real (confirmado en Bricks).

### Modal
Overlay navy oscuro con blur suave. Panel blanco con border-radius 28px. Header con título y X de cierre. Body scrollable. Footer con botones alineados a la derecha. Animación de entrada: scale(0.98) + translateY(12px) → normal en 300ms.

---

## Sistema de icono chips

Círculos de 48px x 48px. Border-radius full (completamente circular).  
- **Variante primaria:** Fondo `#FFE9EC` (rojo pastel), icono `#FF2D46`. En hover de card interactiva: fondo pasa a `#FF2D46` sólido, icono blanco.
- **Variante neutra:** Fondo `#F9FAFB`, icono `#1E2939`. Sin cambio en hover.  
Los iconos son SVG lineales (stroke, no fill), stroke-width 2px, 22x22px dentro del chip.

---

## Estructura visual de páginas

### Sección hero (ATF)
- Padding vertical: 150px (especial — solo para el hero)
- Layout: 2 columnas (50%/50%) — texto a la izquierda, imagen/visual a la derecha
- H1: 59-60px, uppercase, weight 900, navy, con span en rojo en la palabra clave
- Tagline: 18px, gris medio, max-width 480px
- CTAs: botón primario + botón outline, gap 12px
- Fondo: blanco con sutil patrón de cuadrícula (opcional, 40px grid)

### Sección de servicios
- Padding: 60px vertical
- Encabezado centrado: overline rojo → H2 → descripción gris
- Grid 3 columnas de cards interactivas

### Sección de métricas
- Fondo: puede ser blanco o navy oscuro
- Grid 4 columnas de stats
- Números muy grandes como protagonistas

### Sección de proceso (Growth Loop)
- Lista vertical de 5 pasos
- Círculo numerado izquierda: borde rojo para paso activo, navy para los demás
- Título + descripción a la derecha de cada paso

### Sección de clientes
- Logos en carrusel o grid
- Filtro CSS: saturate(0) en reposo, saturate(1) en hover
- Altura máxima de logos: 60px

---

## Reglas de coherencia visual

### Siempre hacer

1. **El rojo se usa con moderación.** Un CTA rojo por sección como máximo. El rojo es señal de "actúa ahora" — si todo es rojo, nada lo es.
2. **Headings siempre en Navy `#0F172A`.** Nunca en gris, nunca en colores semánticos.
3. **Spacing generoso.** Si dudas, añade más espacio. La marca respira.
4. **Imágenes con border-radius 20px** cuando están en cards o contenedores redondeados.
5. **Logos de clientes** siempre en escala de grises (saturate 0) salvo en hover o en contexto de caso de éxito.
6. **El footer es claro.** Fondo blanco, no navy. El navy se reserva para secciones hero y bloques de impacto.
7. **Estadísticas grandes.** Si hay métricas, hazlas protagonistas: 48px+, weight 900, color rojo o navy.

### Nunca hacer

1. **No mezclar el rojo de marca con el rojo de error** en el mismo contexto sin diferenciación clara.
2. **No usar el logo en colores fuera de los definidos** (azul, verde, violeta sobre el isotipo están prohibidos).
3. **No usar font-weight 400 en headings.** Mínimo 700 para H4+, 900 para H1-H3.
4. **No usar gradientes de color en elementos de UI.** Solo fondos planos. Los gradientes solo en overlays de imagen.
5. **No usar más de 3 tamaños tipográficos distintos en una misma sección.**
6. **No centrar texto largo (>3 líneas).** Solo títulos cortos, stats y overlines se centran.
7. **No usar sombras fuertes en elementos planos.** La jerarquía de sombra es sm→md→lg siguiendo la elevación real.
8. **No usar border-radius 0.** Nunca esquinas agudas en la UI pública.

### Ratio de uso de colores (aproximado por diseño)

| Color | Proporción |
|-------|-----------|
| Blanco `#FFFFFF` y Gris Hielo `#F9FAFB` | 65–70% |
| Navy `#0F172A` + `#0B1628` | 15–20% |
| Gris de texto `#1E2939` + `#6A7282` | 10% |
| Rojo Creativos `#FF2D46` | 5–8% |
| Semánticos + accent bg | <5% |

---

## Assets disponibles

### Logos (archivos locales)

| Variante | Archivo | Cuándo usar |
|----------|---------|-------------|
| Principal (bicolor) | `SVG/Logo-MKT-Principal.svg` | Fondos claros — uso estándar |
| Blanco (monocromo) | `SVG/Logo-MKT-Blanco.svg` | Sobre fondos oscuros o fotografía |
| Negro (monocromo) | `SVG/Logo-MKT-Negro.svg` | Documentos, uso institucional B&W |
| Solo isotipo rojo | `SVG/Icono-rojo.svg` | Favicon, avatar, sello de marca |
| Solo isotipo blanco | `SVG/Icono-blanco.svg` | Isotipo sobre fondo oscuro |

**URL CDN confirmada:** `https://loscreativos.co/wp-content/uploads/2026/01/Logo-MKT-Principal.svg`

### Descripción del isotipo
Forma de C abierta circular con flecha ascendente integrada en el extremo superior derecho. Trazo grueso. La C apunta hacia la derecha (dirección de progreso). La flecha sube, señalando crecimiento. Color: Rojo Creativos `#FF2D46`. Transmite: **movimiento, crecimiento, performance, dirección**.

### Tipografía
10 pesos de Satoshi en OTF disponibles en `/font-los-creativos/` (Light a Black, con itálicas).

### Imágenes del equipo (WordPress CDN)
- Fabio Araujo (founder): `/2026/02/fabio-araujo-los-creativos-founder.jpeg`
- David Martínez Mata: `/2026/02/David.png`
- Juan Uribe: `/2026/02/Juan.png`
- Sebastian Londoño: `/2026/02/Sebastian.png`
- Camila Velásquez: `/2026/02/Camila.png`

### Logos de clientes (WordPress CDN)
Bancolombia, Sura, EAFIT, UPB, Tigo, Renault, Haceb, Uber, Carulla, Éxito, Cruz Verde, El Español, Pepperstone — todos en `/wp-content/uploads/2026/03/logo-[nombre].*`
