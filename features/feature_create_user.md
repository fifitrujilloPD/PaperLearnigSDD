# Feature: Register User

## Description

Flujo de diseño para que un usuario nuevo se registre en codeCollection. Incluye la creación de cuenta en contexto organizacional (elegir o crear organización, o unirse por invitación). El diseño debe comunicar claramente los pasos y qué datos se piden.

---

## Screens / Views

- **Landing o página de bienvenida** — Punto de entrada con CTA “Registrarse” o “Crear cuenta”.
- **Pantalla de registro (sign up)** — Formulario principal de alta.
- **Pantalla o paso “Tu organización”** — Elegir organización existente (si hay invite) o crear nueva (nombre de empresa/equipo).
- **Pantalla de verificación de email (opcional)** — Mensaje “Revisa tu correo” con CTA para ir al inbox.
- **Pantalla de éxito** — Confirmación y redirección al dashboard o onboarding.

---

## Components & UI elements

- Formulario: campos **email**, **contraseña**, **nombre** (o nombre para mostrar).
- Selector o input de **organización**: crear nueva (nombre) o “Tengo un código de invitación”.
- Botón principal: “Crear cuenta” / “Registrarme”.
- Enlaces: “¿Ya tienes cuenta? Iniciar sesión”, “Política de privacidad”, “Términos”.
- (Si hay invite) Campo “Código de invitación” o uso de link mágico que pre-rellena la org.
- Mensajes de validación inline (debajo de cada campo o bajo el form).
- Header/logo de codeCollection y posible ilustración o copy de bienvenida.

---

## User flow

1. Usuario llega a landing o a URL de registro.
2. Usuario rellena email, contraseña y nombre en la pantalla de registro.
3. Siguiente paso: “Tu organización” — escribe nombre de empresa o pega código de invitación.
4. Clic en “Crear cuenta”.
5. (Opcional) Pantalla “Revisa tu correo” con instrucciones.
6. Pantalla de éxito y redirección al dashboard (o primer uso).

---

## States to design

- **Default** — Formulario vacío, campos con placeholder.
- **Focus** — Campo activo, posible hint de contraseña (ej. “Mínimo 8 caracteres”).
- **Loading** — Botón en estado “Enviando…” o spinner, form deshabilitado.
- **Validation error** — Mensaje bajo campo (ej. “Email ya registrado”, “Contraseña demasiado corta”).
- **Success** — Mensaje de confirmación y botón “Ir al dashboard” o auto-redirect.
- **Empty state “organización”** — Si no hay invite: solo opción “Crear organización” con input de nombre.

---

## Edge cases (UX)

- **Email ya registrado** — Mensaje claro bajo el campo o bajo el form: “Este correo ya tiene cuenta. ¿Iniciar sesión?” con link.
- **Contraseña no cumple política** — Lista corta de requisitos (longitud, caracteres) y mensaje al enviar si falla.
- **Código de invitación inválido o expirado** — Mensaje en pantalla o en modal: “Este enlace ya no es válido. Pide uno nuevo a tu administrador.”
- **Campos obligatorios vacíos** — Validación al enviar o en blur; mensajes junto a cada campo.
- **Organización ya existente** — Si el nombre de org ya existe: mensaje “Esta organización ya está registrada” y opción “Solicitar unirme” o “Usar código de invitación”.
