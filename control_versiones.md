# Control de versiones con Git

La gestión de códigos de desarrollo en la DAI pretende alinearse a los [lineamientos](https://conacyt-arquitectura.github.io/git/) propuestos por la Dirección de Arquitectura y Modelado para Cómputo aplicado a Datos, los cuales son una extensión de [A successful Git branching model](https://nvie.com/posts/a-successful-git-branching-model/). El versionamiento de código debe estár alineado a [Semantic Versioning 2.0.0](https://semver.org/spec/v2.0.0.html). 


## Flujo de git

Convenciones de características de ramas:
<div align="center"><img src="https://conacyt-arquitectura.github.io/assets/images/git/diagram.png" /></div>

- `main` *antes `master`*: Es la rama principal en la que se encuentran solo las versiones productivas del sistema que se han liberado a producción.
    - No esta permitido subir código roto
    - Solo el rol maintainer puede ejecutar la operación de `push/merge` a esta rama
    - Esta rama nunca se debe borrar
    - Cada que se haga un merge en esta rama se debe agregar el `Tag` de la versión correspondiente que debe estar en la forma de vX.Y.Z descrito en [Semantic Versioning 2.0.0](https://semver.org/spec/v2.0.0.html)

- `develop`: Es la rama secundaria. En esta rama el equipo de desarrollo trabajará día con día una nueva versión del sistema. Bifurca de `main`y se une con `main` *(main === master)*

- `feature`: Este tipo de ramas se usan para desarrollar nuevas características o funcionalidades para futuras entregas. Cuando la implementación es aprobada, se unirá a `develop` o, si es rechazada, se eliminará. Bifurca de `develop` y se une con `develop`. La propuesta de nomenclatura es que tenga el prefijo `feature-`, por ejemplo `feature-lectura-graficas`. Idealmente estas ramas no se deben encontrar en el repositorio remoto, pero si lo llegan a estar, se deben borrar una vez que sea descartada o unida a `develop`.

- `release`: Se utiliza para preparar una nueva entrega para el ambiente de producción (`main`), resolver pequeños defectos y preparar metadatos. Bifurca de `develop` y se une con `develop`y `main`. La propuesta de nomenclatura es con el prefijo `relase-`, por ejemplo `release-1.0.2`. El beneficio de tener este tipo de rama es que se mantiene la rama `develop` limpia y lista para recibir nuevas versiones y que puede ser usada por el equipo de QA para probar la entrega antes de que llegue a producción. *NOTA: Actualmente no se utiliza ni la rama de release ni un ambiende de QA ya que todas las pruebas se revisan en los ambientes de desarrollo que se compilan desde la rama `develop`. Quizás en el futuro que tengamos equipo de pruebas podriamos adoptar ésta práctica.*

- `hotfix`: Las ramas de este tipo se utilizan para resolver bugs que surjan en el ambiente de producción. Bifurcan de  `main` y se unen con `main` y `develop`. La convención de nombre propuesto es `hotfix-[modulo-version]`, por ejemplo, si la versión en producción es la `1.2.0` y se encuentra un error en las gráficas, el nombre podría ser `hotfix-graficas-1.2.1`.

En los [lineamientos](https://conacyt-arquitectura.github.io/git/) se pueden consultar más detalles y algunos ejemplos.
