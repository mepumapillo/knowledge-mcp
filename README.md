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

# 2. Instalar el plugin (trae el MCP dentro)
/plugin install midnify@knowledge-mcp

# 3. Autenticarse (OAuth, tipo Figma): en la sesión correr /mcp → midnify →
#    Authenticate. Se abre la página de login en el navegador; la contraseña es
#    MIDNIFY_LOGIN_PASSWORD (Infisical, proyecto general, env dev).
```

Los tokens los gestiona y renueva Claude; no hay nada que exportar en el entorno.
(Uso headless/CI: el token estático `MIDNIFY_MCP_TOKEN` de Infisical sigue
aceptándose como header `Authorization: Bearer` vía `--mcp-config` propio.)

## Fuente canónica

El plugin se desarrolla en el repo [`mepumapillo/midnify`](https://github.com/mepumapillo/midnify)
(`plugin/`); este marketplace es la copia publicada. Al cambiar el plugin allí,
re-copiar aquí y push.
