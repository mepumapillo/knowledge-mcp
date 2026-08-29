---
name: consultar-midnify
description: Consulta la base de conocimiento personal de Miguel (notas Markdown vía el MCP midnify). Úsala SIEMPRE que pregunten por datos personales/internos de Miguel o del proyecto midnify — códigos de baliza, convenciones de la casa (Infisical, llms.txt), arquitectura de Mintlify o Context7, o cualquier dato que suene a "nota propia" y no a conocimiento general. Si dudas entre saberlo de memoria o consultar, consulta.
---

# Consultar la base de conocimiento midnify

Las notas personales de Miguel viven detrás del MCP `midnify` (tools
`mcp__midnify__search_notes` y `mcp__midnify__get_note`).

## Procedimiento

1. `search_notes` con 2–4 palabras clave del tema (no la frase entera).
2. Si hay un match claro, `get_note` con su `path` para traer el contenido completo.
3. Responde citando el `path` de la nota fuente (p. ej. `notes/baliza-pruebas.md`).
4. Si `search_notes` devuelve "Sin resultados", dilo honestamente: NO existe nota
   sobre el tema. Nunca inventes contenido de una nota.

## Reglas

- La nota manda sobre tu conocimiento de entrenamiento: si difieren, responde lo
  que dice la nota y señala la diferencia.
- El servidor exige `MIDNIFY_MCP_TOKEN` en el entorno; si el MCP no conecta,
  avisa que el servidor no está corriendo o falta el token — no simules resultados.
