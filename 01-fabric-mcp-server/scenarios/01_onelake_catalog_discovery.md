# Fabric MCP Server: Descubrir el Catálogo de OneLake

## Dónde corre

Mismo lugar que PBI Modeling MCP: VS Code + Copilot Chat, modo Agent. Ver [Setup](../setup.md).

## Valor

Una capa de descubrimiento: en vez de operar sobre el semantic model (PBI Modeling MCP) o dar instrucciones de alto nivel (Fabric Skills), esta herramienta busca en el catálogo real de OneLake a través de workspaces.

## Prompts

Verificación básica, sin tocar el tenant:
```
What Fabric workload types are available?
```

Búsqueda real en el catálogo (solo lectura):
```
Busca en el catálogo de OneLake items relacionados con 'powerbi-mcp-demo'
```

Versión en inglés, en caso de que el agente no reconozca la instrucción en español:
```
Search the OneLake catalog for items related to 'powerbi-mcp-demo'
```

## Qué hace

El agente consulta el catálogo de OneLake y devuelve los items reales que coinciden con la búsqueda -- en este caso, el Lakehouse `SalesLakehouse` y el Semantic Model `SalesModel` del workspace `powerbi-mcp-demo`.

## Requiere

[Setup - Fabric MCP Server](../setup.md)

## Diferencia con PBI Modeling MCP

Este servidor no toca el Semantic Model (tablas, medidas, relaciones) -- ese alcance es de PBI Modeling MCP.

## No incluido en este escenario a propósito

Esta misma extensión también expone herramientas de escritura/ejecución real, como `create_pipeline` y `run_pipeline` (Data Factory). Estas herramientas ejecutan acciones reales sobre el tenant y no se documentan como parte de este escenario.

## Public Preview

Fabric MCP Server es un proyecto open source en Public Preview: las tools disponibles pueden cambiar antes de GA.

---
👉 [Continuar con Fabric Skills](../../02-fabric-skills/README.md)
