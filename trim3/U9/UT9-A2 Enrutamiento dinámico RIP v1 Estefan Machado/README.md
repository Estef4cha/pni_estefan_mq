# ENRUTAMIENTO DINÁMICO RIP V1

Dada la siguiente topología de red:

![](img/001.png)

1. Crear el siguiente esquema de red usando el ***Packet Tracert***. Configurar las interfaces de cada router y asignarle una dirección `IP` por cada interfaz.

+ R1

 ~~~
Router(config)#interface fastEthernet 0/0
Router(config-if)#ip address 192.168.1.1 255.255.255.0
Router(config-if)#no shutdown
Router(config-if)#exit
Router(config)#interface serial 0/0/0
Router(config-if)#ip address 192.168.2.1 255.255.255.0
Router(config-if)#no shutdown
 ~~~

+ R2

 ~~~
Router(config)#interface serial 0/0/0
Router(config-if)#ip address 192.168.2.1 255.255.255.0
Router(config-if)#no shutdown
Router(config-if)#exit
Router(config)#interface fastEthernet 0/0
Router(config-if)#ip address 192.168.3.1 255.255.255.0
Router(config-if)#no shutdown
Router(config-if)#exit
Router(config)#interface serial 0/0/1
Router(config-if)#ip address 192.168.4.1 255.255.255.0
Router(config-if)#no shutdown
 ~~~
 
 + R3
 
 ~~~
Router(config)#interface serial 0/0/0
Router(config-if)#ip address 192.168.4.1 255.255.255.0
Router(config-if)#no shutdown
Router(config-if)#exit
Router(config)#interface fastEthernet 0/0
Router(config-if)#ip address 192.168.5.1 255.255.255.0
Router(config-if)#no shutdown
Router(config-if)#exit
Router(config)#interface serial 0/0/1
Router(config-if)#ip address 192.168.6.1 255.255.255.0
Router(config-if)#no shutdown
 ~~~
 
 + R4
 
 ~~~
Router(config)#interface serial 0/0/0
Router(config-if)#ip address 192.168.6.1 255.255.255.0
Router(config-if)#no shutdown
Router(config-if)#exit
Router(config)#interface fastEthernet 0/0
Router(config-if)#ip address 192.168.7.1 255.255.255.0
Router(config-if)#no shutdown
Router(config-if)#exit
Router(config)#interface serial 0/0/1
Router(config-if)#ip address 192.168.8.1 255.255.255.0
Router(config-if)#no shutdown
 ~~~
 
 + R5
 
 ~~~
Router(config)#interface serial 0/0/0
Router(config-if)#ip address 192.168.8.1 255.255.255.0
Router(config-if)#no shutdown
Router(config-if)#exit
Router(config)#interface fastEthernet 0/0
Router(config-if)#ip address 192.168.9.1 255.255.255.0
Router(config-if)#no shutdown
 ~~~

2. Activar el protocolo `RIP` en cada uno de los routers de la figura de arriba.

+ R1

 ~~~
Router(config)#router rip
 ~~~

+ R2

 ~~~
Router(config)#router rip
 ~~~
 
 + R3
 
 ~~~
Router(config)#router rip 
 ~~~
 
 + R4
 
 ~~~
Router(config)#router rip 
 ~~~
 
 + R5
 
 ~~~
Router(config)#router rip 
 ~~~

3. Publicar las redes con el protocolo `RIP` en cada una de los routers. 

+ R1

 ~~~
Router(config-router)#network 192.168.2.0
Router(config-router)#network 192.168.1.0
 ~~~

+ R2

 ~~~
Router(config-router)#network 192.168.2.0
Router(config-router)#network 192.168.3.0
Router(config-router)#network 192.168.4.0
 ~~~
 
+  R3

 ~~~
Router(config-router)#network 192.168.4.0
Router(config-router)#network 192.168.5.0
Router(config-router)#network 192.168.6.0
 ~~~
 
 + R4
 
 ~~~
Router(config-router)#network 192.168.6.0
Router(config-router)#network 192.168.7.0
Router(config-router)#network 192.168.8.0
 ~~~
 
 + R5
 
 ~~~
Router(config-router)#network 192.168.8.0
Router(config-router)#network 192.168.9.0 
 ~~~

5. Muestra la tabla de enrutamiento del router **R3** para verificar si ha "aprendido" las redes de sus vecinos.

 + R3
 
 ~~~
Router#show ip route
Codes: C - connected, S - static, I - IGRP, R - RIP, M - mobile, B - BGP
       D - EIGRP, EX - EIGRP external, O - OSPF, IA - OSPF inter area
       N1 - OSPF NSSA external type 1, N2 - OSPF NSSA external type 2
       E1 - OSPF external type 1, E2 - OSPF external type 2, E - EGP
       i - IS-IS, L1 - IS-IS level-1, L2 - IS-IS level-2, ia - IS-IS inter area
       * - candidate default, U - per-user static route, o - ODR
       P - periodic downloaded static route

Gateway of last resort is not set

C    192.168.4.0/24 is directly connected, Serial0/0/0
C    192.168.6.0/24 is directly connected, Serial0/0/1
 ~~~

 + Comprobar si la distancia a las redes se corresponde con la métrica. Considerando que en `RIP` la métrica es el número de saltos. Por ejemplo la red `192.168.8.0/24` debe tener métrica 2.
 + ¿Cual es la distancia administrativa de las redes aprendidas por `RIP`?

 + R3
 
 ~~~
 
 ~~~

6. Activar el modo de depuración en el router R2.

 + R2
 
 ~~~
Router#debug ip rip
RIP protocol debugging is on
Router#RIP: sending  v1 update to 255.255.255.255 via Serial0/0/0 (192.168.2.1)
RIP: build update entries
      network 192.168.4.0 metric 1
RIP: sending  v1 update to 255.255.255.255 via Serial0/0/1 (192.168.4.1)
RIP: build update entries
      network 192.168.2.0 metric 1
 ~~~

+ ¿Cuáles son las rutas enviadas por R2 a R1?

~~~
Router#RIP: sending  v1 update to 255.255.255.255 via Serial0/0/0 (192.168.2.1)
~~~

+ ¿Cuáles son las rutas recibidas en R2 por parte de R3?

~~~
RIP: sending  v1 update to 255.255.255.255 via Serial0/0/1 (192.168.4.1)
~~~

+ Razonar, analizando los apartados a y b, si funciona el horizonte dividido.

~~~

~~~

7. Como se observa en el esquema de red, por la parte de la red Ethernet no hay ningún router, por tanto, se quiere evitar que el router no mande tráfico `RIP` por esa interfaz, ¿Qué se debe de hacer?

 + R1
 
 ~~~

 ~~~

+ R2

 ~~~

 ~~~
 
 + R3
 
 ~~~

 ~~~
 
 + R4
 
 ~~~

 ~~~
 
 + R5
 
 ~~~
 
 ~~~

8. Usando `show ip protocolos` en el router R2 y contestar a las siguientes preguntas:

+ ¿ Qué versión se está enviando?

~~~
~~~

+ ¿ Qué versión se acepta?

~~~
~~~

+ ¿ Cada cuanto tiempo se envían las tablas de rutas ?

~~~
~~~

+ ¿ Qué redes están siendo publicadas por el `RIP` ?

~~~
~~~

+ ¿ Qué vecinos le están mandando información de enrutamiento?

~~~
~~~




