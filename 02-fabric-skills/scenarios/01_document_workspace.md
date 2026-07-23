# Fabric Skills: Documentar el Workspace

## Dónde corre

A diferencia de PBI Modeling MCP (panel de Copilot Chat), este corre en la terminal integrada de VS Code, con GitHub Copilot CLI. Ver [Setup](../setup.md).

## Valor

Amplía el alcance más allá del semantic model: documentación de todo el workspace (Lakehouse + Semantic Model) generada por un agente que sigue instrucciones (Skills), no por un servidor MCP que ejecuta directamente.

## Diferencia con PBI Modeling MCP

| | PBI Modeling MCP | Fabric Skills (este escenario) |
|--|:---:|:---:|
| Qué es | Servidor MCP (ejecuta) | Instrucciones `SKILL.md` (enseñan) |
| Dónde corre | VS Code + Copilot Chat | VS Code, terminal integrada |
| Alcance | Solo el Semantic Model | Todo el workspace |
| Quién ejecuta la acción | El servidor MCP directamente | El agente, siguiendo el skill |

## Prompt

Dentro de una sesión de `copilot`:

```
Usando FabricAdmin, documenta mi workspace powerbi-mcp-demo
```

Versión en inglés, en caso de que el agente no reconozca la instrucción en español:

```
Using FabricAdmin, document my Workspace powerbi-mcp-demo
```

## Qué hace

El agente carga el skill de administración (`FabricAdmin`), identifica los items del workspace `powerbi-mcp-demo` -- incluyendo el Lakehouse `SalesLakehouse` y el Semantic Model `SalesModel` -- y genera documentación de metadata sin llamadas manuales a la API.

## Resultado esperado

Un archivo `.md` con la documentación del workspace completo (no solo del modelo), guardado en la carpeta de trabajo activa.

## Requiere

[Setup - Fabric Skills](../setup.md)

## Nota

Skills for Fabric produce documentación y definiciones de items, pero no genera reportes de Power BI terminados -- eso sigue siendo trabajo del Modeling MCP o de Power BI Desktop.

---
👉 [Continuar con PBI Modeling MCP](../../03-pbi-modeling-mcp/README.md)
