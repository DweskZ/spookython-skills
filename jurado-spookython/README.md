# jurado-spookython

Se porta como jurado de la SpookyThon 2026. Le pegas el pitch, te hace tres preguntas, pone nota con los cuatro criterios públicos y te deja tres cambios.

Funciona en Kiro, Claude Code, Codex, Cursor y en cualquier agente que lea Agent Skills. La carpeta es la skill. Cambia solo el lugar donde la copias.

## Instalar

Díganle al agente: "Descarga e instala estas skills: https://github.com/DweskZ/spookython-skills". El agente copia la carpeta.

A mano, la carpeta `jurado-spookython` completa (con `references/` y `assets/`) va en la carpeta de skills del proyecto:

| Agente | Carpeta |
| --- | --- |
| Kiro | `.kiro/skills/jurado-spookython/` |
| Claude Code | `.claude/skills/jurado-spookython/` |
| Otros | Revisa en la documentación de tu agente dónde busca `SKILL.md` |

Ejemplo con Kiro, desde la raíz de tu proyecto:

```bash
mkdir -p .kiro/skills
cp -r /ruta/a/jurado-spookython .kiro/skills/
```

## Usar

Escribe en el chat de tu agente algo como:

- "Evalúa mi pitch" y pega el texto.
- "Simula el jurado con mi reto".
- "¿Qué preguntas me va a hacer el jurado?"
- "¿Cómo preparo mi pitch?" para el modo estudio.

En Kiro también puedes invocarla con `/jurado-spookython` seguido de tu pitch.

Úsala después de `constructor-pitch`: primero el guion, después el jurado.

Si tu equipo todavía no recibió su reto, puedes practicar con un reto hipotético que elijas. La estructura y las preguntas son las mismas.

## El flujo

1. Primero pide el reto en una oración y una persona con nombre, rol y situación. Si contestan "la comunidad" o "todos", no sigue.
2. Lee el pitch, lo parte en los siete tramos, estima el tiempo hablado, pone nota y hace tres preguntas.
3. Ustedes responden como lo harían frente al jurado. Ahí mira si hay un dato, un "no lo sé" con plan, o un invento.
4. Después llega el informe: tres cambios, del que más mueve la nota al que menos.

El pitch lo reescriben ustedes. Aquí reciben el cambio y, como mucho, una frase de ejemplo. La persona, el número y la demo salen de lo que ustedes contaron. La nota usa los cuatro criterios que publicó la organización. Los pesos no están publicados.
