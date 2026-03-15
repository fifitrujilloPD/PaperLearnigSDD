# UI Specification — codeCollection

Esta especificación define los **design tokens** y **reglas de UI** para codeCollection. Todos los diseños (Figma, etc.) y las implementaciones deben usar estos tokens para mantener consistencia visual y de comportamiento.

---

## 1. Principios de uso

- **Solo se usan tokens definidos aquí.** No se introducen colores, espaciados, radios ni tipografías fuera del sistema.
- **Los tokens semánticos tienen prioridad** sobre los globales cuando exista mapeo (ej. `semantic.states.error` en lugar de elegir un rojo a mano).
- **Los componentes referencian tokens** para border-radius, padding, tipografía y sombras; no valores fijos arbitrarios.

---

## 2. Global — Color

### 2.1 Brand Blue (primario)

| Token | Valor | Uso recomendado |
|-------|--------|-------------------|
| `global.color.brandBlue.50` | `#E8F2FA` | Fondos muy suaves, hover muy sutil |
| `global.color.brandBlue.100` | `#CFE4F3` | Fondos suaves, borders sutiles |
| `global.color.brandBlue.200` | `#A0C8E6` | Bordes, dividers |
| `global.color.brandBlue.300` | `#71ADD9` | Iconos secundarios, estados hover |
| `global.color.brandBlue.400` | `#428FCC` | Texto o iconos sobre fondos claros |
| `global.color.brandBlue.500` | `#1B73B5` | **Primario principal** (botones, links, elementos activos) |
| `global.color.brandBlue.600` | `#0C5A99` | Primario hover/pressed |
| `global.color.brandBlue.700` | `#003D6D` | Primario active, texto sobre claro |
| `global.color.brandBlue.800` | `#002F54` | Texto fuerte sobre claro |
| `global.color.brandBlue.900` | `#001F38` | Texto o fondos muy oscuros |
| `global.color.brandBlue.950` | `#001525` | Fondos más oscuros, contraste máximo |

**Regla:** El color principal de la marca (CTAs, links, selecciones) debe usar la escala `brandBlue`; el tono por defecto para acciones primarias es `500`; hover `600`; active/pressed `700`.

---

### 2.2 Neutral (grises, texto, fondos)

| Token | Valor | Uso recomendado |
|-------|--------|-------------------|
| `global.color.neutral.50` | `#F9FAFB` | Fondo de página |
| `global.color.neutral.100` | `#F2F4F7` | Fondos de sección, cards secundarias |
| `global.color.neutral.200` | `#EAECF0` | Bordes suaves, dividers |
| `global.color.neutral.300` | `#D0D5DD` | Bordes de inputs, iconos deshabilitados |
| `global.color.neutral.400` | `#98A2B3` | Placeholder, labels secundarios |
| `global.color.neutral.500` | `#667085` | Texto secundario |
| `global.color.neutral.600` | `#475467` | Texto terciario, labels |
| `global.color.neutral.700` | `#344054` | Texto body principal |
| `global.color.neutral.800` | `#1D2939` | Texto fuerte, títulos secundarios |
| `global.color.neutral.900` | `#101828` | **Títulos y texto principal** |
| `global.color.neutral.950` | `#0B1220` | Texto sobre fondos muy claros, máximo contraste |

**Regla:** Texto principal en `neutral.900` o `neutral.800`; cuerpo en `neutral.700`; secundario en `neutral.500`/`neutral.600`; placeholder en `neutral.400`. Fondos de UI en `neutral.50`/`neutral.100`; bordes en `neutral.200`/`neutral.300`.

---

### 2.3 Error

| Token | Valor | Uso recomendado |
|-------|--------|-------------------|
| `global.color.error.50` | `#FEF3F2` | Fondo sutil de mensajes de error |
| `global.color.error.100` | `#FEE4E2` | Fondos de alertas error |
| … | … | (escala 200–950 disponible) |
| `global.color.error.500` | `#F04438` | Iconos y texto de error |
| `global.color.error.600` | `#D92D20` | Botones destructivos, error hover |

