# Skill: Los Creativos — Claude.ai Artifacts

## Descripción

Esta skill permite crear artifacts HTML/CSS/JS en Claude.ai que respetan el design system de Los Creativos. Los artifacts se ejecutan en un sandbox con restricciones específicas — esta guía garantiza que el código funcione sin errores.

---

## Restricciones del entorno de artifacts (qué NO hacer)

```
❌ NO cargar fuentes externas (Google Fonts, CDN de Satoshi)
❌ NO usar @font-face con URLs http/https (bloqueado por CSP)
❌ NO hacer fetch() ni XMLHttpRequest a APIs externas
❌ NO usar localStorage, sessionStorage, IndexedDB
❌ NO importar módulos externos (npm, unpkg, jsdelivr sin allowlist)
❌ NO usar document.cookie
❌ NO referencias a archivos locales (../../font-los-creativos/)
❌ NO usar WebSockets ni EventSource
❌ NO window.open() ni navegación externa directa

✅ SÍ usar CSS custom properties inline
✅ SÍ usar JavaScript vanilla (sin frameworks)
✅ SÍ usar SVG inline (para logos e iconos)
✅ SÍ usar Tailwind CDN: <script src="https://cdn.tailwindcss.com"></script>
✅ SÍ usar font-family con stack de sistema como fallback
✅ SÍ usar Inter/system-ui como sustituto visual de Satoshi
✅ SÍ usar animaciones CSS puras
✅ SÍ usar Grid y Flexbox
```

---

## CSS Variables — pegar en cualquier artifact

Copia este bloque en el `<style>` de cualquier artifact. Incluye el stack de fuentes compatible con sandbox:

```html
<style>
/* ── LOS CREATIVOS DESIGN SYSTEM v1.0 ────────────────────── */

:root {
  /* Fuente: Satoshi no disponible en sandbox. Inter es el sustituto
     más cercano: geométrica, alta legibilidad, disponible en sistema. */
  --font-sans: 'Inter', 'Segoe UI', system-ui, -apple-system, sans-serif;

  /* COLORES DE MARCA */
  --color-primary:        #FF2D46;
  --color-primary-hover:  #E02036;
  --color-dark:           #0F172A;
  --color-dark-alt:       #0B1628;
  --color-accent-bg:      #FFF1F2;
  --color-accent-bg-soft: #FFE9EC;

  /* NEUTROS */
  --color-bg:             #F9FAFB;
  --color-surface:        #FFFFFF;
  --color-surface-soft:   #F9FAFB;
  --color-text:           #1E2939;
  --color-text-strong:    #0F172A;
  --color-text-muted:     #6A7282;
  --color-border:         #E0E0E0;

  /* SEMÁNTICOS */
  --color-success:        #16A34A;
  --color-success-bg:     #ECFDF3;
  --color-warning:        #F59E0B;
  --color-warning-bg:     #FFFBEB;
  --color-error:          #CF2E2E;
  --color-error-bg:       #FFF1F2;
  --color-info:           #2563EB;
  --color-info-bg:        #EFF6FF;

  /* TIPOGRAFÍA */
  --fw-light:   300;
  --fw-regular: 400;
  --fw-medium:  500;
  --fw-bold:    700;
  --fw-black:   900;

  --fs-display: 56px;
  --fs-h1:      40px;
  --fs-h2:      32px;
  --fs-h3:      28px;
  --fs-h4:      22px;
  --fs-h5:      18px;
  --fs-body-lg: 18px;
  --fs-body-md: 16px;
  --fs-body-sm: 14px;
  --fs-caption: 12px;

  /* ESPACIADO */
  --sp-1:  4px;  --sp-2:  8px;  --sp-3: 12px;
  --sp-4: 16px;  --sp-5: 20px;  --sp-6: 24px;
  --sp-7: 30px;  --sp-8: 40px;  --sp-9: 60px;

  /* RADIO */
  --r-sm:   10px;
  --r-md:   15px;
  --r-lg:   20px;
  --r-xl:   28px;
  --r-full: 9999px;

  /* SOMBRAS */
  --shadow-sm: 0 1px 2px rgba(0,0,0,.05);
  --shadow-md: 0 4px 17px -8px rgba(0,0,0,.18);
  --shadow-lg: 0 12px 30px rgba(0,0,0,.14);

  /* MOTION */
  --t-fast: 150ms ease;
  --t-base: 200ms ease;
  --t-slow: 300ms ease;
}

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
body {
  font-family: var(--font-sans);
  font-size: var(--fs-body-md);
  color: var(--color-text);
  background: var(--color-bg);
  line-height: 1.6;
  -webkit-font-smoothing: antialiased;
}
img, svg { display: block; max-width: 100%; }
button { cursor: pointer; font: inherit; }
</style>
```

