---
name: constructor-pitch
description: "Trigger: armar pitch, construir pitch, escribir mi pitch, guion del pitch, proyecto ya hecho, SpookyThon. Builds a 5-minute pitch from a repo or from facts the team supplies; never invents the user, numbers, or demo."
license: Apache-2.0
metadata:
  author: "DweskZ"
  version: "1.6"
---

## Activation Contract

Load when a SpookyThon 2026 team asks to write, build, structure, or draft its 5-minute pitch, its script, or its slide content.

## Hard Rules

- Reply in Spanish. The questions and the notes follow `references/voz.md`. The script itself is first person plural, the way the team will say it. Template headings stay.
- A user is one named person, with a role, a place, and a moment. "Todos", "la comunidad", "los ciudadanos", "los dueños", "los clientes", "la gente" or "los usuarios" is not a user. If there is no project to read, ask for a name and stop. If there is a repo, README, or code, keep going and mark the name `[PENDIENTE: nombre]`.
- Never invent the person, the contrast numbers, their source, the demo flow, the momento wow, the AWS services, or the cost. A number without a source the team stated is `[PENDIENTE: fuente]`, not a line in the script.
- You may speak the role the project already states ("un estudiante"). You may not invent a name, a city, or a biography.
- Pendientes are not spoken. A tramo with no fact has no heading and no paragraph. The technical tramo names the services the project actually uses. If none are AWS, say those. Do not put "falta AWS" in the script.
- A pipeline step, a feature, or a service name is not a momento wow. Write those words only when the source says what the audience sees change. Otherwise the phrase does not appear.
- Do not pad to 400 words. If the spoken count is under 250, the first sentence of Conteo is "Esto no es un pitch de 5 minutos." Then name the pendientes that kept it short.
- With no project to read, ask once for every gap, then stop. With a repo, README, or code, deliver the script in that same reply. Gaps go under Pendientes. Do not wait.
- Spoken words, excluding headings and `[PENDIENTE]` markers: target 400 to 500, ceiling 550. Tramo 4 narration stays under 80 words, because the team shows that block. Report the count and the time at 140 words per minute.
- Maximum 10 slides, one idea per slide, no list longer than three items. Return the markdown template only.
- Use only the four public criteria in `references/criterios-publicos.md`.
- Do not score the pitch. The last line points the team to `jurado-spookython`.

## Decision Gates

| Input | Action |
|---|---|
| Repo, README, or code of a project already built | Read it. Build the script from what it states. Name, numbers, cost, and roles stay `[PENDIENTE]` unless they are written there. Put the missing questions under Pendientes |
| Chat only, no project, and no named user | Ask only for the missing gate item, then stop |
| Gate passed, any of the ten inputs missing | Extract what they already wrote. Ask `references/entrevista.md` for the missing items only, then stop |
| All inputs present, or the team says to continue with placeholders | Build with `assets/guion-pitch.md` |
| Team asks to change one tramo | Edit only that tramo |

## Execution Steps

1. If the input is an existing project, read it and continue. If it is only a chat and the gate fails, stop.
2. Match the ten inputs in `references/entrevista.md`. Repo: write the gaps into Pendientes and continue. Chat only: ask once and stop.
3. Write a spoken paragraph only for a tramo that has a fact from the team or the repo. Do not emit an empty tramo. Do not label a step "momento wow" unless the source describes the change on screen. If it does not, add `[PENDIENTE: momento wow]` under Pendientes only.
4. Count spoken words by splitting those paragraphs on whitespace. Time is that count divided by 140, shown as M:SS. If over 550, cut tramos 5 and 6 first. Keep tramo 4 narration under 80 words without deleting the flow.
5. Derive at most 10 slides and the speaker notes. Assign speakers from the roles they gave. If roles are missing, use one speaker and `[PENDIENTE: quién habla]`.
6. Deliver `assets/guion-pitch.md`. Before sending, delete any spoken sentence whose only job is to say that something is missing. Check that every number in the script appears with its source under Datos usados. If it does not, replace it with `[PENDIENTE: fuente]`.

## Output Contract

Markdown in Spanish, only the sections in `assets/guion-pitch.md`: Datos usados, Guion por tramo, Diapositivas, Notas para el presentador, Conteo, Pendientes. Close with one line telling the team to run `jurado-spookython` on this script.

## References

- `references/entrevista.md` — the ten inputs the team must supply and the exact question for each.
- `references/estructura-pitch.md` — the seven tramos with times, principles, and criteria.
- `references/criterios-publicos.md` — the four public criteria, deliverables, dates, and score anchors.
- `references/voz.md` — how the Spanish the team reads should sound.
- `assets/guion-pitch.md` — output template.
