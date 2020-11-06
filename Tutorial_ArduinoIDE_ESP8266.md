# Tutorial instalacion ARduinoIDE para trabajar con el chip Esp8266 (contenido en Wemos)

## Que es un ESP8266?
El microcontrolador ESP8266 (*Micro Control Unit MCU*) es una especie de mini computador, que contiene una unidad de Wifi, capacidades de microcontrolador, un LED y otras cosas.


![ESP8266](/Images/ESP8266.jpg)
***

## ESP86 y placas que lo contienen como NodeMCU y Wemos D1 mini
El ESP8266 se puede encontrar en el mercado acoplado a diferentes placas (boards) como por ejemplo: NodeMCU, wemos d1 mini y una infinidad de otros.

por ejemplo en NodeMCU se puede observar que el microcontrolador ESP8266 viene incluido.

![NODEMCU](/Images/NodeMCU.png)



Este tutorial esta basado en el Uso de Wemos D1 mini, que al igual que NodeMCU, trae incluido el ESP8266.

![wemos](/Images/wemos_d1_mini.png)

Wemos D1 mini se puede conectar por medio de un adaptador directamente a un puerto USB en el computador.

**Atencion**: ESP8266 trabaja en base a 3,3 Volts. Normalmente una coneccion USB libera alrededor de 5v. Para solucionar esto Wemos D1 mini contiene un adaptador de voltaje, de modo que al conectar Wemos por cable USB todo funciona sin problemas.
***


***
## Seleccionando un ambiente de desarrollo para programar y compilar tu ESP8266

Te recomiendo iniciar tu proceso con el ambiente de desarrollo de arduino **Arduino Integrated DEvelopment Environment (Arduino IDE)**. Este ambiente se utiliza para cargar programas en el controlador *Arduino*. Sin embargo, con algunos cambios se puede adaptar para trabajar sin problemas con el ESpP8266 (contenido en WEMOS).


Lo primero que debes hacer es descargar arduino desde [Download here](https://www.arduino.cc/en/main/software).

![](/Images/Download_Arduino.png)

Una vez que este descargado, instala el archivo **-exe** y sigue las instrucciones.


**OPCIONAL** el desarrollo también se podría realizar con una alternativa de *Arduino IDE* llamada *PlatformIO*
