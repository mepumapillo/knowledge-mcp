# knowledge-mcp — marketplace de plugins de conocimiento

Marketplace de Claude Code separado de os-neoperant: aquí viven los plugins de
conocimiento personal (MCPs de notas estilo "Context7 propio"). Repo **público**:
solo contiene los plugins (URL del servidor + skills) — las notas viven detrás
del MCP con auth, nunca aquí.

## Plugins

| Plugin | Qué hace |
|---|---|
| `midnify` | Conecta el MCP de notas de Miguel (`https://midnify.srv1727066.hstgr.cloud/mcp`, OAuth) + skill `consultar-midnify` |

## Instalación (cualquier usuario)

```bash
# 1. Crear cuenta (registro abierto):
#    https://midnify.srv1727066.hstgr.cloud/signup

# 2. Agregar el marketplace e instalar el plugin (trae el MCP + skills)
/plugin marketplace add mepumapillo/knowledge-mcp
/plugin install midnify@knowledge-mcp

# 3. Autenticarse (OAuth, tipo Figma): en la sesión correr /mcp → midnify →
#    Authenticate. Se abre la página de login en el navegador: entra con TU
#    cuenta (la del paso 1).
```

Los tokens los gestiona y renueva Claude; no hay nada que exportar en el entorno.
(Uso headless/CI del owner: el token estático `MIDNIFY_MCP_TOKEN` de Infisical
sigue aceptándose como header `Authorization: Bearer` vía `--mcp-config` propio.)

## Fuente canónica

El plugin se desarrolla en el repo `mepumapillo/midnify` (privado, carpeta
`plugin/`); este marketplace es la copia publicada. Al cambiar el plugin allí,
re-copiar aquí y push.
