<div class="topnav">
  <ul>
    <li><a href="https://conacyt-dai.github.io/protocolo-desarrollo/">Página principal</a></li>
    <li><a href="toma_de_requerimientos">Toma de requerimientos</a></li>
    <li>Tecnologías y bibliotecas sugeridas</li>
    <li><a href="control_versiones">Control de versiones</a></li>
    <li><a href="documentacion_de_proyectos">Requerimientos mínimos de documentación</a></li>
    <li><a href="testing">Testing</a></li>
    <li><a href="solicitud_de_recursos">Flujos para solicitud de recursos</a></li>
    <li><a href="estilo_de_codigo">Estilo de código</a></li>
  </ul>
</div>
___


# Tecnologías y bibliotecas sugeridads


## Node
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

### Instalación de node
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

### Iniciando un proyecto en node.js

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


## Geoserver
<div style="text-align: center;">

[<img src="https://docs.geoserver.org/stable/en/user/_static/chrome/geoserver-logo.png" />](https://geoserver.org)

</div>

GeoServer es un servidor de código abierto para compartir datos geoespaciales. Diseñado para la interoperabilidad, publica datos de cualquier fuente de datos espaciales importante utilizando estándares abiertos.

GeoServer implementa protocolos OGC estándar de la industria, como Web Feature Service (WFS), Web Map Service (WMS) y Web Coverage Service (WCS). Hay formatos y opciones de publicación adicionales disponibles como extensiones, incluido el Servicio de procesamiento web (WPS) y el Servicio de mosaicos de mapas web (WMTS).

### Instalación
Para instalar con un servidor de aplicaciones existente como Tomcat, consulte la sección de archivo web.

GeoServer requiere un entorno Java 8 o Java 11, disponible en [OpenJDK](http://openjdk.java.net/), [AdoptOpenJDK](https://adoptopenjdk.net/) o proporcionado por la distribución de su sistema operativo.

**Nota:** _Para obtener más información sobre Java y GeoServer, consulte la sección sobre [Consideraciones de Java](https://docs.geoserver.org/stable/en/user/production/java.html#production-java)._

#### Linux binary
El binario independiente de la plataforma es una aplicación web GeoServer incluida dentro de Jetty, un servidor de aplicaciones portátil y ligero. Tiene las ventajas de funcionar de manera muy similar en todos los sistemas operativos y es muy simple de configurar.

1. Asegúrese de tener un Java Runtime Environment (JRE) instalado en su sistema.
2. Seleccione la versión de GeoServer que desea descargar. Si no está seguro, seleccione [Estable](http://geoserver.org/release/stable).
3. Seleccione **Platform Independent Binary** en la página de descarga.
4. Descargue el archivo y descomprímalo en el directorio donde le gustaría ubicar el programa. Use `/usr/share/geoserver` como sugerencia.
5. Agregue una variable de entorno para guardar la ubicación de GeoServer escribiendo el siguiente comando:
```
echo "export GEOSERVER_HOME=/usr/share/geoserver" >> ~/.profile
. ~/.profile
```
6. Conviértase en el propietario de la carpeta `geoserver`. Escriba el siguiente comando en la ventana de la terminal, reemplazando `USER_NAME` con su propio nombre de usuario:
```
sudo chown -R USER_NAME /usr/share/geoserver/
```
7. Inicie GeoServer cambiando al directorio `geoserver/bin` y ejecutando el script `startup.sh`:
```
cd geoserver/bin
sh startup.sh
```
8. En un navegador web, vaya a `http://localhost:8080/geoserver`.

Si ve el logotipo de GeoServer, entonces GeoServer se instaló correctamente.

<div align="center"><img src="https://docs.geoserver.org/stable/en/user/_images/success.png" /></div>

Para apagar GeoServer, cierre la ventana de línea de comandos persistente o ejecute el archivo `shutdown.sh` dentro del directorio `bin`.

#### Web archive
GeoServer está empaquetado como un servlet independiente para usar con servidores de aplicaciones existentes como Apache Tomcat y Jetty.

1. Asegúrese de tener un Java Runtime Environment (JRE) instalado en su sistema.
2. Navegue a la [página de descarga de GeoServer](http://geoserver.org/download/).
3. Seleccione Archivo web en la página de descarga.
4. Descarga y descomprime el archivo.
5. Implemente el archivo web como lo haría normalmente. A menudo, todo lo que se necesita es copiar el archivo geoserver.war al directorio de aplicaciones web del servidor de aplicaciones y la aplicación se implementará (Es posible que sea necesario reiniciar su servidor de aplicaciones).
6. Utilice el método de su aplicación contenedora para iniciar y detener aplicaciones web para ejecutar GeoServer.
7. Para acceder a la [interfaz de administración web](https://docs.geoserver.org/stable/en/user/webadmin/index.html#web-admin), abra un navegador y navegue hasta `http://SERVER/geoserver`. Por ejemplo, con Tomcat ejecutándose en el puerto 8080 en localhost, la URL sería `http://localhost:8080/geoserver`.


### Crear un espacio de trabajo
Un espacio de trabajo es un contenedor que se utiliza para agrupar capas similares.

__Nota:__ _Este paso es opcional si desea utilizar un espacio de trabajo existente. Por lo general, se crea un espacio de trabajo para cada proyecto, que puede incluir tiendas y capas que están relacionadas entre sí._

1. En un navegador web, vaya a `http://SERVER/geoserver`.
2. Inicie sesión en GeoServer como se describe en la sección [Iniciar sesión](https://docs.geoserver.org/stable/en/user/gettingstarted/web-admin-quickstart/index.html#logging-in).
3. Vaya a __Data__ ‣ __Workspaces__.
<div align="center"><img src="https://docs.geoserver.org/stable/en/user/_images/data_workspaces1.png" /></div>

4. Haga clic en el botón Agregar nuevo espacio de trabajo.
5. Se le pedirá que ingrese un nombre de espacio de trabajo y un URI de espacio de nombres.
<div align="center"><img src="https://docs.geoserver.org/stable/en/user/_images/new_workspace.png" /></div>

6. Ingrese el __Nombre__ como `workspace` y el __URI__ del espacio de nombres como `http://geoserver.org/workspace`.

__Nota:__ _El nombre de un espacio de trabajo es un identificador que describe su proyecto. No debe exceder los diez caracteres ni contener espacios. Un URI de espacio de nombres (Identificador uniforme de recursos) generalmente puede ser una URL asociada con su proyecto con un identificador final agregado que indica el espacio de trabajo. El URI del espacio de nombres archivado no necesita resolverse en una dirección web válida real._
7. Haga clic en el botón __Enviar__. El espacio de trabajo de `workspace` se agregará a la lista de espacios de trabajo.

### Crear un almacén de datos con origen de postgis
Una vez que se crea el espacio de trabajo, estamos listos para agregar un nuevo almacén de datos. Los almacenes de datos le dice a GeoServer cómo conectarse al archivo geográfico.
1. Vaya a __Data__ ‣ __Stores__.
2. Debería ver una lista de almacenes de datos, incluido el tipo de almacén y el espacio de trabajo al que pertenece.
3. Haga clic en el botón `Add new Store`. Se le redirigirá a una lista de las fuentes de datos compatibles con GeoServer. _Tenga en cuenta que las fuentes de datos son extensibles, por lo que su lista puede verse ligeramente diferente._
<div align="center"><img src="https://docs.geoserver.org/stable/en/user/_images/datastores.png" /></div>

4. Haga clic en __PostGIS__.
5. Ingrese la información básica del almacén (Workspace, Data Source Name, Description).
6. Especifique los parámetros de __conexión__ de la base de datos PostGIS:

    | Option | Value |
    | ------ | ----- |
    | dbtype | `postgis` |
    | host | (`db host`) |
    | port | (`db port`) |
    | database | (`db name`) |
    | schema | (`db schema`) |
    | user | (`postgres user`) |
    | passwd | (Password for the `postgres` user) |
    | validate connections | (Checked) |

7. Clic en __Guardar__.

### Publicar capas geográficas
Ahora que el almacén está preparado, podemos publicar la capa.
1. Vaya a __Data__ ‣ __Layers__.
2. Haga clic en __Add a new resource__.
3. En el menú del selector Nueva capa, seleccione el almacén de datos.
4. En la fila de la capa resultante, seleccione el nombre de la capa que desea publicar.
5. La página Editar capa define los datos y los parámetros de publicación de una capa. Introduzca un título breve y un resumen para la capa.
6. Genere los cuadros delimitadores de la capa haciendo clic en los enlaces Calcular a partir de datos y luego Calcular a partir de límites nativos.
<div align="center"><img src="https://docs.geoserver.org/stable/en/user/_images/boundingbox.png" /></div>

7. Haga clic en la pestaña __Publicación__ en la parte superior de la página.
8. Podemos establecer el estilo de la capa aquí. En Configuración de WMS, asegúrese de que el Estilo predeterminado esté configurado a la geometría correcta.
<div align="center"><img src="https://docs.geoserver.org/stable/en/user/_images/style.png" /></div>

9. Finalice la configuración de la capa desplazándose hasta la parte inferior de la página y haciendo clic en __Guardar__.

#### Vista previa de la capa
Para verificar que la capa se publicó correctamente, podemos obtener una vista previa de la capa.
1. Navegue a la pantalla Vista previa de la capa y busque su capa.
2. Haga clic en el enlace __OpenLayers__ en la columna de formatos comunes.
3. Un mapa de OpenLayers se cargará en una nueva pestaña y mostrará los datos del shapefile con el estilo predeterminado. Puede utilizar este mapa de vista previa para hacer zoom y desplazarse por el conjunto de datos, así como para mostrar los atributos de las entidades.



## Vue CLI
[Vue CLI](https://cli.vuejs.org/) es un sistema completo para el desarrollo rápido de Vue.js, que proporciona:

* Soporte de proyectos interactivos a través de @vue/cli.
* Creación rápida de prototipos de configuración cero a través de @vue/cli + @vue/cli-service-global.
* Una interfaz gráfica de usuario completa para crear y administrar proyectos de Vue.js.


Vue CLI tiene como objetivo ser la línea de base de herramientas estándar para el ecosistema Vue. Garantiza que las diversas herramientas de compilación funcionen sin problemas junto con valores predeterminados razonables para que pueda concentrarse en escribir su aplicación en lugar de pasar días luchando con configuraciones. Al mismo tiempo, todavía ofrece la flexibilidad de modificar la configuración de cada herramienta sin la necesidad de expulsarla.

## Vue

[Vue](https://vuejs.org/) es un framework progresivo para construir interfaces de usuario. A diferencia de otros frameworks monolíticos, Vue está diseñado desde cero para ser adoptable de forma incremental. La biblioteca principal se centra solo en la capa de vista y es fácil de integrar con otras bibliotecas o proyectos existentes. Por otro lado, Vue también es perfectamente capaz de impulsar aplicaciones sofisticadas de una sola página cuando se usa en combinación con herramientas modernas y bibliotecas de soporte.

Consulte [Comparación con otros frameworks](https://vuejs.org/v2/guide/comparison.html) para obtener información de cómo se compara Vue con otras bibliotecas/frameworks.



## Sass
[Sass](https://sass-lang.com/) (*Syntactically Awesome Stylesheets*) es un metalenguaje de CSS. Permite usar funcionalidades que no existen en CSS, pero todas las funcionalidades de CSS funcionan también en Sass. Esisten dos tipos de formatos que Sass interpreta: `.scss` y `.sass`. La diferencia radica en la sintaxis y [aquí](https://sass-lang.com/documentation/syntax) puedes compararlos. En la DAI se suele usar el formato `.scss`.

Algunas de las funcionalidades básicas que se pueden implementar en Sass, a diferencia de CSS, se describen mediante ejemplos a continuación con la finalidad de sacar el máximo provecho a esta herramienta (los ejemplos son tomados de [aquí](https://sass-lang.com/guide)):

### Variables

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

### Anidamiento *(Nesting)*

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

### Modularización 

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

### Mixins
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

### Extend / herencia
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

### Operadores
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




## D3

Data-Driven-Documents [D3](https://d3js.org/) es conocida como una de las bibliotecas de JavaScript más poderosas para visualizar datos, cuenta con una amplia [documentación](https://github.com/d3/d3/wiki) y su uso radica en ligara bases de datos a elementos de HTML, principalmente de SVG; de tal forma que, datos numéricos, temporales o categoricos se asocien a estilos y atributos de los elementos HTML o SVG. De esta forma se logra la transducción de una base de datos a una visualización web. Al mes de abril de 2021, en la DAI se usa la versión 6 de D3.

### Introducción a D3.js

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
    .append(elementos DOM)
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

**Escalas**

Supón que tienes una base de datos, cuyos valores a visualizar con un diagrama de dispersión van de 0 a 5,000,000 para el eje horizontal y de 400 a 1,000 para el eje vertical, mientras que el tamaño del svg es de 800px X 800px. En este caso sería deseable tener una función de parametrización que asigne 0px al valor mínimo de las variables y 800px al máximo en el caso de la variable horizontal y 0px para 5,000,000 y 800px para 0 en el caso del eje vertical, ya que el origen en el svg se encuentra en la esquina superior izquierda, a diferencia de como ocurre en un plano cartesiano convencional. Para esto existen las funciones de escala de d3. Las más comunes son:

* `d3.scaleLinear()`: Ideal para el caso planteado anteriormente, toma dominio (entrada) y rango (salida)
    ```
    //Mapea 0 a 800 y 5000000 a 0
    var escalaY=d3.scaleLinear()
        .domain([0,5000000]) 
        .range([800,0])        

    console.log(escalaY(2500000))
    // 400    
    ```

* `d3.scaleBand()`: Mapea un domino discreto a uno continuo. Es decir, el rango lo divide en el número de elementos del domino y asigna esos intervalos. Esta función es muy útil para gráficas de barras  

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


* `d3.scaleTime()`: Mapea de forma lineal datos temporales a numéricos. Para transformar fechas en formato de texto a formato temporal, la función `d3.timeParse()` puede ser de utilidad:

    ```
    var parseDate = d3.timeParse("%Y-%m-%d");
    var escalaT=d3.scaleTime()
        .domain([parseDate("2021-01-01"),parseDate("2021-03-01")])
        .range([ 0, 800 ])
    console.log(escalaT(parseDate("2021-02-01")))
    // 420.3389830508475

    ```

* `d3.scaleOrdinal()`:  mapea datos discretos a datos discretos. Su función recuerda a la de un diccionario
    ```
    var escalaX=d3.scaleOrdinal()
        .domain(["Gato","Perro","Vaca"])
        .range([ "orange","#fff","#000" ])
    console.log(escalaX("Perro"))
    // #fff

    ```

**Ejes**

Una buena práctica para colocar los ejes graduados es el uso de márgenes que dejen un espacio alrededor de la visualización, en donde se puedan colocar los ejes sin que estos se empalmen con los elementos de la visualización o queden fuera y no visibles de ésta. Colocar ejes graduados puede ser muy sencillo si ya se han definido las escalas previamente, como se muestra en el siguiente código:

```
const margin = { left: 30, top: 10, right: 10, bottom: 10 } 

const ancho= 400-margin.left-margin.right, alto = 300-margin.top-margin.bottom;
const svg = d3.select("div#contenedorVisualizacion")
    .attr("width",ancho+margin.left+margin.right)
    .attr("height",alto+margin.top+margin.bottom)
    .append("g")
    .attr("transform",`translate(${margin.left},${margin.top})`)

    //Definiendo svg de dimensiones de 400pxX300px, se le agrega un grupo "g" y se traslada al margen derecho y superior


const escalaX = d3.scaleLinear()
    .domain([0, 50])  
    .range([0, ancho])
const escalaY = d3.scaleLinear()
    .domain([0, 100])  
    .range([alto,0])

svg.append('g').call(d3.axisBottom(escalaX))
    .attr('transform', `translate(0,${alto})`)  // Agrega eje graduado y lo posiciona abajo, con una separación de margin.bottom de la orilla inferior del svg

svg.append('g').call(d3.axisLeft(escalaY))
    // Agrega eje graduado 

```

Si deseas profundizar más en este tema, se hizo [este](https://github.com/jdanielgoh/taller-d3) repositorio para la DAI, el cual incluye ejemplos prácticos de lo que se ha visto hasta ahora y profundiza en otro tipo de funcionalidades de d3, como eventos y transiciones, responsividad y estilos elaborados, fuerzas y procesos creativos.

Los ejemplos que aquí se han abordado están basados en [este tutoria](https://observablehq.com/@uvizlab/d3-tutorial-2-introduction-to-d3-with-observable?collection=@uvizlab/d3-tutorial) y se recomienda [este](https://observablehq.com/@d3/learn-d3-by-example?collection=@d3/learn-d3) otro que es más avanzado. Cabe mencionar que observabe es una especie de notebooks para crear visualizaciones de datos y la estructura puede parecer a veces un poco distinta la la de un script de js, por lo cual hay que leer los ejemplos con cuidado.


## OpenLayers
[OpenLayers](https://openlayers.org/) facilita la colocación de un mapa dinámico en cualquier página web. Puede mostrar mosaicos de mapas, datos vectoriales y marcadores cargados desde cualquier fuente. OpenLayers se ha desarrollado para promover el uso de información geográfica de todo tipo. Es de código abierto completamente gratuito (JavaScript).

### Instalación en el proyecto
Utilizando __nodejs__, el comando de instalación es el siguiente:
```
npm install ol
```

### Ejemplos básicos

1. Un mapa simple con una fuente OSM.

main.js
```
import 'ol/ol.css';
import Map from 'ol/Map';
import OSM from 'ol/source/OSM';
import TileLayer from 'ol/layer/Tile';
import View from 'ol/View';

var map = new Map({
  layers: [
    new TileLayer({
      source: new OSM(), // mapa base de openStreetMap
    }) ],
  target: 'map',
  view: new View({
    center: [0, 0], // Centro del mapa (coordenadas)
    zoom: 2,
  }),
});
```

HTML
```
<div id="map" class="map"></div>
```

2. Consumiendo un servicios wms/wfs

JS
```
import 'ol/ol.css';
import ImageWMS from 'ol/source/ImageWMS';
import Map from 'ol/Map';
import OSM from 'ol/source/OSM';
import View from 'ol/View';
import GeoJSON from 'ol/format/GeoJSON';
import VectorSource from 'ol/source/Vector';
import {Stroke, Style} from 'ol/style';
import {bbox as bboxStrategy} from 'ol/loadingstrategy';
import {Image as ImageLayer, Tile as TileLayer, Tile as TileLayer, Vector as VectorLayer} from 'ol/layer';

var layers = [
  new TileLayer({source: new OSM()}),
  new ImageLayer({ // wms service
    source: new ImageWMS({
      url: '<url del servicio wms>',
      params: {'LAYERS': 'topp:states'},
      ratio: 1,
      serverType: 'geoserver',
    }),
  }),
  new VectorLayer({ // wfs service
    source: new VectorSource({
      format: new GeoJSON(),
        url: function (extent) {
            return ('<url del servicio wfs>');
        },
        strategy: bboxStrategy,
      }),
      style: new Style({
        stroke: new Stroke({
        color: 'rgba(0, 0, 255, 1.0)',
        width: 2,
      }),
    }),
  })
];
var map = new Map({
  layers: layers,
  target: 'map',
  view: new View({
    center: [-10997148, 4569099],
    zoom: 4,
  }),
});
```

Para más ejemplo prácticos consulte [OpenLayers Examples](https://openlayers.org/en/latest/examples/index.html). Para la documentación competa de los componentes el [OpenLayers Apidoc](https://openlayers.org/en/latest/apidoc/).


## Simple statistics

[Simple statistics](https://simplestatistics.org/) es una biblioteca de JavaScript para implementar métodos estadísticos. En la DAI se ha usado para implementar el método de clasificación con cortes naturales (jenks) para algunos mapas, ya que hay veces en que los cuantiles dan resultados no deseados.

Suponiento que tienes un Array `data` de valores numéricos a clasificar en `n` cantidad de grupos, con la función `ss.jenks(data,n)` esto es posible y te devuelve los cortes naturales.

Con ayuda de d3 se podría crear una escala de la siguiente manera:

```
let colores=["#000","#ab324d","#e2e2e2","#fff"]
let clases = ss.jenks(data,colores.length) //En este caso devuelve un array de 5 elementos
let clases_to_d3= [...clases] //Creamos una copia porque es posible que el array original se use después para nomenclatura

clases_to_d3.shift() //Borramos el primer elemento

let scale = d3.scaleThreshold()
    .domain(clases_to_d3)
    .range(colores)
```
Si hay alguna duda sobre como funciona `scaleThreshold()` se recomienda consultar la [documentación](https://github.com/d3/d3-scale/blob/master/README.md#threshold-scales), en resumen mapea números, según el intervalo o rango en el que se encuentren, a valores discretos.

A pesar de que Simple statistics es una vasta biblioteca, hasta ahora en la DAI, este es e único uso que se le ha dado. No obstante, es bueno revisarla y saber de su existencia por si en un futuro se requiere implementar otros métodos estadísticos. 

___

Para proximas entregas se planea documentar 
* Django
* Jekill (dependiendo de si se segurá utilizando)
* Amcharts
* Bulma










<style>
.topnav ul {
    font-size: 14px;
    display: flex;
    list-style: none;
    justify-content: center;
    flex-wrap: wrap;
}
.topnav ul li {
    margin-inline: 4px;
}
.topnav ul li:first-child {
    margin-top: 4px;
}
.topnav ul li > a {
    color: #1e6bb8;
}
.topnav ul li > a:hover {
    text-decoration: none;
    color: #159957;
}
</style>