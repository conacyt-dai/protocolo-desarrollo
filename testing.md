# Testing

Un framework de pruebas unitarias permite escribir pruebas sobre un bloque de código, sin interferir en el entorno de desarrollo ni en la propia aplicación. Sirven para asegurarnos de que un bloque de código, función, clase o componente trabajan correctamente y abarca la mayoría de casos de uso que se le pueden dar, lo cual proporciona robustez y calidad a nuestro código.

El framework de pruebas propuesto es [Jest](https://jestjs.io/). Cuando se inicializa un proyecto de forma manual con vue-cli, se puede elegir si se desean integrar pruebas unitarias al proyecto, así como la instalación de Jest como framework de pruebas. Esta elección proverá al proyecto de [Vue Test Utils](https://vue-test-utils.vuejs.org/), la librería oficial de testing unitario para vue. Con esta configuración, se creará una carpeta de pruebas `/test` en donde podremos alojar los archivos `.js` con las pruebas. A continuación se muestra un ejemplo básico de un componente "contador" que aumenta en una unidad una variable cada que se hace click en un botton.


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
