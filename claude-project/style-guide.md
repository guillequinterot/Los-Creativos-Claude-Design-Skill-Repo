# Los Creativos — Style Guide
**Design System v1.0 | 2026**

---

## Principios de Diseño

Extraídos de `UI Kit Componentes.txt` y la identidad de marca observada en sitio y archivos:

1. **Resultados primero** — Cada elemento visual debe reforzar el mensaje de performance, crecimiento y conversión. El rojo de marca es acción, no decoración.
2. **Alto contraste** — Textos oscuros sobre fondos claros, o blancos sobre oscuros. Nunca grises medios sobre blancos.
3. **Geometría redondeada** — Radios grandes (20px) en cards y botones para un carácter moderno sin perder seriedad B2B.
4. **Bold, no ruidoso** — Jerarquía tipográfica fuerte (Black 900 en headings), pero sin exceso de colores. El rojo se usa con moderación.
5. **Conversión-first** — CTAs visibles, formularios limpios, fricción mínima. Los botones primarios siempre en rojo.

---

## Colores

### Marca

| Token | Valor | Uso |
|-------|-------|-----|
| `--color-primary` | `#FF2D46` | CTAs, acciones principales, logo isotipo, acento de identidad |
| `--color-dark` | `#0F172A` | Texto principal, botón secundario, logo wordmark |
| `--color-dark-alt` | `#0B1628` | Fondos de sección hero, gradientes oscuros |
| `--color-accent-bg` | `#FFF1F2` | Highlights de marca, banners, fondos de bloques de acento |
| `--color-accent-bg-soft` | `#FFE9EC` | Chips de icono en reposo, estado activo suave |

### Neutros

| Token | Valor | Uso |
|-------|-------|-----|
| `--color-bg` | `#F9FAFB` | Fondo base de página |
| `--color-surface` | `#FFFFFF` | Cards, modales, paneles |
| `--color-surface-soft` | `#F9FAFB` | Fondo de inputs, elementos de baja elevación |
| `--color-text` | `#1E2939` | Texto de lectura (párrafos, body) |
| `--color-text-strong` | `#0F172A` | Headings, labels, texto de máxima importancia |
| `--color-text-muted` | `#6A7282` | Metadatos, placeholders, subtítulos, captions |
| `--color-border` | `#E0E0E0` | Strokes de componentes, separadores |
| `--color-border-soft` | `rgba(15,23,42,0.10)` | Separadores internos sutiles |
| `--color-white` | `#FFFFFF` | Texto sobre fondos oscuros |

### Semánticos

| Token | Valor | Uso |
|-------|-------|-----|
| `--color-success` | `#16A34A` | Confirmaciones, métricas positivas |
| `--color-success-bg` | `#ECFDF3` | Fondo de alerts/badges de éxito |
| `--color-warning` | `#F59E0B` | Estados preventivos, acciones con riesgo |
| `--color-warning-bg` | `#FFFBEB` | Fondo de alerts de advertencia |
| `--color-error` | `#CF2E2E` | Errores de formulario, validaciones fallidas |
| `--color-error-bg` | `#FFF1F2` | Fondo de alerts/inputs con error |
| `--color-info` | `#2563EB` | Links, banners informativos, tooltips |
| `--color-info-bg` | `#EFF6FF` | Fondo de alerts informativos |

> **Nota sobre error vs primary:** El error (`#CF2E2E`) es distinto del primary (`#FF2D46`) intencionalmente. Ver `conflicts.md` para el detalle.

---

## Tipografía

**Fuente única: Satoshi**
Geométrica sans-serif, alta legibilidad, carácter moderno. Ideal para productos B2B enfocados en resultados.
Archivos disponibles en `/font-los-creativos/` (10 pesos en OTF).

### Escala de tamaños

| Token | Tamaño | Peso | Leading | Uso |
|-------|--------|------|---------|-----|
| `--fs-display2xl` | 60px | 900 Black | 1.1 | Hero principal, portada |
| `--fs-display-xl` | 48px | 900 Black | 1.1 | Display secundario |
| `--fs-h1` | 40px | 900 Black | 1.2 | Título de página |
| `--fs-h2` | 32px | 700 Bold | 1.2 | Sección principal |
| `--fs-h3` | 28px | 700 Bold | 1.25 | Subsección |
| `--fs-h4` | 22px | 700 Bold | 1.3 | Card title, sidebar title |
| `--fs-h5` | 18px | 500 Medium | 1.35 | Label prominente |
| `--fs-body-lg` | 18px | 400 Regular | 1.6 | Párrafo destacado, intro |
| `--fs-body-md` | 16px | 400 Regular | 1.6 | Párrafo estándar, botones |
| `--fs-body-sm` | 14px | 400 Regular | 1.5 | Texto secundario, labels |
| `--fs-caption` | 12px | 400 Regular | 1.4 | Metadata, badges, hints |
| `--fs-overline` | 11px | 500 Medium | 1.3 | Labels en uppercase tracking ancho |

