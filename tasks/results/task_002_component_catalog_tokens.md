# Component Catalog — Design tokens used

Referencia rápida de los tokens de **spec/ui_spec.md** aplicados en las pantallas del catálogo de componentes (Paper).

## Sidebar

- **Fondo:** `#FFFFFF` (blanco sobre neutral.50)
- **Borde derecho:** `global.color.neutral.200` → #EAECF0
- **Padding:** 24px vertical, 16px horizontal
- **Sección label:** 12px / 600 (lg-semibold), `neutral.500` → #667085, letter-spacing 0.05em
- **Nodo repo:** 14px / 600 (lg-semibold), `neutral.900` → #101828
- **Nodo categoría:** 14px / 400 (sm-regular), `neutral.700` → #344054
- **Nodo activo:** fondo `brandBlue.50` → #E8F2FA, texto `brandBlue.500` → #1B73B5, 14px / 500 (md-medium)
- **Chevrons:** stroke `neutral.700` → #344054

## Barra de búsqueda (Input)

- **Radius:** `components.input.radius` → 12px
- **Padding:** `components.input.padding.x` 16px, `.y` 8px
- **Borde default:** `neutral.300` → #D0D5DD
- **Borde focus:** `brandBlue.500` → #1B73B5 (2px)
- **Placeholder:** `neutral.400` → #98A2B3, 14px / 400
- **Valor:** `neutral.900` → #101828, 14px / 500

## Filtros (chips)

- **Chip activo:** fondo `brandBlue.500` → #1B73B5, texto `#FFFFFF`, radius 12px
- **Chip inactivo:** borde `neutral.300` → #D0D5DD, fondo blanco, texto `neutral.700` → #344054, radius 12px
- **Height:** 32px (`components.button.height.sm`)

## Tarjetas de componente (Card)

- **Radius:** `components.card.radius` → 16px
- **Shadow:** `semantic.shadow.card` → 0px 1px 2px rgba(16,24,40,0.25)
- **Preview zone:** fondo `neutral.100` → #F2F4F7, height 140px
- **Padding contenido:** `components.card.padding.compact` → 16px
- **Título:** `components.card.headerTypography` → 16px / 600, `neutral.900` → #101828
- **Subtítulo:** 12px / 400, `neutral.500` → #667085

## Vista detalle — Cabecera

- **Breadcrumb:** 12px / 400, `neutral.500` → #667085; separador `neutral.400` → #98A2B3; último segmento 12px / 500, `neutral.900`
- **Título:** 24px / 700 (xl-bold), `neutral.900` → #101828
- **Link "Abrir en repo":** 14px / 500, `brandBlue.500` → #1B73B5

## Vista detalle — Preview

- **Fondo:** `neutral.100` → #F2F4F7, radius 16px, padding 32px
- **Componente preview:** tokens del componente original (ej. Button: brandBlue.500, radius 12)

## Vista detalle — Panel variantes/controles

- **Fondo:** blanco, radius 16px, shadow card sm, padding 24px
- **Título panel:** 16px / 600, `neutral.900`
- **Sección label:** 12px / 600, `neutral.500`, uppercase, spacing 0.05em
- **Item activo:** fondo `brandBlue.50` → #E8F2FA, texto `brandBlue.500` → #1B73B5
- **Item inactivo:** 14px / 400, `neutral.700` → #344054
- **Control input:** borde `neutral.300`, radius 12px, padding 8px 16px
- **Control toggle:** 36×20px, thumb blanco, track `neutral.300`
- **Size selector activo:** fondo `brandBlue.500`, texto blanco, radius 8px

## Empty state (sin repos)

- **Icono container:** 64px, radius 16px, fondo `neutral.100` → #F2F4F7
- **Título:** 20px / 600, `neutral.900` → #101828
- **Cuerpo:** 14px / 400, `neutral.500` → #667085, text-align center
- **CTA:** `components.button.height.md` → 40px, `brandBlue.500`, radius 12px, 14px / 500 blanco

## Búsqueda sin resultados

- **Icono:** 56px container, radius 16px, fondo `neutral.100`
- **Título:** 16px / 600, `neutral.900`
- **Cuerpo:** 14px / 400, `neutral.500`, text-align center

## Loading (skeletons)

- **Skeleton bars:** `neutral.200` → #EAECF0, radius 4px
- **Skeleton card preview:** `neutral.200` → #EAECF0
- **Skeleton card text:** fondo `neutral.100` → #F2F4F7, radius 4px

## Fondo general

- **Página:** `global.color.neutral.50` → #F9FAFB