**Regla:** Mensajes de error, validación de formularios y acciones destructivas usan la escala `error`. Para estados semánticos usar `semantic.states.error` (ver más abajo).

---

### 2.4 Success

| Token | Valor | Uso recomendado |
|-------|--------|-------------------|
| `global.color.success.50` | `#ECFDF3` | Fondo sutil éxito |
| `global.color.success.500` | `#12B76A` | Iconos, texto de éxito |
| `global.color.success.600` | `#079455` | Success hover, confirmaciones |

**Regla:** Confirmaciones, estados correctos y feedback positivo usan la escala `success`.

---

### 2.5 Warning

| Token | Valor | Uso recomendado |
|-------|--------|-------------------|
| `global.color.warning.50` | `#FFFAEB` | Fondo sutil advertencia |
| `global.color.warning.500` | `#F79009` | Iconos, texto de advertencia |
| `global.color.warning.600` | `#DC6803` | Warning hover |

**Regla:** Advertencias (no bloqueantes) y estados de atención usan la escala `warning`.

---

### 2.6 Secondary (Orange, Purple, Pink, Blue)

- **Orange** (`global.color.secondary.orange.*`): acentos secundarios; naranja principal `500` = `#F97316`.
- **Purple** (`global.color.secondary.purple.*`): acentos alternativos (ej. badges, tags).
- **Pink** (`global.color.secondary.pink.*`): acentos ocasionales.
- **Blue** (`global.color.secondary.blue.*`): variante azul no-brand (ej. info, links secundarios).

**Regla:** No sustituir `brandBlue` por `secondary.blue` en acciones primarias. Usar secondary para variedad en ilustraciones, badges o estados informativos.

---

## 3. Global — Spacing

| Token | Valor | Uso recomendado |
|-------|--------|-------------------|
| `global.spacing.0` | `0px` | Sin espacio |
| `global.spacing.4` | `4px` | Gaps mínimos entre icono y texto |
| `global.spacing.8` | `8px` | Entre elementos muy relacionados |
| `global.spacing.16` | `16px` | Padding interno de componentes, gaps estándar |
| `global.spacing.24` | `24px` | Entre secciones pequeñas, padding de cards |
| `global.spacing.32` | `32px` | Entre bloques de contenido |
| `global.spacing.40` | `40px` | Respiración entre secciones |
| `global.spacing.48` | `48px` | Separación de bloques grandes |
| `global.spacing.56` | `56px` | |
| `global.spacing.64` | `64px` | Separación máxima entre secciones |

**Regla:** La escala de espaciado es 4–8–16–24–32–40–48–56–64. Evitar valores intermedios (ej. 12px, 20px) salvo que se documente excepción. Gaps entre elementos relacionados: 8 o 16; entre secciones: 24 o 32.

---

## 4. Global — Radius

| Token | Valor | Uso recomendado |
|-------|--------|-------------------|
| `global.radius.0` | `0px` | Sin redondeo |
| `global.radius.4` | `4px` | Badges, chips pequeños |
| `global.radius.8` | `8px` | Inputs pequeños, avatares pequeños |
| `global.radius.12` | `12px` | **Botones, inputs, controles estándar** |
| `global.radius.16` | `16px` | Cards, modales |
| `global.radius.24` | `24px` | Modales grandes, containers destacados |

**Regla:** Botones e inputs usan `radius.12` por defecto (alineado con `components.button` y `components.input`). Cards y contenedores tipo card usan `radius.16`.

---

## 5. Global — Typography

### 5.1 Font family

| Token | Valor |
|-------|--------|
| `global.typography.fontFamily.sans` | `Inter, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial` |

**Regla:** Todo el texto de la UI usa esta familia. No introducir otras fuentes sin actualizar este token y la spec.

