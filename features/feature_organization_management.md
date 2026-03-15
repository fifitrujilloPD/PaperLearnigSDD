# Feature: Organization Management (B2B)

## Description

Flujo de diseño para que los usuarios gestionen su organización (empresa/equipo): ver y editar datos de la org, invitar miembros, asignar roles y ver la lista de miembros. Solo los admins ven y usan las acciones de gestión. Pensado para diseño en Figma (pantallas, modales, componentes).

---

## Screens / Views

- **Configuración de la organización (o “Equipo”)** — Pantalla principal con pestañas o secciones: “General”, “Miembros”, “Repositorios” (si aplica).
- **Sección General** — Nombre de la organización, posible logo, slug o identificador (solo lectura o editable según rol).
- **Sección Miembros** — Lista de miembros con avatar, nombre, email, rol y acciones (editar rol, quitar). Botón “Invitar miembro”.
- **Modal “Invitar miembro”** — Campo email, selector de rol (Admin / Miembro), botón “Enviar invitación”.
- **Modal “Editar rol”** — Selector de rol para un miembro existente.
- **(Opcional) Selector de organización** — En header o sidebar cuando el usuario pertenece a varias orgs: dropdown para cambiar de contexto.

---

## Components & UI elements

- **Form General:** input nombre de organización, posible upload de logo, texto “Identificador: org-slug” (solo lectura).
- **Tabla o lista de miembros:** filas con avatar, nombre, email, badge de rol (Admin / Miembro), menú de acciones (⋮) con “Cambiar rol” y “Quitar del equipo”.
- **Botón “Invitar miembro”** — Abre modal.
- **Modal Invitar:** campo email, select rol, botón “Enviar invitación”, “Cancelar”.
- **Modal Editar rol:** select rol, “Guardar”, “Cancelar”.
- **Confirmación “Quitar miembro”** — Modal o inline: “¿Quitar a [nombre] del equipo?” con “Quitar” y “Cancelar”.
- **Selector de organización (multi-org):** dropdown en header con nombre de cada org y check o indicador en la activa.

---

## User flow

**Ver y editar organización (admin)**
1. Usuario entra a Configuración > Organización (o “Equipo”).
2. En “General” ve/edita nombre (y logo si aplica).
3. En “Miembros” ve la lista; puede abrir “Invitar miembro”, “Editar rol” o “Quitar”.

**Invitar miembro**
1. Admin clic en “Invitar miembro”.
2. Modal: escribe email, elige rol, “Enviar invitación”.
3. Modal se cierra; en la lista aparece el invitado como “Invitación pendiente” (opcional).

**Cambiar de organización (si hay varias)**
1. Usuario abre selector de org en header.
2. Elige otra organización; la vista actualiza contexto (repos, catálogo, etc.).

---

## States to design

- **General:** formulario por defecto, loading al guardar, éxito (toast o mensaje “Guardado”).
- **Lista miembros:** vacía (“Aún no hay miembros. Invita al primero.”), con datos, loading al cargar.
- **Modal Invitar:** default, loading al enviar, éxito (“Invitación enviada”) y cierre.
- **Modal Quitar:** confirmación con nombre del miembro; loading al confirmar.
- **Rol:** badge “Admin” / “Miembro” con distinto estilo si se quiere.

---

## Edge cases (UX)

- **Intentar quitar al último admin** — Mensaje: “Debe haber al menos un administrador. Asigna otro admin antes de quitar a este.” o deshabilitar la acción.
- **Email ya miembro** — Al invitar: “Este correo ya pertenece al equipo.” bajo el campo o en toast.
- **Usuario sin permiso (miembro no admin)** — No mostrar “Invitar miembro” ni “Editar organización”; solo ver datos de la org y lista de miembros (solo lectura si se desea).
- **Invitación expirada** — En la lista, fila “Invitación expirada” con acción “Reenviar” o “Eliminar”.
- **Organización duplicada** — Al crear/editar nombre: “Ya existe una organización con este nombre.” si aplica.
