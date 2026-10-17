# Skills para ensayar el pitch de la SpookyThon 2026

Dos carpetas. Una escribe el guion y la otra lo critica. Funcionan en Kiro y en cualquier agente que lea Agent Skills.

## Cómo se usan

Díganle a su agente, con este enlace:

> Descarga e instala estas skills: https://github.com/DweskZ/spookython-skills

El agente deja las dos carpetas en el proyecto. Después escriben `Arma mi pitch` o `Evalúa mi pitch`. Lo que no sepan queda marcado como pendiente. Si no les dieron la persona, el número o la demo, el texto lo dice.

El orden: primero `constructor-pitch`, después `jurado-spookython`. En Kiro también pueden invocarlas con `/constructor-pitch` y `/jurado-spookython`.

## Si un agente lee esto para instalarlas

1. Descarga este repositorio.
2. Copia las carpetas `constructor-pitch` y `jurado-spookython` completas, con `references/` y `assets/`, a la carpeta de skills del proyecto. En Kiro es `.kiro/skills/`. En Claude Code es `.claude/skills/`. Si es otro agente, usa la carpeta donde ese agente lee `SKILL.md`.
3. No instales dependencias. No hace falta.
4. Confirma las dos rutas y dile al usuario que ya puede escribir `Arma mi pitch` o `Evalúa mi pitch`.

## Qué hace cada una

**constructor-pitch.** Pide el reto en una oración y una persona concreta. Entrevista los datos que faltan, todos juntos, una sola vez. Devuelve el guion de 5 minutos, con tiempos, quién habla, y el contenido de hasta diez diapositivas. Lo hablado queda entre 400 y 500 palabras para que unos dos minutos sean la demo.

**jurado-spookython.** Si el guion ya trae el reto y la persona, sigue de largo. Pone nota con los cuatro criterios públicos, hace tres preguntas y espera. Cuando responden, entrega la nota y tres cambios.

Pueden editar los archivos. Son de ustedes.
