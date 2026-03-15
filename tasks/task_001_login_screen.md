# Task

Diseñar la **pantalla de login (sign in)** con formulario de email y contraseña.

**Herramienta:** se usa el MCP de **Paper** para crear los diseños en el canvas.

## Requirements

- Seguir **feature_authentication.md** (sección Pantalla de login, Components & UI elements, User flow, States to design y Edge cases de login).
- Aplicar los design tokens y reglas de **spec/ui_spec.md** (colores, espaciado, radius, tipografía, componentes Button e Input).
- Entregable es **solo diseño** en Paper: sin backend, APIs ni base de datos.

**Alcance de la pantalla de login:**

- Formulario con campos **email** y **contraseña**.
- Botón principal **“Iniciar sesión”**.
- Enlace **“¿Olvidaste tu contraseña?”**.
- Enlace **“¿No tienes cuenta? Regístrate”**.
- Estados a diseñar: **default** (form vacío), **focus** en campos, **loading** (“Iniciando sesión…”), **error** (mensaje “Email o contraseña incorrectos” con opción “¿Olvidaste tu contraseña?”).
- Layout y jerarquía visual coherentes con el resto de la app (logo, título, espaciado según ui_spec).

## Output

- Pantalla de login en **Paper** (MCP) con:
  - Un artboard principal con el formulario completo.
  - Variantes o estados: default, focus (email o contraseña), loading, error.
  - Componentes alineados a ui_spec (inputs con radius 12, padding 16/8; botón con height 40, tipografía 14 medium; mensaje de error usando semantic.states.error).
- Breve anotación o doc que indique qué token se usó en campos, botón y mensaje de error (opcional pero recomendado).
