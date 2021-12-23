
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
-  ## EXPOSE
	Indica los puertos TCP/IP los cuales se pueden accede a los servicios del contenedor
```plain
EXPOSE 8080
```    
-  ## COPY
	Copia un archivo del directorio local a la imagen que se esta construyendo
```plain
COPY ./ejemplo.war /usr/local/tomcat/webapps/
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
  



