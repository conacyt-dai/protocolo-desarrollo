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

Para iniciar el proyecto creamos una carpeta y, en la terminal, ubicado dentro de la carpeta del proyecto escribimos 

```
npm init
```
A continuación nos pedirá ingresar algunas líneas para la configuración inicial de `package.json`, el cual contendrá la información del proyecto, incluendo las dependencias que se pueden instalar posteriormente con `npm`



Para la instalación de paquetes 



### Geoserver

### Django


## Librerías 
### Vue
### Sass
### D3
### OpenLayers
### Simple statistics
### Jekill*
### Amcharts*
### Bulma*
