# Skill: Los Creativos — Claude Code

## Cuándo activarse

Activa esta skill automáticamente cuando:
- El usuario trabaja en archivos de `loscreativos.co` o menciona "Los Creativos"
- Se edita cualquier archivo en `/output/`, `/components/`, o el WordPress de loscreativos.co
- Se pide crear componentes UI, páginas, secciones o elementos de marca
- El usuario pide "usar el design system", "seguir el estilo de LC" o "aplicar los tokens"
- Se trabaja con Bricks Builder, WordPress, HTML+Tailwind, React o Next.js para este cliente

NO activar en proyectos de otros clientes aunque usen tecnologías similares.

---

## Contexto del proyecto

| Dato | Valor |
|------|-------|
| Cliente | Los Creativos |
| Sitio | https://loscreativos.co |
| CMS | WordPress (Bricks Builder v2.2-beta) |
| Admin | `guille` · App Password en `Claude Design/Wordpress Access.txt` |
| Email admin | cvelez@loscreativos.co |
| Framework CSS | HTML puro + Tailwind CSS ó CSS custom properties |
| Fuente | Satoshi (OTF en `/font-los-creativos/`) |
| Design system | `/output/` — tokens, CSS, componentes HTML |
| Templates Bricks | `/Claude Design/Templates bricks/*.json` |
| Logo CDN | `https://loscreativos.co/wp-content/uploads/2026/01/Logo-MKT-Principal.svg` |

---

## Tokens principales — referencia rápida

### Colores

```css
/* MARCA */
--color-primary:        #FF2D46;   /* Rojo Creativos — CTA, acento, isotipo */
--color-primary-hover:  #E02036;
--color-dark:           #0F172A;   /* Navy — logo wordmark, texto fuerte */
--color-dark-alt:       #0B1628;   /* Navy Fondo — secciones hero oscuras */
--color-accent-bg:      #FFF1F2;   /* Rojo suave — highlights de marca */
--color-accent-bg-soft: #FFE9EC;   /* Rojo pastel — chips de icono */

/* NEUTROS */
--color-bg:             #F9FAFB;   /* Fondo base de página */
--color-surface:        #FFFFFF;   /* Cards, modales */
--color-surface-soft:   #F9FAFB;   /* Fondo de inputs */
--color-text:           #1E2939;   /* Texto de lectura (var(--gray2) en Bricks) */
--color-text-strong:    #0F172A;   /* Headings */
--color-text-muted:     #6A7282;   /* Secundario (var(--gray) en Bricks) */
--color-border:         #E0E0E0;   /* Strokes de componentes */

/* SEMÁNTICOS */
--color-success:        #16A34A;
--color-success-bg:     #ECFDF3;
--color-warning:        #F59E0B;
--color-warning-bg:     #FFFBEB;
--color-error:          #CF2E2E;   /* ≠ primary — ver conflicts.md */
--color-error-bg:       #FFF1F2;
--color-info:           #2563EB;
--color-info-bg:        #EFF6FF;
```

### Tipografía

```css
--font-sans:     'Satoshi', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
--fw-light:  300;  --fw-regular: 400;  --fw-medium: 500;
--fw-bold:   700;  --fw-black:   900;

/* ESCALA */
--fs-display2xl: 60px;   /* Hero H1 — uppercase, weight 900 */
--fs-display-xl: 48px;
--fs-h1:         40px;
--fs-h2:         32px;
--fs-h3:         28px;
--fs-h4:         22px;   /* Card titles */
--fs-h5:         18px;
--fs-body-md:    16px;   /* Estándar */
--fs-body-sm:    14px;   /* Labels, hints */
--fs-caption:    12px;   /* Badges, meta */
--fs-overline:   11px;   /* Uppercase tracking 0.08em */
```

### Espaciado, radio y sombra

```css
/* SPACING (base 4px) */
--space-1:4px  --space-2:8px   --space-3:12px  --space-4:16px
--space-5:20px --space-6:24px  --space-7:30px  --space-8:40px
--space-9:60px --space-10:80px

/* RADIUS */
--radius-sm:10px  --radius-md:15px  --radius-lg:20px
--radius-xl:28px  --radius-full:9999px

/* SHADOW */
--shadow-sm: 0 1px 2px rgba(0,0,0,.05);
--shadow-md: 0 4px 17px -8px rgba(0,0,0,.18);   /* Hover de cards */
--shadow-lg: 0 12px 30px rgba(0,0,0,.14);         /* Modales */

/* LAYOUT */
--container-max:    1100px;
--section-pad-y:    60px;
--section-pad-y-hero: 150px;   /* Solo para ATF hero */
--grid-gutter:      24px;

/* MOTION */
--motion-fast:150ms ease  --motion-base:200ms ease  --motion-slow:300ms ease
```