### Letter Spacing

| Token | Valor | Uso |
|-------|-------|-----|
| `--ls-tight` | `-0.02em` | Display y H1 para headings impactantes |
| `--ls-tight-sm` | `-0.01em` | H2 y H3 |
| `--ls-normal` | `0em` | Texto de lectura |
| `--ls-wide` | `0.06em` | Botones (uppercase) |
| `--ls-wider` | `0.08em` | Overlines (uppercase tracking máximo) |

### Pesos disponibles

| Peso | Número | Uso típico |
|------|--------|------------|
| Light | 300 | Texto decorativo de gran tamaño |
| Regular | 400 | Body text, párrafos |
| Medium | 500 | Labels, nav links, overlines |
| Bold | 700 | H2–H5, botones, énfasis |
| Black | 900 | Display, H1, números estadísticos |

---

## Espaciado

Sistema base 4px. Todos los tokens son múltiplos de 4.

| Token | Valor | Uso típico |
|-------|-------|------------|
| `--space-1` | 4px | Micro (gap entre icono y texto) |
| `--space-2` | 8px | Gap interno pequeño |
| `--space-3` | 12px | Gap entre elementos relacionados |
| `--space-4` | 16px | Padding interno de componentes pequeños |
| `--space-5` | 20px | Padding de modales, padding mobile |
| `--space-6` | 24px | Grid gutter, gap entre cards |
| `--space-7` | 30px | Padding de cards |
| `--space-8` | 40px | Separación entre secciones internas |
| `--space-9` | 60px | Padding vertical de secciones |
| `--space-10` | 80px | Padding horizontal desktop, secciones hero |

---

## Radios (Geometría)

| Token | Valor | Uso |
|-------|-------|-----|
| `--radius-sm` | 10px | Inputs, chips pequeños, badges |
| `--radius-md` | 15px | Cards secundarias, dropdowns, textareas |
| `--radius-lg` | 20px | Cards principales, botones md/lg |
| `--radius-xl` | 28px | Modales, containers de sección |
| `--radius-full` | 9999px | Pills, avatares, chips circulares, dots |

**Principio:** Redondeo generoso como señal de modernidad y accesibilidad visual. Nunca 0px (sharp corners) excepto en elementos técnicos internos.

---

## Sombras / Elevación

| Token | CSS | Uso |
|-------|-----|-----|
| `--shadow-sm` | `0 1px 2px rgba(0,0,0,0.05)` | Elevación base, cards en reposo |
| `--shadow-md` | `0 4px 17px -8px rgba(0,0,0,0.18)` | Cards en hover, dropdowns, tooltips |
| `--shadow-lg` | `0 12px 30px rgba(0,0,0,0.14)` | Modales, drawers, popovers |

**Sistema de elevación:** sm → md (hover) → lg (overlay). No usar lg en elementos inline.

---

## Motion / Animación

| Token | Valor | Uso |
|-------|-------|-----|
| `--motion-fast` | `150ms ease` | Cambios de color, opacity, scale |
| `--motion-base` | `200ms ease` | Transiciones estándar de UI |
| `--motion-slow` | `300ms ease` | Hover de cards, modales, slides |

**Principio:** Nunca más de 300ms en interacciones de UI. Usar `prefers-reduced-motion` para usuarios con sensibilidad al movimiento.

---

## Layout

| Token | Valor |
|-------|-------|
| `--container-max` | 1100px |
| `--grid-gutter` | 24px |
| `--section-pad-y` | 60px |
| `--section-pad-x-lg` | 80px (desktop) |
| `--section-pad-x-sm` | 20px (mobile) |

**Grid:** 12 columnas. Breakpoints: mobile < 768px, tablet 768–1024px, desktop > 1024px.

---

## Componentes

### Botones

4 variantes × 3 tamaños = 12 combinaciones base.

| Variante | `.btn-*` | Uso |
|---------|---------|-----|
| Primary | `.btn-primary` | CTA principal, acción de conversión |
| Secondary | `.btn-secondary` | Acción secundaria importante |
| Outline | `.btn-outline` | Alternativa visual ligera |
| Ghost | `.btn-ghost` | Acciones de menor jerarquía |

