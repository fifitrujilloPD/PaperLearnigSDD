# UI Specification — codeCollection

Esta especificación define los **design tokens** y **reglas de UI** para codeCollection. Todos los diseños (Figma, etc.) y las implementaciones deben usar estos tokens para mantener consistencia visual y de comportamiento.

> **Fuente de verdad:** `Ligth mode.tokens.json` exportado de Figma. Cualquier cambio en tokens debe reflejarse aquí y en el sistema de diseño.

---

## 1. Principios de uso

- **Solo se usan tokens definidos aquí.** No se introducen colores, espaciados, radios ni tipografías fuera del sistema.
- **Los tokens semánticos tienen prioridad** sobre los globales cuando exista mapeo (ej. `semantic.color.text-error` en lugar de elegir un rojo a mano).
- **Los componentes referencian tokens** para border-radius, padding, tipografía y sombras; no valores fijos arbitrarios.
- **Light mode es el modo por defecto.** Los tokens de dark mode se documentan para futura implementación.

---

## 2. Global — Color

### 2.1 Brand Blue (primario)

| Token | Valor | Uso recomendado |
|-------|--------|-------------------|
| `global.color.brandBlue.50` | `#E8F2FA` | Fondos muy suaves, hover muy sutil, bg-brand-ships |
| `global.color.brandBlue.100` | `#CFE4F3` | Fondos suaves, border-brand |
| `global.color.brandBlue.200` | `#A0C8E6` | Bordes, dividers |
| `global.color.brandBlue.300` | `#71ADD9` | Iconos secundarios, estados hover |
| `global.color.brandBlue.400` | `#428FCC` | Texto o iconos sobre fondos claros |
| `global.color.brandBlue.500` | `#1B73B5` | Links, elementos activos secundarios |
| `global.color.brandBlue.600` | `#0C5A99` | Button hover |
| `global.color.brandBlue.700` | `#003D6D` | **Button color, button press, bg-brand-color, text-primary-brand** |
| `global.color.brandBlue.800` | `#002F54` | Texto fuerte sobre claro |
| `global.color.brandBlue.900` | `#001F38` | Texto o fondos muy oscuros |
| `global.color.brandBlue.950` | `#001525` | Fondos más oscuros, contraste máximo |

**Regla:** El color principal de la marca (CTAs, botones, textos de marca) debe usar la escala `brandBlue`; el tono por defecto para **botones primarios** es `700`; hover `600`; active/pressed `700`.

---

### 2.2 Neutral (grises, texto, fondos)

| Token | Valor | Uso recomendado |
|-------|--------|-------------------|
| `global.color.neutral.50` | `#F9FAFB` | Fondo de página (bg-primary) |
| `global.color.neutral.100` | `#F2F4F7` | Fondos de sección, button-disabled |
| `global.color.neutral.200` | `#EAECF0` | Bordes suaves, dividers, border-secondary |
| `global.color.neutral.300` | `#D0D5DD` | Bordes de inputs (border-primary), iconos deshabilitados |
| `global.color.neutral.400` | `#98A2B3` | Placeholder, text-disabled |
| `global.color.neutral.500` | `#667085` | Texto secundario |
| `global.color.neutral.600` | `#475467` | Texto terciario (text-tertiary), labels |
| `global.color.neutral.700` | `#344054` | Texto body principal (text-secondary) |
| `global.color.neutral.800` | `#1D2939` | Texto fuerte, títulos secundarios |
| `global.color.neutral.900` | `#101828` | Títulos y texto fuerte |
| `global.color.neutral.950` | `#0B1220` | **Texto principal (text-primary)**, máximo contraste |

**Regla:** Texto principal en `neutral.950`; body en `neutral.700`; terciario en `neutral.600`; disabled/placeholder en `neutral.400`. Fondos de UI en `neutral.50`/`neutral.100`; bordes en `neutral.200`/`neutral.300`.

---

### 2.3 Error

