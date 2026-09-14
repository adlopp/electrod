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

## Origen de las imágenes — confirmado
Actualización 2026-09-14: se confirma que las 14 fotos de "Trabajos realizados"
son instalaciones reales hechas por ElectroD (no IA/catálogo, corrigiendo la
duda inicial). A partir de ahora `redactor-contenido` y `especialista-seo-local`
pueden describirlas y marcarlas (`schema.org` `ImageObject`, alt text, pies de
foto) como trabajo propio sin matices. Si en algún momento se detecta que
alguna imagen concreta no lo es, hay que corregir esa pieza puntual, no volver
a la cautela genérica de antes.

## Pendiente de confirmar con el amigo — resuelto vs. abierto
| # | Pregunta | Respuesta |
|---|---|---|
| 1 | Nombre fiscal / autónomo y NIF (aviso legal) | **Parcialmente resuelto** — según factura de Wix (8 jun 2026, #1244634347), el titular de la cuenta es **David Lechuga Campoy / Acotados Construccion SL**, Calle Aguado 14, 18009 Granada (Andalucía, España). Falta aún el **NIF/CIF** para poder cerrar el aviso legal — el resto de datos ya se pueden usar. |
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
**NIF/CIF** (bloquea el aviso legal, ya tenemos el resto de datos del titular)
y **dónde está registrado el dominio** (bloquea apuntar el DNS — la factura de
Wix del 8 jun 2026 solo incluye el "Plan Premium Light", sin línea de dominio,
así que probablemente `electrod.es` esté registrado fuera de Wix; falta
confirmarlo mirando la sección "Dominios" del panel de Wix). El resto ya no
bloquea el trabajo de estrategia/contenido/diseño, que puede arrancar.

## Titular / datos fiscales (para el aviso legal)
Según factura de Wix #1244634347 (8 jun 2026 – 8 jun 2027, Plan Premium Light,
168 € + 21% IVA = 203,28 €):
- **Nombre/razón social:** David Lechuga Campoy / Acotados Construccion SL
- **Dirección:** Calle Aguado 14, 18009 Granada, Andalucía, España
- **NIF/CIF:** pendiente — único dato que falta para cerrar el aviso legal.

Ningún agente debe inventar respuestas a lo que sigue abierto: debe marcarlo
como pendiente en su entrega en vez de rellenarlo.

## Inventario de imágenes disponibles
Descargadas en `src/assets/originales/` (18 ficheros, calidad original de Wix,
pendientes de optimizar con `astro:assets` al integrarlas):

- `logo.png`
- `portada-trabajos.png`, `servicio-destacado.png`, `iluminacion-led-exterior.jpg`
- `trabajo-01-fachada-chalet-iluminacion.png` … `trabajo-14-instalaciones-comerciales.jpg`
  (14 fotos de la página "Trabajos realizados" de la web actual)
