# Caso conectado: Descubrir → Diseñar → Construir → Consultar

Este documento describe cómo las tres secciones de este repositorio (Fabric MCP Server, Fabric Skills, PBI Modeling MCP) se encadenan sobre el mismo entorno (`environment/`), en vez de ser tres ejercicios independientes.

---

## El flujo

| Paso | Sección | Qué responde | Referencia |
|---|---|---|---|
| 1. Descubrir | [Fabric MCP Server](../01-fabric-mcp-server/) | ¿Qué existe en la plataforma? | [Escenario](../01-fabric-mcp-server/scenarios/01_onelake_catalog_discovery.md) |
| 2. Diseñar | [Fabric Skills](../02-fabric-skills/) | ¿Cómo debería estructurarse? | [Escenario](../02-fabric-skills/scenarios/01_document_workspace.md) |
| 3. Construir | [PBI Modeling MCP](../03-pbi-modeling-mcp/) | Refinar el semantic model contra mejores prácticas | [Escenarios 01-06, 08](../03-pbi-modeling-mcp/scenarios/) |
| 4. Consultar | [PBI Modeling MCP (Remote)](../03-pbi-modeling-mcp/) | Responder una pregunta de negocio en lenguaje natural | [Escenario 07](../03-pbi-modeling-mcp/scenarios/07_remote_dax_query.md) |

---

## Paso 1 - Descubrir

Prompt de referencia (ver [prompts de esta sección](../01-fabric-mcp-server/prompts/prompts_es.md)):

```
Busca en el catálogo de OneLake items relacionados con 'sales'
```

Este paso identifica los items reales del workspace `powerbi-mcp-demo` -- el Lakehouse `SalesLakehouse` y el Semantic Model `SalesModel` -- que los pasos siguientes usan por nombre.

## Paso 2 - Diseñar

Prompt de referencia (adaptado para hacer referencia explícita al item descubierto en el Paso 1):

```
Usando FabricDataEngineer, diseña una arquitectura medallion (Bronze/Silver/Gold) para el SalesLakehouse que se encontró en el workspace powerbi-mcp-demo
```

El resultado es una propuesta de arquitectura que trata el semantic model del Paso 3 como la capa Gold de ese diseño.

## Paso 3 - Construir

Este paso usa los escenarios ya documentados en [PBI Modeling MCP](../03-pbi-modeling-mcp/scenarios/), en particular:
- [01 - Conectar](../03-pbi-modeling-mcp/scenarios/01_connect.md)
- [02 - Crear relaciones](../03-pbi-modeling-mcp/scenarios/02_relationships.md)
- [05 - Best practices](../03-pbi-modeling-mcp/scenarios/05_best_practices.md)

El semantic model refinado aquí es el mismo que el Paso 2 identificó conceptualmente como la capa Gold.

## Paso 4 - Consultar

Cierre del flujo con una pregunta de negocio en lenguaje natural sobre el modelo ya refinado, usando el Remote MCP -- ver [Escenario 07](../03-pbi-modeling-mcp/scenarios/07_remote_dax_query.md).

---

## Por qué está encadenado y no son 3 ejercicios sueltos

Cada paso hace referencia explícita al resultado del paso anterior (`SalesLakehouse`, `SalesModel`) en vez de usar prompts genéricos sin contexto. El mismo entorno (`environment/`) sostiene los cuatro pasos.
