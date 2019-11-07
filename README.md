# 3en1 (aka Terremoto) Robot de combate

## Introducción
**3en1** (aka Terremoto) es un robot de combate dirigido por control remoto de categoría de 1 libra creado para competir en la [OSHWDEM](https://oshwdem.org) 2018. Tras un año ha sido re-habilitado para volver a competir en la edición 2019.

Los diseñadores y constructores del robot son:
- Benjamin García Aguilar
- Daniel López García

## Especificaciones
**3en1** es un robot de tipo **spinner**, es decir, su arma principal es una masa giratoria. En este caso se trata de un disco que ha sido cortado de forma que tenga una muesca con la que golpear.
El robot puede moverse adelante y atrás y todas las curvas posibles hasta girar sobre si mismo.
Tanto el movimiento como el arma son manejados por control remoto desde una emisora de radio-control.
>Gracias al diseño del mismo, permite también que en caso de vuelco se pueda manejar boca abajo de forma sencilla activando una palanca de la emisora.

## Componentes
A continuación detallo los materiales y componentes que fueron necesarios para su construcción:

- 1 plancha de aluminio de 1mm de grosor.
- 2 [motores DC]([https://tienda.bricogeek.com/motores/220-motor-micro-metal-dc-con-reductora-298-1.html?search_query=Micro+Metal&results=35](https://tienda.bricogeek.com/motores/220-motor-micro-metal-dc-con-reductora-298-1.html?search_query=Micro+Metal&results=35)) tipo "micro metal".
- 2 [ruedas de gomaespuma](https://www.ebay.com/sch/i.html?_nkw=Racing+Foam+Tires+Wheel+Rims+4Pcs+Set+For+HSP+HPI+1%2F10+On-road+RC+Car+12mm+Hex) de 68mm de diámetro.
- 2 [acoples hexagonales](https://www.ebay.com/itm/2x-3mm-Flexible-Motor-Brass-Shaft-Hex-Coupling-Coupler-w-wrench-for-Tyre-Wheel/253223731688?ssPageName=STRK%3AMEBIDX%3AIT&_trksid=p2057872.m2749.l2649) para eje de 3mm.
- 2 ESC para motores DC con marcha reversible de 10A.
- 1 motor brushless RCX 1804 2400kv.
- 1 ESC para motor Brushless.
- 1 disco de corte de madera.
- 1 batería LiPO 3S 600mAh.
- Tornillería M3, M2 y espaciadores.
- 1 Emisora Flysky FS-TH9X 2.4GHz con emisor y receptor.

![Wheels](/res/wheels.jpg) ![Acoples](/res/acoples.jpg) ![Motors](/res/motors.jpg)

## Diseño
Idealmente cuando se diseña un aparato de este tipo se utiliza un programa de modelado por ordenador con el que poder jugar con dimensiones y formas sin necesitar utilizar ningún material y teniendo total libertad de creación. 

Nosotros no teníamos los conocimientos para ello por lo que, en su lugar, hicimos directamente un prototipo en cartón, material con el que se puede experimentar rapidamente hasta encontrar las dimensiones y forma adecuadas. El diseño estuvo condicionado por la posesión de algunos componentes reciclados de otros robots, drones, etc. Dado que teníamos un motor brushless con su ESC pensamos que un spinner era lo que más se adecuaba. También queríamos que el robot fuese reversible y que las ruedas estuviesen protegidas por la carrocería por lo que dimos con un diseño en forma de sandwich (de ahí el nombre de 3en1). 

La tapa superior e inferior cerrarían la carrocería y tendrían huecos para que las ruedas sobresaliesen y tuviesen tracción. En la lamina interior irían sujetos los motores y a su vez el eje de las ruedas. Las tres láminas irían unidas por tornillos pero manteniendo la distancia necesaria entre ellos mendiante unos separadores.

El arma, asomaría por la parte frontal y se situaría verticalmente hacia el centro del robot. Para ello, el motor que la sujerará deberá estar sujeto por su base sobre una de las dos tapas exteriores.
Dicha arma fue re-utilizada de un difunto robot anterior, y se trata de un disco de corte de madera. Queríamos que esta vez, en lugar de cortar, golpease al oponente con la esperanza de inutilizarlo. 

## Construcción

### Carrocería
Dibujamos las láminas de cartón sobre una plancha de aluminio y lo cortamos utilizando una sierra de calar y unas tijeras de corte de chapa en algúnos puntos complicados. 
> Importante limar todos los bordes para no cortarse las manos montando el robot después.

![Sandwich](/res/sandwich.jpg)

### Arma
Pegamos un papel sobre el disco y dibujamos sobre el una curva que iba alejándose cada vez más del borde del disco hasta que llegaba a una distancia de un centimetro. En ese punto sería el punto de golpeo donde el corte vuelve bruscamente hasta el borde.
Logicamente al hacer esto el disco queda desbalanceado, y hacerlo girar sobre su eje produciría muchas vibraciones. Para minimizarlas (eliminarlas completamente ha sido imposible), lo hicimos girar sobre su eje en posición vertical. El punto hacia el que cae bruscamente y sobre el que finalmente se estabiliza es el que tiene más peso y por lo tanto del que debemos quitar. Para ello hicimos muchos, muchos agujeros con el taladro re-balanceando el disco cada vez y haciendo agujeros cada vez más pequeños.

### Electrónica
La electrónica se basa en un receptor de emisora que se encarga de mandar órdenes a los 3 ESCs que son los encargados de traducir las órdenes en [PWM](https://en.wikipedia.org/wiki/Pulse-width_modulation) que recibe de la emisora a los cambios de tensión necesarios para mover los motores como el piloto ordena. Los 3 ESCs, dado que son capaces de funcionar a 12V se alimentan directamente con la batería (hacíendolos pasar antes por un interruptor que permita el apagado inmediato). El receptor de la emisora sin embargo funciona a 5V por lo que debemos usar uno de los BEC incorporados en cualquiera de los tres ESCs para alimentarlo.

![Electronica](/res/electronica3en1.jpg)
![Wiring](/res/wiring.jpg)

### Configuración
Antes de empezar a poner todo junto es hora de configurar la emisora. Podríamos asociar cada uno de los 3 canales a una palanca o control de la emisora, pero manejar el robot iba a se algo complejo. Finalmente decidomos que lo más sencillo era utilizar el sitch derecho (que por defecto se mantiene en el centro) para controlar el movimiento como si manejásemos un tanque.
El stick izquierdo, que mantiene la posición lo usaremos solo en su eje vertical para controlar la velocidad de giro del arma.
Además tendremos dos interruptores con funciones extra: uno para inutilizar el robot y otro para que en el caso de que nos vuelquen y tengamos que manejarlo al revés, el stick derecho se invierta y nos sea más sencillo.
![emisora](/res/emisora.jpg)
![mixer1](/res/mixer1.jpg)
![mixer2](/res/mixer2.jpg)

### Montaje
Parece lo más simple, pero encajar todas estas piezas en un espacio tan pequeño lleva tiempo. Acortar los cables que incialmente se dejan muy largos o hacer recortes y modificaciones de última hora en el chasis son cosas que están aseguradas.
![top](/res/top.jpg)
![bottom](/res/bottom.jpg)
![front](/res/front.jpg)
![back](/res/back.jpg)
![weight](/res/weight.jpg)