
![docker.png](../Images/docker.png)


Acontinuacion definiremos en que consiste el Dockerfile y el docker compose

# ¿Que es el Dockerfile?

Un Dockerfile es un archivo de texto plano que contiene una serie de instrucciones necesarias para crear una imagen que, posteriormente, se convertirá en una sola aplicación utilizada para un determinado propósito. Por lo tanto con una imagen construida, podemos correr un contenedor.


# Elementos de un Dockerfile
-  ### FROM
 	Indica la imagen base sobre la que se construirá la aplicación dentro del contenedo    
```plain
FROM tomcat:8.0.47 
```
-  ### MAINTAINER
	Indica el nombre del autor del dockerfile
```plain
MAINTAINER Andres Valencia "avalencia@gmail.com"
```  
-  ### EXPOSE
	Indica los puertos TCP/IP los cuales se pueden accede a los servicios del contenedor
```plain
EXPOSE 8080
```    
-  ### WORKDIR
	Indica el directorio de trabajo dentro del contenedor
```plain
WORKDIR ruta/de/Proyecto
```  
-  ### COPY o ADD
	Copia un archivo del directorio local a la imagen que se esta construyendo
```plain
COPY ./ejemplo.war /usr/local/tomcat/webapps/
ADD ./ejemplo.war /usr/local/tomcat/webapps/ejemplo.war
```  
-  ### RUN
	Nos permite ejecutar comandos en el contenedor, por ejemplo, instalar paquetes o librerías
```plain
RUN apt-get update
```    
-  ### CMD
	Establece el commando del proceso de inicio del contenedor
```plain
CMD ["catalina.sh","run"]
```      
# Crear y ejecutar un Dockerfile
Perfecto, con los elementos anteriores podemos crear un Dockerfile, como ejemplo tomaremos el [siguiente](https://github.com/Afelipe1599/TomcatDocker/tree/main/Docker/Dockerfile) :
```plain
#Imagen que se va a ejecutar
FROM tomcat:8.0.47

#Puerto por donde va a escuchar
EXPOSE 8080

#Comando de inicio
CMD ["catalina.sh","run"]
```     
Para ejecutarlo primero se debe construir la imagen, esto se hace desde la terminal con el siguiente comando desde el directorio donde se encuentra el docker file:
```plain
docker build -t tomcatprueba .
```     
-t define el nombre de la imagen.

Posterior a esto ya podemos ejecutar dicha imagen, para correr la imagen se utiliza el siguiente comando:
```plain
docker run -p 8080:8080 tomcatprueba
```   
 -p publica los puertos de un contenedor en el host, en este caso el 8080 del contenedor al 8080 de la maquina que lo esta ejecutando.
 
Con esto ya tendriamos un tomcat corriendo en nuestro computador atravez de una imagen de docker.

# ¿Que es el docker-compose?
Esta es una herramienta que nos ayuda a utilizar imagenes de docker tanto las predeterminadas como las creadas por nosotros obteniendo como resultado un conjunto de scripts que nos facilitan la construcción de nuestros servicios. La mayor ventaja de este es que podemos crear diferentes contenedores y por cada contenedor diferentes servicios.

# Elementos de un docker-compose
-  ### VERSION
	Se refiere a la version de docker-compose
```plain
version: '3'
```     
-  ### SERVICES
	Servirá para configurar todos nuestros contenedores partiendo de una imagen base, además de poder indicar variables de entorno o establecer ubicaciones.
```plain
services:
```     
-  ### VOLUMES
	 Donde podremos definir la persistencia de datos de nuestros contenedores.
```plain
volumes:
```     
-  ### IMAGE
	 Se refiere a la imagen que va a correr nuestro contendor en el docker-compose
```plain
image:tomcat:8.0.47
```   
-  ### PORTS
	 Se refiere a el mapeo de puertos que se le haran a la maquina
```plain
    ports:
      - "8080:8080"
``` 
-  ### NETWORKS
	 Si queremos que nuestros contenedores se encuentren en la misma red este comando nos sirve
```plain
networks:
``` 
# Crear y ejecutar un docker-compose
Con los elementos mencionados anteriormente construiremos un docker-compose sencillo que ejecute un contenedor con una imagen de tomcat en el puerto 8080 de la siguiente manera:
```plain
version: '3'
services:
  web:
    image: tomcat:8.0.47
    ports:
      - "8080:8080"
``` 
Para ejecutarlo nos ubicamos en la raiz del proyecto y ejecutamos el comando 
```plain
docker-compose up
``` 
Con este comando docker-compose estaria levantantdo un contenedor con tomcat corriendo en el puerto 8080 de la maquina local

## PLUS
si quisieramos correr dos contenedores solo hace falta agregarlo al docker compose de la siguiente manera:
```plain
version: '3'
services:
  web:
    image: tomcat:8.0.47
    ports:
      - "8081:8080"
  web2:
    image: tomcat:8.0.47
    ports:
      - "8080:8080"      
```
con este docker-compose tendriamos dos tomcats corriendo en puertos diferentes, uno en el 8080 y otro en el 8081

- [docker-compose](https://github.com/Afelipe1599/TomcatDocker/tree/main/Docker/docker-compose.yml)
- [Dockerfile](https://github.com/Afelipe1599/TomcatDocker/tree/main/Docker/Dockerfile)








