# Task

Diseñar el **catálogo de componentes**: vista principal con navegación (sidebar/árbol), lista de componentes, detalle con preview y variantes, búsqueda, filtros, y estados vacíos/carga/error.

**Herramienta:** se usa el MCP de **Paper** para crear los diseños en el canvas.

## Requirements

- Seguir **feature_component_catalog.md** (Screens/Views, Components & UI elements, User flow, States to design y Edge cases).
- Aplicar los design tokens y reglas de **spec/ui_spec.md** (colores, espaciado, radius, tipografía, componentes Button, Input, Card).
- Entregable es **solo diseño** en Paper: sin backend, APIs ni base de datos.
- Para la vista detalle (preview + variantes + controles), alinearse con **feature_realtime_preview.md** y **feature_variants_and_controls.md** en lo que aplique.

**Alcance del catálogo:**

- **Vista principal:** sidebar o árbol (Repositorio > Categoría > Componente), área de contenido (lista o detalle).
- **Lista de componentes:** grid o lista de tarjetas: nombre, repo/categoría, miniatura (placeholder si aplica).
- **Vista detalle:** cabecera con nombre, breadcrumb (Repo > Categoría > Componente), zona de preview y panel de variantes/controles.
- **Barra de búsqueda:** input “Buscar componentes…”, icono lupa; resultados en dropdown o página.
- **Filtros:** por repositorio y por categoría (dropdown o chips).
- **Empty states:** sin repos (“Conecta un repositorio…”) + CTA “Ir a Repositorios”; con repos pero sin componentes (“Sincronizando…” / “Aún no hay componentes”).
- **Estados a diseñar:** catálogo vacío (sin repos), lista con datos, cargando (skeletons o spinner), búsqueda sin resultados, detalle cargado; edge cases: componente no encontrado, sync en curso/error (badge “Sincronizando” / “Error de sync”).
- Layout y jerarquía visual coherentes con ui_spec (espaciado 8/16/24/32, radius 12/16, Card/Input/Button según spec).

## Output

- Catálogo de componentes en **Paper** (MCP) con:
  - Artboard(s) de **vista principal**: sidebar + área de contenido (lista de componentes o detalle).
  - Artboard de **lista de componentes** (tarjetas/grid) con datos de ejemplo.
  - Artboard de **vista detalle** de un componente (cabecera, preview, variantes/controles).
  - Barra de búsqueda y filtros integrados en la vista principal o en artboard dedicado.
  - Variantes/estados: empty state (sin repos), empty state (repos sin componentes), cargando, búsqueda sin resultados, componente no encontrado (opcional).
  - Componentes alineados a ui_spec (Card radius 16, padding 24; Input radius 12; Button height 40; tipografía y colores según tokens).
- Breve anotación o doc que indique qué tokens se usaron en sidebar, tarjetas, cabecera, búsqueda y filtros (opcional pero recomendado).