| Token | Valor | Uso recomendado |
|-------|--------|-------------------|
| `global.color.error.50` | `#FEF3F2` | Fondo sutil error (bg-error) |
| `global.color.error.100` | `#FEE4E2` | Fondos de alertas error |
| `global.color.error.200` | `#FECDCA` | Border error |
| `global.color.error.300` | `#FDA29B` | Bordes error hover |
| `global.color.error.400` | `#F97066` | Iconos error light |
| `global.color.error.500` | `#F04438` | Iconos y texto de error |
| `global.color.error.600` | `#D92D20` | **Text-error**, botones destructivos |
| `global.color.error.700` | `#B42318` | Error active/pressed |
| `global.color.error.800` | `#912018` | Error dark |
| `global.color.error.900` | `#7A271A` | Error muy oscuro |
| `global.color.error.950` | `#55160C` | Error máximo contraste |

**Regla:** Mensajes de error, validación de formularios y acciones destructivas usan la escala `error`. Texto de error: `600`; fondo sutil: `50`; borde: `200`.

---

### 2.4 Success

| Token | Valor | Uso recomendado |
|-------|--------|-------------------|
| `global.color.success.50` | `#ECFDF3` | Fondo sutil éxito (bg-success) |
| `global.color.success.100` | `#D1FADF` | Fondos de alertas éxito |
| `global.color.success.200` | `#A6F4C5` | Border success |
| `global.color.success.300` | `#6CE9A6` | Bordes success hover |
| `global.color.success.400` | `#32D583` | Iconos success light |
| `global.color.success.500` | `#12B76A` | Iconos y texto de éxito |
| `global.color.success.600` | `#079455` | **Text-success**, confirmaciones |
| `global.color.success.700` | `#067647` | Success active |
| `global.color.success.800` | `#085D3A` | Success dark |
| `global.color.success.900` | `#074D31` | Success muy oscuro |
| `global.color.success.950` | `#052E1C` | Success máximo contraste |

**Regla:** Confirmaciones, estados correctos y feedback positivo usan la escala `success`. Texto: `600`; fondo sutil: `50`; borde: `200`.

---

### 2.5 Warning

| Token | Valor | Uso recomendado |
|-------|--------|-------------------|
| `global.color.warning.50` | `#FFFAEB` | Fondo sutil advertencia (bg-warning) |
| `global.color.warning.100` | `#FEF0C7` | Fondos de alertas warning |
| `global.color.warning.200` | `#FEDF89` | Border warning |
| `global.color.warning.300` | `#FEC84B` | Bordes warning hover |
| `global.color.warning.400` | `#FDB022` | Iconos warning light |
| `global.color.warning.500` | `#F79009` | Iconos y texto de advertencia |
| `global.color.warning.600` | `#DC6803` | **Text-warning**, warning hover |
| `global.color.warning.700` | `#B54708` | Warning active |
| `global.color.warning.800` | `#93370D` | Warning dark |
| `global.color.warning.900` | `#7A2E0E` | Warning muy oscuro |
| `global.color.warning.950` | `#4E1D09` | Warning máximo contraste |

**Regla:** Advertencias (no bloqueantes) y estados de atención usan la escala `warning`. Texto: `600`; fondo sutil: `50`; borde: `200`.

---

### 2.6 Secondary (Orange, Purple, Pink, Blue, Brown)

#### Orange (`global.color.secondary.orange.*`)

| Token | Valor |
|-------|--------|
| `.50` | `#FFF3ED` |
| `.100` | `#FFE4D5` |
| `.200` | `#FFCAA8` |
| `.300` | `#FDAA74` |
| `.400` | `#FB8247` |
| `.500` | `#F97316` |
| `.600` | `#EF6820` |
| `.700` | `#C44C11` |
| `.800` | `#9C3C13` |
| `.900` | `#7E2F12` |
| `.950` | `#4A1A0A` |

#### Purple (`global.color.secondary.purple.*`)

| Token | Valor |
|-------|--------|
| `.50` | `#F4F3FF` |
| `.100` | `#EBE9FE` |
| `.200` | `#D9D6FE` |
| `.300` | `#BDB4FE` |
| `.400` | `#9B8AFB` |
| `.500` | `#7A5AF8` |
| `.600` | `#6938EF` |
| `.700` | `#5925DC` |
| `.800` | `#4A1FB8` |
| `.900` | `#3E1C96` |
| `.950` | `#27115F` |

#### Pink (`global.color.secondary.pink.*`)

