# 01 - Landing Chuvama Box y Gimnasio

- **Estado:** Aprobado
- **Depende de:** (ninguno)
- **Fecha:** 2026-10-01
- **Objetivo:** Implementar como sitio estático (HTML/CSS/JS vanilla) la landing page de una sola página para Chuvama Box y Gimnasio, a partir del diseño ya aprobado en Claude Design (`Chuvama Landing.dc.html`), lista para revisar como demo.

## Alcance

### Incluye

- Página única `index.html` con las secciones, en este orden:
  1. Header sticky con logo ("Chuvama Box · Gym"), nav por anclas (Nosotros, Servicios, Planes, Horarios, Ubicación) y botón de WhatsApp.
  2. Hero (`#inicio`): headline, subtítulo, botones CTA ("Ver planes" / "Escribir por WhatsApp"), imagen de fondo y tarjetas flotantes (rating de Google, horario resumido, sello de marca).
  3. Ribbon de servicios (franja clara: Box ◆ Pesas ◆ Aeróbicos ◆ Entrenamiento personal).
  4. Nosotros (`#nosotros`): texto de presentación, etiquetas de público objetivo (Mujeres, Hombres, Jóvenes, Familias, Niños), bloque de cita del coach, imagen.
  5. Servicios (`#servicios`): 4 tarjetas numeradas (Gimnasio mixto y pesas, Box, Ejercicios aeróbicos, Entrenamiento personal).
  6. Galería de instalaciones: grid de 6 imágenes con etiqueta superpuesta por imagen.
  7. Planes (`#planes`): 4 tarjetas de precio (Gimnasio, Box, Gimnasio + Box como plan destacado, Entrenamiento personal), bloques de Inscripción/Visita del día, CTA de WhatsApp y nota "precios de ejemplo".
  8. Horarios (`#horarios`): tabla Lunes a viernes / Sábado / Domingo.
  9. Opiniones: rating agregado + 3 testimonios.
  10. Ubicación (`#ubicacion`): dirección, teléfono, botones "Cómo llegar" (Google Maps) y "WhatsApp", placeholder visual de mapa.
  11. Footer: logo, dirección corta, redes sociales, aviso de horarios y copyright.
  12. Barra fija inferior (mobile y desktop) con WhatsApp y Cómo llegar.
- Navegación por anclas con scroll suave (`#inicio`, `#nosotros`, `#servicios`, `#planes`, `#horarios`, `#ubicacion`).
- Enlaces externos a WhatsApp (`wa.me/525512345678`) y a Google Maps (URL de búsqueda), sin integración ni formularios propios.
- Paleta, tipografías (Google Fonts: Anton, Barlow, Barlow Condensed, JetBrains Mono) y estilos que replican fielmente el diseño aprobado.
- 4 imágenes reales del gimnasio (`uploads/pasted-1790880336837-0.png`, `pasted-1790880306257-0.png`, `pasted-1790880321105-0.png`, `pasted-1790880294088-0.png` del proyecto de Claude Design) descargadas e incluidas como archivos locales en `images/` para la galería.
- El resto de imágenes (hero, nosotros, 2 de galería) se mantienen como enlaces hotlink a Unsplash, igual que en el diseño original.
- Diseño responsive mobile-first tal como está definido en el archivo fuente (grids `auto-fit`, `clamp()` para tipografía y espaciados).
- Datos de contacto (dirección, teléfono, WhatsApp) y precios tratados explícitamente como placeholders de ejemplo, igual que ya están marcados en el diseño original.
- Menú hamburguesa en mobile: el nav de anclas se colapsa detrás de un botón de hamburguesa por debajo de un breakpoint (ej. 768px), con un panel/drawer que se abre y cierra al tocar el botón o un enlace.

### No incluye

- La sección final "Guía de diseño · para desarrollo" (swatches de color, muestras de tipografía) del archivo fuente — es documentación para el desarrollador, no contenido para visitantes, y no se incluye en el HTML público.
- Formulario de contacto, newsletter, backend, CMS, base de datos, login o cualquier persistencia.
- Analytics o tracking de ningún tipo.
- Integración real de Google Maps (iframe embebido) — se mantiene el placeholder visual del diseño.
- Multi-idioma, multi-página, blog, sistema de reservas o de clases.
- Build tooling, bundlers, Tailwind o frameworks (React, Vue, etc.) — stack vanilla sin paso de build.
- Optimización/compresión avanzada de imágenes, CDN o despliegue a producción — se entrega como archivos estáticos que se abren directamente o se alojan donde el usuario decida.

## Modelo de datos

No aplica: es un sitio estático sin estado, sin backend y sin estructuras de datos nuevas. Todo el contenido vive directamente en el HTML.

## Plan de implementación

