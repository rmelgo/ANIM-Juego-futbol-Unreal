# Juego de fútbol diseñado en Unreal

![Inicial](https://github.com/rmelgo/ANIM-Juego-futbol-Unreal/assets/145989723/691de0b5-49c5-47a3-8a74-c31ce08c9c6d)

# - Introducción

Proyecto realizado en la asignatura de Animación Digital del grado de Ingenieria Informática de la Universidad de Salamanca. El enunciado del proyecto se encuentra subido en el repositorio en un archivo PDF llamado <a href="https://github.com/rmelgo/ANIM-Juego-plataformas-Unity/blob/main/Enunciado%20Unity.pdf" target="_blank">*Enunciado Practica Unreal.pdf*</a>.

El principal objetivo de este proyecto es la realización de un juego en Unreal que cumpla una serie de requisitos básicos como:
- Manejo de diferentes mallas estáticas.
- Uso de Blueprints propios para el desarrollo de la lógica del juego.
- Importación de personajes y animaciones y su configuración (al menos animaciones básicas).
- Desarrollo de un menú simple para el juego y un HUD en alguno de los niveles.
- Uso de sonidos y de físicas.
- Gestión de eventos colisiones y lógica asociada a ellos para el desarrollo del gameplay del juego.
- Mallas de navegación y enemigos controlados con una IA básica.
- Sistemas de partículas.

De esta manera, se utilizán las distintos conocimientos sobre Unreal junto con el apoyo de varios assets gratuitos de la tienda de Unreal que permitan diseñar las plataformas, la infraestructura, el balón, la portería, el diseño del personaje, etc.

# - Comentarios sobre el entorno de ejecución

Para ejecutar este programa, se requerirá de una distribución del Sistema Operativo **Windows**.    

Esto se debe a que el entorno de Unreal funciona sobre Windows, además de que los ejecutables generados sólo pueden ejecutarse en Windows.

Para desarrollar el juego se ha utilizado la versión *4.27.2* de Unreal.

# Comentarios sobre el material adjuntado

El proyecto cuenta con los siguientes ficheros:

- Una carpeta llamada **Scripts** que contiene los scripts necesarios que realizan diferentes funcionalidades del juego como el moviemiento del personaje, el movimiento de los obstaculos, la gestión de la camara, etc.
  
  - Incluye un fichero ejecutable **Trabajo Unity.exe** en el cual se puede ejecutar el juego directamente.
  
- Un documento llamado **Trabajo_Unreal.pdf** en el que se describe detalladamente el proceso de construcción del juego adjuntado capturas, código y explicaciones de los distintos pasos realizados en el desarrollo del juego.

Para descargar el **juego completo**, se adjunta el siguiente enlace, ya que es muy pesado para ser subido directamente en GitHub (4.9 GB):

https://drive.google.com/drive/folders/1PYdAgAr5YeVEQKe_FzbJWYPXH64iJrcS?usp=share_link

# - Características del juego

Las características básicas del juego son las siguientes:

- El juego consta de 2 níveles que el personaje debe superar para ganar en el juego.
- Cada nivel cuentan con una serie de obstaculos, plataformas, enemigos, etc que el personaje debe superar para pasar al siguiente nivel.
- El objetivo de cada nivel es superar los distintos obstaculos, plataformas y enemigos con el balon y meter un gol en la portería que se encuentra al final del nivel.
- Existen una serie de rivales de color rojo que van a perseguir a nuestro personaje, siempre y cuando nuestro personaje entre en su rango de visión.
- Cuando los enemigos estan muy cerca de nuestro personaje, realizarán una entrada en segada con el objetivo de quitar vida a nuestro personaje.
- Existen una serie de objetos distribuidos por el mapa que producen distintos efectos sobre el personaje. A continuación se explicarán con mayor detalle.
- Cada vez que el personaje fracase en su intento de superar el nivel, se le colocará de nuevo en la plataforma de inicio del nivel. Existen distintas maneras de fallar en un nivel. A continuación se explicarán con mayor detalle.

## Controles básicos

El personaje cuenta con los siguientes controles básicos:

- Con las flechas del teclado o con las teclas ***W***, ***A***, ***S*** y ***D*** se puede mover al personaje hacia delante, hacia la izquierda, hacia atras y hacia la derecha respectivamente.
- Con la tecla ***espacio***, el personaje puede saltar.
- Con el ***click izquierdo*** de ratón, el personaje puede realizar un pequeño toque de balón para superar a los enemigos y las plataformas. Es imprescible que el persoanje se encuentre cerca del balón para poder realizar esta acción.
- Con el ***click derecho*** de ratón, el personaje puede realizar un disparo o toque largo de balón para superar a los enemigos y las plataformas y marcar gol en la portería. Es imprescible que el persoanje se encuentre cerca del balón para poder realizar esta acción.
- Con la tecla ***P***, el personaje puede simular una falta. Al realizar esta acción, nuestro personaje será sancionado con tarjeta amarilla.
- Con la tecla ***Z***, el personaje realiza su celebración habitual, inclyendo su grito caracteristico (Siuuuh!!).
- Con la tecla ***C***, el personaje realiza un gesto de disconformidad, inclyendo un sonido de negación.
- Con la tecla ***N***, el personaje dice la siguiente frase prepotente:
  
```Si todos estuvieran a mi nivel, estariamos primeros a lo mejor.```

- Con la tecla ***J***, el personaje dice la siguiente frase prepotente:
  
```Desde que estoy en España dime un jugador que haya marcado más goles que yo fuera de casa. Uno.```

- Con la tecla ***G***, el personaje dice la siguiente frase prepotente:
  
```Yo pienso que por ser rico, por ser guapo, por ser buen jugador, las personas tienen envidia de mí. No tiene otra explicación.```

- Con la tecla ***Y***, el personaje dice la siguiente frase prepotente:

```A mi me importa Real Madrid y yo.```

## Objetos del juego

En el juego, existen distintos juegos que el personaje puede recoger:

- **Balón de oro**: Se tratan de objetos coleccionables por el personaje. Cuanto mayor sea el número de balones de oro recogidos por el personaje, mayor será la puntuación final del juego.

  En la esquina superior izquierda, existirá un pequeño contador que irá contabilizando el número de balones de oro recogidos por el personaje.

  Al recoger un balon de oro, se reproduce un efecto de partículas doradas y se reproduce la siguiente frase: 

  ```Cristiano balón de oro```

  <p align="center">
    <img src="https://github.com/rmelgo/ANIM-Juego-futbol-Unreal/assets/145989723/aad5c2ef-9b27-4af3-beb3-191952ac9602">
  </p>

- **Botella de Coca-Cola**: Este objeto quita vida a nuestro personaje, ya que la Coca-Cola no es saludable para nuestro personaje.

  Al recoger una botella de Coca-Cola, se reproduce un efecto de partículas de chispas y se reproduce la siguiente frase: 

  ```Coca-cola```
  
  <p align="center">
    <img src="https://github.com/rmelgo/ANIM-Juego-futbol-Unreal/assets/145989723/943ad280-39df-40fb-a850-cb0495755952">
  </p>

  - **Botella de Agua**: Este objeto suma vida a nuestro personaje, ya que el agua es saludable para nuestro personaje.

  Al recoger una botella de agua, se reproduce un efecto de partículas de agua y se reproduce la siguiente frase: 

  ```Agua``
  
  <p align="center">
    <img src="https://github.com/rmelgo/ANIM-Juego-futbol-Unreal/assets/145989723/6fb2a4da-d4fd-4423-a55b-80cd9c716580">
  </p>

  - **Ferrari**: Este objeto otorga más velocidad de movimiento a nuestro personaje durante unos segundos, ya que el Ferrari es rápido y le gusta mucho a nuestro personaje.

  Al recoger un Ferrari, se reproduce un efecto de partículas de propulsión, se muestra un pequeño icono de x2 en la parte superior indicando que ha aumentado la velocidad del personaje y se reproduce un sonido de Ferrari. 

  <p align="center">
    <img src="https://github.com/rmelgo/ANIM-Juego-futbol-Unreal/assets/145989723/b67dbb9a-fb1e-42e9-b685-01acef0782f2">
  </p>

## Formas de perder en un nivel

En el juego, existen distintas formas en las que el personaje puede fracasar en su intento de superar el nivel:

- **El balón se cae al agua**: El balón se cae de las plataformas y cae al agua. De esta manera, al no existir balón, el personaje no puede conducir el balón a la portería por lo que habrá fracasado en su intento de meter gol.

  ![Perder 1](https://github.com/rmelgo/ANIM-Juego-futbol-Unreal/assets/145989723/904c1bd5-b0c1-4c5b-9a93-6f975b87c357)

- **El personaje se cae al agua**: El personaje se cae de las plataformas y cae al agua. De esta manera, al no existir el personaje, el personaje no puede conducir el balón a la portería por lo que habrá fracasado en su intento de meter gol.

  ![Perder 2](https://github.com/rmelgo/ANIM-Juego-futbol-Unreal/assets/145989723/1b3327c7-221b-4986-ac20-0019e239f83a)

- **El personaje se queda sin vida**: El personaje se queda sin vida o bien por recibir demasiadas entradas o ingerir demasiada Coca-Cola. De esta manera, al haber muerto el personaje, este no puede conducir el balón a la portería por lo que habrá fracasado en su intento de meter gol.

  ![Perder 3](https://github.com/rmelgo/ANIM-Juego-futbol-Unreal/assets/145989723/169788a7-8c9a-4069-acd0-716b25695bc8)

- **Fallo al disparar a la portería**: El personaje dispara a la portería pero no introduce el balón en la misma sino que el balón se va fuera. De esta manera, al haber fallado el disparo y no poder recuperar el balón, el personaje habrá fracasado en su intento de meter gol.

  ![Perder 4](https://github.com/rmelgo/ANIM-Juego-futbol-Unreal/assets/145989723/d5f808cc-b285-4eb2-8d9a-a59a8e982f49)

- **El personaje es expulsado**: El personaje recibe una segunda tarjeta amarilla por haber simulado una falta, lo que supondrá una tarjeta roja y la expulsión del personaje. De esta manera, al haber sido expulsado el personaje, este no puede conducir el balón a la portería por lo que habrá fracasado en su intento de meter gol.

  ![Perder 5](https://github.com/rmelgo/ANIM-Juego-futbol-Unreal/assets/145989723/0180c246-4de8-4234-a0d9-f4ce6939c14a)

- **El personaje se encuentra en fuera de juego**: El personaje no se desplaza a una velocidad adecuada hacia la portería por lo que será cazado por el sistema de juego. De esta manera, al encontrarse en fuera de juego el personaje, este no puede conducir el balón a la portería por lo que habrá fracasado en su intento de meter gol.

  ![Perder 6](https://github.com/rmelgo/ANIM-Juego-futbol-Unreal/assets/145989723/30d0b0cb-d3b6-4fdb-b247-1a0a3a71f078)
 
## Niveles

En el juego, existen 2 niveles, de los cuales se puede destacar lo siguiente:

- **Nivel 1**: Este nivel incorpora 3 plataformas con enemigos rivales a los que el personaje debe superar para meter gol en la portería. Las plataformas incorporan los 4 tipos de objetos antes mencionados.
- **Nivel 2**: Este nivel incorpora 5 plataformas con enemigos rivales a los que el personaje debe superar para meter gol en la portería. Las plataformas incorporan los 4 tipos de objetos antes mencionados.

  Por otra parte existen varios componentes que le dotan de mayor dificultad a este nivel:
    - **Enemigos mas rápidos**: En este nivel los enemigos se desplazan más rapido que en el nivel anterior. Son capaces de correr a la misma velocidad que nuestro personaje.
    - **Sistema de fuera de juego**: En este nivel, existe un plano de color rojo que va a ir barriendo el nivel lentamente. Si dicho plano alcanza y atraviesa al personaje, este se encontrará en fuera de juego y perderá.
    - **Plataformas móviles**: En este nivel, existe una serie de plataformas móviles que el personaje debe superar con el balón. Como la sección que incorpora las plataformas móviles es bastante difícil de superar con el balón a la primera, si el personaje pierde el balón en esta sección, automáticamente se le repondrá otro balón para que siga intentando superar el nivel.
      
# - Ejemplo de ejecución

En el siguiente video, se adjunta una demostración del funcionamiento del juego:

[![Alt text](https://github.com/rmelgo/ANIM-Juego-futbol-Unreal/assets/145989723/e7d5733c-7ac7-4d37-8ba4-f33e6565ed5b)](https://youtu.be/Q2wRhGV-U7k)

**Nota**: Hacer click a la imagen para acceder al video