| Token | Valor |
|-------|--------|
| `.50` | `#FDF2FA` |
| `.100` | `#FCE7F6` |
| `.200` | `#FCCEEE` |
| `.300` | `#FAA7E0` |
| `.400` | `#F670C7` |
| `.500` | `#EE46BC` |
| `.600` | `#DD2590` |
| `.700` | `#C11574` |
| `.800` | `#9E165F` |
| `.900` | `#851651` |
| `.950` | `#4D0A2E` |

#### Blue (`global.color.secondary.blue.*`)

| Token | Valor |
|-------|--------|
| `.50` | `#EFF8FF` |
| `.100` | `#D1E9FF` |
| `.200` | `#B2DDFF` |
| `.300` | `#84CAFF` |
| `.400` | `#53B1FD` |
| `.500` | `#2E90FA` |
| `.600` | `#1570EF` |
| `.700` | `#175CD3` |
| `.800` | `#1849A9` |
| `.900` | `#194185` |
| `.950` | `#102A56` |

#### Brown (`global.color.secondary.brown.*`)

| Token | Valor |
|-------|--------|
| `.50` | `#ECE4D9` |
| `.100` | `#ECE4D9` |
| `.200` | `#D7C7B0` |
| `.300` | `#C3A886` |
| `.400` | `#B5916A` |
| `.500` | `#AC7F5E` |
| `.600` | `#94634B` |
| `.700` | `#7C4F41` |
| `.800` | `#674139` |
| `.900` | `#563631` |
| `.950` | `#2F1C19` |

**Regla:** No sustituir `brandBlue` por `secondary.blue` en acciones primarias. Usar secondary para variedad en ilustraciones, badges, tags o estados informativos. Brown puede usarse para acentos cálidos.

---

## 3. Semantic — Color Aliases (Light Mode)

Estos tokens son los **alias semánticos** que se usan en diseño e implementación. Referencian los tokens globales y son la capa que cambia entre light y dark mode.

### 3.1 Background

| Token | Referencia | Valor resuelto | Uso |
|-------|------------|----------------|-----|
| `semantic.bg.primary` | `neutral.50` | `#F9FAFB` | Fondo principal de página |
| `semantic.bg.container` | — | `#FFFFFF` | Cards, sidebars, contenedores |
| `semantic.bg.brandColor` | `brandBlue.700` | `#003D6D` | Fondos de marca (hero, banners) |
| `semantic.bg.brandChips` | `brandBlue.50` | `#E8F2FA` | Chips, badges de marca |
| `semantic.bg.error` | `error.50` | `#FEF3F2` | Fondo de alertas error |
| `semantic.bg.warning` | `warning.50` | `#FFFAEB` | Fondo de alertas warning |
| `semantic.bg.success` | `success.50` | `#ECFDF3` | Fondo de alertas success |

### 3.2 Text

| Token | Referencia | Valor resuelto | Uso |
|-------|------------|----------------|-----|
| `semantic.text.primary` | `neutral.950` | `#0B1220` | Títulos y texto principal |
| `semantic.text.secondary` | `neutral.700` | `#344054` | Body, texto descriptivo |
| `semantic.text.tertiary` | `neutral.600` | `#475467` | Labels, captions |
| `semantic.text.disabled` | `neutral.400` | `#98A2B3` | Placeholder, texto deshabilitado |
| `semantic.text.primaryBrand` | `brandBlue.700` | `#003D6D` | Texto de marca sobre claro |
| `semantic.text.primaryWhite` | — | `#FFFFFF` | Texto sobre fondos oscuros/brand |
| `semantic.text.error` | `error.600` | `#D92D20` | Texto de error |
| `semantic.text.warning` | `warning.600` | `#DC6803` | Texto de advertencia |
| `semantic.text.success` | `success.600` | `#079455` | Texto de éxito |

### 3.3 Button

| Token | Referencia | Valor resuelto | Uso |
|-------|------------|----------------|-----|
| `semantic.button.color` | `brandBlue.700` | `#003D6D` | Fondo botón primario |
| `semantic.button.hover` | `brandBlue.600` | `#0C5A99` | Fondo botón hover |
| `semantic.button.press` | `brandBlue.700` | `#003D6D` | Fondo botón pressed |
| `semantic.button.disabled` | `neutral.100` | `#F2F4F7` | Fondo botón deshabilitado |

### 3.4 Border

