# Fabric MCP Server

Exploración de las capacidades de [Fabric MCP Server](https://github.com/microsoft/mcp/tree/main/servers/Fabric.Mcp.Server) de Microsoft, una extensión de VS Code que expone conocimiento y operaciones de Microsoft Fabric a un agente de IA.

> ⚠️ **Public Preview**: Este proyecto está en Public Preview. Las tools disponibles pueden cambiar antes de GA.

---

## ¿Qué es Fabric MCP Server?

Fabric MCP Server es una extensión de VS Code que conecta un agente de IA (GitHub Copilot en modo Agent) con Microsoft Fabric. Su documentación oficial la describe como una herramienta "local-first" que nunca se conecta al entorno real -- sin embargo, su lista real de herramientas incluye acciones que sí ejecutan sobre el tenant, como la búsqueda en el catálogo de OneLake y operaciones de Data Factory. Ver la advertencia detallada en [Setup](setup.md).

---

## Rol en el ejercicio conectado

Esta sección cubre la capa de **descubrimiento**: encontrar qué existe en la plataforma antes de diseñar o construir sobre ello. Ver [el caso conectado completo](../docs/connected-scenario.md).

---

## Estructura de esta sección

```
01-fabric-mcp-server/
├── README.md
├── setup.md
├── scenarios/
│   └── 01_onelake_catalog_discovery.md
└── prompts/
    ├── prompts.md      ← Prompts validados (inglés)
    └── prompts_es.md   ← Prompts validados (español)
```

---

## Requisitos generales

- [Entorno compartido](../environment/01_fabric_setup.md) ya creado (Lakehouse + Semantic Model).
- VS Code con la extensión GitHub Copilot Chat.

---

## Comenzar

👉 **Paso 1:** [Setup](setup.md)

👉 **Paso 2:** [Escenario - Descubrir el catálogo de OneLake](scenarios/01_onelake_catalog_discovery.md)
