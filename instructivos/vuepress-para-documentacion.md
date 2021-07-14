# Vuepress para documentacion

Con la finalidad de que la documentacion generada desde la DAI, desde archivos markdown, pueda ser desplegada en un sitio estatico se sugiere la implementacion de vuepress. Cuando la documentacion sea aplia y amerite su publicacion para su facil consulta  en web, esta herramienta es una alternativa para hacerlo así. 

[Vuepress](https://vuepress.vuejs.org/) convierte automaticamente los archivos markdown a archivos html con estructura de sitio web . Algunas alternativas a vuepress son [Jekyll](https://jekyllrb.com/) [Hugo](https://gohugo.io/) , [Github pages (basado en jekyll)](https://pages.github.com/)

Nota: Vuepress tambien puede usarse para el desarrollo de cualquier sitio estatico que como requerimiento use el proceso *serve side render*, y ademas de que es posible agregar componentes interactivos de Vue dentro del markdown.

## Agregar vuepress a un proyecto

Tomando un proyecto que ya tenga archivos .md  instalamos vuepress. 

Si el proyecto no es de nodejs, debera evaluarse si es posible incorporar node js, en teoria solo es para generar documentacion y si el proyecto es de python por ejemplo, estos archivos generados por nodejs deberian de ignorarse (al igual que los que necesiten ser ignorados en el .gitignore). Para inicializar un proyecto de node dentro de un proyecto existente se puede ejecutar `npm init`.

```bash
#instalar vuepress
npm install vuepress
```

Agregar los scripts de desarrollo y construcción, dentro del archivo `package.json`.

```json
...
"scripts":{
    "serve:docs": "vuepress dev",
    "build:docs": "vuepress build"
}
...
```

Ejecutando: `npm run serve:docs` puede ya verse el sitio en local con la pagina de inicio en el `README.md` principal o `index.md`


### Agregar navegacion la barra de navegacion y otras utilidades

Para agregar mas configuraciones a vuepress e incluso componentes interactivos debera contarse con el directorio `.vuepress`.


```
mkdir .vuepress
```

Generar el archivo de configuracion de vuepress `.vuepress/config.js` con la siguiente estructura

```js

```