# constructor-pitch

Arma el guion de 5 minutos con lo que el equipo ya sabe: la persona, los números, la demo y los servicios. Pone los tiempos y quién habla. Si un dato no está, el guion dice pendiente.

Después pásenlo por `jurado-spookython`.

Funciona en Kiro, Claude Code, Codex, Cursor y en cualquier agente que lea Agent Skills.

## Instalar

Díganle al agente: "Descarga e instala estas skills: https://github.com/DweskZ/spookython-skills". El agente copia la carpeta.

A mano, la carpeta `constructor-pitch` completa (con `references/` y `assets/`) va en la carpeta de skills del proyecto:

| Agente | Carpeta |
| --- | --- |
| Kiro | `.kiro/skills/constructor-pitch/` |
| Claude Code | `.claude/skills/constructor-pitch/` |
| Otros | Revisa en la documentación de tu agente dónde busca `SKILL.md` |

## Usar

- "Arma mi pitch" y cuenta lo que tengas.
- "Escribe el guion del pitch con estos datos".
- "Dame la lista de diapositivas".

En Kiro también puedes invocarla con `/constructor-pitch`.

## El flujo

1. Pide el reto en una oración y una persona con nombre. Sin eso no sigue.
2. Mira los diez datos y pregunta los que faltan, todos juntos, una sola vez.
3. Devuelve siete tramos con tiempos y quién habla. Lo hablado queda entre 400 y 500 palabras, para dejar unos dos minutos de demo. Hasta diez diapositivas, con el contenido de cada una, y notas para quien presenta.
4. Lo que no contaron queda escrito como pendiente.

La nota la pone `jurado-spookython`. Aquí no hay puntaje.
