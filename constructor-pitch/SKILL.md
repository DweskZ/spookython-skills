---
name: constructor-pitch
description: "Trigger: armar pitch, construir pitch, escribir mi pitch, guion del pitch, diapositivas del pitch, SpookyThon. Builds a 5-minute SpookyThon pitch from facts the team supplies; never invents the user, numbers, or demo."
license: Apache-2.0
metadata:
  author: "DweskZ"
  version: "1.3"
---

## Activation Contract

Load when a SpookyThon 2026 team asks to write, build, structure, or draft its 5-minute pitch, its script, or its slide content.

## Hard Rules

- Reply in Spanish. The questions and the notes follow `references/voz.md`. The script itself is first person plural, the way the team will say it. Template headings stay.
- A user is one named person, with a role, a place, and a moment. "Todos", "la comunidad", "los ciudadanos", "los dueños", "los clientes", "la gente" or "los usuarios" is not a user. Ask for a name and stop.
- Never invent the person, the contrast numbers, their source, the demo flow, the momento wow, the AWS services, or the cost. A number without a source the team stated is `[PENDIENTE: fuente]`, not a line in the script.
- Ask for every missing input in one grouped message, then stop. Do not continue to a later step in that same reply.
- Spoken words, excluding headings and `[PENDIENTE]` markers: target 400 to 500, ceiling 550. Tramo 4 narration stays under 80 words, because the team shows that block. Report the count and the time at 140 words per minute.
- Maximum 10 slides, one idea per slide, no list longer than three items. Return the markdown template only.
- Use only the four public criteria in `references/criterios-publicos.md`.
- Do not score the pitch. The last line points the team to `jurado-spookython`.

## Decision Gates

| Input | Action |
|---|---|
| No challenge sentence, or the user has no name | Ask only for the missing gate item, then stop |
| Gate passed, any of the ten inputs missing | Extract what they already wrote. Ask `references/entrevista.md` for the missing items only, then stop |
| All inputs present, or the team says to continue with placeholders | Build with `assets/guion-pitch.md` |
| Team asks to change one tramo | Edit only that tramo |

## Execution Steps

1. Gate. Stop if it fails.
2. Match the ten inputs in `references/entrevista.md` to the message. Ask once for the gaps. Stop.
3. Write the seven tramos in `references/estructura-pitch.md` from the team's facts only. Name the demo peak "momento wow". If they did not describe one, mark `[PENDIENTE: momento wow]` and do not invent it.
4. Count spoken words only. If over 550, cut tramos 5 and 6 first. Shorten tramo 4 narration to under 80 words without deleting the flow.
5. Derive at most 10 slides and the speaker notes. Assign speakers from the roles they gave. If roles are missing, use one speaker and `[PENDIENTE: quién habla]`.
6. Deliver `assets/guion-pitch.md`. Before sending, check that every number in the script appears with its source under Datos usados. If it does not, replace it with `[PENDIENTE: fuente]`.

## Output Contract

Markdown in Spanish, only the sections in `assets/guion-pitch.md`: Datos usados, Guion por tramo, Diapositivas, Notas para el presentador, Conteo, Pendientes. Close with one line telling the team to run `jurado-spookython` on this script.

## References

- `references/entrevista.md` — the ten inputs the team must supply and the exact question for each.
- `references/estructura-pitch.md` — the seven tramos with times, principles, and criteria.
- `references/criterios-publicos.md` — the four public criteria, deliverables, dates, and score anchors.
- `references/voz.md` — how the Spanish the team reads should sound.
- `assets/guion-pitch.md` — output template.
