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

Las cifras del panel de inversión publicitaria son una **estimación ilustrativa** para mostrar la tendencia (caída de TV lineal e impresos, ascenso de buscador, social, CTV y retail media). No son datos auditados de una fuente concreta.

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
