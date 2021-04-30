# Estilo de código

## Convenciones de desarrollo en la DAI

El equipo de desarrollo deberá leer e implementar las recomendaciones que se encuentran en la [guía de desarrollo](https://github.com/flkt-crnpio/dai-guia-de-buenas-practicas).
Adoptaremos la convención de escribir las variables con el estilo `snake_case` y las funciones de javascript con `camelCase`, Además, las variables de tipo booleano deberán tener el prefijo `is_`.

A continuación se exponen una serie de conceptos que deberán ser puestos en práctica por el equipo de desarrollo de la DAI.



## Conceptos DRY y SOLID

### DRY

*Don't repeat yourself* es un principio de desarrollo de software que promueve la reducción de duplicación. Según este principio, ninguna piezas de información debe ser duplicada, pues esto dificulta implementar cambios y la evolución misma del código. Con piezas de información nos podemos referir a:
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
* Los módulos de alto nivel no deberían depender de los de bajo nivel. Ambos deberán depender de abstracciones

* Las abstracciones no deberían depender de los detalles. Son los detalles los que deberían depender de las abstracciones.


## Código limpio

A continuación se rescatan algunas recomendaciones de *Clean code*, de Uncle Bob 

### Nombres significativos

Debemos utilizar nombres de variables y de funciones que revelen la intención o uso de ésta, de manera clara, que sean pronunciables y fáciles de buscar. La única excepción pueden ser variables que se usan en ciclos o mapeos de arrays. Las funciones preferentemente deberían contener un verbo

```
//Mal
var f=111;
var fi=111;
var fech_inic=111;
var fch_inc=111;


//Mejor
var fecha_de_inicio=111
```

### Funciones

- Deben ser tan cortas como se pueda. 
- Es mejor tener muchas funciones cortas que menos funciones muy largas. 
- Preferentemente su nivel de anidamiento no debería ser mayor de uno o dos, esto las hace más fácil de leer y entender. 
- Debe hacer una cosa y la debe hacer bien. En este punto puede haber una ambigüedad sobre qué es hacer bien una cosa; lo ideal es que una función descomponga un concepto más grande (como lo debería indicar el nombre de la función) en un conjunto de pasos en el siguiente nivel de abstracción.
- Un nivel de abstracción por función

- Evitar pasar un booleano como argumento. ESto significaría que tu función puede hacer más de una cosa y que podría estar usando varios niveles de abstracción 

- Si una función toma más de 3 argumentos, quizá lo mejor sea que tome objetos como argumento.

### Comentarios

- También se debe dar mantenimiento a los comentarios, ya que a veces el código se va modificando y nos olvidamos de revisar si los comentarios siguen vigentes. 
- Un código limpio que no necesite comentarios es mucho mejor
- Procura que el código se explique a sí mismo
- Puedes explicar y clarificar cuando sea necesario, sin ser redundante