---

## Logo SVG inline (para usar sin URL externa)

El logo se puede incrustar directamente como SVG inline. Versiones disponibles:

### Isotipo solo (icon — rojo)

```html
<!-- Isotipo "C-arrow" — 48×48px recomendado -->
<svg width="48" height="48" viewBox="0 0 100 100" fill="none" xmlns="http://www.w3.org/2000/svg">
  <path d="M 82 32 A 40 40 0 1 0 85 50" stroke="#FF2D46" stroke-width="22" stroke-linecap="butt"/>
  <polygon points="62,5 105,15 88,48" fill="#FF2D46"/>
</svg>
```

### Wordmark simplificado (texto puro — cuando no hay SVG disponible)

```html
<div style="font-family:var(--font-sans);font-size:20px;font-weight:900;letter-spacing:-0.02em;">
  <span style="color:#0F172A;">LOS </span><span style="color:#FF2D46;">CREATIVOS</span>
</div>
```

---

## Componentes en HTML — compatibles con sandbox

### Botón

```html
<style>
.btn {
  display: inline-flex; align-items: center; justify-content: center; gap: 8px;
  font-family: var(--font-sans); font-weight: var(--fw-bold);
  text-transform: uppercase; letter-spacing: 0.06em;
  border: 2px solid transparent; border-radius: var(--r-lg);
  cursor: pointer; text-decoration: none; white-space: nowrap;
  transition: background var(--t-base), box-shadow var(--t-base), transform var(--t-fast);
}
.btn:active { transform: scale(0.97); }
.btn-primary { background: var(--color-primary); color: #fff; padding: 12px 20px; font-size: 16px; box-shadow: var(--shadow-md); }
.btn-primary:hover { background: var(--color-primary-hover); box-shadow: var(--shadow-lg); }
.btn-secondary { background: var(--color-dark); color: #fff; padding: 12px 20px; font-size: 16px; }
.btn-outline { background: transparent; color: var(--color-dark); border-color: var(--color-border); padding: 12px 20px; font-size: 16px; }
.btn-sm { padding: 8px 16px; font-size: 14px; border-radius: var(--r-sm); }
.btn-lg { padding: 16px 32px; font-size: 16px; }
</style>

<button class="btn btn-primary">SOLICITAR CONSULTORÍA</button>
<button class="btn btn-secondary">Ver Casos</button>
<button class="btn btn-outline">Saber Más</button>
```

### Card

```html
<style>
.card {
  background: var(--color-surface);
  border: 1px solid var(--color-border);
  border-radius: var(--r-lg);
  padding: var(--sp-7);
  box-shadow: var(--shadow-sm);
  transition: box-shadow var(--t-slow), border-color var(--t-base), transform var(--t-slow);
}
.card-interactive { display: block; text-decoration: none; color: inherit; cursor: pointer; }
.card-interactive:hover { box-shadow: var(--shadow-md); border-color: rgba(255,45,70,.3); transform: translateY(-3px); }
.card-dark { background: #172233; border-color: rgba(255,255,255,.08); color: #fff; }
</style>

<div class="card">
  <h4 style="font-size:22px;font-weight:700;color:var(--color-text-strong);margin-bottom:12px;">Título</h4>
  <p style="font-size:14px;color:var(--color-text-muted);line-height:1.6;">Descripción del contenido de la card.</p>
</div>
```

### Badge

```html
<style>
.badge {
  display: inline-flex; align-items: center; gap: 4px;
  padding: 5px 10px; border-radius: var(--r-full);
  font-size: 12px; font-weight: var(--fw-bold); line-height: 1;
  border: 1px solid transparent; white-space: nowrap;
}
.badge-primary { background: var(--color-accent-bg); color: var(--color-primary); border-color: var(--color-border); }
.badge-dark    { background: var(--color-dark); color: #fff; }
.badge-success { background: var(--color-success-bg); color: var(--color-success); }
.badge-error   { background: var(--color-error-bg); color: var(--color-error); }
.badge-info    { background: var(--color-info-bg); color: var(--color-info); }
</style>

<span class="badge badge-primary">SEO</span>
<span class="badge badge-success">Activo</span>
<span class="badge badge-dark">Nuevo</span>
```

### Input

