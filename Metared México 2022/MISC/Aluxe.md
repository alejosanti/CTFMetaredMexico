# Aluxe
MISC, 100 points

## Description
![](../images/image20.png)

## Solution
Nos brindan un archivo con lo que pareciera ser una comunicación vía mail:

![](../images/image4.png)

Lo curioso es que hay un header llamado x-header-aluxe con mucho contenido, por lo que comprobamos si está codificado:

![](../images/image15.png)

Usando base64, podemos ver que corresponde a una imagen png, por lo que pegamos el texto en una página que nos muestra la imagen:

![](../images/image19.png)

Y la imagen contiene la flag, reto completado.

![](../images/image14.png)