Ejemplo modelo OSI

1.¿Qué niveles OSI son los niveles de soporte de red?

-Físicos, enlaces y redes.

2.¿Qué niveles OSI son los niveles de soporte de usuario?

-Sesión, presentación y aplicación.

3.¿Cómo están OSI e ISO relacionadas entre sí?

-Porque ISO es la organización de estándares que creó el modelo de interconexión de OSI.

4.Enumere los niveles del modelo OSI.

-Nivel 1: Física
-Nivel 2: Enlace de datos
-Nivel 3: Red
-Nivel 4: Transporte
-Nivel 5: Sesión
-Nivel 6: Presentación
-Nivel 7: Aplicación

5.¿Cómo pasa la información de un nivel OSI al siguiente?

-Cuando el proceso emisor envía datos al proceso receptor, entrega los datos a la capa de aplicación, donde se añade la cabecera de aplicación en la parte delantera de los datos, que se entrega a la capa de presentación, y de esta manera se prosigue hasta la capa física.

6.¿Qué son las cabeceras y cola y cómo se añaden y se quitan?

-Las cabeceras se añaden en la máquina emisora en los niveles, 6 , 5 , 4, 3, 2, y en el nivel 2 se añade una cola. Se quitan en la máquina receptora al pasar nivel por nivel, cada nivel procesa y elimina los datos que son para él.

7.¿Cuáles son las responsabilidades del nivel físico?

-El nivel físico proporciona los medios mecánicos, eléctricos, funcionales y procedimentales para activar, mantener y desactivar conexiones físicas para la transmisión de bits entre entidades de enlace de datos.

8.¿Cuáles son las responsabilidades del nivel de enlace?

-El nivel de enlace de datos detecta y corrige los errores que ocurren en el nivel físico, y así proporciona una línea libre de errores de transmisión al nivel de red. Para ello trocea los datos de entrada en tramas de datos, los transmite secuencialmente, y procesa las tramas reconocidas.
                   
9.¿Cuáles son las responsabilidades del nivel de red?

-El nivel de red se ocupa de encaminar los datos hacia su destino estableciendo el camino de transmisión. Este nivel elige la ruta más adecuada para que los paquetes, bloques de datos en los que el nivel de red divide los mensajes, lleguen a su destino.

10.¿Cuáles son las responsabilidades del nivel de transporte?

-El nivel de transporte o capa de transporte es el cuarto nivel del modelo OSI, y está encargado de la transferencia libre de errores de los datos entre el emisor y el receptor, aunque no estén directamente conectados, así como de mantener el flujo de la red.
               
11.El nivel de transporte crea una conexión entre el origen y el destino. ¿Cuáles son los tres eventos involucrados en la conexión?

-Los tres niveles de transporte son: el establecimiento de la conexión, transferencia de datos y liberación de la conexión.
     
12.¿Cuál es la diferencia entre una dirección de punto en servicio, una dirección lógica y una dirección física?

-La diferencia fundamental entre la dirección lógica y la dirección física es que la dirección lógica es generada por la CPU durante la ejecución de un programa mientras que la dirección física se refiere a una ubicación en la unidad de memoria.
               
13.¿Cuáles son las responsabilidades del nivel de sesión?

-El nivel de sesión o capa de sesión es el quinto nivel del modelo OSI, que proporciona los mecanismos para controlar el diálogo entre las aplicaciones de los sistemas finales. En muchos casos, los servicios de la capa de sesión son parcialmente, o incluso, totalmente prescindibles.
     
14.¿Cuáles son las responsabilidades del nivel de presentación?

-El nivel de presentación o capa de presentación es el sexto nivel del Modelo OSI,y es el que se encarga de la representación de la información, de manera que aunque distintos equipos puedan tener diferentes representaciones internas.
              
15.¿Cuál es el objetivo de la traducción en el nivel de presentación?

-La capa de presentación es la que ve el usuario también se la denomina capa de usuario, presenta el sistema al usuario, le comunica la información y captura la información del usuario en un mínimo proceso.

16.Indique alguno de los servicios proporcionados por el nivel de aplicación.

-Correo electrónico, control de seguridad, transferencia de ficheros, emulación de terminales y carga de programas a través de líneas de comunicaciones.
               
17.¿Cómo se relacionan los niveles de la familia del protocolo TCP/IP con los niveles del modelo OSI?

-El modelo OSI describe las comunicaciones de red ideales con una familia de protocolos. TCP/IP no se corresponde directamente con este modelo. TCP/IP combina varias capas OSI en una única capa, o no utiliza determinadas capas. La tabla siguiente muestra las capas de la implementación de Oracle Solaris de TCP/IP.

18.El nivel sesión decide la localización de los puntos de sincronización.

19.En el nivel enlace de datos, la unidad de datos se denomina trama.

20.Los servicios de correos y de directorios están disponibles a los usuarios de la red a través del nivel: Aplicaciones.

21.A medida que los paquetes de datos se mueven de los niveles inferiores a los superiores las cabeceras: Añadidas.






Estefan MAchado Quintero 1ºASIR
