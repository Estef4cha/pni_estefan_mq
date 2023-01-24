1. Identificar el puerto raíz.

El puerto raíz es el SW02   

![](1.png)

2. Identificar los puertos no designados y en que switch se encuentran.

En el SW01:

![](2.png)

En el SW03:

![](3.png)

En el SW05:

![](4.png)

3. Comprobar que ya no existen bucles en nuestra red.

Como se ve en la imagen el protocolo STP ha configurado los puertos de forma que no hay bucles lógicos.

![](5.png)

4. Comprobar que existe un camino único entre cada par de switches.

Entre SW01-SW03:

![](6.png)

Entre SW01-SW04:

![](7.png)

Y así todos los caminos siguientes:

![](5.png)

5. Hacer pruebas de conectividad entre todos los equipos de la red.

![](8.png)

![](9.png)

![](10.png)

![](11.png)