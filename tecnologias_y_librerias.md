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

Algunas de las funcionalidades básicas que se pueden implementar en Sass, a diferencia de CSS, se describen mediante ejemplos a continuación, con la finalidad de sacar el máximo provecho a esta herramienta (los ejemplos son tomados de [aquí](https://sass-lang.com/guide)):

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
### OpenLayers
### Simple statistics
### Jekill*
### Amcharts*
### Bulma*
