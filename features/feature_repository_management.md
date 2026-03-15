# Feature: Repository Management

## Description

Flujo de diseño para conectar y gestionar repositorios de componentes (Storybooks): pantalla de listado, “Añadir repo”, formulario o wizard de conexión, selección de rama/tag/commit y estados de sincronización. Todo lo que el usuario ve y toca en la UI (vistas, modales, componentes).

---

## Screens / Views

- **Listado de repositorios** — Dentro de la organización: tarjetas o tabla con nombre del repo, última sincronización, rama/ref actual, estado (OK / Error / Sincronizando) y acciones (configurar, re-sincronizar, desvincular).
- **Pantalla o modal “Añadir repositorio”** — Paso 1: URL del repo (GitHub/GitLab) y opcionalmente credenciales o “Conectar con GitHub”. Paso 2: elegir rama, tag o commit para sincronizar.
- **Detalle de un repositorio (opcional)** — Configuración del repo, historial de syncs, cambiar rama/ref.
- **Empty state** — “Aún no hay repositorios conectados. Conecta tu primer Storybook.”

---

## Components & UI elements

- **Lista de repos:** tarjeta o fila por repo con: icono/avatar del repo, nombre, “Última sync: hace X” o “Sincronizando…”, badge de rama/tag, botones “Sincronizar” y “Configuración” o menú (⋮).
- **Botón “Añadir repositorio” / “Conectar repo”.**
- **Modal o pantalla Añadir repo:** campo **URL del repositorio**, botón “Conectar con GitHub” (OAuth) o campo token si aplica; siguiente paso: **selector de rama/tag/commit** (dropdown o lista), botón “Sincronizar” o “Añadir”.
- **Estados visuales por repo:** indicador verde (OK), amarillo (sincronizando), rojo (error) con tooltip o mensaje corto.
- **Modal confirmación “Desvincular repositorio”** — “¿Desvincular [nombre]? El catálogo dejará de actualizarse.” con “Desvincular” y “Cancelar”.

---

## User flow

**Conectar primer repositorio**
1. Usuario entra a Repositorios (o Configuración > Repositorios).
2. Ve empty state y clic en “Añadir repositorio”.
3. Introduce URL o “Conectar con GitHub” y autoriza.
4. Siguiente paso: elige rama (p. ej. `main`) o tag/commit.
5. Clic en “Sincronizar” o “Añadir”; ve estado “Sincronizando…” y luego “Listo” en la tarjeta.

**Re-sincronizar o cambiar rama**
1. En la lista, clic en “Sincronizar” o “Configuración”.
2. Si es config: puede cambiar rama/tag/commit y guardar; se lanza sync.
3. Indicador de progreso y luego estado actualizado.

**Desvincular**
1. Menú del repo > “Desvincular”.
2. Modal de confirmación; usuario confirma y el repo desaparece de la lista.

---

## States to design

- **Lista:** vacía (ilustración + copy + CTA), con 1 o más repos (tarjetas con estados).
- **Tarjeta repo:** estado “Listo” (verde), “Sincronizando…” (spinner o animación), “Error” (mensaje corto + “Reintentar”).
- **Modal Añadir:** paso 1 (URL), paso 2 (rama/tag); loading al conectar o al sincronizar; error (URL inválida, sin acceso, sin Storybook).
- **Detalle/Config:** formulario rama/tag, botón “Guardar y sincronizar”, loading.

---

## Edge cases (UX)

- **URL inválida o repo inaccesible** — Mensaje bajo el campo o en toast: “No pudimos acceder al repositorio. Revisa la URL y permisos.”
- **Repo sin Storybook** — Tras analizar: “Este repositorio no parece contener un Storybook. Revisa la documentación.”
- **Rama/tag no existe** — En el selector, mensaje o estado vacío: “No se encontró esa rama” o deshabilitar “Sincronizar” hasta elegir ref válida.
- **Error de sincronización** — En la tarjeta: “Error al sincronizar. [Reintentar]” y opcional “Ver detalles” (lista de errores).
- **Repo ya conectado** — Al añadir la misma URL: “Este repositorio ya está conectado en esta organización.”
- **Sin permisos** — Usuario miembro sin permiso: no mostrar “Añadir repositorio” o deshabilitar acciones; solo lectura.
