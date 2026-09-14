---
name: construir-web
description: Orquesta el ciclo completo de construcción/auditoría de la web de ElectroD usando los subagentes del proyecto (desarrollador-senior, especialista-seo-local, disenador-ux-ui, redactor-contenido, qa-rendimiento). Úsala cuando el usuario pida avanzar una fase del plan, lanzar la ronda de estrategia, construir páginas, o auditar y corregir el sitio antes de desplegar.
---

# Orquestación de la web de ElectroD

Esta skill te recuerda, como director del proyecto, el pipeline y el orden en el
que lanzar a cada subagente, y qué documento de `docs/` es la fuente de verdad
en cada paso. Referencia completa del proyecto:
`C:\Users\adryi\.claude\plans\tengo-un-amigo-que-logical-sonnet.md`.

## Antes de nada
Comprueba qué existe ya en `docs/`. Si `docs/brief-proyecto.md` no existe o le
faltan datos del negocio (NAP, servicios, municipios), complétalo con el usuario
antes de lanzar cualquier agente — todos los demás dependen de que ese brief sea
correcto.

## Paso 1 — Estrategia (en paralelo)
Lanza a la vez, cada uno con el contexto de `docs/brief-proyecto.md`:
- `especialista-seo-local` → produce/actualiza `docs/brief-seo.md`
- `disenador-ux-ui` → produce/actualiza `docs/sistema-diseno.md`
- `redactor-contenido` → produce/actualiza `docs/inventario-contenido.md`

No hace falta esperar a que los tres terminen para revisar resultados
individuales, pero **no lances el paso 2 hasta tener los tres documentos**.

## Paso 2 — Construcción
Lanza `desarrollador-senior` pasándole explícitamente las rutas de
`docs/brief-seo.md`, `docs/sistema-diseno.md` e `docs/inventario-contenido.md`,
y qué páginas del mapa construir en esta pasada (no hace falta todo el sitio de
una vez; puede ir por bloques: andamiaje → home → servicios → zonas → resto).

## Paso 3 — Auditoría (en paralelo, sobre el build)
Lanza a la vez:
- `especialista-seo-local` → audita el build, añade filas a `docs/registro-auditorias.md`
- `qa-rendimiento` → audita el build, añade filas a `docs/registro-auditorias.md`

## Paso 4 — Corrección
Lanza `desarrollador-senior` con `docs/registro-auditorias.md` como input,
pidiéndole que resuelva las filas `bloqueante` e `importante` como mínimo y
marque cada una como resuelta al corregirla.

## Paso 5 — Repetir 3–4
Hasta que `docs/registro-auditorias.md` no tenga hallazgos `bloqueante` ni
`importante` abiertos.

## Paso 6 — Lanzamiento
Solo tras el paso 5 en verde: confirma con el usuario, haz merge a `main`,
verifica el deploy en la URL `*.github.io`, y entonces (y solo entonces) guía la
configuración del DNS de `electrod.es` — es un cambio de cara al público, pide
confirmación explícita antes de tocar el dominio real.

## Reglas generales al orquestar
- Cada subagente **lee** los `docs/` que declara su ficha de agente y **escribe
  solo el suyo** (o código, en el caso del desarrollador). Si un agente necesita
  un dato que no está en ningún `docs/`, pregúntaselo tú al usuario en vez de
  dejar que el agente lo invente.
- No emitas informes de progreso sin fundamento: cada "listo" debe verificarse
  con `docs/registro-auditorias.md` en cero hallazgos abiertos relevantes, o con
  la salida real de `npm run build` / Lighthouse.
