# knowledge-mcp — marketplace personal de plugins de conocimiento

Marketplace de Claude Code separado de os-neoperant: aquí viven los plugins de
conocimiento personal (MCPs de notas estilo "Context7 propio").

## Plugins

| Plugin | Qué hace |
|---|---|
| `midnify` | Conecta el MCP de notas personales (`https://midnify.srv1727066.hstgr.cloud/mcp`, Bearer auth) + skill `consultar-midnify` |

## Instalación en una máquina nueva

```bash
# 1. Agregar el marketplace (repo privado — requiere gh/git autenticado)
/plugin marketplace add mepumapillo/knowledge-mcp

# 2. Instalar el plugin
/plugin install midnify@knowledge-mcp

# 3. Auth: el MCP exige MIDNIFY_MCP_TOKEN en el entorno (vive en Infisical,
#    proyecto general, env dev). Lanzar Claude con el token inyectado:
MIDNIFY_MCP_TOKEN=$(infisical --domain="https://infisical.srv1727066.hstgr.cloud" \
  secrets get MIDNIFY_MCP_TOKEN \
  --projectId c0e59779-a204-48f4-a759-2a511fb64b8b --env dev --plain --silent) claude
```

Sin el token, el servidor responde `401` y el MCP no conecta — esa es la auth.

## Fuente canónica

El plugin se desarrolla en el repo [`mepumapillo/midnify`](https://github.com/mepumapillo/midnify)
(`plugin/`); este marketplace es la copia publicada. Al cambiar el plugin allí,
re-copiar aquí y push.
