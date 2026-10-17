# jurado-spookython

Una skill que se comporta como el jurado de la SpookyThon 2026. Le pegas tu pitch, te hace las preguntas incómodas, te puntúa con los cuatro criterios públicos y te devuelve tres cambios concretos.

Funciona en cualquier agente que soporte el estándar abierto Agent Skills: Kiro, Claude Code, Codex, Cursor y otros. La carpeta es la skill; lo único que cambia es dónde la copias.

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

1. **La puerta.** Antes de evaluar, el jurado pide tu reto en una oración y tu usuario en una oración: una persona concreta, con rol y situación. Si respondes "la comunidad" o "todos", no avanza.
2. **El pitch.** Mapea tu texto a los siete tramos del pitch de 5 minutos, estima el tiempo hablado, puntúa los cuatro criterios públicos con evidencia y te hace tres preguntas incómodas.
3. **Las respuestas.** Respondes las tres preguntas como lo harías frente al jurado real. El simulador juzga si hay evidencia, honestidad o bluff.
4. **El informe.** Estructura, criterios, preguntas y exactamente tres cambios ordenados por impacto.

## Qué no hace

- No reescribe tu pitch. Da cambios, no reemplazos.
- No inventa la persona, el número de contraste ni la demo por ti. Eso lo decides tú.
- No conoce ponderaciones ni rúbricas internas. Usa solo lo que la organización publicó: Uso de AWS, Impacto, Pitch y Demo.
