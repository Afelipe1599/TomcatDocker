# TomcatDocker

![portadas.png](Images/portadas.png)


En este repositorio se repasara como dockerizar el contenedor de servlets tomcat ademas de como desplegar este contenedor en 3 opciones en la nube como lo son AWS, Azure y Gcloud

## Docker馃悑

Docker es una plataforma de software que le permite crear, probar e implementar aplicaciones r谩pidamente. Docker empaqueta software en unidades estandarizadas llamadas contenedores que incluyen todo lo necesario para que el software se ejecute, incluidas bibliotecas, herramientas de sistema, c贸digo y tiempo de ejecuci贸n. Con Docker, puede implementar y ajustar la escala de aplicaciones r谩pidamente en cualquier entorno con la certeza de saber que su c贸digo se ejecutar谩.

## Contenedores馃摝 vs Maquinas virtuales馃捇

Docker le proporciona una manera est谩ndar de ejecutar su c贸digo. Docker es un sistema operativo para contenedores. De manera similar a c贸mo una m谩quina virtual virtualiza (elimina la necesidad de administrar directamente) el hardware del servidor, los contenedores virtualizan el sistema operativo de un servidor. Docker se instala en cada servidor y proporciona comandos sencillos que puede utilizar para crear, iniciar o detener contenedores.

Docker Engine se encarga de lanzar y gestionar los contenedores con nuestras aplicaciones, pero en lugar de exponer los diferentes recursos de hardware de la m谩quina de manera discreta (es decir, 1 procesador y "x" GB de RAM... para cada aplicaci贸n), lo que hace es compartirlos entre todos los contenedores optimizando su uso y eliminando la necesidad de tener sistemas operativos separados para conseguir el aislamiento.

![containers-vs-virtual-machines.jpg](Images/containers-vs-virtual-machines.jpg)



- [Creado el docker file y docker compose](https://github.com/Afelipe1599/TomcatDocker/tree/main/Docker)
- [Desplegarlo en AWS](https://github.com/Afelipe1599/TomcatDocker/tree/main/Aws)
- [Desplegarlo en GCLOUD](https://github.com/Afelipe1599/TomcatDocker/tree/main/Gcloud)
- [Desplegarlo en AZURE](https://github.com/Afelipe1599/TomcatDocker/tree/main/Azure)
