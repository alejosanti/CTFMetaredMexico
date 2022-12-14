# Sniffer Man
Network, 100 points

## Description
![](../images/image17.png)

## Solution
Nos dan un archivo con comunicaciones.

Lo abrimos con Wireshark. Primero miramos las comunicaciones por HTTP, pero esto no llevó a ningún resultado. Se podía ver que el servidor brindaba una página con varias fotos, de las que no se veía ningún código o flag encubierta, y lo único interesante era que un botón “Download” referenciaba a flag.txt, pero tampoco pudimos acceder a ese archivo por este medio.

Viendo que la comunicación HTTP no parecía llegar a ningún lado, vimos la comunicación por Telnet:

![](../images/image18.png)

Como se puede ver, luego de “Telnet is insecure” hay un texto que, por la forma, pareciera corresponder a la flag.

Probamos varios decodificadores, y al final encontramos que el ROT-13 +18 genera un string con algo de sentido, se puede ver que comienza con "flagMX":

![](../images/image7.png)

Probamos esa flag y no es correcta.

El ROT que aplicamos solo es con el alfabeto \[A-Z\], por lo que interpretamos que faltó hacer la rotación de números.

Se puede identificar que el texto quiere decir “Man in the middle attack”, por lo que manualmente cambiamos por los números que generarían el mensaje, es decir, corriendo cada número 2 lugares:

```
2 → 4
9 → 1
1 → 3
```

Dando como resultado: flagMX{M4n_1n_Th3_M1ddl3_4tt4ck}

Reto resuelto.

![](../images/image2.png)