# Control de versiones con Git

La gestión de códigos de desarrollo en la DAI pretende alinearse a los [lineamientos](https://conacyt-arquitectura.github.io/git/) propuestos por la Dirección de Arquitectura y Modelado para Cómputo aplicado a Datos, los cuales son una extensión de [A successful Git branching model](https://nvie.com/posts/a-successful-git-branching-model/). El versionamiento de código debe estár alineado a [Semantic Versioning 2.0.0](https://semver.org/spec/v2.0.0.html). La solicitud de repositorios remotos en [Gitlab](https://scm.crip.conacyt.mx/) se lleva a cabo con dicha Dirección y se deben expresar las siguientes especificaciones.

- Grupo al que pertenecerá el proyecto: Se refiere al PRONACE al que pertenecerá el proyecto, o bien, al nombre del dominio general. Al mes de abril de 2021 la DAI tiene los grupos `alimentacion`, `salud` y `proyectos-crip`

- Nombre del repositorio: Corresponde al nombre del proyecto, nombre del ENI o carpeta que contiene al proyecto en el servidor. Puede tener los sufijos `-web` o `-data` que especifican si el repositorio corresponde a un proyecto de desarrollo web o a uno de procesamiento de datos respectivamente y se debe especifiar quien será propietarix.

Al mes de abril de 2021 los repositorios que tiene la DAI son `coronavirus-data`, `coronavirus-web` y `vacunacion` en el grupo de `salud`; `disciplinas-web`, `portada-web` y `subdisciplinas-web` en el grupo de `proyectos-crip` y, finalmente, `glifosato` en el grupo de `alimentacion`.



## Flujo de git

Convenciones de características de ramas:
- `master`: Es la rama principal en la que se encuentran solo las versiones productivas del sistema que se han liberado a producción.
    - No esta permitido subir código roto
    - Solo el rol master puede ejecutar la operación de `push/merge` a esta rama
    - Esta rama nunca se debe borrar

- `develop`: Es la rama secundaria. En esta rama el equipo de desarrollo trabajará día con día una nueva versión del sistema. Bifurca de `master`y se une con `master`

- `feature`: Este tipo de ramas se usan para desarrollar nuevas características o funcionalidades para futuras entregas. Cuando la implementación es aprobada, se unirá a `develop` o, si es rechazada, se eliminará. Bifurca de `develop` y se une con `develop`. La propuesta de nomenclatura es que tenga el prefijo `feature-`, por ejemplo `feature-lectura-graficas`. Idealmente estas ramas no se deben encontrar en el repositorio remoto, pero si lo llegan a estar, se deben borrar una vez que sea descartada o unida a `develop`.

- `release`: Se utiliza para preparar una nueva entrega para el ambiente de producción (`master`), resolver pequeños defectos y preparar metadatos. Bifurca de `develop` y se une con `develop`y `master`. La propuesta de nomenclatura es con el prefijo `relase-`, por ejemplo `release-1.0.2`. El beneficio de tener este tipo de rama es que se mantiene la rama `develop` limpia y lista para recibir nuevas versiones y que puede ser usada por el equipo de QA para probar la entrega antes de que llegue a producción.

- `hotfix`: Las ramas de este tipo se utilizan para resolver bugs que surjan en el ambiente de producción. Bifurcan de  `master` y se unen con `master` y `develop`. La convención de nombre propuesto es `hotfix-[modulo-version]`, por ejemplo, si la versión en producción es la `1.2.0` y se encuentra un error en las gráficas, el nombre podría ser `hotfix-graficas-1.2.1`.


En los [lineamientos](https://conacyt-arquitectura.github.io/git/) se pueden consultar más detalles y algunos ejemplos.

