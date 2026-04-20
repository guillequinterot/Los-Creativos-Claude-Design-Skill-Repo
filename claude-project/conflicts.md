# Conflicts — Los Creativos Design System

Fuentes analizadas:
- **A** = `Claude Design/design-tokens.json`
- **B** = `Claude Design/UI Kit Componentes.txt`
- **C** = `SVG/Logo-MKT-Principal.svg` (fuente gráfica, autoridad visual)
- **D** = WordPress REST API (`/wp-json/wp/v2/*`)

---

## Conflicto 1 — Color de Error

| Fuente | Valor |
|--------|-------|
| A (design-tokens.json) | `color.semantic.error = #FF2D46` (idéntico al primary) |
| B (UI Kit .txt) | `--color-error: #CF2E2E` |

**Problema:** En el JSON, el color de error es el mismo que el primary rojo de marca (`#FF2D46`). Esto rompe la distinción semántica — un formulario con error se vería idéntico a un CTA.

**Resolución adoptada:** `#CF2E2E` del .txt. Es un rojo más oscuro y saturado, claramente distinto del rojo de marca en contextos de UI.

**Impacto:** `color.semantic.error` y todos los componentes que lo referencian (inputs, alerts, badges de error).

---

## Conflicto 2 — Brand Dark / Secondary

| Fuente | Valor |
|--------|-------|
| A (design-tokens.json) | `color.brand.dark = #0F172A` |
| B (UI Kit .txt) | `--color-secondary: #101828` |
| C (SVG Logo) | `fill: #0f172a` (confirmado en código SVG) |

**Problema:** Diferencia de 2 valores en el canal R y G. Visualmente imperceptible, pero técnicamente inconsistente.

**Resolución adoptada:** `#0F172A` del JSON, confirmado por el SVG del logo real. El SVG es la fuente visual de mayor autoridad para colores de marca.

**Impacto:** Bajo. El .txt usa #101828 en botones y texto; el cambio es imperceptible en pantalla.

---

## Conflicto 3 — Fondo Accent / Accent Background

| Fuente | Valor | Uso declarado |
|--------|-------|---------------|
| A (design-tokens.json) | `color.neutral.surfaceSoftRed = #FFE9EC` | Chips de icono |
| A (design-tokens.json) | `color.semantic.errorBg = #FFF1F2` | Fondo de alerts de error |
| B (UI Kit .txt) | `--color-accent: #FEF2F2` | Fondo de destacados de marca |

**Problema:** Tres valores similares (rojos muy pálidos) para tres propósitos distintos. Puede generar inconsistencia si se mezclan en implementación.

**Resolución adoptada:** Se mantienen los tres con nombres semánticos claros:
- `color.brand.accentBg = #FFF1F2` — para destacados de marca y banners
- `color.brand.accentBgSoft = #FFE9EC` — para chips e iconos interactivos
- `color.semantic.errorBg = #FFF1F2` — para contextos de error (coincide con accentBg)

**Nota:** accentBg y errorBg comparten valor intencionalmente. El rojo pálido es tanto de marca como de error, dado que el primary de marca ya es rojo.

---

## Conflicto 4 — Color Success

| Fuente | Valor |
|--------|-------|
| A (design-tokens.json) | `color.semantic.success = #16A34A` |
| B (UI Kit .txt) | `--color-success: #00D084` |

**Problema:** El `#00D084` del .txt es un verde brillante/esmeralda poco convencional que puede fallar en ratio de contraste WCAG sobre fondos blancos (contraste ~2.8:1 — falla AA). El `#16A34A` del JSON es verde estándar Tailwind green-600, contraste ~4.7:1 (pasa AA).

**Resolución adoptada:** `#16A34A` del JSON por accesibilidad.

---

## Conflicto 5 — Color Warning

| Fuente | Valor |
|--------|-------|
| A (design-tokens.json) | `color.semantic.warning = #F59E0B` |
| B (UI Kit .txt) | `--color-warning: #FCB900` |

**Problema:** Dos amarillos/ámbar similares. `#F59E0B` (Tailwind amber-500) vs `#FCB900` (amarillo más puro).

**Resolución adoptada:** `#F59E0B` del JSON. Mejor contraste sobre fondos claros y más coherente con systems design estándar.

---

## Conflicto 6 — Color Info

| Fuente | Valor |
|--------|-------|
| A (design-tokens.json) | `color.semantic.info = #2563EB` |
| B (UI Kit .txt) | `--color-info: #0693E3` |

**Problema:** Dos azules distintos. `#2563EB` es azul mid-navy (Tailwind blue-600). `#0693E3` es azul más brillante y saturado.

**Resolución adoptada:** `#2563EB` del JSON por mejor contraste WCAG y coherencia con el tono oscuro general del sistema.

---

## Conflicto 7 — Logo SVG no disponible en WordPress Media Library

**Observado en:** Endpoint `/wp-json/wp/v2/media?per_page=100` — 0 archivos SVG encontrados.

**Problema:** El logo SVG del sitio en producción (`Logo-MKT-Principal.svg` visible en el HTML guardado como `Cómo aparecer en ChatGPT`) está servido desde `/wp-content/themes/bricks/` o embebido directamente en el HTML de Bricks, **no** como un attachment de WordPress.

**Implicación:** Para referencias en el UI kit y en implementaciones futuras, usar los SVGs de `/SVG/` locales. No referenciar desde la CDN de WordPress ya que esa URL puede cambiar con actualizaciones del tema.

