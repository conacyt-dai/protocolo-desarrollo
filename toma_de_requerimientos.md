<div class="topnav">
  <a href="https://conacyt-dai.github.io/protocolo-desarrollo/">Página principal</a>
  <a class="active" href="toma_de_requerimientos">Toma de requerimientos</a>
  <a href="tecnologias_y_bibliotecas">Tecnologías y bibliotecas sugeridas</a>
  <a href="control_versiones">Control de versiones</a>
  <a href="documentacion_de_proyectos">Requerimientos mínimos de documentación</a>
  <a href="testing">Testing</a>
  <a href="solicitud_de_recursos">Flujos para solicitud de recursos</a>
  <a href="estilo_de_codigo">Estilo de código</a>
</div>

# Toma de requerimientos

Para llevar a cabo un proyecto de forma óptima, evitando conflictos a futuro sobre incompatibilidad, rendimiento, escalabilidad, etc. es importante tener una idea clara sobre los requerimientos que se esperan del desarrollo. Esto es crucial para determinar desde un inicio cuales son las tecnologías y flujos que se usarán en el proceso.

El objetivo de este apartado es que el equipo de desarrollo tenga claro cuales son los puntos que se deben tener claros cuando se nos solicita un desarrollo, y que quienes nos lo soliciten procuren cubrir todos estos puntos al comunicar sus requerimientos.

A continuación se mencionan algunas de las características que debe tener un requerimiento según [Northware](https://www.northware.mx/2012/01/15/tecnicas_efectivas_toma_requerimientos/)

* **Necesario:** Si hay alguna duda sobre la necesidad del requerimiento, se puede preguntar ¿Qué sería lo peor de no incluirlo?, si no se encuentra una respuesta o consecuencia, es probable que no sea un requerimiento necesario. 

	Ejemplo: ¿Qué sería lo peor de no usar Jekyll y sólo usar Vue?

* **Completo:** Se proporciona información suficiente para la comprensión del requerimiento.

* **Consistente:** No se contradice con otro requerimiento. Ejemplo de inconsistencias:
	* Un mapa con sólo front-end que muestre polígonos de AGEBS de todo el país.
	* Que cargue rápido.<br><br>

* **Factible:** El requerimiento debe ser realizable dentro de los calendarios y otras restricciones del equipo. Si hay dudas sobre su factibilidad, se debe dar un tiempo para investigar y realizar pruebas.

* **Modificable:** Quienes desarrollamos en la DAI, debemos estar abiertos y ser conscientes de que los requerimientos pueden cambiar. Sin embargo, será necesario hacer una recalendarización de los tiempos de entrega debido a los nuevos requerimientos o la modificación de los mismos.

* **Priorizado:** Categorizar en _Esencial_, _Deseado_, u _Opcional_ nos ayuda a organizar nuestros tiempos. Estas categorías normalmente se definen en las subdirecciones y por lo general todos los requerimientos suelen ser esenciales.

* **Verificable:** Determinar los criterios de aceptación y el sitio de demostración, prueba o inspección. Normalmente, estas revisiones se hacen en el ambiente de desarrollo antes de pasar a producción, a menos de que se requiera lo contrario.


El documento que comúnmente se usa como el levantamiento del requerimiento es el diseño, normalmente en XD, elaborado por la Subdirección de Visualización de Datos de la DAI. Lo ideal es que el desarrollo inicie hasta que se tenga el requerimiento, es decir el diseño, sin embargo hay algunas otras cuestiones que no necesariamente se tienen siempre en XD, por lo cual se mencionan a continuación algunos requerimientos que, en experiencia del equipo de desarrollo, han sido importante tener claro y preguntar antes de iniciar el proyecto:

* Sitio con distintos usuarios y permisos
* Servicios de mapas
* Cantidad de datos a visualizar  simultáneamente (polígonos, puntos, etc)
* Periodicidad de actualización
* Duración del mantenimiento a la página
* Alojamiento de archivos y espacio proyectado (ej. reportes PDF y PPT)
* Otras consideraciones para determinar si el sitio requiere back-end, seguridad y bases de datos.

A su vez, se deben especificar con detalle los casos de uso y las historias de usuario, es decir todos los pasos que puede llevar a cabo el usuario con las funciones del sistema.










<style>
.topnav {
  overflow: hidden;
  background-color: #159957;
  background-image: linear-gradient(120deg, #155799, #159957);
}
.topnav a {
  float: left;
  color: #f2f2f2;
  text-align: center;
  padding: 6px 8px;
  text-decoration: none;
  transition: color 0.2s, background-color 0.2s, border-color 0.2s;
}
.topnav a:hover {
  background-color: rgba(255,255,255,0.2);
  color: #f2f2f2;
}
.topnav a.active {
  background-color: rgba(255,255,255,0.08);
  color: #f2f2f2;
}
</style>