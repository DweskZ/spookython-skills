---
name: constructor-pitch
description: "Trigger: armar pitch, construir pitch, escribir mi pitch, guion del pitch, diapositivas del pitch, SpookyThon. Builds a 5-minute SpookyThon pitch script from facts the team supplies; never invents user, numbers or demo."
license: Apache-2.0
metadata:
  author: "DweskZ"
  version: "1.1"
---

## Activation Contract

Load when a SpookyThon 2026 team asks to write, build, structure, or draft its 5-minute pitch, its script, or its slide list.

## Hard Rules

- Reply in neutral Spanish. Write the script in the team's voice, first person plural.
- Do not build until the team states its challenge in one sentence and its user in one sentence: a concrete person with a role and a situation. "Todos", "la comunidad", "los ciudadanos" is not a user. Ask again and stop.
- Never invent the person, the contrast numbers, the demo flow, the AWS services, or the cost. Collect them with `references/entrevista.md`. Anything the team does not give becomes `[PENDIENTE: qué falta]` in the script, never a made-up value.
- Ask for every missing input in one grouped message, then stop. Never one question per turn.
- The spoken script targets 400 to 500 words. Hard ceiling: 550. The demo block is about two minutes of showing, not reading, so a 700-word script leaves no time to show it. Report the word count and the estimated spoken time at 140 words per minute.
- Maximum 10 slides, one idea per slide, no list longer than three items.
- Use only the four public criteria in `references/criterios-publicos.md`.
- Do not score or evaluate the pitch. Point the team to the `jurado-spookython` skill for that.

## Decision Gates

| Input | Action |
|---|---|
| No challenge sentence or no user sentence | Ask only for the missing gate item, then stop |
| Gate passed, inputs missing | Extract every input already present in what the team wrote. Send the grouped interview from `references/entrevista.md` for the missing items only, then stop |
| All inputs present, or the team accepts placeholders | Build the script with `assets/guion-pitch.md` |
| Team asks to shorten or change one part | Edit only the named tramo and keep the rest |

## Execution Steps

1. Gate: if the message already contains the challenge in one sentence and a concrete person, extract both and continue. If either is missing or the person is "todos", "la comunidad" or "los ciudadanos", ask only for the missing gate item, then stop.
2. Check the ten inputs in `references/entrevista.md` against what the team already wrote. Ask once, only for what is missing.
3. Write the seven tramos in `references/estructura-pitch.md` with their time marks, using only the team's facts. Call the demo's peak "momento wow".
4. Count spoken words. Aim for 400 to 500. If over 550, cut from tramos 5 and 6 first. Never cut tramos 1, 4, or 7. Keep tramo 4 short: the team shows that part.
5. Derive the slide list (max 10) and the speaker notes from the script. Assign who speaks each tramo from the team roles.
6. Deliver with `assets/guion-pitch.md` and close with one line suggesting the team run `jurado-spookython` on the result.

## Output Contract

Markdown in Spanish following `assets/guion-pitch.md`: Datos usados, Guion por tramo con tiempos y quién habla, Lista de diapositivas, Notas para el presentador, Conteo de palabras y tiempo, Pendientes.

## References

- `references/entrevista.md` — the ten inputs the team must supply and the exact question for each.
- `references/estructura-pitch.md` — the seven tramos with times, principles, and criteria.
- `references/criterios-publicos.md` — the four public criteria, deliverables, and dates.
- `assets/guion-pitch.md` — output template.