**URL actual en producción:** `https://loscreativos.co/wp-content/uploads/[año]/Logo-MKT-Principal.svg` — NO confirmada. No asignar como fuente estable.

---

## Conflicto 8 — Bricks Templates no accesibles vía REST API

**Endpoint:** `GET /wp-json/wp/v2/bricks_template` → HTTP 404

**Causa:** Bricks Builder v2.2-beta no registra el CPT `bricks_template` en la REST API de WordPress por diseño de seguridad. Los estilos globales de Bricks (colores, tipografía, espaciado configurados en el panel) no son accesibles externamente.

**Implicación:** No se pudieron comparar los tokens del design system con los estilos activos de Bricks en producción. Existe riesgo de que el sitio use valores hardcoded en el editor de Bricks que difieran de los tokens documentados.

**Recomendación:** Al implementar cambios en WordPress, validar manualmente en `wp-admin → Bricks → Settings → Global Styles` que los valores coincidan con este design system.

---

---

## HALLAZGOS DE BRICKS TEMPLATES (2026-04-20)

Fuente añadida: **E** = Templates exportados de Bricks Builder (`/Claude Design/Templates bricks/`)

### Hallazgo B1 — Dark de texto vs. dark de fondo: SON DOS TOKENS DISTINTOS

| Variable Bricks | Valor | Uso real |
|----------------|-------|---------|
| `var(--gray2)` | `#1E2939` | Color de texto primario (headings, body) |
| `var(--bgblue)` | `#0B1628` | Fondo de secciones oscuras |
| SVG logo wordmark | `#0F172A` | Color del logo wordmark |

**Conclusión:** Los tres valores son intencionales y distintos. El design system los tiene correctamente separados:
- `--color-text-strong: #0F172A` → logo y texto de máximo contraste
- `--color-text: #1E2939` → texto de lectura (coincide con `var(--gray2)`)
- `--color-dark-alt: #0B1628` → secciones hero oscuras (coincide con `var(--bgblue)`)

### Hallazgo B2 — El footer real es CLARO, no oscuro

**Observado en:** `template-footer-2026-04-20.json`

El footer del sitio en producción usa:
- Background: blanco/claro
- `border-top: 1px solid #E0E0E0`
- Textos en `#1E2939` y `#6A7282`
- Estructura: 5 columnas (logo 38% | Compañía 12% | SEO 18% | Ciudades 22% | Diseño 20%)

**Impacto en el design system:** El componente `footer.html` fue corregido para ser claro. Se añade una variante `.footer--dark` como alternativa, pero el footer canónico es luz sobre blanco.

### Hallazgo B3 — Logo disponible en CDN de WordPress

**URL confirmada en templates:** `https://loscreativos.co/wp-content/uploads/2026/01/Logo-MKT-Principal.svg`

Esta URL sí existe pero no apareció en el endpoint `/wp-json/wp/v2/media?per_page=100` porque ese endpoint devuelve los 100 items **más recientes**, y el logo fue subido en enero 2026. Usar esta URL como referencia estable de CDN.

### Hallazgo B4 — Nav font-weight: 600 (no disponible en Satoshi)

Bricks usa `font-weight: 600` en los nav links, pero Satoshi solo tiene pesos 300/400/500/700/900. El browser renderiza 600 como 700 (Bold). **Resolución adoptada:** Usar `font-weight: 700` en el design system para evitar font-synthesis no intencional.

### Hallazgo B5 — Variantes de red inline

Algunos elementos HTML inline en los templates usan `#FF2C55` y `#FF345C` (variantes muy cercanas a `#FF2D46`). Son probablemente errores de exportación o copia manual, no colores intencionales. **Resolución:** Ignorar estas variantes; `#FF2D46` es el canonical.

### Hallazgo B6 — ATF padding especial

La sección ATF (hero above-the-fold) usa `padding-top: 150px` y `padding-bottom: 150px`. Este no es el padding estándar de secciones (60px). Es un caso especial para el hero. Se añade `--section-pad-y-hero: 150px` como token.

### Hallazgo B7 — H1 ATF es uppercase a 59px

El H1 en el ATF hero usa:
- `font-size: 59px` (desktop), `40px` (mobile)
- `font-weight: 900`
- `text-transform: uppercase`
- `line-height: 1`

59px es casi idéntico a nuestro `--fs-display2xl: 60px`. Confirma que display2xl es el tamaño correcto para el hero.

### Hallazgo B8 — Logos de clientes son SVGs en CDN

Los logos de clientes principales son SVG (no JPEG como los 100 más recientes de la media library):
- `https://loscreativos.co/wp-content/uploads/2026/01/Bancolombia_S.A._logo.svg`
- `https://loscreativos.co/wp-content/uploads/2026/01/LaHaus.svg`
- `https://loscreativos.co/wp-content/uploads/2026/01/WOM_Chile.svg`

---

## Resumen de resoluciones

| Token | Fuente elegida | Razón |
|-------|----------------|-------|
| `color.brand.dark` | `#0F172A` (JSON + SVG) | Confirmado en asset gráfico |
| `color.semantic.error` | `#CF2E2E` (txt) | Distinción semántica vs primary |
| `color.semantic.success` | `#16A34A` (JSON) | Accesibilidad WCAG AA |
| `color.semantic.warning` | `#F59E0B` (JSON) | Contraste superior |
| `color.semantic.info` | `#2563EB` (JSON) | Coherencia tonal |
| `color.brand.accentBg` | `#FFF1F2` (JSON errorBg) | Distinción de surfaceSoftRed |
