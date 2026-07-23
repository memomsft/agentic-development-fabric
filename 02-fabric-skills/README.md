# Fabric Skills

Exploración de las capacidades de [Skills for Fabric](https://github.com/microsoft/skills-for-fabric) de Microsoft, un conjunto de instrucciones (`SKILL.md`) que enseña a agentes de IA a operar sobre Microsoft Fabric.

> ⚠️ **Public Preview**: Este proyecto está en Public Preview.

---

## ¿Qué es Fabric Skills?

A diferencia de un servidor MCP, Skills for Fabric no ejecuta nada por sí mismo. Son instrucciones que un agente de IA (GitHub Copilot CLI o Claude Code) carga al inicio de una sesión, incluyendo agentes especializados como `FabricAdmin`, `FabricDataEngineer`, `FabricAppDev` y `FabricMigrationEngineer`. El agente es quien decide qué hacer y qué herramientas usar -- Skills provee el conocimiento, no la ejecución.

---

## Rol en el ejercicio conectado

Esta sección cubre la capa de **diseño**: con base en lo que se descubrió en la plataforma, un agente experto propone cómo debería estructurarse. Ver [el caso conectado completo](../docs/connected-scenario.md).

---

## Estructura de esta sección

```
02-fabric-skills/
├── README.md
├── setup.md
├── scenarios/
│   └── 01_document_workspace.md
└── prompts/
    ├── prompts.md      ← Prompts validados (inglés)
    └── prompts_es.md   ← Prompts validados (español)
```

---

## Requisitos generales

- [Entorno compartido](../environment/01_fabric_setup.md) ya creado (Lakehouse + Semantic Model).
- GitHub Copilot CLI (paquete npm, distinto de la extensión de VS Code).

---

## Comenzar

👉 **Paso 1:** [Setup](setup.md)

👉 **Paso 2:** [Escenario - Documentar el workspace](scenarios/01_document_workspace.md)
