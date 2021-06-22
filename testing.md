<div class="topnav">
  <a href="https://conacyt-dai.github.io/protocolo-desarrollo/">Página principal</a>
  <a href="toma_de_requerimientos">Toma de requerimientos</a>
  <a href="tecnologias_y_bibliotecas">Tecnologías y bibliotecas sugeridas</a>
  <a href="control_versiones">Control de versiones</a>
  <a href="documentacion_de_proyectos">Requerimientos mínimos de documentación</a>
  <span>Testing</span>
  <a href="solicitud_de_recursos">Flujos para solicitud de recursos</a>
  <a href="estilo_de_codigo">Estilo de código</a>
</div>
<hr />


# Testing

Un framework de pruebas unitarias permite escribir pruebas sobre un bloque de código, sin interferir en el entorno de desarrollo ni en la propia aplicación. Sirven para asegurarnos de que un bloque de código, función, clase o componente trabajan correctamente y abarca la mayoría de casos de uso que se le pueden dar, lo cual proporciona robustez y calidad a nuestro código.

## Pruebas en Vue
El framework de pruebas propuesto es [Jest](https://jestjs.io/). Cuando se inicializa un proyecto de forma manual con vue-cli, se puede elegir si se desean integrar pruebas unitarias al proyecto, así como la instalación de Jest como framework de pruebas. Esta elección proverá al proyecto de [Vue Test Utils](https://vue-test-utils.vuejs.org/), la biblioteca oficial de testing unitario para vue. Con esta configuración, se creará una carpeta de pruebas `/test` en donde podremos alojar los archivos `.js` con las pruebas. A continuación se muestra un ejemplo básico de un componente "contador" que aumenta en una unidad una variable cada que se hace click en un botton.


```
//Contador.vue
<template>
    <div>
      <div>contador: {{counter}}</div>
      <button class="contador" @click="counter++">aumenta</button>
  </div>
</template>

<script>
export default {
  name: 'Contador',
  props: {
    msg: String
  },
   data:()=>{return {
    counter:0
  }},
}
</script>
```
Test unitario para verificar si el texto en el componente se modifica como es de esperarse al dar un click 

```
// tests/unit/contador.spec.js

import { mount } from '@vue/test-utils'
import Contador from '@/components/Contador.vue'

describe('Contador.vue', () => {
    it("incrementa al dar click correctamente", () => {
        const wrapper = mount(Contador) //selecciona el contenedor montado
        expect(wrapper.text()).toContain("contador: 0") //verifica que exista el texto en el estado inicial
        //Simulamos un click y verificamos que el texto se modifique como se espera 
        wrapper.find("button").trigger("click").then(() => {
            expect(wrapper.text()).toContain("contador: 1")
        })

    })
})

```

En la [documentación](https://jestjs.io/docs/getting-started) de Jest se pueden consultar varios casos de uso para javascript, así como en la [documentación](https://vue-test-utils.vuejs.org/) de vue para testear componentes.

___

Para proximas entregas se planea documentar 
* pruebas en python




<hr style="display:none" />
<style>.topnav{font-size:1rem;display:flex;justify-content:center;flex-wrap:wrap;}.topnav>a,span{margin-inline:4px;}.topnav>a{color:#1e6bb8;}.topnav>a:hover{text-decoration:none;color:#159957;}</style>