---

## Clases de componentes disponibles

> Importar siempre: `<link rel="stylesheet" href="/output/ui-kit.css" />`

### Botones

```html
<!-- Estructura: .btn + variante + tamaño -->
<button class="btn btn-primary btn-lg">SOLICITAR CONSULTORÍA</button>
<button class="btn btn-secondary btn-md">Ver Casos de Éxito</button>
<button class="btn btn-outline btn-md">Saber Más</button>
<button class="btn btn-ghost btn-sm">Cancelar</button>

<!-- Con icono -->
<button class="btn btn-primary btn-md">
  <svg ...></svg> Llamar Ahora
</button>

<!-- Loading -->
<button class="btn btn-primary btn-md btn-loading">Procesando</button>

<!-- Disabled -->
<button class="btn btn-primary btn-md" disabled>No disponible</button>
```

**Tamaños:** `btn-sm` (10/16px) · `btn-md` (12/20px) · `btn-lg` (16/32px)
**Regla:** Siempre uppercase, letter-spacing wide, border-radius 20px.

### Inputs

```html
<div class="input-wrapper">
  <label class="input-label" for="campo">Label</label>
  <input id="campo" class="input" type="text" placeholder="..." />
  <span class="input-hint">Texto de ayuda</span>
</div>

<!-- Error -->
<div class="input-wrapper input-wrapper--error">
  <label class="input-label" for="campo-err">Email *</label>
  <input id="campo-err" class="input" type="email" value="invalido" />
  <span class="input-hint input-hint--error">✕ Email no válido</span>
</div>

<!-- Con icono -->
<div class="input-group">
  <svg class="input-icon" ...></svg>
  <input class="input" type="search" placeholder="Buscar..." />
</div>

<!-- Select -->
<select class="input">
  <option disabled selected>Selecciona</option>
  <option>SEO Técnico</option>
</select>

<!-- Textarea -->
<textarea class="input" rows="4" placeholder="Mensaje..."></textarea>
```

### Cards

```html
<!-- Card básica -->
<div class="card">
  <h4 class="card__title">Título</h4>
  <p class="card__body">Descripción...</p>
</div>

<!-- Card interactiva (siempre con <a>) -->
<a href="/servicio" class="card card-interactive">
  <div class="icon-chip">
    <svg ...></svg>
  </div>
  <h4 class="card__title">SEO Técnico</h4>
  <p class="card__body">Descripción...</p>
</a>

<!-- Card stat (métricas) -->
<div class="card card-stat">
  <div class="card-stat__value card-stat__value--primary">+320%</div>
  <div class="card-stat__label">Tráfico orgánico</div>
</div>

<!-- Card dark (sección #0B1628) -->
<div class="card card-dark">
  <h4 class="card__title" style="color:white;">Título</h4>
  <p class="card__body text-muted">Descripción</p>
</div>
```

### Badges

```html
<span class="badge badge-primary">SEO</span>
<span class="badge badge-dark">Nuevo</span>
<span class="badge badge-soft">Caso de Éxito</span>
<span class="badge badge-success badge-dot">Activo</span>
<span class="badge badge-error">Pausado</span>
<span class="badge badge-info">Actualizado</span>
```

### Alerts

```html
<div class="alert alert-success" role="alert">
  <svg ...></svg>
  <div class="alert__content">
    <p class="alert__title">¡Listo!</p>
    <p class="alert__body">Los cambios se guardaron.</p>
  </div>
  <!-- Opcional: botón de cierre -->
  <button class="alert-dismiss" onclick="this.closest('.alert').remove()">✕</button>
</div>
<!-- Variantes: alert-success · alert-warning · alert-error · alert-info · alert-brand -->
```

### Modal

