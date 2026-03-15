# Feature: Variants and Controls

## Description

Flujo de diseño para listar las variantes (stories) de un componente y para el panel de controles (props editables): cómo se muestran, cómo se selecciona una variante, cómo se cambian los controles y cómo el usuario ve el resultado en el preview. Todo lo que se diseña en Figma (paneles, componentes, estados).

---

## Screens / Views

- **Panel de variantes** — Lista o tabs de variantes (stories): nombre de cada una, selección activa; al hacer clic, el preview se actualiza.
- **Panel de controles** — Lista de controles por variante: etiqueta + control (input texto, checkbox, select, number, etc.); al cambiar un valor, el preview se actualiza al instante.
- **Vista detalle de componente** — Layout que combina preview (centro) + panel variantes (lateral o superior) + panel controles (lateral o inferior).

---

## Components & UI elements

- **Lista de variantes:** items clicables con nombre de la variante (p. ej. “Primary”, “Secondary”, “Disabled”); estado seleccionado resaltado; posible scroll si hay muchas.
- **Controles:** fila por control con:
  - **Label** (nombre del prop).
  - **Control:** texto (input), boolean (switch/checkbox), select (dropdown), número (input number o slider), color (color picker) según tipo.
- **Panel colapsable (opcional)** — “Variantes” y “Controles” como acordeones para ganar espacio.
- **Estado “Sin variantes”** — Mensaje: “Este componente no tiene variantes definidas.”
- **Estado “Sin controles”** — Mensaje: “Esta variante no tiene controles editables.” o lista vacía.

---

## User flow

1. Usuario tiene abierto un componente (preview visible).
2. En el panel de variantes ve la lista; hace clic en una variante → el preview y el panel de controles se actualizan.
3. En el panel de controles cambia un valor (p. ej. texto del botón, estado disabled) → el preview se actualiza al instante sin botón “Aplicar”.
4. Puede seguir alternando variantes y jugando con controles en la misma pantalla.

---

## States to design

- **Variantes:** lista con una variante seleccionada (estado activo); hover en ítems; lista vacía (“Sin variantes”).
- **Controles:** cada tipo de control en estado default, focus y (si aplica) error (valor inválido).
- **Preview actualizando** — Opcional: micro-feedback al cambiar control (ej. breve shimmer o sin nada si es instantáneo).
- **Control deshabilitado** — Si un control no aplica a la variante actual, gris o oculto.

---

## Edge cases (UX)

- **Componente sin variantes** — Panel de variantes con mensaje “No hay variantes” y preview mostrando el componente por defecto si existe.
- **Variante sin controles** — Panel de controles vacío o mensaje “Esta variante no tiene controles”; preview sigue visible.
- **Valor inválido en control** — Por tipo (ej. número donde se esperaba texto): mensaje inline bajo el control “Valor no válido” o revertir al último valor válido; el preview no debe romperse.
- **Muchas variantes o muchos controles** — Scroll en ambos paneles; variantes como tabs si hay muchas para ahorrar espacio.
- **Controles que dependen de otro** — Si un control muestra/oculta otro, diseñar la transición (aparecer/desaparecer o deshabilitar) para que sea clara.
