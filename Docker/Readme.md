
![docker.png](../Images/docker.png)


Acontinuacion definiremos en que consiste el Dockerfile y el docker compose

# ¿Que es el Dockerfile?

Un Dockerfile es un archivo de texto plano que contiene una serie de instrucciones necesarias para crear una imagen que, posteriormente, se convertirá en una sola aplicación utilizada para un determinado propósito. Por lo tanto con una imagen construida, podemos correr un contenedor.


# Elementos de un Dockerfile
-  ## FROM
 	Indica la imagen base sobre la que se construirá la aplicación dentro del contenedo    
```plain
FROM tomcat:8.0.47 
```
-  ## MAINTAINER
	Indica el nombre del autor del dockerfile
```plain
MAINTAINER Andres Valencia "avalencia@gmail.com"
```  
-  ## EXPOSE
	Indica los puertos TCP/IP los cuales se pueden accede a los servicios del contenedor
```plain
EXPOSE 8080
```    
-  ## WORKDIR
	Indica el directorio de trabajo dentro del contenedor
```plain
WORKDIR ruta/de/Proyecto
```  
-  ## COPY o ADD
	Copia un archivo del directorio local a la imagen que se esta construyendo
```plain
COPY ./ejemplo.war /usr/local/tomcat/webapps/
ADD ./ejemplo.war /usr/local/tomcat/webapps/ejemplo.war
```  
-  ## RUN
	Nos permite ejecutar comandos en el contenedor, por ejemplo, instalar paquetes o librerías
```plain
RUN apt-get update
```    
-  ## CMD
	Establece el commando del proceso de inicio del contenedor
```plain
CMD ["catalina.sh","run"]
```      
# Crear y ejecutar un Dockerfile
Perfecto, con los elementos anteriores podemos crear un docker file, como ejemplo tomaremos el siguiente:

```plain
#Imagen que se va a ejecutar
FROM tomcat:8.0.47

#Puerto por donde va a escuchar
EXPOSE 8080

#Comando de inicio
CMD ["catalina.sh","run"]
```     
  



