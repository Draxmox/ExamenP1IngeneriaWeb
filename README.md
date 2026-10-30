# Discovery Homepage

Maquetación responsive del homepage de Discovery (diseño de Figma Community: "Discovery homepage"), hecha con HTML5 semántico y SCSS. Sin frameworks y sin JavaScript.

## Tecnologías

- HTML5 semántico
- SCSS (compilado a CSS con Dart Sass)
- Metodología BEM
- Mobile-first con media queries

## Estructura

```
discovery-homepage/
├── index.html
├── scss/styles.scss    <- aquí se edita
├── css/styles.css      <- se genera solo, no editar
└── img/                <- imágenes exportadas del Figma
```

## Cómo compilar

Instalar Sass una sola vez (requiere Node.js):

```
npm install -g sass
```

Dejar corriendo en la terminal, dentro de esta carpeta:

```
sass --watch --no-source-map scss/styles.scss:css/styles.css
```

Cada vez que se guarda `styles.scss`, se actualiza `styles.css`. Para detenerlo: `Ctrl + C`.

## Decisiones técnicas

- **BEM:** bloques, elementos (`__`) y modificadores (`--`), sin selectores anidados en el CSS final. Ejemplo: `card__title--light`.
- **Mobile-first:** los estilos base son de móvil. Hay dos puntos de quiebre, `$bp-tablet` (768 px) y `$bp-desktop` (1024 px), definidos como variables en `styles.scss`.
- **Flexbox (1 dimensión):** barra Live Now, cabecera, carruseles, newsletter y footer.
- **CSS Grid (2 dimensiones):** hero principal y cuadrícula de Latest Stories.
- **Mixins:** `mq` (media queries), `flex-center`, `flex-between`, `flex-column` y `grid-cols`.
- **Carruseles:** scroll nativo con `scroll-snap`. En Chrome y Edge, las flechas las genera el navegador con `::scroll-button()`. En otros navegadores se desliza con el scroll normal.
- **Modal sin JavaScript:** se abre con un enlace a `#modal` (pseudo-clase `:target`) y se cierra con un enlace a `#!`. El fondo se oscurece con una capa `rgba`.

## Créditos

Diseño: "Discovery homepage" (Figma Community). Proyecto académico, Ingeniería de Software, UDLA.
