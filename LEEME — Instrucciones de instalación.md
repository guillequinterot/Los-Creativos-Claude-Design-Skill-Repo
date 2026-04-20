# Los Creativos — Design System 2026
## Instrucciones de instalación

---

## Estructura de esta carpeta

```
entregable/
├── claude-project/      → Subir a Claude.ai Project
└── skills/              → Instalar en Claude Code (equipo)
```

---

## 1. Carpeta `claude-project/` — Claude.ai Projects

Estos archivos van como **knowledge** en el Project de Claude.ai llamado "Los Creativos Design".

**Cómo subirlos:**
1. Ir a [claude.ai](https://claude.ai) → abrir el Project "Los Creativos Design"
2. Click en **"Add content"** → **"Upload files"**
3. Seleccionar **todos los archivos** de la carpeta `claude-project/` y la subcarpeta `components/`
4. Claude los indexará como contexto permanente del proyecto

**Archivos incluidos:**

| Archivo | Qué contiene |
|---|---|
| `design-tokens.json` | Tokens del sistema (colores, tipografía, spacing, radio, sombras) en formato W3C |
| `ui-kit.css` | Hoja de estilos completa con @font-face, variables CSS y 14 componentes |
| `style-guide.md` | Guía editorial del design system (colores, tipos, componentes, uso) |
| `conflicts.md` | Conflictos resueltos entre fuentes y hallazgos de Bricks Builder |
| `components/button.html` | Botones: 4 variantes × 3 tamaños, estados loading/disabled |
| `components/input.html` | Inputs, selects, textarea, checkbox/radio, validación |
| `components/card.html` | Cards: básica, interactiva, stat, dark, caso de éxito |
| `components/badge.html` | Badges: 7 variantes, dot, icon, category tags |
| `components/alert.html` | Alerts: success/warning/error/info/brand, dismissable, toast |
| `components/modal.html` | Modals: CTA, destructivo, informativo, formulario complejo |
| `components/nav.html` | Nav con megamenu real (3 columnas), mobile hamburger |
| `components/footer.html` | Footer canónico claro (5 columnas) + variante oscura |

---

## 2. Carpeta `skills/` — Claude Code Skills

Cada subcarpeta es una **skill** que se instala en Claude Code. Hay 3 skills con propósitos distintos.

### Descripción de cada skill

| Skill | Cuándo se activa | Para quién |
|---|---|---|
| `loscreativos-claude-code` | Al trabajar en código HTML/CSS/JS del sitio | Devs y Claude Code CLI |
| `loscreativos-claude-ai` | Al crear artifacts en Claude.ai | Equipo creativo |
| `loscreativos-claude-design` | Al pedir piezas visuales o decisiones de diseño | Todo el equipo |

### Cómo instalar (cada miembro del equipo)

**Opción A — Skill a nivel de usuario** (disponible en todos los proyectos):
```
~/.claude/skills/loscreativos-claude-code/SKILL.md
~/.claude/skills/loscreativos-claude-ai/SKILL.md
~/.claude/skills/loscreativos-claude-design/SKILL.md
```

En Windows la ruta es:
```
C:\Users\[nombre]\AppData\Roaming\claude\skills\
```

**Opción B — Skill a nivel de proyecto** (solo en este proyecto):
Copiar la carpeta `skills/` dentro de la carpeta `.claude/` del proyecto:
```
[tu-proyecto]/.claude/skills/loscreativos-claude-code/SKILL.md
```

**Pasos concretos:**
1. Abrir terminal
2. Copiar la carpeta de la skill a la ruta correcta:
   ```bash
   cp -r skills/loscreativos-claude-code ~/.claude/skills/
   cp -r skills/loscreativos-claude-ai ~/.claude/skills/
   cp -r skills/loscreativos-claude-design ~/.claude/skills/
   ```
3. Reiniciar Claude Code
4. Verificar con `/skills` en Claude Code — deben aparecer las 3 skills de LC

---

## Resumen rápido

```
claude-project/  →  claude.ai → Project → Add content → Upload files
skills/          →  ~/.claude/skills/ en cada computador del equipo
```

---

*Design System generado con Claude Code — Los Creativos 2026*
