# Brief de proyecto — Web de ElectroD

Fuente de verdad para todos los agentes. Última actualización: 2026-09-14.

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
- **Teléfono:** 622 735 199
- **Email:** instalacioneselectrod@gmail.com
- **Horario:** lunes a domingo, 08:00–23:00
- **Zona de servicio:** Granada capital y área metropolitana
- **Redes:** Instagram (URL exacta pendiente de confirmar)

## Pendiente de confirmar con el amigo antes de dar por cerradas ciertas páginas
1. Nombre fiscal / autónomo y NIF (aviso legal).
2. ¿Dirección física real o servicio a domicilio sin local? (cambia el schema y el GBP).
3. ¿Son suyas todas las fotos actuales? (derechos de uso — varias parecen de catálogo/render).
4. ¿El 622 735 199 tiene WhatsApp Business?
5. URL exacta del Instagram; ¿otras redes?
6. ¿Tiene ya Google Business Profile creado?
7. Lista definitiva de servicios y si hay tarifa de desplazamiento / precios de referencia.
8. ¿Ofrece urgencias 24h o solo dentro del horario indicado?
9. Municipios exactos que quiere cubrir (propuesta de partida: Armilla, Maracena, La Zubia, Las Gabias, Ogíjares, Peligros — a validar).
10. ¿Tiene clientes/reseñas para testimonios reales?
11. ¿Sigue con el email de Gmail o quiere correo del dominio (`info@electrod.es`)?
12. ¿En qué cuenta de GitHub va el repo? ¿Dónde está registrado el dominio para tocar el DNS?

Ningún agente debe inventar respuestas a estos puntos: si un dato falta, debe
marcarlo como pendiente en su entrega en vez de rellenarlo.

## Inventario de imágenes disponibles
Descargadas en `src/assets/originales/` (18 ficheros, calidad original de Wix,
pendientes de optimizar con `astro:assets` al integrarlas):

- `logo.png`
- `portada-trabajos.png`, `servicio-destacado.png`, `iluminacion-led-exterior.jpg`
- `trabajo-01-fachada-chalet-iluminacion.png` … `trabajo-14-instalaciones-comerciales.jpg`
  (14 fotos de la página "Trabajos realizados" de la web actual)
