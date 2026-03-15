# Feature: Realtime Preview

## Description

Flujo de diseño para la vista de preview en tiempo real de un componente: área donde se renderiza el componente, relación con la navegación del catálogo y con el panel de variantes/controles. Incluye estados de carga, error y responsive/iframe si aplica. Pensado para diseñar en Figma (layout, componentes, estados).

---

## Screens / Views

- **Vista detalle de componente** — Layout compartido con Catálogo y Variants: zona de **preview** (iframe o contenedor de render) ocupa la parte central o principal; lateral o inferior para variantes y controles.
- **Toolbar del preview (opcional)** — Tamaño de vista (100% / responsivo), fondo (claro/oscuro), zoom.
- **Pantalla o overlay de error** — Cuando el preview no puede renderizar.

---

## Components & UI elements

- **Contenedor de preview** — Marco o iframe que muestra el componente renderizado; fondo configurable (blanco/gris/transparente) para ver bien el componente.
- **Toolbar (opcional):** botones o dropdown “Tamaño” (Desktop / Tablet / Móvil), “Fondo”, “Zoom in/out” o “Fit”.
- **Estado de carga** — Skeleton o spinner dentro del contenedor con texto “Cargando preview…”.
- **Estado de error** — Mensaje en el contenedor: “No se pudo cargar el preview” con “Reintentar” y posible detalle colapsable.
- **Breadcrumb o título** — Encima del preview: nombre del componente y variante actual (p. ej. “Button > Primary”).

---

## User flow

1. Usuario abre un componente desde el Catálogo (lista o árbol).
2. El área de preview muestra primero “Cargando preview…” y luego el componente renderizado.
3. Al cambiar variante (en el panel de variantes) o un control (en el panel de controles), el preview se actualiza en tiempo real sin recargar la página.
4. Opcional: usuario cambia tamaño de vista o fondo desde la toolbar del preview.

---

## States to design

- **Loading** — Contenedor con skeleton o spinner y texto “Cargando preview…”.
- **Loaded** — Componente visible en el marco; fondo neutro (gris claro o blanco).
- **Error** — Mensaje claro + botón “Reintentar”; opcional “Ver detalles” para mensaje técnico.
- **Responsive** — Si hay tamaños predefinidos: marcos para Desktop / Tablet / Móvil con el mismo componente dentro.
- **Sin variante seleccionada** — Si aplica: mensaje “Selecciona una variante” o mostrar la primera por defecto.

---

## Edge cases (UX)

- **Preview no carga** — Mensaje: “No se pudo cargar el preview. Puede que el componente tenga dependencias no disponibles.” con “Reintentar”.
- **Componente o variante no encontrado** — Mismo contenedor con estado error: “Esta variante ya no existe” y link “Volver al catálogo”.
- **Catálogo no sincronizado** — Si los datos están desactualizados, el preview puede fallar; considerar mensaje “Los datos del catálogo pueden estar desactualizados. [Sincronizar].”
- **Preview muy grande o que desborda** — Scroll dentro del contenedor o “Fit to view” para que siempre se vea completo.
- **Navegación rápida** — Al cambiar de componente antes de que cargue el anterior: cancelar carga anterior y mostrar loading del nuevo; evitar parpadeos confusos.