| Token | Referencia | Valor resuelto | Uso |
|-------|------------|----------------|-----|
| `semantic.border.primary` | `neutral.300` | `#D0D5DD` | Bordes de inputs, controles |
| `semantic.border.secondary` | `neutral.200` | `#EAECF0` | Dividers, bordes suaves |
| `semantic.border.tertiary` | `neutral.100` | `#F2F4F7` | Bordes muy sutiles |
| `semantic.border.disabled` | `neutral.100` | `#F2F4F7` | Bordes deshabilitados |
| `semantic.border.brand` | `brandBlue.100` | `#CFE4F3` | Bordes de marca |
| `semantic.border.error` | `error.200` | `#FECDCA` | Bordes de error |
| `semantic.border.warning` | `warning.200` | `#FEDF89` | Bordes de warning |
| `semantic.border.success` | `success.200` | `#A6F4C5` | Bordes de success |

---

## 4. Semantic — Color Aliases (Dark Mode)

> Para futura implementación. Los alias cambian de referencia pero mantienen los mismos nombres de token.

### 4.1 Background (Dark)

| Token | Referencia | Valor resuelto |
|-------|------------|----------------|
| `semantic.bg.primary` | `neutral.950` | `#0B1220` |
| `semantic.bg.container` | `neutral.900` | `#101828` |
| `semantic.bg.brandColor` | `brandBlue.700` | `#003D6D` |
| `semantic.bg.brandChips` | `brandBlue.900` | `#001F38` |
| `semantic.bg.error` | `error.950` | `#55160C` |
| `semantic.bg.warning` | `warning.950` | `#4E1D09` |
| `semantic.bg.success` | `success.950` | `#052E1C` |

### 4.2 Text (Dark)

| Token | Referencia | Valor resuelto |
|-------|------------|----------------|
| `semantic.text.primary` | `neutral.50` | `#F9FAFB` |
| `semantic.text.secondary` | `neutral.300` | `#D0D5DD` |
| `semantic.text.tertiary` | `neutral.400` | `#98A2B3` |
| `semantic.text.disabled` | `neutral.500` | `#667085` |
| `semantic.text.primaryBrand` | `neutral.50` | `#F9FAFB` |
| `semantic.text.primaryWhite` | — | `#FFFFFF` |
| `semantic.text.error` | `error.400` | `#F97066` |
| `semantic.text.warning` | `warning.400` | `#FDB022` |
| `semantic.text.success` | `success.400` | `#32D583` |

### 4.3 Button (Dark)

| Token | Referencia | Valor resuelto |
|-------|------------|----------------|
| `semantic.button.color` | `brandBlue.700` | `#003D6D` |
| `semantic.button.hover` | `brandBlue.600` | `#0C5A99` |
| `semantic.button.press` | `brandBlue.700` | `#003D6D` |
| `semantic.button.disabled` | `neutral.700` | `#344054` |

### 4.4 Border (Dark)

| Token | Referencia | Valor resuelto |
|-------|------------|----------------|
| `semantic.border.primary` | `neutral.500` | `#667085` |
| `semantic.border.secondary` | `neutral.600` | `#475467` |
| `semantic.border.tertiary` | `neutral.700` | `#344054` |
| `semantic.border.disabled` | `neutral.700` | `#344054` |
| `semantic.border.brand` | `brandBlue.400` | `#428FCC` |
| `semantic.border.error` | `error.400` | `#F97066` |
| `semantic.border.warning` | `warning.400` | `#FDB022` |
| `semantic.border.success` | `success.400` | `#32D583` |

---

## 5. Global — Spacing

| Token | Valor | Uso recomendado |
|-------|--------|-------------------|
| `global.spacing.0` | `0px` | Sin espacio |
| `global.spacing.4` | `4px` | Gaps mínimos entre icono y texto |
| `global.spacing.8` | `8px` | Entre elementos muy relacionados, padding botones |
| `global.spacing.10` | `10px` | Gap top/bottom button md |
| `global.spacing.12` | `12px` | Gap top/bottom button lg, padding input, gap left/right button sm/md |
| `global.spacing.14` | `14px` | Gap top/bottom button xl |
| `global.spacing.16` | `16px` | Gap left/right button lg, gaps estándar |
| `global.spacing.24` | `24px` | Gap left/right button xl, padding de cards |
| `global.spacing.32` | `32px` | Entre bloques de contenido |
| `global.spacing.40` | `40px` | Respiración entre secciones |
| `global.spacing.48` | `48px` | Separación de bloques grandes |
| `global.spacing.56` | `56px` | |
| `global.spacing.64` | `64px` | Separación máxima entre secciones |

