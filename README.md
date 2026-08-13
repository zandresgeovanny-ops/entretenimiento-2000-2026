# Atención · 2000 — 2026

Pieza editorial de scroll cinematográfico sobre la **evolución de la industria del entretenimiento y sus modelos publicitarios** entre 2000 y 2026.

Un aparato electrónico flota en un escenario negro y **va cambiando con los años** conforme se hace scroll: televisor de tubo → reproductor MP3 → teléfono inteligente → pantalla conectada → visor de realidad mixta. La cámara orbita 360°, el fondo es un shader de onda que migra de fósforo ámbar a índigo sintético, y un panel lateral muestra cómo se reparte la inversión publicitaria en cada época.

## Las cinco épocas

| Años | Época | Aparato | Modelos publicitarios |
|---|---|---|---|
| 2000 — 2005 | La era del rating | Televisor de tubo | Spot de 30", GRP / rating, product placement, prensa y exterior |
| 2006 — 2011 | La era del clic | Reproductor MP3 | CPM / banner, pre-roll, buscador, patrocinio |
| 2012 — 2017 | La era del perfil | Teléfono inteligente | Native ads, creadores, CPC / CPA, segmentación |
| 2018 — 2022 | La era de la subasta | Pantalla conectada | Programática / RTB, CTV, AVOD, video corto |
| 2023 — 2026 | La era del modelo | Visor de realidad mixta | IA generativa, retail media, dato propio, economía creadora |

## Procedencia de los datos

El panel lateral reparte el gasto publicitario mundial entre seis canales. **Los dos extremos de la serie están publicados; los tres tramos intermedios son interpolación entre ellos**, y la pieza lo declara en pantalla: el pie del panel dice «dato publicado» o «interpolado» según la era que estés viendo.

| Era | Procedencia | Referencia |
|---|---|---|
| 2000–2005 | Publicado | TV 37 % y periódicos 29,8 % del gasto mundial en 2005; internet 3,8 % (ZenithOptimedia, recogido por [NBC News](https://www.nbcnews.com/news/amp/wbna7545838)) |
| 2006–2011 | Interpolado | — |
| 2012–2017 | Interpolado | — |
| 2018–2022 | Interpolado | — |
| 2023–2026 | Publicado | Digital = 73 % del gasto mundial (740 mM $ de 1,06 B $); dentro del digital, buscador 40 %, display 18 %, social 32 %, vídeo/CTV 10 %; retail media 62 mM $; TV lineal ~11 % ([dentsu](https://www.dentsu.com/news-releases/ad-spend-growth-is-projected-to-slow-to-5-percent-in-2026-still-outpacing-economic-growth), [Digital Applied](https://www.digitalapplied.com/blog/digital-advertising-statistics-2026-data-points)) |

Las cinco columnas suman 100 % y la serie es monótona en las dos direcciones que cuenta la pieza: TV lineal e impresos caen sin repuntes, buscador y social suben sin retrocesos.

## Seguridad

`vercel.json` fija las cabeceras del despliegue: CSP con `default-src 'none'` que solo admite scripts de `unpkg.com` y tipografías de `fonts.gstatic.com`, más `nosniff`, `X-Frame-Options: DENY`, `Referrer-Policy`, `Permissions-Policy` y HSTS. La pieza no tiene backend, formularios ni entradas de usuario.

## Detalles técnicos

- Un solo archivo: `index.html`. Sin build, sin framework, sin bundler.
- Three.js r0.160 vía importmap desde unpkg (única dependencia externa junto a Google Fonts).
- Los cinco aparatos son **geometría procedural** — no hay ningún modelo `.glb` ni imagen que descargar.
- Shader GLSL de onda de fondo, 450 partículas aditivas, iluminación de tres puntos con sombras suaves.
- Página de 900vh; todo el movimiento se deriva del scroll con suavizado por lerp.

## Ejecutar en local

Los módulos ES no funcionan con `file://`, hace falta un servidor estático:

```bash
npx serve .
```

## Despliegue

Sitio estático puro: Vercel lo publica sin configuración (sin `vercel.json`, sin build command).
