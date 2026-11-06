# Bienvenida a casa, Heredera

Portal de bienvenida de **Herederas del Reino**: un recorrido espiritual guiado en ocho momentos.

**Publicado en:** https://herederas-del-reino.github.io/bienvenida/
**Sitio principal del ministerio:** https://herederas-del-reino.github.io/

## Los ocho momentos

| # | Momento | Qué hace |
|---|---|---|
| 01 | La puerta de bienvenida | Entrada cinematográfica; al pulsar «Comenzar mi recorrido» la luz de la puerta lleva a la carta. |
| 02 | Una carta para tu corazón | Sobre con sello de cera que se abre (clic o teclado); la carta permanece abierta hasta que se guarda. |
| 03 | ¿Quién soy en Cristo? | Tres verdades que revelan texto bíblico, explicación y pregunta de reflexión. |
| 04 | Estudio bíblico | Lector de tres lecciones: lectura, contexto, enseñanza, aplicación, pregunta y oración. |
| 05 | Un tesoro de la Palabra | Cinco sobres por circunstancia; cada uno abre texto, contexto, reflexión, copiar y compartir tarjeta. |
| 06 | Un momento con mi Padre | Oración guiada línea por línea; espacio para una narración autorizada. |
| 07 | Aquí caminamos juntas | Ministerio, pastora, encuentros y recursos. |
| 08 | Bienvenida a casa | Tarjeta PNG generada en el navegador: descargar, compartir, WhatsApp. |

## Privacidad

- Sin formularios, registros, cookies, `localStorage`, analítica ni scripts externos.
- Las fuentes están alojadas en el propio sitio (no se consulta a Google Fonts).
- Las tarjetas se generan con `canvas` en el dispositivo; nada se envía a servidores.
- Política de seguridad de contenido (CSP) que solo permite recursos del propio sitio.

## Cómo actualizar el contenido (sin tocar el código)

| Quiero cambiar… | Archivo |
|---|---|
| Enlaces (sitio, Zoom, Instagram, YouTube), encuentros, mensaje de la pastora, música | `data/config.js` |
| Textos bíblicos, verdades de identidad, promesas | `data/verses.js` |
| Lecciones del estudio bíblico | `data/lessons.js` |
| Textos fijos (carta, oración, títulos) | `index.html` |
| Colores, tipografías y espaciado | `css/variables.css` |

### Mensaje y foto de la pastora
En `data/config.js` → `pastora.mensaje`, escribe el mensaje **aprobado por ella**. Para una foto oficial, guárdala en `assets/images/` (formato `.webp`, mínimo 400 × 400 px) y cambia `pastora.foto`.

### Música o narración
Guarda el archivo autorizado en `assets/audio/` y escribe su ruta en `musica` o `narracionOracion` dentro de `data/config.js`. Mientras estén vacíos, los controles no aparecen. Nunca hay reproducción automática.

### Textos bíblicos
Se usa la **Reina-Valera 1960** (© Sociedades Bíblicas en América Latina, 1960; renovado © Sociedades Bíblicas Unidas, 1988). Cada referencia enlaza al pasaje completo en BibleGateway. Si agregas pasajes, cópialos exactamente de la RVR1960.

## Estructura

```text
bienvenida/
├── index.html            Estructura de los 8 momentos
├── css/                  fonts · variables · base · layout · components · animations · responsive
├── js/                   main (entrada) y un módulo por momento
│   ├── navigation.js     barra, progreso, índice y puntos
│   ├── animations.js     apariciones, mariposas, puerta
│   ├── welcome-letter.js sobre y carta
│   ├── identity.js       verdades de identidad
│   ├── bible-study.js    lector bíblico
│   ├── promises.js       tesoro de promesas
│   ├── prayer.js         oración guiada
│   ├── family.js         ministerio, pastora, encuentros
│   ├── final.js          tarjeta final
│   ├── share-card.js     generador de tarjetas PNG
│   └── music.js          música opcional
├── data/                 config · verses · lessons (contenido separado de la lógica)
└── assets/               images · icons · fonts · audio
```

## Probar en tu computador

Los módulos JavaScript necesitan un servidor local (no funcionan abriendo el archivo con doble clic):

```bash
cd herederas-del-reino
python -m http.server 5600
```

Abre http://localhost:5600/bienvenida/

## Publicar (GitHub Pages)

El repositorio `Herederas-Del-Reino/bienvenida` publica la rama `main` (carpeta raíz) en GitHub Pages. Cada `git push` actualiza el sitio en uno o dos minutos:

```bash
git add -A
git commit -m "Describe tu cambio"
git push
```

Si necesitas configurarlo de nuevo: *Settings → Pages → Build and deployment → Deploy from a branch → main / (root)*.

## Créditos de imágenes

Logotipo (`logo-oficial.webp`, tomado sin alteraciones del encabezado del sitio principal), fotografías del ministerio, flores y mariposas: recursos oficiales de Herederas del Reino. Imágenes de la puerta, el sobre, las Biblias, la ventana, el fondo de rosas y el arco floral: proporcionadas por el ministerio. Fuentes: Playfair Display, Cormorant Garamond y DM Sans (SIL Open Font License).