```html
<style>
.input-wrapper { display: flex; flex-direction: column; gap: 8px; }
.label { font-size: 14px; font-weight: var(--fw-bold); color: var(--color-text-strong); }
.input {
  width: 100%; height: 48px;
  background: var(--color-surface-soft);
  border: 1.5px solid var(--color-border);
  border-radius: var(--r-md);
  color: var(--color-text); font-size: 16px;
  padding: 0 14px; outline: none;
  transition: border-color var(--t-base), box-shadow var(--t-base);
}
.input::placeholder { color: var(--color-text-muted); }
.input:focus { border-color: var(--color-primary); box-shadow: 0 0 0 3px rgba(255,45,70,.12); }
</style>

<div class="input-wrapper">
  <label class="label" for="email">Correo electrónico</label>
  <input id="email" class="input" type="email" placeholder="tu@empresa.com" />
</div>
```

### Alert

```html
<style>
.alert {
  display: flex; gap: 12px; align-items: flex-start;
  padding: 14px 16px; border-radius: var(--r-md);
  border: 1px solid transparent; font-size: 14px; line-height: 1.6;
}
.alert-success { background: var(--color-success-bg); color: var(--color-success); border-color: rgba(22,163,74,.25); }
.alert-error   { background: var(--color-error-bg);   color: var(--color-error);   border-color: rgba(207,46,46,.25); }
.alert-info    { background: var(--color-info-bg);    color: var(--color-info);    border-color: rgba(37,99,235,.25); }
.alert-brand   { background: var(--color-accent-bg);  color: var(--color-primary); border-color: rgba(255,45,70,.2); }
</style>

<div class="alert alert-success" role="alert">
  <span>✓</span>
  <p>Los cambios han sido guardados exitosamente.</p>
</div>
```

---

## 5 prompts de ejemplo para invocar la skill

### Prompt 1 — Landing page completa

```
Usando el design system de Los Creativos (primary: #FF2D46, dark: #0F172A, 
font: Inter como sustituto de Satoshi, border-radius: 20px en botones y cards), 
crea un artifact HTML de una landing page para el servicio "SEO Técnico".
Debe incluir: nav sticky con logo inline SVG, sección hero con H1 + CTA + stat numbers, 
grid de 3 servicios con icon chips, sección de proceso (5 pasos), 
y footer claro de 3 columnas. Usa CSS custom properties del design system LC.
```

### Prompt 2 — Componente interactivo

```
Crea un artifact con el formulario de contacto de Los Creativos.
Design system: primary #FF2D46, dark #0F172A, border-radius inputs 15px, 
botones 20px. Campos: nombre, empresa, email, servicio (select), mensaje (textarea), 
checkbox de privacidad. Incluye validación en JS vanilla con estados de error visual 
(borde rojo #CF2E2E, hint de error) y estado de éxito con alert verde #16A34A.
```

### Prompt 3 — Dashboard / visualización de datos

```
Usando los colores de Los Creativos (primary: #FF2D46, dark: #0F172A, 
success: #16A34A, warning: #F59E0B), crea un artifact que muestre un 
dashboard de métricas SEO: 4 stat cards grandes (tráfico, keywords top3, 
backlinks, conversiones), una gráfica de barras CSS pura mostrando 
evolución mensual, y 3 cards de alertas semánticas (success/warning/info). 
Fondo #F9FAFB, cards blancas con sombra shadow-md.
```

### Prompt 4 — Presentación / slide

```
Crea un artifact tipo slide/presentación para Los Creativos.
Una sola pantalla visible (viewport height 100vh). 
Fondo #0B1628 (navy dark). Logo con SVG inline del isotipo rojo.
H1 en blanco 60px weight 900 uppercase con span rojo en la palabra clave.
3 stats en grid horizontal: +320% tráfico, 150+ empresas, 12 países.
Botón CTA rojo "SOLICITAR CONSULTORÍA". 
Usa la paleta exacta del design system LC.
```

### Prompt 5 — Style guide visual

```
Genera un artifact HTML que muestre el style guide visual de Los Creativos.
Secciones: 1) Paleta de colores (swatches con hex y nombre), 
2) Escala tipográfica (display a caption con los tamaños reales), 
3) Botones (4 variantes), 4) Badges (todas las variantes), 
5) Cards (básica, interactiva hover, dark, stat), 
6) Alerts (4 semánticas + brand).
Primary: #FF2D46, dark: #0F172A, font: Inter. 
Sin dependencias externas. Self-contained.
```

---

## Patrón base para cualquier artifact LC

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Los Creativos — [Nombre del artifact]</title>
  <style>
    /* PEGAR AQUÍ EL BLOQUE DE CSS VARIABLES DE ESTA SKILL */

    /* Estilos adicionales del componente */
  </style>
</head>
<body>

  <!-- CONTENIDO AQUÍ -->

  <script>
    // JavaScript vanilla — sin imports externos
  </script>
</body>
</html>
```
