# Estilo de código


## Conceptos DRY y SOLID

### DRY

*Don't repeat yourself*  es un principio de desarrollo de software que promueve la reducción de duplicación. Según este principio, ninguna piezas de información debe ser duplicada, pues esto dificula implementar cambios y la evolución misma del código. Con piezas de información nos podemos referir a:
- código
- bases de datos
- información textual o documentación 


### SOLID

Es un acrónimo que hace referencia a prácticas aplicadas a la programación orientada a objetos.

**S: Single Responsability Principle**

Las clases o métodos deben hacer sólo una cosa sencilla y concreta. Esto hace que sea más fácil de mantener, reutilizar y hacer test unitarios.

**Open/Closed Principle**

Las clases o métodos deben estar abiertos a extensiones pero cerradas a modificaciones.

**Liskov Substitution Principle**

Sea `f(x)` un propiedad comprobable de los objetos `x` de tipo `T`. Entonces `f(y)` debe ser verdad para los objetos `y` del tipo `S`, en donde `S` es un subtipo de `T`.

En otras paralabras plantea que cada clase que se hereda de otra debe poder usarse como su padre si necesidad de conocer las diferencias entre ellas. 

**Interface Segregation Principle**

El cliente no debe ser forzado a depender de métodos que no usa.
Cada interface tendrá una  única responsabilidad, es preferible tener muchas interfaces con pocos métodos que una interface con muchos métodos.

**Dependency Inversion Principle**

Depender de abstracciones y no de implementaciones, establece que 
* Los módulos de alto nivel no deberían depender de los de bajo nivel. Ambos deberan depender de abstracciones

* Las abstracciones no deberían depender de los detalles. Son los detalles los que deberían depender de las abstracciones.


## Convenciones de desarrollo en la DAI
El equipo de desarrollo deberá leer e implementar las recomendaciones que se encuentran en la [guía de desarrollo](https://github.com/flkt-crnpio/dai-guia-de-buenas-practicas).
Adoptaremos la convencion de escribir las variables con el estilo `snake_case` y las funciones de javascript con `camelCase`, Además, las variables de tipo boleano deberán tener el prefijo `is_`.

