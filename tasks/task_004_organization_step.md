# Task

Diseñar la **pantalla "Tu organización"** — paso donde el usuario elige o crea una organización durante el registro.

**Herramienta:** se usa el MCP de **Paper** para crear los diseños en el canvas.

## Requirements

- Seguir **feature_create_user.md** (sección Pantalla o paso "Tu organización", Components & UI elements, User flow paso 3, States to design y Edge cases de organización).
- Aplicar los design tokens y reglas de **spec/ui_spec.md**.
- Entregable es **solo diseño** en Paper: sin backend, APIs ni base de datos.

**Alcance de la pantalla de organización:**

- Header con logo, título "Tu organización" y subtítulo breve ("Crea tu equipo o únete a uno existente").
- Sección **"Crear organización"** con input "Nombre de la organización" y botón "Continuar".
- Sección **"Tengo un código de invitación"** — campo para pegar código e ingresar.
- Separador visual (línea o "o") entre ambas opciones.
- Enlace para volver al paso anterior (si aplica).
- Estados a diseñar:
  - **Default** — Ambas opciones visibles, campos vacíos.
  - **Focus** — Campo de nombre de organización activo.
  - **Invite code entry** — Campo de código de invitación activo con texto ingresado.
  - **Validation error: código inválido** — Mensaje "Este enlace ya no es válido. Pide uno nuevo a tu administrador."
  - **Validation error: org existente** — Mensaje "Esta organización ya está registrada" con opciones "Solicitar unirme" o "Usar código de invitación".
- Layout coherente con pantalla de registro (task_003) — misma estructura visual, progresión clara de pasos.

## Tokens de referencia (ui_spec.md actualizado)

| Elemento | Token | Valor |
|----------|-------|-------|
| Fondo página | `semantic.bg.primary` / `neutral.50` | `#F9FAFB` |
| Contenedor | `semantic.bg.container` | `#FFFFFF` |
| Título | `semantic.text.primary` / `neutral.950` | `#0B1220`, 24px semibold |
| Subtítulo | `semantic.text.secondary` / `neutral.700` | `#344054`, 14px regular |
| Input radius | `components.input.radius` | `8px` |
| Input padding | `components.input.padding` | `12px / 12px` |
| Input borde | `semantic.border.primary` / `neutral.300` | `#D0D5DD` |
| Input focus | `brandBlue.500` + focus ring 2px | `#1B73B5` |
| Placeholder | `semantic.text.disabled` / `neutral.400` | `#98A2B3` |
| Botón fondo | `semantic.button.color` / `brandBlue.700` | `#003D6D` |
| Botón radius | `components.button.radius` | `8px` |
| Botón padding md | `components.button` | `10px 12px` |
| Separador | `semantic.border.secondary` / `neutral.200` | `#EAECF0` |
| Error texto | `semantic.text.error` / `error.600` | `#D92D20` |
| Error fondo | `semantic.bg.error` / `error.50` | `#FEF3F2` |
| Error borde | `semantic.border.error` / `error.200` | `#FECDCA` |
| Warning texto | `semantic.text.warning` / `warning.600` | `#DC6803` |
| Warning fondo | `semantic.bg.warning` / `warning.50` | `#FFFAEB` |
| Enlaces | `brandBlue.500` | `#1B73B5` |
| Logo bg | `semantic.bg.brandColor` / `brandBlue.700` | `#003D6D` |
| Font family | `global.typography.fontFamily.primary` | Roboto |

## Output

- Pantalla de organización en **Paper** (MCP) con:
  - Artboards (1440×900) por estado: default, focus, invite code entry, error código inválido, error org existente.
  - Componentes alineados a ui_spec (inputs radius 8px, padding 12/12; botón radius 8px; errores con semantic.states.error).
  - Continuidad visual con task_003 (registro) — mismo encabezado, misma estructura.
- Documento de tokens en `/tasks/results/task_004_organization_step_tokens.md`.
