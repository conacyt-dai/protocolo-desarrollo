# Tecnologías y librerías sugeridads (back y front end)

## Tecnologías
### Node
Node es un entorno de ejecución para JavaScript construido con el motor de JavaScript V8 de Chrome y una arquitectura orientada a eventos. Está diseñado para crear aplicaciones network escalables, como por ejemplo,  servidores.

Los puntos más fuertes de Node son :
- Asincronía  
- Backend completo
- NPM
- Paralelismo
- Liberías propias
- Código abierto
- Multiplataforma (Se puede correr en distintos lugares)
- Orientado a Eventos
- No sólo se limita a los servidores HTTP

Conceptos de node para la DAI

En la DAI se ha usado node para crear aplicaciones web, las cuales, hasta ahora sólo han sido de front-end.

A continuación se desarrollaran los pasos para inicializar un proyecto de este tipo.

#### Instalación de node
Al mes de abril de 2021 se usa la versión 14 de node en la DAI, esta es la versión que actualmente proyecta una duración de vida más larga. Para saber si tienes instalado node y la versión, puedes ejecutar en la terminal `node -v`.
Si no lo tienes instalado, puedes instalarlo mediante `nvm` (node version manager), considerado una de las mejores opciones para instalar node.

1. Instalación de  `nvm`
    **Linux/MacOS**

    En la consola de tu equipo ejecutar el siguiente comando
    
    ```
    wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
    ```
    
    Verifica la instalación ejecutando
    
    ```
    command -v nvm
    ```
    
    La respuesta en tu consola a esto debe de ser `nvm`.
    
    Si no se logra obtener lo anterior, cierra tu terminal y abre una nueva e inténtalo de nuevo. Consulta la siguiente [guía](https://github.com/nvm-sh/nvm#install--update-script) si se tiene algún otro problema con la instalación.

2. Instalarción de  `node.js` mediante `nvm`.

    **Linux/MacOS**

    En la consola de tu equipo se ejecuta el siguiente comando para instalar la última versión de `node.js`.
    
    ```
    nvm install node
    ```
    
    Verifica la instalación ejecutando
    
    ```
    nvm run node --version
    ```

    Lo cual te debe de regresar la versión instalada de `node` y de `npm`, como por ejemplo:
    
    ```
    Running node v14.2.0 (npm v6.14.4)
    v14.2.0
    ```

    Para instalar una versión es específico de node, por ejemplo la `14.16.1`, escribe en la terminal:

    ```
    nvm install 14.16.1
    ``` 

    y para cambiarte a la versión instalada escribes:

    ```
    nvm use 14.16.1
    ``` 

    puedes configurar la versión que quieres que se use por defecto con los siguiente comandos 
    ```
    nvm alias default 14.16.1
    nvm alias node 14.16.1
    nvm alias stable 14.16.1
    ```



#### Iniciando un proyecto en node.js

`npm` es el sistema de gestión de paquetes por defecto de Node.js. Podemos verificar su instalación con `npm -v`, aunque debería estar ya instalado si se realizaron los pasos de la sección anterior.

Para iniciar el proyecto creamos una carpeta y, en la terminal, ubicades dentro de la carpeta del proyecto escribimos 

```
npm init
```
A continuación nos pedirá ingresar algunas líneas para la configuración inicial de `package.json`, el cual contendrá la información del proyecto, incluendo las dependencias que se pueden instalar posteriormente con `npm`

Para la instalación de paquetes se usa `npm install` + el nombre del paquete, que instalará por defecto la última versión. Por ejemplo 
```
npm install d3
```
Por lo general, el proyecto tendrá una carpeta `src` que es en dónde se alojará el proyecto en desarrollo, incluyendo carpetas de `assets`, `js` y `css`. Por otra parte, se suele crear la carpeta `dist` en proyectos en donde se usan preprocesadores; el contenido de esta carpeta es el que iría a producción.

Cabe mencionar que muchos de los proyectos se usará `Vue CLI`, un framework de desarrollo que se explicará más adelante. El uso de esta herramienta nos ayudará a estructurar el proyecto.




### Geoserver

### Django


## Librerías 
### Vue

### Sass
Sass (*Syntactically Awesome Stylesheets*) es un metalenguaje de CSS. Permite usar funcionalidades que no existen en CSS, pero todas las funcionalidades de CSS funcionan también en Sass. Esisten dos tipos de formatos que Sass interpreta: `.scss` y `.sass`. La diferencia radica en la sintaxis y [aquí](https://sass-lang.com/documentation/syntax) puedes compararlos. En la DAI se suele usar el formato `.scss`.

Algunas de las funcionalidades básicas que se pueden implementar en Sass, a diferencia de CSS, se describen mediante ejemplos a continuación con la finalidad de sacar el máximo provecho a esta herramienta (los ejemplos son tomados de [aquí](https://sass-lang.com/guide)):

#### Variables

**SCSS**
```
$font-stack:    Helvetica, sans-serif;
$primary-color: #333;

body {
  font: 100% $font-stack;
  color: $primary-color;
}
```

**CSS resultante**
```
body {
  font: 100% Helvetica, sans-serif;
  color: #333;
}
```
La gran ventaja de esto es poder guardar parámetros de diseño en variables, y si estos cambian en el futuro, se pueden modificar en una sola línea y no en cada línea que se usó.

#### Anidamiento *(Nesting)*

**SCSS**
```
nav {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  li { display: inline-block; }

  a {
    display: block;
    padding: 6px 12px;
    text-decoration: none;
  }
}

```

**CSS resultante**
```
nav ul {
  margin: 0;
  padding: 0;
  list-style: none;
}
nav li {
  display: inline-block;
}
nav a {
  display: block;
  padding: 6px 12px;
  text-decoration: none;
}
```
Sass puede preservar la jerarquía de elementos en HTML mediante los selectores de CSS

#### Modularización 

Puedes escribir fragmentos parciales de Sass e incluirlos en otros archivos. Esta es una buena práctica para modularizar los estilos. Este tipo de archivos se deben nombrar iniciando con un guión bajo, por ejemplo `_base.scss` o `_variables.scss`. El guion bajo le permite saber a Sass que el archivo es parcial y que no debe ser procesado a CSS. Para importar el archivo se usa `rule`.

**SCSS parcial**
```
// _base.scss
$font-stack:    Helvetica, sans-serif;
$primary-color: #333;

body {
  font: 100% $font-stack;
  color: $primary-color;
}

```

**SCSS que importa parcial**
```
// styles.scss
@use 'base';

.inverse {
  background-color: base.$primary-color;
  color: white;
}

```

**CSS resultante**
```
body {
  font: 100% Helvetica, sans-serif;
  color: #333;
}

.inverse {
  background-color: #333;
  color: white;
}
```

Modularizar los estilos hace que sean más fáciles de mantener.

#### Mixins
**SCSS**
```
@mixin transform($property) {
  -webkit-transform: $property;
  -ms-transform: $property;
  transform: $property;
}
.box { @include transform(rotate(30deg)); }

```

**CSS resultante**
```
.box {
  -webkit-transform: rotate(30deg);
  -ms-transform: rotate(30deg);
  transform: rotate(30deg);
}

```

Permite escribir bloques de CSS y llamarlos como si fuera una función pasándo un parámetro.

#### Extend / herencia
**SCSS**
```
/* This CSS will print because %message-shared is extended. */
%message-shared {
  border: 1px solid #ccc;
  padding: 10px;
  color: #333;
}

// This CSS won't print because %equal-heights is never extended.
%equal-heights {
  display: flex;
  flex-wrap: wrap;
}

.message {
  @extend %message-shared;
}

.success {
  @extend %message-shared;
  border-color: green;
}

.error {
  @extend %message-shared;
  border-color: red;
}

.warning {
  @extend %message-shared;
  border-color: yellow;
}

```

**CSS resultante**
```
.message, .success, .error, .warning {
  border: 1px solid #ccc;
  padding: 10px;
  color: #333;
}

.success {
  border-color: green;
}

.error {
  border-color: red;
}

.warning {
  border-color: yellow;
}

```

Permite escribir bloques propiedades de css y extenderlos a otros selectores

#### Operadores
**SCSS**
```
.container {
  width: 100%;
}

article[role="main"] {
  float: left;
  width: 600px / 960px * 100%;
}

aside[role="complementary"] {
  float: right;
  width: 300px / 960px * 100%;
}


```

**CSS resultante**
```
.container {
  width: 100%;
}

article[role="main"] {
  float: left;
  width: 62.5%;
}

aside[role="complementary"] {
  float: right;
  width: 31.25%;
}

```

Sass permite realizar operaciones matemáticas con los operadores `+`, `-`, `*` y `/` sin necesidad de usar la función `calc()`  




### D3

Data-Driven-Documents [D3](https://d3js.org/) es conocida como una de las librerías de JavaScript más poderosas para visualizar datos, cuenta con una amplia [documentación](https://github.com/d3/d3/wiki) y su uso radica en ligara bases de datos a elementos de HTML, principalmente de SVG; de tal forma que, datos numéricos, temporales o categoricos se asocien a estilos y atributos de los elementos HTML o SVG. De esta forma se logra la transducción de una base de datos a una visualización web. Al mes de abril de 2021, en la DAI se usa la versión 6 de D3.

#### Introducción a D3.js
[fuente 1](https://observablehq.com/@d3/learn-d3-by-example?collection=@d3/learn-d3)
[fuente 2 ](https://observablehq.com/@uvizlab/d3-tutorial-2-introduction-to-d3-with-observable?collection=@uvizlab/d3-tutorial)

El entorno SVG (*Scalable Vector Graphics*) nos permite dibujar una amplia variedad de gráficos como puntos, rectángulos, curvas, polígonos, etc. Este tipo de gráficos se ajusta a diferentes tamaños de pantalla y la resolución no se pixelea.

**Métodos de manipulación del DOM**

`d3.select("p")` Encuenta el elemento `p` en el DOM y hace referencia al siguiente paso de la cadena. Si existen varios `p`, seleccionará solo al primero del DOM.

`.selectAll("p")` Encuentra todos los elementos `p` 

`.append("p")` Agrega un elemento `p` al elemento que se seleccionó previamente mediante los métodos anteriores.

Cabe mencionar que los métodos de selección anteriores se pueden concatenar. Por ejemplo, el siguiente caso es válido y agregará un svg a cada `div` hijo de `div#contenedorVisualizaciones`:

```
...
<div id="contenedorVisualizaciones">
    <div></div>
    <div></div>
</div>
...
<script>
    d3.select("#contenedorVisualizaciones")
        .selectAll("div")
        .append("svg")
</script>
```

**Conectando datos al DOM**

La *fórmula* o cadena para asociar datos a elementos de un svg, suponiendo que el elemento `<svg id="visualizacion"> </svg>` ya fue creado, es la siguiente 

```
d3.select("svg#visualizacion")
    .selectAll(elementos del DOM)
    .data(Array de datos)
    .enter()
    .append(elementos, generalmente)
    // Los siguientes parámetros son para declarar estilos y atributos
    //y pueden ir tantos como sean necesarios
    .attr(atributo,valor)
    .style(estilo,valor)
    // en caso de que hayas agregado algún objeto que admita texto:
    .text(texto)

```
`.select()` toma como argumento un string, por ejemplo "svg" selecciona el elemento al cual agregaremos otros objetos

`.selectAll()` toma como argumento un string, por ejemplo ".circulos" y seleccionará todos los elementos dentro de la selección que le precedió y pueden ocurrir dos cosas:
    
* Si los elementos seleccionados no existen, después del `.data().enter().append()`, agregará los elementos que se designaron como argumento del `.append()` como hijos de `svg#visualizacion`. Este es el caso más común
    
* Si los elementos ya existen, la cadena que sigue `.data().enter().append()` requeriría un paso intermedio `.exit()` para obtener el resultado del caso anterior y resolver casos en los que la longitud de los datos es distinta de la de los elementos existentes seleccionados. De otra forma, este método agregaría el elemento designado como argumento del `.append()` a cada uno de los elementos seleccionados con el `.selectAll()`. [Acá](http://bl.ocks.org/alansmithy/e984477a741bc56db5a5) se encuentra un ejemplo y [acá](https://bost.ocks.org/mike/join/) un artículo para más información.

`.data()` toma como argumento un array, puede ser un array de objetos o alguna otra estructura más elaborada. Crea una asociación uno a uno entre cada elemento del Array y cada elemento del DOM

`.enter()` para crear nuevos elementos asociados a los datos se debe usar esta función. Toma los elementos seleccionados y los datos, y si hay más datos que elementos del DOM, creea un nuevo espacio para el siguiente paso de la cadena.

`.append()` toma como argumento un string, que represente al elemento DOM que se desea agregar. Por ejemplo "circle"

`.attr()` toma dos argumentos de tipo string, el primero corresponde al atributo y el segundo al valor. Un ejemplo es `.attr("href","google.com")`

`.style()` toma dos argumentos de tipo string, el primero corresponde al estilo y el segundo al valor. Un ejemplo es `.style("fill","white")`

**Ejes y escalas**

Supón que tienes una base de datos, cuyos valores a visualizar con un diagrama de dispersión van de 0 a 5,000,000 para el eje horizontal y de 400 a 1,000 para el eje vertical, mientras que el tamaño del svg es de 800px X 800px. En este caso sería deseable tener una función de parametrización que asigne 0px al valor mínimo de las variables y 800px al máximo en el caso de la variable horizontal y 0px para 5,000,000 y 800px para 0 en el caso del eje vertical, ya que el origen en el svg se encuentra en la esquina superior izquierda, a diferencia de como ocurre en un plano cartesiano convencional. Para esto existen las funciones de escala de d3. Las más comunes son:

* d3.scaleLinear(): Ideal para el caso planteado anteriormente, toma dominio (entrada) y rango (salida)
    ```
    //Mapea 0 a 800 y 5000000 a 0
    var escalaY=d3.scaleLinear()
        .domain([0,5000000]) 
        .range([800,0])        

    console.log(escalaY(2500000))
    // 400    
    ```

* d3.scaleBand(): Mapea un domino discreto a uno continuo. Es decir, el rango lo divide en el número de elementos del domino y asigna esos porcentajes 

    ```
    var escalaX=d3.scaleBand()
        .domain(["Gato","Perro"]) 
        .range([0,100])        
        .padding(.5) //Separación entre "bandas"

    console.log(escalaX("Gato"))
    // 20 
    console.log(escalaX("Perro"))
    // 60
    console.log(escalaX.bandWidth())
    // 20

    ```


* d3.scaleTime(): Mapea de forma lineal datos temporales a numéricos. Para transformar datos de fecha en formato de texto la función `d3.timeParse` puede ser de utilidad:

    ```
    var parseDate = d3.timeParse("%Y-%m-%d");
    var escalaT=d3.scaleTime()
        .domain([parseDate("2021-01-01"),parseDate("2021-03-01")])
        .range([ 0, 800 ])
    console.log(escalaT(parseDate("2021-02-01")))
    // 420.3389830508475

    ```

* d3.scaleOrdinal():  mapea datos discretos a datos discretos. Su función recuerda a la de un diccionario
    ```
    var escalaX=d3.scaleOrdinal()
        .domain(["Gato","Perro","Vaca"])
        .range([ "orange","#fff","#000" ])
    console.log(escalaX("Perro"))
    // #fff

    ```









 

### OpenLayers
### Simple statistics
### Jekill*
### Amcharts*
### Bulma*
