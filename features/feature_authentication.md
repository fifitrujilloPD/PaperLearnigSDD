# Feature: Authentication

## Description

Flujo de diseño para que un usuario inicie sesión, cierre sesión y recupere su contraseña. Incluye las vistas de login, la sesión activa (header/nav con usuario), logout y el flujo “Olvidé mi contraseña”. Todo debe sentirse coherente con el resto de la app.

---

## Screens / Views

- **Pantalla de login (sign in)** — Formulario email + contraseña.
- **Pantalla “Olvidé mi contraseña”** — Campo email para enviar enlace o código.
- **Pantalla “Revisa tu correo” (reset)** — Confirmación de que se envió el email.
- **Pantalla “Nueva contraseña”** — Formulario para restablecer (llegada por link en email).
- **Vistas autenticadas** — Header o navegación con avatar/menú de usuario (dropdown con “Cerrar sesión”).

---

## Components & UI elements

- **Login:** campos **email** y **contraseña**, botón “Iniciar sesión”, link “¿Olvidaste tu contraseña?”.
- **Recuperar contraseña:** campo **email**, botón “Enviar enlace” / “Enviar código”.
- **Nueva contraseña:** campos **contraseña** y **Confirmar contraseña**, botón “Guardar”.
- **Header/Nav (logged in):** avatar o iniciales, nombre o email, menú desplegable con “Cerrar sesión” y posible “Mi cuenta” o “Configuración”.
- Mensajes de error (credenciales incorrectas, link expirado).
- Enlace “¿No tienes cuenta? Regístrate” en pantalla de login.

---

## User flow

**Login**
1. Usuario llega a login (por link “Iniciar sesión” o al acceder a ruta protegida).
2. Introduce email y contraseña y pulsa “Iniciar sesión”.
3. Loading y luego redirección al dashboard (o a la ruta que intentaba acceder).

**Logout**
1. Usuario abre menú de perfil en el header.
2. Clic en “Cerrar sesión”.
3. Sesión se cierra y redirección a login o landing.

**Recuperar contraseña**
1. Desde login, clic en “¿Olvidaste tu contraseña?”.
2. Pantalla con campo email; usuario escribe y pulsa “Enviar”.
3. Pantalla “Revisa tu correo” con instrucciones.
4. Usuario abre el link del email y llega a “Nueva contraseña”.
5. Introduce nueva contraseña (y confirmación), guarda y vuelve a login.

---

## States to design

- **Login:** default (form vacío), focus en campos, loading (“Iniciando sesión…”), error (mensaje “Email o contraseña incorrectos”).
- **Recuperar contraseña:** default, loading al enviar, éxito (“Revisa tu correo”).
- **Nueva contraseña:** default, validación (no coinciden, demasiado corta), loading, éxito y redirección.
- **Header usuario:** collapsed (solo avatar), expanded (dropdown con Cerrar sesión).
- **Sesión expirada:** modal o banner “Tu sesión ha expirado. Inicia sesión de nuevo.” con botón a login.

---

## Edge cases (UX)

- **Credenciales incorrectas** — Mensaje claro bajo el form: “Email o contraseña incorrectos. ¿Olvidaste tu contraseña?”.
- **Sesión expirada** — Modal o banner no intrusivo con CTA “Iniciar sesión” y opción de cerrar.
- **Link de reset expirado o ya usado** — Pantalla dedicada: “Este enlace ya no es válido. Solicita uno nuevo.” con link a “Olvidé mi contraseña”.
- **Email no encontrado en “Olvidé contraseña”** — Por seguridad no revelar si existe; mismo mensaje “Si existe una cuenta con este correo, recibirás un enlace.” y pantalla “Revisa tu correo”.
- **Cerrar sesión ya cerrada** — No mostrar error; estar en login o landing es suficiente.
