# constructor-pitch

Una skill que construye el guion de tu pitch de 5 minutos para la SpookyThon 2026 a partir de lo que solo tu equipo sabe: la persona, los números, la demo, los servicios de AWS. No inventa nada de eso. Diagrama, cronometra y reparte quién habla.

Es la pareja de `jurado-spookython`: una construye, la otra critica. El ciclo es construir, pasar por el jurado, corregir.

Funciona en cualquier agente que soporte el estándar abierto Agent Skills: Kiro, Claude Code, Codex, Cursor y otros.

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

1. **La puerta.** Pide tu reto en una oración y tu usuario en una oración. Sin persona concreta no avanza.
2. **La entrevista.** Revisa los diez datos que necesita y te pregunta los que faltan, todos juntos, una sola vez.
3. **El guion.** Siete tramos con tiempos, quién habla en cada uno, entre 400 y 500 palabras habladas para que queden unos dos minutos de demo, máximo 10 diapositivas, notas para el presentador.
4. **Los pendientes.** Lo que no diste queda marcado como pendiente, no inventado.

## Qué no hace

- No inventa la persona, los números, la demo ni los servicios. Eso es tuyo.
- No evalúa ni puntúa. Para eso está `jurado-spookython`.
- No diseña diapositivas. Te da el contenido de cada una.