1. Crear la estructura base del proyecto: `index.html` con esqueleto HTML5, `<head>` con meta charset/viewport, título, carga de Google Fonts (Anton, Barlow, Barlow Condensed, JetBrains Mono), link a `styles.css` y `script.js` (con `defer`).
2. Descargar las 4 imágenes reales del proyecto de Claude Design hacia `images/` con nombres descriptivos (`images/instalaciones-vista-general.png`, `images/instalaciones-pesas.png`, `images/instalaciones-maquinas.png`, `images/instalaciones-ring.png`).
3. Maquetar el header sticky (logo, nav de anclas, botón WhatsApp) en `styles.css`, incluyendo el botón de hamburguesa y el panel/drawer de nav para mobile (oculto en desktop).
4. Maquetar la sección hero (`#inicio`): headline, subtítulo, CTAs, imagen de fondo Unsplash y tarjetas flotantes.
5. Maquetar el ribbon de servicios.
6. Maquetar la sección "Nosotros" (`#nosotros`): texto, etiquetas, cita del coach e imagen.
7. Maquetar la sección "Servicios" (`#servicios`) con las 4 tarjetas numeradas.
8. Maquetar la galería con grid de 6 imágenes (4 locales + 2 Unsplash) y etiquetas superpuestas.
9. Maquetar la sección "Planes" (`#planes`): 4 tarjetas de precio, bloques de inscripción/visita y CTA de WhatsApp.
10. Maquetar la sección "Horarios" (`#horarios`) con la tabla de días/horas.
11. Maquetar la sección "Opiniones" con rating agregado y 3 testimonios.
12. Maquetar la sección "Ubicación" (`#ubicacion`): dirección, teléfono, botones de acción y placeholder de mapa.
13. Maquetar el footer (logo, dirección corta, redes, aviso de horarios/copyright).
14. Agregar la barra fija inferior con WhatsApp y Cómo llegar, visible en todos los breakpoints según el diseño.
15. Implementar `script.js`: scroll suave para los enlaces de anclas del nav, toggle de apertura/cierre del menú hamburguesa en mobile (y cierre automático al seleccionar un enlace); sin lógica adicional.
16. Revisar el responsive en mobile/tablet/desktop comparando contra el diseño original y ajustar donde sea necesario.
17. Verificación final: abrir `index.html` en el navegador, revisar las 11 secciones públicas más la barra fija, probar los enlaces (WhatsApp, Maps, anclas) y confirmar que la sección "Guía de diseño" no está presente.

## Criterios de aceptación

- [ ] `index.html` contiene las 11 secciones públicas (header, hero, ribbon, nosotros, servicios, galería, planes, horarios, opiniones, ubicación, footer) más la barra fija móvil, sin la sección "Guía de diseño".
- [ ] La paleta de colores coincide con el diseño: `#C8323D` (rojo acento), `#0B0B0E` (negro lona), `#16161D` (grafito), `#7DD3FF` (azul neón), `#F3F1EE` (hueso).
- [ ] Las 4 tipografías de Google Fonts cargan y se aplican según el diseño: Anton en titulares/precios, Barlow Condensed en botones/etiquetas/subtítulos, Barlow en texto corrido, JetBrains Mono en numeración de secciones.
- [ ] Las 4 imágenes reales del gimnasio están en `images/` como archivos locales y se muestran en la galería.
- [ ] Los enlaces a WhatsApp (`wa.me`) y Google Maps funcionan con el número/dirección de ejemplo del diseño.
- [ ] La navegación por anclas hace scroll suave a cada sección (`#inicio`, `#nosotros`, `#servicios`, `#planes`, `#horarios`, `#ubicacion`).
- [ ] La barra fija inferior con WhatsApp y Cómo llegar es visible en vista mobile y no se superpone con el footer.
- [ ] En mobile (debajo del breakpoint definido), el nav se colapsa detrás de un botón de hamburguesa; al tocarlo se abre/cierra el panel de enlaces, y al seleccionar un enlace el panel se cierra.
- [ ] El layout es responsive: se verifica visualmente en al menos 3 anchos (375px, 768px, 1440px) sin overflow horizontal.
- [ ] No hay formularios, llamadas a backend, ni dependencias de build; el sitio abre directamente con `index.html` en el navegador.
- [ ] No se usa Tailwind ni ningún framework CSS/JS adicional; solo HTML, CSS y JS vanilla en tres archivos separados.

## Decisiones tomadas y descartadas

- **Vanilla HTML/CSS/JS en vez de Tailwind:** el diseño ya está resuelto en CSS plano (sin utilidades de Tailwind); convertirlo añadiría trabajo de traducción sin aportar valor a un demo de una sola página.
- **Tres archivos separados (`index.html` + `styles.css` + `script.js`) en vez de todo embebido:** más mantenible que un único archivo, sin la complejidad de un build step.
- **Placeholder visual del mapa en vez de iframe real de Google Maps:** es un demo, no requiere integración real.
- **Datos de contacto (dirección, teléfono, WhatsApp) como placeholders de ejemplo:** se tratan igual que los precios, que el propio diseño ya marca como "de ejemplo, sujetos a confirmación".
- **Excluir la sección "Guía de diseño · para desarrollo" del HTML público:** es documentación para el desarrollador (paleta, tipografías), no contenido para visitantes del sitio.
- **Agregar menú hamburguesa en mobile (ajuste sobre el diseño original):** el diseño aprobado en Claude Design no define un menú colapsable (el nav hace wrap), pero el usuario pidió explícitamente esta mejora de usabilidad mobile al revisar la spec; se añade un botón de hamburguesa con panel/drawer solo para mobile, sin tocar el comportamiento desktop.
- **Mantener la mezcla de imágenes del diseño (4 fotos reales + hotlinks a Unsplash) en vez de reemplazar todo por stock:** preserva la fidelidad al diseño aprobado por el usuario.

## Riesgos identificados

- Los enlaces hotlink a Unsplash dependen de disponibilidad externa; si una imagen deja de estar disponible, esa sección quedará con fondo vacío. No se mitiga en este demo; queda como posible mejora futura descargar también esas imágenes.
- Las fuentes de Google Fonts requieren conexión a internet; sin conexión, el sitio usará las fuentes de respaldo del sistema (`sans-serif`/`monospace`).