---

### 5.2 Scale (tamaño + peso + line-height)

Cada tamaño tiene cuatro variantes: **sm-regular** (400), **md-medium** (500), **lg-semibold** (600), **xl-bold** (700).

| Scale | Tamaño | Line-height | Uso típico |
|-------|--------|-------------|------------|
| **12** | 12px | 16px | Labels, captions, helper text, badges |
| **14** | 14px | 20px | Body pequeño, botones, inputs, tabla |
| **16** | 16px | 24px | Body estándar, títulos de card |
| **20** | 20px | 28px | Subtítulos |
| **24** | 24px | 32px | Títulos de sección |
| **32** | 32px | 40px | Títulos de página |
| **40** | 40px | 48px | Hero, títulos grandes |
| **56** | 56px | 64px | Display |

**Regla:** Usar solo combinaciones del scale (ej. `semantic.typography.14.md-medium` para labels de botón). No mezclar tamaños fuera de la escala (ej. 13px, 18px) salvo excepción documentada.

---

## 6. Global — Shadow

| Token | Valor | Uso recomendado |
|-------|--------|-------------------|
| `global.shadow.sm` | `0px 1px 2px 0px rgba(16,24,40,0.25)` | Cards, dropdowns ligeros |
| `global.shadow.md` | `0px 4px 10px 0px rgba(16,24,40,0.30)` | Modales, popovers |

**Regla:** No añadir sombras fuera de estas dos sin documentar. Cards usan `sm`; modales y popovers `md`.

---

## 7. Semantic — States

Estos tokens deben usarse para **estados de UI** (éxito, advertencia, error, foco) en lugar de elegir un color global a mano.

| Token | Valor | Uso |
|-------|--------|-----|
| `semantic.states.success.default` | `global.color.success.600` | Texto/icono de éxito |
| `semantic.states.success.subtleBg` | `global.color.success.50` | Fondo sutil éxito (banners, alerts) |
| `semantic.states.warning.default` | `global.color.warning.600` | Texto/icono advertencia |
| `semantic.states.warning.subtleBg` | `global.color.warning.50` | Fondo sutil advertencia |
| `semantic.states.error.default` | `global.color.error.600` | Texto/icono error, botón destructivo |
| `semantic.states.error.subtleBg` | `global.color.error.50` | Fondo sutil error (validación, alertas) |
| `semantic.states.focusRing.width` | `2px` | Grosor del anillo de foco |
| `semantic.states.focusRing.offset` | `2px` | Separación del anillo al borde del elemento |

**Regla:** Mensajes de error en formularios: texto en `error.default`, fondo del mensaje o borde en `error.subtleBg`. Todos los elementos focusables deben mostrar focus ring con `focusRing.width` y `focusRing.offset` (color coherente con marca, ej. brandBlue).

---

## 8. Semantic — Shadow

| Token | Valor | Uso |
|-------|--------|-----|
| `semantic.shadow.card` | `global.shadow.sm` | Cards |
| `semantic.shadow.popover` | `global.shadow.md` | Popovers, dropdowns, modales |

---

## 9. Semantic — Typography

Los tokens `semantic.typography.[size].[variant]` referencian la escala global (ej. `semantic.typography.14.md-medium` → escala 14, medium). Usar estos en componentes para mantener una sola fuente de verdad.

**Regla:** En Figma, asignar estilos de texto que coincidan con estos tokens (12/14/16/20/24/32/40/56 con regular/medium/semibold/bold y line-height indicado).

---

## 10. Components — Button

