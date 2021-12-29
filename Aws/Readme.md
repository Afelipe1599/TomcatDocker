![aws.png](../Images/aws.png)

# Subiendo nuestro contenedor a ECR
Para comenzar a utilizar nuestras propias imagenes en AWS lo primero que tenemos que hacer es subirla a ECR, este servicio es el que nos ofrece amazon para subir nuestras propias imagenes a un repositorio publica o privado con el cual podemos disponer para utilizarlas en AWS.

1. Crear repositorio.
![aws1.png](../Images/aws1.png)
2. Escoger un nombre y si va a ser publico o privado.
![aws2.PNG](../Images/aws2.PNG)
![aws3.PNG](../Images/aws3.PNG)
![aws4.PNG](../Images/aws4.PNG)
3. Acontinuacion subiremos nuestra imagen al repositorio dandole click en view push comands.
![aws5.png](../Images/aws5.png)
4. Ejecutamos los comandos que se muestran.
![aws6.PNG](../Images/aws6.PNG)
5. Subimos nuestra imagen.
![aws7.PNG](../Images/aws7.PNG)

# Desplegar nuestro contenedor en ECS con EC2

1. Crear cluster de ECS.
![EC21.png.png](../Images/EC21.png.png)
