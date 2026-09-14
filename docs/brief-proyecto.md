# Brief de proyecto — Web de ElectroD

Fuente de verdad para todos los agentes. Última actualización: 2026-09-14
(tras confirmar datos con el amigo).

## Objetivo
Reconstruir https://www.electrod.es/ (hoy en Wix) como sitio estático en Astro,
código limpio, diseño cuidado, SEO local fuerte para Granada, alojado gratis en
GitHub Pages (el amigo solo paga el dominio).

Plan completo de referencia:
`C:\Users\adryi\.claude\plans\tengo-un-amigo-que-logical-sonnet.md`

## Decisiones tomadas
| Tema | Decisión |
|---|---|
| Stack | Astro + GitHub Actions → GitHub Pages |
| Alcance SEO local | Servicios + zonas clave (Granada capital + municipios del cinturón) |
| Blog | Estructura montada y vacía al lanzamiento (1 artículo de ejemplo) |
| Imágenes | Solo las ~16 de la web actual, ya descargadas en `src/assets/originales/` |
| Dominio canónico | `https://www.electrod.es` |

## Datos del negocio (NAP) — confirmados
- **Nombre:** ElectroD
- **Actividad:** instalaciones eléctricas nuevas, renovación de cableado,
  reparación de averías (cortocircuitos, cortes de suministro), mantenimiento
  preventivo y supervisión técnica. Experiencia en viviendas, locales
  comerciales, naves industriales, garajes y comunidades. Carnet de Instalador
  de Baja Tensión Oficial.
- **Teléfono:** 622 735 199 (sin WhatsApp Business)
- **Email:** instalacioneselectrod@gmail.com (se mantiene el de Gmail por ahora, no hay correo de dominio)
- **Horario:** lunes a domingo, 08:00–23:00 — **no hay urgencias 24h**, ese horario es el real, no anunciar "24h".
- **Modelo de negocio:** sin local/tienda física — **servicio a domicilio** (Service Area Business). No se publica dirección. El schema.org debe usar `areaServed`, no `address` con calle real, y el Google Business Profile (si se crea) debe configurarse como negocio de área de servicio con dirección oculta.
- **Zona de servicio:** Granada capital + área metropolitana. Confirmados de entrada: Granada, Albolote, Armilla, Maracena, La Zubia, Las Gabias, Ogíjares, Peligros. Lista **ampliable** — no cerrada, tratar como "y alrededores" en el copy para no limitar el área real.
- **Redes:** Instagram — https://www.instagram.com/instalaciones_electrod/

## ⚠️ Importante — origen de las imágenes
El amigo cree que las fotos actuales de "Trabajos realizados" **están generadas
con IA / son de catálogo**, no fotos reales de sus instalaciones. Implicaciones
para todos los agentes:
- `redactor-contenido`: no describir estas imágenes como "nuestros trabajos
  reales" ni construir testimonios/pies de foto que afirmen que son instalaciones
  hechas por ElectroD. Usarlas como *ambientación* del tipo de resultado que se
  ofrece, dejándolo claro o al menos sin afirmar autoría (ej. "Así de limpio
  queda un cuadro eléctrico bien instalado" en vez de "Instalación realizada por
  nuestro equipo en Granada").
- `especialista-seo-local`: el `schema.org` `ImageObject`/galería no debe
  vincular estas imágenes a reseñas o testimonios reales; evitar cualquier
  marcado que implique autoría verificable (riesgo de señales falsas de E-E-A-T).
- Objetivo a medio plazo (Fase 6, post-lanzamiento): sustituir progresivamente
  por fotos reales de trabajos cuando el amigo las tenga — dejar la galería
  fácil de actualizar por el desarrollador.

## Pendiente de confirmar con el amigo — resuelto vs. abierto
| # | Pregunta | Respuesta |
|---|---|---|
| 1 | Nombre fiscal / autónomo y NIF (aviso legal) | **Abierto** — no lo sabe. El aviso legal se publica con `[PENDIENTE: NIF y nombre fiscal]` hasta tenerlo; no se puede lanzar a producción sin cerrarlo (obligatorio por LSSI). |
| 2 | ¿Dirección física o domicilio sin local? | **Resuelto** — domicilio sin local, servicio a domicilio. |
| 3 | ¿Son suyas las fotos? | **Resuelto (con matiz)** — probablemente generadas con IA/catálogo. Ver aviso arriba. |
| 4 | ¿WhatsApp Business? | **Resuelto** — no tiene. No poner CTA de WhatsApp, solo llamada. |
| 5 | URL de Instagram | **Resuelto** — https://www.instagram.com/instalaciones_electrod/ |
| 6 | ¿Google Business Profile creado? | **Abierto** — no lo sabe. `especialista-seo-local` debe comprobarlo/crearlo como parte del checklist fuera de la web. |
| 7 | Lista de servicios y precios | **Abierto** — no hay lista cerrada. Usar los servicios ya conocidos de la web actual (instalaciones nuevas, renovación de cableado, reparación de averías, mantenimiento preventivo) como base; sin precios públicos (CTA a "presupuesto sin compromiso"). |
| 8 | ¿Urgencias 24h? | **Resuelto** — no, solo el horario indicado (08:00–23:00, L–D). No anunciar 24h en ningún sitio. |
| 9 | Municipios exactos | **Resuelto (abierto a ampliar)** — ver zona de servicio arriba. |
| 10 | ¿Reseñas/testimonios? | **Resuelto** — aún no tiene. No inventar testimonios; dejar la sección preparada para cuando existan. |
| 11 | ¿Email de dominio? | **Resuelto** — sigue con el de Gmail por ahora. |
| 12 | Repo/DNS | **Parcialmente resuelto** — repo destino: `https://github.com/adlopp/electrod.git`. Dónde está registrado el dominio para tocar el DNS: **aún no se sabe**, pendiente para la Fase 5 (Lanzamiento). |

Puntos que siguen realmente abiertos y bloquean algo antes del lanzamiento:
**NIF/nombre fiscal** (bloquea el aviso legal) y **dónde está registrado el
dominio** (bloquea apuntar el DNS). El resto ya no bloquea el trabajo de
estrategia/contenido/diseño, que puede arrancar.

Ningún agente debe inventar respuestas a lo que sigue abierto: debe marcarlo
como pendiente en su entrega en vez de rellenarlo.

## Inventario de imágenes disponibles
Descargadas en `src/assets/originales/` (18 ficheros, calidad original de Wix,
pendientes de optimizar con `astro:assets` al integrarlas):

- `logo.png`
- `portada-trabajos.png`, `servicio-destacado.png`, `iluminacion-led-exterior.jpg`
- `trabajo-01-fachada-chalet-iluminacion.png` … `trabajo-14-instalaciones-comerciales.jpg`
  (14 fotos de la página "Trabajos realizados" de la web actual)