| Token | Valor | Regla |
|-------|--------|--------|
| `components.button.radius` | `global.radius.12` | Todos los botones usan radius 12px |
| `components.button.padding.x` | `global.spacing.16` | Padding horizontal 16px |
| `components.button.padding.y` | `global.spacing.8` | Padding vertical 8px |
| `components.button.height.sm` | 32px | Botón pequeño |
| `components.button.height.md` | 40px | Botón estándar |
| `components.button.height.lg` | 48px | Botón grande |
| `components.button.focus.ringWidth` | `semantic.states.focusRing.width` | 2px |
| `components.button.focus.ringOffset` | `semantic.states.focusRing.offset` | 2px |
| `components.button.labelTypography` | `semantic.typography.14.md-medium` | Texto del botón: 14px, medium |

**Reglas de UI:**
- Botón primario: fondo `brandBlue.500`, texto blanco; hover `brandBlue.600`; active `brandBlue.700`.
- Botón secundario/ghost: borde `neutral.300` o fondo `neutral.100`, texto `neutral.700`; hover fondo `neutral.200` o borde `neutral.400`.
- Botón destructivo: usar `semantic.states.error.default` para fondo o borde.
- Altura por defecto: `height.md` (40px). Respetar padding x/y para no deformar el hit area.

---

## 11. Components — Input

| Token | Valor | Regla |
|-------|--------|--------|
| `components.input.radius` | `global.radius.12` | Inputs con radius 12px |
| `components.input.padding.x` | `global.spacing.16` | Padding horizontal 16px |
| `components.input.padding.y` | `global.spacing.8` | Padding vertical 8px |
| `components.input.helperTextTypography` | `semantic.typography.12.sm-regular` | Texto de ayuda bajo el input: 12px, regular |
| `components.input.valueTypography` | `semantic.typography.14.md-medium` | Valor escrito: 14px, medium |

**Reglas de UI:**
- Borde default: `neutral.300`; focus: borde `brandBlue.500` y focus ring según `semantic.states.focusRing`.
- Placeholder: `neutral.400`; valor: `neutral.900` o `neutral.800`.
- Estado error: borde `error.500` o `error.600`; helper text en `error.default` y/o fondo `error.subtleBg` en el mensaje.
- Label encima del input: tipografía 14 medium o 12 medium según jerarquía; color `neutral.700` o `neutral.800`.

---

## 12. Components — Card

| Token | Valor | Regla |
|-------|--------|--------|
| `components.card.radius` | `global.radius.16` | Cards con radius 16px |
| `components.card.padding.default` | `global.spacing.24` | Padding estándar 24px |
| `components.card.padding.compact` | `global.spacing.16` | Versión compacta 16px |
| `components.card.shadow` | `semantic.shadow.card` | Sombra sm |
| `components.card.headerTypography` | `semantic.typography.16.lg-semibold` | Título de card: 16px, semibold |
| `components.card.bodyTypography` | `semantic.typography.14.sm-regular` | Cuerpo: 14px, regular |

**Reglas de UI:**
- Fondo de card: `neutral.50` o blanco sobre fondo `neutral.50`/`neutral.100`.
- Título de card en `neutral.900`; cuerpo en `neutral.700`. Opcional subtítulo en `neutral.600`.
- Separación entre header y body: al menos `spacing.8` o `spacing.16`.

---

## 13. Resumen de reglas UI

1. **Color:** Primario = brandBlue (500/600/700). Texto y fondos = neutral. Estados = semantic.states (success, warning, error). Focus = focusRing.
2. **Spacing:** Solo escala 0–64 en pasos definidos; preferir 8, 16, 24, 32 entre elementos y secciones.
3. **Radius:** Botones e inputs 12px; cards 16px; modales 16–24px.
4. **Typography:** Una sola familia (Inter + fallbacks). Solo escalas 12–56 con variantes sm/md/lg/xl.
5. **Shadow:** Solo sm (cards, listas) y md (modales, popovers).
6. **Componentes:** Button, Input y Card usan exclusivamente los tokens de `components.*`; no inventar padding, radius ni tipografía fuera de estos.

---

*Documento de referencia para diseño (Figma) e implementación. Cualquier cambio en tokens debe reflejarse aquí y en el sistema de diseño.*
