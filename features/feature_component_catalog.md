# Feature: Component Catalog

## Description

Flujo de diseño para navegar y explorar el catálogo de componentes: vista de lista o árbol por repositorio/categoría/paquete, búsqueda, tarjetas o filas de componente y entrada al detalle (preview y variantes). Incluye empty states y estados de carga. Todo lo que se diseña en Figma para esta experiencia.

---

## Screens / Views

- **Vista principal del catálogo** — Árbol o lista lateral (repositorios > categorías > componentes) y área de contenido (lista de componentes o detalle).
- **Lista de componentes** — Grid o lista de tarjetas: nombre del componente, repo/categoría, miniatura del preview (opcional).
- **Vista detalle de componente** — Cabecera con nombre, ruta/repo; zona de preview y panel de variantes/controles (compartida con features Realtime Preview y Variants and Controls).
- **Barra de búsqueda** — Global o sobre el catálogo: filtro por nombre, repo o categoría.
- **Filtros** — Dropdown o chips: por repositorio, por categoría o paquete.

---

## Components & UI elements

- **Sidebar o árbol de navegación:** nodos expandibles (Repositorio > Categoría > Componente); selección activa; posible búsqueda dentro del árbol.
- **Tarjeta de componente:** miniatura (preview estático o placeholder), nombre, ruta o categoría; clic abre detalle.
- **Barra de búsqueda:** input con placeholder “Buscar componentes…”, icono lupa; resultados en dropdown o página de resultados.
- **Filtros:** “Repositorio: todos / Repo A / Repo B”, “Categoría: todas / Buttons / Forms…”.
- **Cabecera de detalle:** título del componente, breadcrumb (Repo > Categoría > Componente), posible “Abrir en repo” (link externo).
- **Empty state:** “No hay componentes aún” o “Conecta un repositorio para ver el catálogo” con CTA a Repositorios.

---

## User flow

**Explorar por navegación**
1. Usuario entra al Catálogo (desde nav principal).
2. Ve sidebar con repos y categorías; expande y hace clic en un componente.
3. El área principal muestra el detalle: preview + variantes + controles.

**Buscar**
1. Usuario escribe en la barra de búsqueda.
2. Ve sugerencias o lista de resultados (nombre, ruta).
3. Clic en un resultado abre el detalle del componente.

**Filtrar**
1. Usuario selecciona un repositorio o categoría en los filtros.
2. La lista (o árbol) se actualiza mostrando solo los componentes que cumplan el filtro.

---

## States to design

- **Catálogo vacío** — Sin repos conectados: ilustración + “Conecta un repositorio para ver tus componentes” + botón “Ir a Repositorios”. Con repos pero sin componentes aún: “Sincronizando…” o “Aún no hay componentes en este repo”.
- **Lista con datos** — Tarjetas o filas con nombre, miniatura, categoría.
- **Cargando** — Skeletons en lista o spinner en área de contenido.
- **Búsqueda sin resultados** — “Ningún componente coincide con ‘…’. Prueba otro término o filtro.”
- **Detalle cargado** — Preview + lista de variantes + panel de controles (ver features Realtime Preview y Variants and Controls).

---

## Edge cases (UX)

- **Sin repositorios conectados** — Empty state claro con CTA a “Añadir repositorio”; no mostrar árbol vacío sin explicación.
- **Sincronización en curso o fallida** — En la lista o en el árbol: badge “Sincronizando” o “Error de sync” con posibilidad de “Reintentar” desde Repositorios.
- **Componente no encontrado** — Si se abre un link a un componente borrado o de otra org: pantalla “Componente no encontrado” con link “Volver al catálogo”.
- **Usuario sin permiso** — Ocultar catálogo o mostrar solo mensaje “No tienes acceso al catálogo de esta organización.”
- **Muchos componentes** — Diseñar scroll, posible paginación o virtualización en lista; árbol colapsable para no saturar.
