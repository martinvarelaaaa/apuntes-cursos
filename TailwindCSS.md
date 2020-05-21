# Tailwind CSS

[Tailwind CSS](https://tailwindcss.com/) se autodefine como una herramienta para hacer CSS personalizado. Además es agnostica a los frameworks de frontend, es decir, puede funcionar con React, Angular, Vue o JS Vanilla.

A diferencia de los otros framewoorks es "utility first", ¿que quiere decir eso? que no viene con componentes(botones, cards, etc) o estilos visuales armados, sino que es una colcección de utilidades que nos ayudan a hacer CSS mucho más rápido.

"La mayoría de los frameworks CSS hacen demasiado" dice el equipo de Tailwind CSS.

## Responsive como base

Todas las utilidades que vienen con [Tailwind tienen variantes responsive](https://tailwindcss.com/docs/responsive-design), haciendo muy fácil el desarrollo responsive sin necesidad de desordenar el CSS custom.

Tailwind usa un prefix `{screen}:` que hace muy fácil saber que estilos aplicar a elementos HTML dependiendo de la pantalla en la que nos encontremos. Por ejemplo:

```html
<div
  class="justify-start sm:justify-center md:justify-end lg:justify-between xl:justify-around ..."
>
  <!-- ... -->
</div>
```

## Component-friendly

Una vez que los proyectos crecen es necesario empezar a separar todo en componentes(idealmente desde que inicie el proyecto).

Talwind proporciona tools que permiten [extrarer `component classes`.](https://tailwindcss.com/docs/extracting-components) Por ejemplo:

```html
<!-- Using utilities: -->
<button
  class="bg-blue-500 hover:bg-blue-600 text-white font-bold py-2 px-4 rounded"
>
  Button
</button>

<!-- Extracting component classes: -->
<button class="btn btn-blue">
  Button
</button>

<style>
  .btn {
    @apply font-bold py-2 px-4 rounded;
  }
  .btn-blue {
    @apply bg-blue-500 text-white;
  }
  .btn-blue:hover {
    @apply bg-blue-600;
  }
</style>
```

## Diseñado para ser customizado

Taiwind nos permite configurar un `theme` para no tener que reescribir los estilos básicos como: tipografia, color, screens, sombras, etc.

Esto se hace a partir de un archivo llamado `tailwind.config.js`.

Tailwind fue creado con [PostCSS](https://postcss.org/) y configurado con JavaScript, esto lo hace muy versatil.

Es mas que un framework, es una herramienta para crear `design systems`.

## Instalación

Se puede instalar como cualquier paquete de NPM.

```bash
npm install tailwindcss
```

En el archivo `package.json` agregar los siguientes scripts.

```json
{
  "scripts": {
    "tw": "node_modules\\.bin\\tailwind build ./src/tailwind.css -c ./tailwind-config.js -o ./src/styles.css",
    "tailwind": "./node_modules/.bin/tailwind init"
  }
}
```

Luego se debe crear el archivo de configuración, para eso se ejecuta el siguiente comando:

```bash
npx tailwind init --full
```

Por último, se deben hacer los imports de Tailwind en el archivo `./src/tailwind.css` que se configuró en el `package.json`.

```css
@tailwind base;

@tailwind components;

@tailwind utilities;
```

Con esto basta para empezar a trabajar.

NOTA: TailWind se puede configurar con gulp, webpack o PostCSS.

## Resumen

- Es simple de utilizar
- Tiene buena documentación
- Permite crear sistemas de diseños completos, permitiendo flexibilidad y escala
- Reduce la cantidad de CSS que se utiliza
