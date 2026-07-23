# Setup - Fabric MCP Server

## Requisitos

- [Entorno base de GitHub Copilot](../03-pbi-modeling-mcp/setup/02_github_copilot.md) completado (VS Code + extensión GitHub Copilot Chat).

---

## Instalación

1. VS Code → Extensions (`Ctrl+Shift+X`)
2. Buscar: `Microsoft Fabric MCP Server`
3. Publisher: **Microsoft**
4. Clic en **Install**
5. Si no se auto-inicia: paleta de comandos (`Ctrl+Shift+P`) → `MCP: List Servers` → `Fabric MCP Server` → `Start Server`

---

## Verificación

1. Copilot Chat (`Ctrl+Shift+I`) → modo Agent → ícono de herramientas 🔧
2. Refrescar y confirmar que `Fabric MCP Server` aparece en la lista, junto a `powerbi-modeling-mcp` y `powerbi-remote`.

Verificación de solo lectura, antes de usar herramientas de escritura:
```
What Fabric workload types are available?
```
```
Busca en el catálogo de OneLake items relacionados con 'powerbi-mcp-demo'
```

---

## Advertencias conocidas

> ⚠️ **Esta extensión mezcla dos tipos de herramientas bajo un mismo nombre.** Su propia descripción dice "corre localmente, nunca se conecta a tu entorno de Fabric en vivo" -- pero la lista real de herramientas incluye acciones que sí tocan el tenant real: búsqueda en el catálogo de OneLake across workspaces, y operaciones de Data Factory como `create_pipeline` y `run_pipeline`. La documentación de Microsoft se contradice a sí misma en este punto.
>
> `create_pipeline` y `run_pipeline` ejecutan acciones reales sobre el tenant (creación y ejecución de pipelines de Data Factory). No ejecutar sin validación previa del entorno.

> ⚠️ Fabric MCP Server también tiene una contraparte remota, **Fabric Core MCP** (`https://api.fabric.microsoft.com/v1/mcp/core`, registrado vía `MCP: Add Server`). Esa versión remota falla en la autenticación con `AADSTS9010010`, reportado en el foro de Fabric Community, sin fecha de arreglo confirmada. Este setup documenta únicamente la versión local (extensión de VS Code), que sí funciona.

---

## Siguiente paso

👉 [Escenario - Descubrir el catálogo de OneLake](scenarios/01_onelake_catalog_discovery.md)