```html
<!-- Overlay -->
<div class="modal-overlay" id="mi-modal">
  <div class="modal">
    <div class="modal__header">
      <h2 class="modal__title">Título del Modal</h2>
      <button class="modal__close" onclick="closeModal('mi-modal')">✕</button>
    </div>
    <div class="modal__body">Contenido...</div>
    <div class="modal__footer">
      <button class="btn btn-outline btn-md" onclick="closeModal('mi-modal')">Cancelar</button>
      <button class="btn btn-primary btn-md">Confirmar</button>
    </div>
  </div>
</div>

<script>
  function openModal(id) {
    document.getElementById(id).classList.add('is-open');
    document.body.style.overflow = 'hidden';
  }
  function closeModal(id) {
    document.getElementById(id).classList.remove('is-open');
    document.body.style.overflow = '';
  }
</script>
```

### Nav y Footer

Ver archivos completos en:
- `/output/components/nav.html` — megamenu real con 88 slugs de WP
- `/output/components/footer.html` — 5 columnas claro (canónico) + variante dark

---

## Snippets de código listos

### Sección hero (ATF) — Bricks-aligned

```html
<section style="padding: 150px 0; background: white;">
  <div class="container">
    <div style="display:grid; grid-template-columns:1fr 1fr; gap:24px; align-items:center;">
      <div>
        <span class="text-overline text-primary" style="margin-bottom:16px;display:block;">
          Agencia de Marketing Digital
        </span>
        <h1 style="font-size:60px;font-weight:900;line-height:1;text-transform:uppercase;color:#0F172A;margin-bottom:24px;">
          Marketing de <span style="color:#FF2D46;">Resultados</span>
        </h1>
        <p style="font-size:18px;color:#6A7282;line-height:1.6;margin-bottom:32px;max-width:480px;">
          Hacemos que Google, ChatGPT y las AI Overviews entiendan por qué elegirte a ti.
        </p>
        <div style="display:flex;gap:12px;flex-wrap:wrap;">
          <a href="/contacto" class="btn btn-primary btn-lg">SOLICITAR CONSULTORÍA</a>
          <a href="/casos-de-exito2" class="btn btn-outline btn-lg">VER CASOS DE ÉXITO</a>
        </div>
      </div>
      <div>
        <!-- Imagen de founders u otro asset -->
        <img src="..." alt="Los Creativos Founders" style="width:100%;border-radius:20px;" />
      </div>
    </div>
  </div>
</section>
```

### Sección de servicios (grid 3 cols)

```html
<section class="section" style="background:var(--color-bg);">
  <div class="container">
    <span class="text-overline text-primary" style="display:block;text-align:center;margin-bottom:12px;">
      Lo que hacemos
    </span>
    <h2 style="text-align:center;margin-bottom:8px;">Nuestros Servicios</h2>
    <p class="text-body-lg text-muted" style="text-align:center;max-width:560px;margin:0 auto 48px;">
      Estrategia, ejecución y resultados medibles.
    </p>
    <div class="grid-3">
      <a href="/tecnico" class="card card-interactive">
        <div class="icon-chip"><!-- SVG --></div>
        <h4 class="card__title">SEO Técnico</h4>
        <p class="card__body">Descripción breve del servicio.</p>
      </a>
      <!-- Repetir para cada servicio -->
    </div>
  </div>
</section>
```

### Sección oscura (dark section)

```html
<section style="background:#0B1628; padding:60px 0;">
  <div class="container">
    <h2 style="color:white;text-align:center;margin-bottom:8px;">Resultados que hablan</h2>
    <p style="color:rgba(255,255,255,.55);text-align:center;margin-bottom:40px;">
      +150 empresas en LATAM confían en nosotros.
    </p>
    <div class="grid-4">
      <div class="card card-stat" style="background:rgba(255,255,255,.05);border-color:rgba(255,255,255,.1);">
        <div class="card-stat__value" style="color:#FF2D46;">+320%</div>
        <div class="card-stat__label" style="color:rgba(255,255,255,.5);">Tráfico orgánico</div>
      </div>
      <!-- Más stats... -->
    </div>
  </div>
</section>
```

### Configuración Tailwind CSS