Siempre usar `.btn` + una variante + un tamaño (`.btn-sm`, `.btn-md`, `.btn-lg`).

### Inputs

Estructura requerida:
```html
<div class="input-wrapper">
  <label class="input-label">Label</label>
  <input class="input" type="text" />
  <span class="input-hint">Texto de ayuda</span>
</div>
```

Estados: default → `:focus` → `--error` → `--success`.

### Cards

| Clase | Uso |
|-------|-----|
| `.card` | Contenedor de información estático |
| `.card-interactive` | Card clickeable con hover lift (usar con `<a>`) |
| `.card-dark` | Card sobre fondo oscuro (secciones navy) |
| `.card-stat` | Número grande + label (métricas, social proof) |

### Alertas

Siempre con icono + mensaje. Opcionalmente dismissable.
Variantes: `.alert-success`, `.alert-warning`, `.alert-error`, `.alert-info`, `.alert-brand`.

### Badges

Indicadores de estado o categoría. Variantes: primary, dark, soft, success, warning, error, info.

---

## Assets de Marca

### Logos disponibles (SVG)

| Archivo | Descripción | Uso |
|---------|-------------|-----|
| `Logo-MKT-Principal.svg` | Wordmark + isotipo bicolor (navy + rojo) | Uso principal en fondos claros |
| `Logo-MKT-Blanco.svg` | Versión blanca completa | Fondos oscuros, fotografía |
| `Logo-MKT-Negro.svg` | Versión navy monocromática | Documentos, uso institucional |
| `Icono-rojo.svg` | Solo el isotipo en rojo | Favicon, avatar, sello |
| `Icono-blanco.svg` | Solo el isotipo en blanco | Sobre fondos oscuros |
| `Icono-negro.svg` | Solo el isotipo en negro | Monocromático |

**Descripción del isotipo:** Forma de C abierta circular con flecha ascendente integrada en el extremo superior derecho. Transmite movimiento, crecimiento y performance. Colores: `#FF2D46` (flecha y arco) sobre `#0F172A` (wordmark).

### Tipografía

10 pesos de **Satoshi** en OTF en `/font-los-creativos/`. Todos importados en `ui-kit.css` vía `@font-face` con `font-display: swap`.

### Logos de clientes (WordPress CDN)

Disponibles en `https://loscreativos.co/wp-content/uploads/2026/03/logo-*.jpg`:
Bancolombia, Sura, EAFIT, UPB, Tigo, Renault, Haceb, Uber, Carulla, Éxito, Cruz Verde, El Español, Pepperstone, Protección, Grupo Sura.

---

## Integración en Tailwind

```js
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        brand: {
          primary:      '#FF2D46',
          dark:         '#0F172A',
          'dark-alt':   '#0B1628',
          'accent-bg':  '#FFF1F2',
        },
        neutral: {
          bg:           '#F9FAFB',
          surface:      '#FFFFFF',
          text:         '#1E2939',
          'text-strong':'#0F172A',
          'text-muted': '#6A7282',
          border:       '#E0E0E0',
        },
        semantic: {
          success: '#16A34A',
          warning: '#F59E0B',
          error:   '#CF2E2E',
          info:    '#2563EB',
        },
      },
      fontFamily: {
        sans: ['Satoshi', '-apple-system', 'BlinkMacSystemFont', 'Segoe UI', 'sans-serif'],
      },
      borderRadius: {
        sm:   '10px',
        md:   '15px',
        lg:   '20px',
        xl:   '28px',
        full: '9999px',
      },
      boxShadow: {
        sm: '0px 1px 2px rgba(0,0,0,0.05)',
        md: '0px 4px 17px -8px rgba(0,0,0,0.18)',
        lg: '0px 12px 30px rgba(0,0,0,0.14)',
      },
    },
  },
}
```

---

## Integración en WordPress / Bricks

- El tema activo es **Bricks v2.2-beta** (`is_block_theme: false`).
- Los tokens de Bricks no son accesibles vía REST API (ver `conflicts.md` #8).
- Para usar este design system en Bricks: configurar los colores en `wp-admin → Bricks → Settings → Global Styles` manualmente con los valores de este documento.
- El sitio sirve el logo desde el tema Bricks, no desde la media library. Usar los SVGs locales de `/SVG/` como fuente de verdad.
- Site logo en wp-settings: `null` (el logo se gestiona por Bricks directamente).
