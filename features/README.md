# Features — codeCollection (Design flows)

Este directorio contiene las **features** como **flujos de diseño** para Figma (u otra herramienta de diseño). No describen APIs, bases de datos ni backend: describen **qué pantallas, vistas, modales y componentes** hay que diseñar y cómo fluye el usuario por ellas.

Cada feature incluye:

- **Description** — Qué hace el usuario en este flujo.
- **Screens / Views** — Pantallas o vistas que intervienen (páginas, modales, secciones).
- **Components & UI elements** — Formularios, botones, listas, campos, modales, etc.
- **User flow** — Pasos del usuario de principio a fin.
- **States to design** — Estados de UI: default, loading, error, empty, éxito.
- **Edge cases (UX)** — Casos límite que el usuario puede ver (errores, vacíos, permisos).

**Product spec de referencia:** [product_spec.md](../spec/product_spec.md)

---

## Índice de features

| Feature | Archivo |
|--------|---------|
| Register User | [feature_create_user.md](feature_create_user.md) |
| Authentication | [feature_authentication.md](feature_authentication.md) |
| Organization Management (B2B) | [feature_organization_management.md](feature_organization_management.md) |
| Repository Management | [feature_repository_management.md](feature_repository_management.md) |
| Component Catalog | [feature_component_catalog.md](feature_component_catalog.md) |
| Realtime Preview | [feature_realtime_preview.md](feature_realtime_preview.md) |
| Variants and Controls | [feature_variants_and_controls.md](feature_variants_and_controls.md) |
| MCP Integration (Setup in UI) | [feature_mcp_integration.md](feature_mcp_integration.md) |

---

## Orden sugerido para diseñar

1. feature_create_user.md — Registro  
2. feature_authentication.md — Login, logout, recuperar contraseña  
3. feature_organization_management.md — Organizaciones y miembros  
4. feature_repository_management.md — Conectar y listar repos  
5. feature_component_catalog.md — Navegación del catálogo  
6. feature_realtime_preview.md — Área de preview  
7. feature_variants_and_controls.md — Paneles de variantes y controles  
8. feature_mcp_integration.md — Pantalla de configuración MCP  
