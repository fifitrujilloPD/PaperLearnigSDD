# Login screen — Design tokens used

Referencia rápida de los tokens de **spec/ui_spec.md** aplicados en la pantalla de login (Paper).

> Actualizado para reflejar los tokens vigentes tras la sincronización con `Ligth mode.tokens.json`.

## Campos (Input)

- **Radius:** `components.input.radius` → `global.radius.8` → **8px**
- **Padding:** `components.input.padding.x` 12px, `padding.y` 12px
- **Borde default:** `semantic.border.primary` / `neutral.300` → #D0D5DD
- **Borde focus:** `brandBlue.500` → #1B73B5 (+ focus ring 2px, offset 2px)
- **Borde error:** `semantic.border.error` / `error.200` → #FECDCA
- **Placeholder:** `semantic.text.disabled` / `neutral.400` → #98A2B3
- **Valor:** `semantic.text.primary` / `neutral.950` → #0B1220
- **Label:** `semantic.text.secondary` / `neutral.700` → #344054, 14px medium

## Botón principal

- **Fondo:** `semantic.button.color` / `brandBlue.700` → #003D6D
- **Hover:** `semantic.button.hover` / `brandBlue.600` → #0C5A99
- **Pressed:** `semantic.button.press` / `brandBlue.700` → #003D6D
- **Padding md:** 10px top/bottom, 12px left/right
- **Radius:** `components.button.radius` → `global.radius.8` → **8px**
- **Tipografía:** `semantic.typography.14.md-medium` → 14px, font-weight 500

## Mensaje de error

- **Texto:** `semantic.text.error` / `error.600` → #D92D20
- **Fondo:** `semantic.bg.error` / `error.50` → #FEF3F2

## Enlaces

- **Color:** `brandBlue.500` → #1B73B5

## Fondo y título

- **Fondo página:** `semantic.bg.primary` / `neutral.50` → #F9FAFB
- **Título "Iniciar sesión":** `semantic.text.primary` / `neutral.950` → #0B1220, 24px semibold (scale 24, lg-semibold)
- **Logo placeholder:** `semantic.bg.brandColor` / `brandBlue.700` → #003D6D, radius 12px

## Tipografía

- **Font family:** `global.typography.fontFamily.primary` → **Roboto**, system-ui, sans-serif