```js
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        brand: {
          primary: '#FF2D46',
          'primary-hover': '#E02036',
          dark: '#0F172A',
          'dark-alt': '#0B1628',
          'accent-bg': '#FFF1F2',
          'accent-soft': '#FFE9EC',
        },
        neutral: {
          bg: '#F9FAFB', surface: '#FFFFFF', 'surface-soft': '#F9FAFB',
          text: '#1E2939', 'text-strong': '#0F172A', 'text-muted': '#6A7282',
          border: '#E0E0E0',
        },
        semantic: {
          success: '#16A34A', 'success-bg': '#ECFDF3',
          warning: '#F59E0B', 'warning-bg': '#FFFBEB',
          error: '#CF2E2E',   'error-bg': '#FFF1F2',
          info: '#2563EB',    'info-bg': '#EFF6FF',
        },
      },
      fontFamily: {
        sans: ['Satoshi', '-apple-system', 'BlinkMacSystemFont', 'Segoe UI', 'sans-serif'],
      },
      borderRadius: { sm:'10px', md:'15px', lg:'20px', xl:'28px', full:'9999px' },
      boxShadow: {
        sm: '0 1px 2px rgba(0,0,0,.05)',
        md: '0 4px 17px -8px rgba(0,0,0,.18)',
        lg: '0 12px 30px rgba(0,0,0,.14)',
      },
      maxWidth: { container: '1100px' },
    },
  },
}
```

---

## Reglas de nomenclatura del proyecto

### Clases CSS
- Componentes: `.btn`, `.card`, `.badge`, `.alert`, `.modal`, `.nav`, `.footer`
- Modificadores: `.btn-primary`, `.card-interactive`, `.badge-success`
- Estados: `.is-open`, `.is-active`, `.is-loading`
- Utilidades de layout: `.container`, `.section`, `.grid-2/3/4`
- NO usar: camelCase en clases CSS, prefijos innecesarios como `lc-`

### Archivos
- Templates Bricks: `template-[nombre-slug]-YYYY-MM-DD.json`
- Componentes HTML: `[componente].html` en `/output/components/`
- Assets: kebab-case (`logo-mkt-principal.svg`, `icono-rojo.svg`)

### Slugs WordPress (estructura real del sitio)
- Servicios SEO bajo `/seo/`: tecnico, contenidos, linkbuilding, auditoria, local, internacional, migracion, on-page
- Servicios IA bajo `/seo/`: chatgpt, gemini, perplexity, ai-overviews, geo, llmo, aeo, claude
- Industrias bajo `/industrias/`: universidades, ecommerce, b2b, inmobiliarias, clinicas, restaurantes, hoteles
- Ciudades SEO bajo `/seo/`: agencia-seo-bogota, agencia-seo-medellin, agencia-seo-cali, etc.
- Ciudades diseño bajo `/diseno-web/`: bogota, medellin, cali, barranquilla, bucaramanga, cartagena

### Variables CSS — convención de nombres
```
--color-[grupo]-[variante]    →  --color-primary, --color-success-bg
--fs-[escala]                 →  --fs-h1, --fs-body-md, --fs-caption
--space-[1-10]                →  --space-4 (16px), --space-6 (24px)
--radius-[sm|md|lg|xl|full]   →  --radius-lg (20px)
--shadow-[sm|md|lg]           →  --shadow-md
--motion-[fast|base|slow]     →  --motion-base (200ms ease)
```

### Convenciones de código
- HTML: semántico siempre (`<button>` para acciones, `<a>` para navegación, `<article>` para posts)
- Botones de formulario: siempre `type="submit"` o `type="button"` explícito
- Imágenes: siempre `alt` descriptivo, `width` y `height` en SVGs
- ARIA: `role="dialog" aria-modal="true"` en modales, `aria-label` en botones icon-only
- No usar `!important` excepto en `.hidden` y `.sr-only`

---

## Archivos de referencia

```
1-Los Creativos - 2026/
├── output/                        ← Design system generado
│   ├── design-tokens.json         ← Fuente de verdad de tokens (W3C)
│   ├── ui-kit.css                 ← CSS custom properties + componentes
│   ├── style-guide.md             ← Documentación completa
│   ├── conflicts.md               ← Conflictos resueltos entre fuentes
│   └── components/
│       ├── button.html, input.html, card.html, badge.html
│       ├── alert.html, modal.html, nav.html, footer.html
├── SVG/                           ← Logos en SVG (fuente local)
├── Png/                           ← Logos en PNG
├── font-los-creativos/            ← Satoshi OTF (10 pesos)
└── Claude Design/
    ├── design-tokens.json         ← Tokens originales (ver conflicts.md)
    ├── UI Kit Componentes.txt     ← Componentes originales Tailwind
    ├── Wordpress Access.txt       ← Credenciales WP (Application Password)
    └── Templates bricks/          ← 17 templates exportados de Bricks
```
