# Task

Diseñar las pantallas de **verificación de email** y **éxito de registro** — pasos finales del flujo de creación de cuenta.

**Herramienta:** se usa el MCP de **Paper** para crear los diseños en el canvas.

## Requirements

- Seguir **feature_create_user.md** (secciones Pantalla de verificación de email y Pantalla de éxito, User flow pasos 5–6).
- Aplicar los design tokens y reglas de **spec/ui_spec.md**.
- Entregable es **solo diseño** en Paper: sin backend, APIs ni base de datos.

**Alcance — Pantalla de verificación de email:**

- Header con logo de codeCollection.
- Icono de email o ilustración simbólica (ej. sobre/inbox).
- Título "Revisa tu correo".
- Texto descriptivo: "Enviamos un enlace de verificación a **{email}**. Haz clic en el enlace para activar tu cuenta."
- Botón secundario **"Abrir mi correo"** (o enlace).
- Texto auxiliar: "¿No recibiste el correo?" con enlace **"Reenviar"**.
- Enlace: "Usar otro email" (volver al registro).

**Alcance — Pantalla de éxito:**

- Header con logo de codeCollection.
- Icono de éxito (check / celebración).
- Título "¡Cuenta creada!".
- Texto descriptivo: "Tu cuenta y organización están listas. Comienza a explorar tus componentes."
- Botón principal **"Ir al dashboard"**.
- Estados a diseñar:
  - **Verification pending** — Pantalla "Revisa tu correo" (estado default).
  - **Success** — Pantalla de confirmación con CTA al dashboard.
- Layout coherente con task_003 y task_004 — misma estructura visual, misma familia tipográfica y tokens.

## Tokens de referencia (ui_spec.md actualizado)

| Elemento | Token | Valor |
|----------|-------|-------|
| Fondo página | `semantic.bg.primary` / `neutral.50` | `#F9FAFB` |
| Contenedor | `semantic.bg.container` | `#FFFFFF` |
| Título | `semantic.text.primary` / `neutral.950` | `#0B1220`, 24px semibold |
| Texto descriptivo | `semantic.text.secondary` / `neutral.700` | `#344054`, 14px regular |
| Texto auxiliar | `semantic.text.tertiary` / `neutral.600` | `#475467`, 14px regular |
| Botón primario fondo | `semantic.button.color` / `brandBlue.700` | `#003D6D` |
| Botón primario radius | `components.button.radius` | `8px` |
| Botón primario padding md | `components.button` | `10px 12px` |
| Botón secundario borde | `semantic.border.primary` / `neutral.300` | `#D0D5DD` |
| Botón secundario fondo | `#FFFFFF` o `neutral.100` | `#FFFFFF` / `#F2F4F7` |
| Botón secundario texto | `semantic.text.secondary` / `neutral.700` | `#344054` |
| Icono container bg | `neutral.100` | `#F2F4F7`, radius 16px |
| Success icono bg | `semantic.bg.success` / `success.50` | `#ECFDF3` |
| Success icono color | `success.600` | `#079455` |
| Enlaces | `brandBlue.500` | `#1B73B5` |
| Logo bg | `semantic.bg.brandColor` / `brandBlue.700` | `#003D6D` |
| Font family | `global.typography.fontFamily.primary` | Roboto |

## Output

- Pantallas de verificación y éxito en **Paper** (MCP) con:
  - Artboard "Registro — Verificación email" (1440×900).
  - Artboard "Registro — Éxito" (1440×900).
  - Componentes alineados a ui_spec (botones radius 8px, tipografía Roboto, colores semánticos).
  - Continuidad visual con task_003 y task_004.
- Documento de tokens en `/tasks/results/task_005_verification_success_tokens.md`.
