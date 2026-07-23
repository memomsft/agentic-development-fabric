# Setup - Fabric Skills

## Requisitos

- [Entorno base de GitHub Copilot](../03-pbi-modeling-mcp/setup/02_github_copilot.md) completado (VS Code + extensión GitHub Copilot Chat).
- Node.js LTS.
- PowerShell 7, requerido por GitHub Copilot CLI. Verificar con `pwsh --version`.
- `az login` completado.

---

## Instalación

### Paso 1 - Instalar GitHub Copilot CLI

Skills for Fabric requiere **GitHub Copilot CLI**, un paquete npm (`@github/copilot`) distinto de la extensión GitHub Copilot Chat de VS Code.

Con VS Code cerrado, en una terminal (PowerShell 7):

```powershell
npm install -g @github/copilot
```

Verificar:

```powershell
copilot --version
```

Iniciar sesión (esto abre un prompt interactivo propio, distinto del prompt de PowerShell -- los siguientes comandos se escriben ahí dentro, no en `PS C:\...>`):

```powershell
copilot
```

### Paso 2 - Instalar Skills for Fabric

El comando de esta sección se escribe **dentro del prompt interactivo** de `copilot`, no en PowerShell directamente.

Con VS Code todavía cerrado:

```
/plugin install fabric-skills@copilot-plugins
```

Una vez confirmada la instalación, VS Code puede reabrirse con normalidad -- la terminal integrada solo se usa para ejecutar prompts, no para instalar o actualizar plugins.

---

## Verificación

Dentro del prompt interactivo de `copilot`:

```
/env
```

Debe aparecer el plugin `fabric-skills`, incluyendo el agente `FabricAdmin`.

---

## Advertencias conocidas

> ⚠️ El marketplace confirmado es `copilot-plugins`. `fabric-collection` no existe (falla con "Marketplace not found").

> ⚠️ **Error conocido en Windows: "Failed to install plugin: Access is denied. (os error 5)"**
> Bug documentado en GitHub Copilot CLI. Causa más común: VS Code abierto con la extensión de Copilot activa mantiene un watcher handle sobre la carpeta de plugins, bloqueando la instalación.
>
> Solución:
> 1. Cerrar VS Code por completo (no solo la terminal integrada).
> 2. Ejecutar la instalación desde una terminal fuera de VS Code.
> 3. Reabrir VS Code una vez terminada la instalación.
>
> Si persiste, verificar que no haya otra sesión de `copilot` corriendo en paralelo y cerrarla antes de reintentar.
>
> Si el error continúa, existe un workaround que evita el instalador de marketplace:
> ```
> git clone https://github.com/microsoft/skills-for-fabric.git
> copilot --plugin-dir .\skills-for-fabric
> ```

---

## Siguiente paso

👉 [Escenario - Documentar el workspace](scenarios/01_document_workspace.md)