**Regla:** La escala de espaciado es 0–4–8–10–12–14–16–24–32–40–48–56–64. Gaps entre elementos relacionados: 8 o 16; entre secciones: 24 o 32. Los valores 10, 12 y 14 se usan principalmente en padding de componentes (botones, inputs).

---

## 6. Global — Radius

| Token | Valor | Uso recomendado |
|-------|--------|-------------------|
| `global.radius.0` | `0px` | Sin redondeo |
| `global.radius.4` | `4px` | Badges, chips pequeños |
| `global.radius.8` | `8px` | **Botones, inputs, controles estándar** |
| `global.radius.10` | `10px` | Controles intermedios |
| `global.radius.12` | `12px` | Cards compactas, controles destacados |
| `global.radius.16` | `16px` | Cards, modales |
| `global.radius.24` | `24px` | Modales grandes, containers destacados |

**Regla:** Botones e inputs usan `radius.8` por defecto (alineado con `components.button` y `components.input`). Cards y contenedores tipo card usan `radius.16`.

---

## 7. Global — Typography

### 7.1 Font family

| Token | Valor |
|-------|--------|
| `global.typography.fontFamily.primary` | `Roboto, system-ui, -apple-system, Segoe UI, Helvetica, Arial, sans-serif` |

**Regla:** Todo el texto de la UI usa Roboto como familia principal. No introducir otras fuentes sin actualizar este token y la spec.

---

### 7.2 Scale (tamaño + peso + line-height)

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

## 8. Global — Shadow

| Token | Valor | Uso recomendado |
|-------|--------|-------------------|
| `global.shadow.sm` | `0px 1px 2px 0px rgba(16,24,40,0.25)` | Cards, dropdowns ligeros |
| `global.shadow.md` | `0px 4px 10px 0px rgba(16,24,40,0.30)` | Modales, popovers |

**Regla:** No añadir sombras fuera de estas dos sin documentar. Cards usan `sm`; modales y popovers `md`.

---

## 9. Semantic — States

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

## 10. Semantic — Shadow

| Token | Valor | Uso |
|-------|--------|-----|
| `semantic.shadow.card` | `global.shadow.sm` | Cards |
| `semantic.shadow.popover` | `global.shadow.md` | Popovers, dropdowns, modales |

---

## 11. Semantic — Typography

Los tokens `semantic.typography.[size].[variant]` referencian la escala global (ej. `semantic.typography.14.md-medium` → escala 14, medium). Usar estos en componentes para mantener una sola fuente de verdad.

**Regla:** En Figma, asignar estilos de texto que coincidan con estos tokens (12/14/16/20/24/32/40/56 con regular/medium/semibold/bold y line-height indicado).

---

## 12. Components — Button

### 12.1 Radius y estructura

| Token | Valor | Regla |
|-------|--------|--------|
| `components.button.radius` | `global.radius.8` | Todos los botones usan radius **8px** |

### 12.2 Padding por tamaño

| Size | Padding (sm) | Gap top | Gap bottom | Gap left | Gap right |
|------|-------------|---------|------------|----------|-----------|
| **sm** | `spacing.8` | `spacing.8` | `spacing.8` | `spacing.12` | `spacing.12` |
| **md** | `spacing.8` | `spacing.10` | `spacing.10` | `spacing.12` | `spacing.12` |
| **lg** | `spacing.8` | `spacing.12` | `spacing.12` | `spacing.16` | `spacing.16` |
| **xl** | `spacing.8` | `spacing.14` | `spacing.14` | `spacing.24` | `spacing.24` |

### 12.3 Focus

| Token | Valor |
|-------|--------|
| `components.button.focus.ringWidth` | `semantic.states.focusRing.width` (2px) |
| `components.button.focus.ringOffset` | `semantic.states.focusRing.offset` (2px) |

### 12.4 Tipografía

| Token | Valor |
|-------|--------|
| `components.button.labelTypography` | `semantic.typography.14.md-medium` (14px, medium) |

