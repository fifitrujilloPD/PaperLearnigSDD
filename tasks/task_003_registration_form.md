# Task

Diseñar la **pantalla de registro (sign up)** con formulario de creación de cuenta.

**Herramienta:** se usa el MCP de **Paper** para crear los diseños en el canvas.

## Requirements

- Seguir **feature_create_user.md** (sección Pantalla de registro, Components & UI elements, User flow pasos 1–2, States to design y Edge cases de registro).
- Aplicar los design tokens y reglas de **spec/ui_spec.md** (colores, espaciado, radius, tipografía, componentes Button e Input).
- Entregable es **solo diseño** en Paper: sin backend, APIs ni base de datos.

**Alcance de la pantalla de registro:**

- Header con logo de codeCollection y título "Crear cuenta".
- Formulario con campos **nombre**, **email** y **contraseña**.
- Hint de contraseña bajo el campo: "Mínimo 8 caracteres".
- Botón principal **"Crear cuenta"**.
- Enlace **"¿Ya tienes cuenta? Iniciar sesión"**.
- Enlaces pie: "Política de privacidad" · "Términos".
- Estados a diseñar:
  - **Default** — Formulario vacío, campos con placeholder.
  - **Focus** — Campo activo (email o contraseña), hint de contraseña visible.
  - **Loading** — Botón "Creando cuenta…", formulario deshabilitado.
  - **Validation error** — Mensajes inline: "Email ya registrado" con link "¿Iniciar sesión?", "Contraseña demasiado corta", campos obligatorios vacíos.
- Layout y jerarquía visual coherentes con la pantalla de login ya diseñada (logo, título, espaciado según ui_spec).

## Tokens de referencia (ui_spec.md actualizado)

| Elemento | Token | Valor |
|----------|-------|-------|
| Fondo página | `semantic.bg.primary` / `neutral.50` | `#F9FAFB` |
| Contenedor | `semantic.bg.container` | `#FFFFFF` |
| Título | `semantic.text.primary` / `neutral.950` | `#0B1220`, 24px semibold |
| Label input | `semantic.text.secondary` / `neutral.700` | `#344054`, 14px medium |
| Input radius | `components.input.radius` | `8px` |
| Input padding | `components.input.padding` | `12px / 12px` |
| Input borde | `semantic.border.primary` / `neutral.300` | `#D0D5DD` |
| Input focus | `brandBlue.500` + focus ring 2px | `#1B73B5` |
| Placeholder | `semantic.text.disabled` / `neutral.400` | `#98A2B3` |
| Valor input | `semantic.text.primary` / `neutral.950` | `#0B1220` |
| Botón fondo | `semantic.button.color` / `brandBlue.700` | `#003D6D` |
| Botón hover | `semantic.button.hover` / `brandBlue.600` | `#0C5A99` |
| Botón radius | `components.button.radius` | `8px` |
| Botón padding md | `components.button` | `10px 12px` |
| Botón tipografía | `semantic.typography.14.md-medium` | 14px, weight 500 |
| Error texto | `semantic.text.error` / `error.600` | `#D92D20` |
| Error fondo | `semantic.bg.error` / `error.50` | `#FEF3F2` |
| Error borde | `semantic.border.error` / `error.200` | `#FECDCA` |
| Enlaces | `brandBlue.500` | `#1B73B5` |
| Logo bg | `semantic.bg.brandColor` / `brandBlue.700` | `#003D6D` |
| Font family | `global.typography.fontFamily.primary` | Roboto |

## Output

- Pantalla de registro en **Paper** (MCP) con:
  - Un artboard principal (1440×900) con el formulario completo.
  - Variantes o artboards por estado: default, focus, loading, validation error.
  - Componentes alineados a ui_spec (inputs radius 8px, padding 12/12; botón con padding 10/12, radius 8px, tipografía 14 medium; mensaje de error con semantic.states.error).
- Documento de tokens en `/tasks/results/task_003_registration_form_tokens.md`.
