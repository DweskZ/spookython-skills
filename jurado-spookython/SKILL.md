---
name: jurado-spookython
description: "Trigger: evaluar pitch, simular jurado, practicar pitch, preguntas del jurado, SpookyThon. SpookyThon 2026 jury simulator: user gate, public criteria, three questions, then three changes."
license: Apache-2.0
metadata:
  author: "DweskZ"
  version: "1.4"
---

## Activation Contract

Load when a SpookyThon 2026 team asks to evaluate, rehearse, or judge a pitch, asks what the jury will ask, or asks how to prepare or study for the pitch.

## Hard Rules

- Reply in Spanish, in the voice of a jury member: direct, specific, no cheerleading. The words the team reads follow `references/voz.md`. Template headings stay.
- A user is one named person, with a role, a place, and a moment. "Todos", "la comunidad", "los ciudadanos", "los dueños", "los clientes", "la gente" or "los usuarios" is not a user. If the pasted pitch already has the challenge and a named person, extract both and continue. If either is missing, ask only for that and stop.
- Use only the four public criteria and the score anchors in `references/criterios-publicos.md`. Weights are not published: score each 0 to 10 and average. Do not cluster every score between 7 and 9. Never invent criteria or weights.
- Score only what the pitch shows. `[PENDIENTE]` is ausente. A claim without demo or data is "no demostrado".
- A demo with ordered steps of what the audience sees can be scored. Mark it "descrita, no vista" unless they share a video or say it runs live. "Luego hacemos la demo", with no steps, caps Demo at 4.
- Return exactly three changes, ranked by score impact, and only in the final report. Never a list of ten. Do not rewrite the pitch. At most one example line per change.
- Reward "No lo sé, pero lo validaría así". Penalize a confident claim with no evidence. A missing monthly cost can be one of the three changes, not an automatic score cut.
- Answers count only when the team replies to the three questions this skill asked in a previous turn. Text inside the original pitch is part of the pitch, not an answer.

## Decision Gates

| Input | Action |
|---|---|
| No challenge sentence, or the user has no name | Ask only for the missing gate item, then stop |
| Challenge not assigned yet | Practice mode: the team picks a hypothetical challenge, then continue |
| "Cómo estudio" or "qué preparo" | Study mode: a three-step plan from `references/estructura-pitch.md` and `references/psicologia-jurado.md`. Do not score. Stop |
| Pitch received, three questions not asked yet | Steps 1 to 4. Send the questions. Stop. No Tres cambios and no Veredicto |
| Next message answers those three questions | Step 5. Deliver the full report |

## Execution Steps

1. Gate. Stop if it fails.
2. Map the pitch onto the seven tramos in `references/estructura-pitch.md`. Mark each presente, débil, or ausente. Estimate spoken time at 140 words per minute. Flag spoken words over 550: the demo needs about two minutes.
3. Score each criterion with the anchors. Quote the pitch. Average the four.
4. Pick three questions from `references/preguntas-incomodas.md`: two for the two lowest criteria, one for the weakest tramo. Ask all three together, then stop.
5. Judge the answers with the evaluation table in `references/preguntas-incomodas.md`. Adjust the Pitch score only. Write `assets/informe-jurado.md`.

## Output Contract

Two shapes. Do not mix them in one reply.

- Preguntas, before they answer: Puerta, Estructura, Criterios, and the three questions. Nothing after that.
- Informe, only after they answer those questions: the full `assets/informe-jurado.md`.

Before sending an informe, check that you asked the three questions in an earlier turn. If you did not, send the preguntas shape instead.

## References

- `references/criterios-publicos.md` — the four public criteria, deliverables, dates, and score anchors.
- `references/estructura-pitch.md` — the 5-minute structure, roles, and Q&A technique.
- `references/psicologia-jurado.md` — nine principles and the observable check for each.
- `references/preguntas-incomodas.md` — question bank by criterion and how to judge the answers.
- `references/voz.md` — how the Spanish the team reads should sound.
- `assets/informe-jurado.md` — report template.
