# Product Specification

## Product Name

**codeCollection**

---

## Description

codeCollection es una plataforma B2B que permite a empresas de desarrollo de software centralizar, versionar y reutilizar sus bibliotecas de componentes (Storybooks). Las compañías pueden guardar sus repositorios de componentes en un único lugar, visualizar componentes y sus variantes en tiempo real con paneles de control, y exponer ese catálogo a agentes de IA mediante MCP (Model Context Protocol) para que los equipos usen sus propios componentes dentro de flujos asistidos por IA.

---

## Primary Users

- **Empresas de desarrollo de software** que mantienen design systems o bibliotecas de componentes (Storybook u equivalentes).
- **Equipos de producto y frontend** que necesitan un catálogo vivo de componentes, documentado y con variantes.
- **Desarrolladores y diseñadores** que quieren descubrir, revisar y reutilizar componentes sin salir de sus flujos de trabajo.
- **Equipos que adoptan agentes de IA** y quieren que esos agentes usen los componentes oficiales de la empresa (vía MCP) en lugar de generar código genérico.

---

## Problem Statement (SDD)

Las empresas acumulan Storybooks y repositorios de componentes dispersos, sin un lugar único donde ver todas las variantes, probar controles y documentar uso. Además, los agentes de IA no conocen los componentes propietarios de la empresa, lo que genera código inconsistente o que hay que refactorizar. codeCollection resuelve la **centralización del catálogo de componentes** y la **integración de ese catálogo con agentes de IA** mediante MCP.

---

## Core Features

1. **Gestión de repositorios de componentes**
  - Conectar y guardar repositorios que contienen Storybooks (o catálogos de componentes).
  - Sincronización y versionado del catálogo (por rama, tag o commit).
2. **Creación y organización de componentes**
  - Los usuarios pueden crear y mantener componentes dentro de sus repositorios vinculados.
  - Estructura por proyectos/organizaciones y permisos básicos (B2B).
3. **Visualización en tiempo real**
  - Vista de componentes en tiempo real en el navegador.
  - Navegación por categorías, paquetes o nombres de componentes.
4. **Variantes y paneles de control**
  - Visualización de todas las variantes (stories) de cada componente.
  - Paneles de control (controls) para ajustar props y ver el resultado al instante.
5. **MCP para agentes de IA**
  - Servidor o integración MCP que expone el catálogo de componentes de la empresa.
  - Los agentes de IA (p. ej. en Cursor u otros clientes MCP) pueden descubrir y usar esos componentes al generar código, manteniendo consistencia con el design system.
6. **Autenticación y modelo B2B**
  - Registro y autenticación de usuarios en contexto organizacional (empresa/equipo).
  - Gestión de acceso por organización (según modelo de producto B2B).

---

## Success Criteria

- Un usuario puede **crear un repositorio** y ver su catálogo de componentes en codeCollection
- Un usuario puede **encontrar un componente, cambiar controles y ver la variante actualizada** en tiempo real en una sola pantalla.
- Un desarrollador puede **usar el MCP de codeCollection** desde un agente de IA y obtener sugerencias o código que referencia componentes reales de su empresa.
- Las empresas pueden **gestionar múltiples repositorios de componentes** desde una sola cuenta/organización.

---

## Key User Stories (SDD)


| Como…            | quiero…                                                            | para…                                              |
| ---------------- | ------------------------------------------------------------------ | -------------------------------------------------- |
| Lead de frontend | centralizar nuestros Storybooks en un solo lugar                   | que el equipo tenga una única fuente de verdad.    |
| Desarrollador    | ver todas las variantes de un componente y jugar con los controles | validar diseños y documentar comportamiento.       |
| Diseñador        | revisar el componente en tiempo real según props                   | asegurar que implementación y diseño coinciden.    |
| Dev que usa IA   | que el agente use nuestros componentes vía MCP                     | generar código alineado con nuestro design system. |
| Admin de cuenta  | gestionar repos y acceso por equipo                                | controlar qué se expone y quién puede verlo.       |


---

## Out of Scope (v1)

- Sustituir Storybook como herramienta de desarrollo local; codeCollection es catálogo y acceso centralizado, no el reemplazo del flujo de desarrollo en repo.
- Editor visual de componentes (drag-and-drop para crear componentes desde cero en la plataforma).

---

## Assumptions

- Los usuarios ya tienen Storybooks (o export compatible) en sus repositorios.
- Los clientes MCP que consuman el servidor MCP soportan las capacidades necesarias (tools/resources que se definan en el spec técnico).
- El modelo B2B implica organizaciones/workspaces por empresa y control de acceso por rol (admin, miembro, etc.) en iteraciones futuras si no en v1.
