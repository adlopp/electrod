# Web de ElectroD (en construcción)

Reconstrucción de https://www.electrod.es/ como sitio estático (Astro),
desplegado gratis en GitHub Pages, con foco en SEO local para Granada.

Plan y contexto completos:
`C:\Users\adryi\.claude\plans\tengo-un-amigo-que-logical-sonnet.md`

## Cómo está organizado este repo

- `docs/` — briefs y registro de auditorías, el "contrato" entre los agentes de Claude Code que construyen la web.
  - `brief-proyecto.md` — NAP, decisiones tomadas, datos pendientes de confirmar.
  - `brief-seo.md` — mapa de URLs, requisitos on-page y de schema.org (lo escribe `especialista-seo-local`).
  - `sistema-diseno.md` — tokens y componentes (lo escribe `disenador-ux-ui`).
  - `inventario-contenido.md` — textos definitivos (lo escribe `redactor-contenido`).
  - `registro-auditorias.md` — hallazgos de SEO/QA con estado (lo escriben `especialista-seo-local` y `qa-rendimiento`).
- `.claude/agents/` — los 5 subagentes del proyecto.
- `.claude/skills/construir-web/` — skill que orquesta el pipeline completo (`/construir-web`).
- `src/assets/originales/` — las ~16 imágenes de la web actual, descargadas del CDN de Wix, listas para optimizar con `astro:assets` al integrarlas.
- `src/` — (resto) proyecto Astro, aún por generar (Fase 2 del plan).

## Estado actual
Fase 0 completada: estructura del repo, agentes, skill de orquestación, briefs
base y las imágenes originales ya descargadas. Siguiente paso: Fase 1
(estrategia SEO/diseño/contenido en paralelo) — requiere primero cerrar los
datos pendientes del amigo listados en `docs/brief-proyecto.md`.
