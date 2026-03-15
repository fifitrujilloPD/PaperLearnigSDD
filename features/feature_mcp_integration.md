# Feature: MCP Integration (Setup & Discovery in UI)

## Description

Flujo de diseño para la parte **visible en la app** de la integración MCP: cómo el usuario configura o descubre el uso de MCP (instrucciones, enlace a documentación, token o URL de conexión si aplica) y cómo ve que sus componentes están disponibles para agentes de IA. No se especifica el protocolo MCP; solo las pantallas, componentes y mensajes que el usuario ve en Figma.

---

## Screens / Views

- **Configuración / Integraciones** — Sección “MCP” o “Agentes de IA”: texto explicativo, pasos para conectar (ej. “Añade el servidor MCP de codeCollection en Cursor”), y opcionalmente campo para API key o URL si la app la expone.
- **Instrucciones o ayuda** — Bloque de copy + enlace “Ver documentación” o “Cómo usar con Cursor”; posible código de ejemplo (snippet) para pegar en configuración del cliente MCP.
- **Estado de conexión (si aplica)** — Indicador “Conectado” / “No configurado” cuando la app pueda comprobar uso (opcional).
- **Empty state** — “Conecta codeCollection a tu agente de IA para usar tus componentes al generar código.” con CTA “Ver instrucciones”.

---

## Components & UI elements

- **Sección MCP** — Título “Integración con agentes de IA (MCP)”, párrafo explicativo, lista de pasos numerados (1. Abre Cursor / cliente MCP, 2. Añade el servidor…).
- **Link “Abrir documentación”** o “Cómo configurar MCP”.**
- **Campo “API key” o “URL del servidor”** — Si la app muestra un token o URL para que el usuario la copie o pegue en el cliente MCP; botón “Copiar”.
- **Snippet de configuración** — Bloque de código (JSON o texto) con botón “Copiar” para que el usuario lo pegue en Cursor u otro cliente.
- **Badge o mensaje** — “Tus componentes están disponibles para agentes que usen esta integración.” cuando esté configurado.
- **Alert o notice** — “Necesitas al menos un repositorio conectado y sincronizado para que los componentes aparezcan en MCP.”

---

## User flow

1. Usuario entra a Configuración > Integraciones (o “MCP” / “Agentes de IA”).
2. Lee la explicación y los pasos; opcionalmente copia API key o snippet de configuración.
3. Abre Cursor (u otro cliente), pega la config y guarda.
4. Vuelve a codeCollection y ve confirmación tipo “Tus componentes están disponibles para agentes de IA” (si la app puede indicarlo).

---

## States to design

- **Por defecto** — Instrucciones visibles, botón “Copiar” para snippet o API key; sin estado “Conectado” si no hay verificación.
- **Con repos y catálogo** — Mensaje positivo: “Tu catálogo está disponible para clientes MCP configurados.”
- **Sin repos o catálogo vacío** — Notice: “Conecta y sincroniza al menos un repositorio para que los componentes aparezcan en MCP.”
- **Copia realizada** — Toast “Copiado al portapapeles” junto al botón “Copiar”.

---

## Edge cases (UX)

- **Usuario sin permisos** — Ocultar sección MCP o mostrar solo texto informativo sin opción de copiar token/snippet.
- **Organización sin componentes** — Mismo mensaje que empty: “Aún no hay componentes. Conecta un repositorio y sincroniza.”
- **Documentación externa** — El enlace “Ver documentación” abre sitio externo; indicar que se abre en nueva pestaña.
- **Token o URL expuesta** — Si se muestra API key o URL, diseño que no parezca “contraseña” editable a la ligera; solo “Copiar” y mensaje de no compartirla.
- **Cliente MCP no compatible** — No se puede detectar desde la app; las instrucciones deben mencionar “Cursor y otros clientes compatibles con MCP” para set expectations.
