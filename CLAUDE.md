# QA Study Tracker — CLAUDE.md

## Qué es este proyecto
Página web interactiva de una sola pantalla (single HTML file) que funciona como
guía de estudio y tracker de progreso para aprender JavaScript + Playwright desde cero.
Usuario: David — QA manual, sin experiencia en programación, español como idioma principal.
Fecha de inicio del plan: 10 de junio de 2025. Duración: 16 semanas.

## Stack
- Un solo archivo: `index.html` (HTML + CSS + JS embebidos)
- Sin frameworks, sin npm, sin build step — se abre directo en el browser
- localStorage para persistir el progreso entre sesiones
- Google Fonts vía CDN (Syne + Inter + JetBrains Mono)

## Archivo de salida
`index.html` en la raíz del proyecto. Solo ese archivo.

## Diseño — reglas no negociables
- Fondo oscuro con undertone púrpura profundo (#0D0B14)
- Acento dorado/ámbar (#F0A500) para elementos desbloqueados y progreso
- Verde teal (#00C49A) para días completados
- Tipografía display: Syne (títulos, semanas). Body: Inter. Código: JetBrains Mono
- NADA de gradientes azul-púrpura genéricos, nada de cards con border-radius enorme
- Estilo inspirado en un dojo / quest map — disciplinado y con carácter
- El elemento signature es un heatmap de actividad (tipo GitHub) en el header

## Estructura del contenido
Ver `docs/curriculum.md` para el contenido día por día.
El diseño de la UI está en `docs/PROMPT.md`.

## Convenciones de código
- Todo el texto visible al usuario en español
- Variables y funciones en inglés (camelCase)
- Comentarios en español
- El progreso se guarda en localStorage con key `qa-tracker-progress`
- No usar `var` — solo `const` y `let`