**Reglas de UI:**
- Botón primario: fondo `semantic.button.color` (brandBlue.700 `#003D6D`), texto blanco; hover `semantic.button.hover` (brandBlue.600 `#0C5A99`); active `semantic.button.press` (brandBlue.700).
- Botón deshabilitado: fondo `semantic.button.disabled` (neutral.100 `#F2F4F7`), texto `semantic.text.disabled`.
- Botón secundario/ghost: borde `semantic.border.primary` (neutral.300) o fondo `neutral.100`, texto `semantic.text.secondary`.
- Botón destructivo: usar `semantic.states.error.default` para fondo o borde.

---

## 13. Components — Input

| Token | Valor | Regla |
|-------|--------|--------|
| `components.input.radius` | `global.radius.8` | Inputs con radius **8px** |
| `components.input.padding.x` | `global.spacing.12` | Padding horizontal **12px** |
| `components.input.padding.y` | `global.spacing.12` | Padding vertical **12px** |
| `components.input.border` | `global.spacing.8` | Border width referencia |
| `components.input.helperTextTypography` | `semantic.typography.12.sm-regular` | Texto de ayuda bajo el input: 12px, regular |
| `components.input.valueTypography` | `semantic.typography.14.md-medium` | Valor escrito: 14px, medium |

**Reglas de UI:**
- Borde default: `semantic.border.primary` (neutral.300 `#D0D5DD`); focus: borde `brandBlue.500` y focus ring según `semantic.states.focusRing`.
- Placeholder: `semantic.text.disabled` (neutral.400 `#98A2B3`); valor: `semantic.text.primary` (neutral.950 `#0B1220`).
- Estado error: borde `semantic.border.error` (error.200); helper text en `semantic.text.error` (error.600).
- Label encima del input: tipografía 14 medium o 12 medium según jerarquía; color `semantic.text.secondary` (neutral.700).

---

## 14. Components — Card

| Token | Valor | Regla |
|-------|--------|--------|
| `components.card.radius` | `global.radius.16` | Cards con radius 16px |
| `components.card.padding.default` | `global.spacing.24` | Padding estándar 24px |
| `components.card.padding.compact` | `global.spacing.16` | Versión compacta 16px |
| `components.card.shadow` | `semantic.shadow.card` | Sombra sm |
| `components.card.headerTypography` | `semantic.typography.16.lg-semibold` | Título de card: 16px, semibold |
| `components.card.bodyTypography` | `semantic.typography.14.sm-regular` | Cuerpo: 14px, regular |

**Reglas de UI:**
- Fondo de card: `semantic.bg.container` (`#FFFFFF`) sobre fondo `semantic.bg.primary`.
- Título de card en `semantic.text.primary` (neutral.950); cuerpo en `semantic.text.secondary` (neutral.700). Opcional subtítulo en `semantic.text.tertiary` (neutral.600).
- Separación entre header y body: al menos `spacing.8` o `spacing.16`.

---

## 15. Resumen de reglas UI

1. **Color:** Botón primario = brandBlue.700 (hover .600). Texto principal = neutral.950. Body = neutral.700. Fondos y estados = semantic aliases. Focus = focusRing.
2. **Spacing:** Escala 0–4–8–10–12–14–16–24–32–40–48–56–64; preferir 8, 16, 24, 32 entre elementos y secciones. Valores 10/12/14 para padding de componentes.
3. **Radius:** Botones e inputs **8px**; cards 16px; modales 16–24px.
4. **Typography:** Una sola familia (**Roboto** + fallbacks). Solo escalas 12–56 con variantes sm/md/lg/xl.
5. **Shadow:** Solo sm (cards, listas) y md (modales, popovers).
6. **Componentes:** Button, Input y Card usan exclusivamente los tokens de `components.*`; no inventar padding, radius ni tipografía fuera de estos.
7. **Semantic aliases:** Usar siempre los tokens semánticos (`semantic.text.primary`, `semantic.bg.container`, `semantic.button.color`, etc.) en lugar de referenciar globales directamente. Esto permite dark mode sin cambiar los componentes.

---

*Documento de referencia para diseño (Figma) e implementación. Sincronizado con `Ligth mode.tokens.json`. Cualquier cambio en tokens debe reflejarse aquí y en el sistema de diseño.*
