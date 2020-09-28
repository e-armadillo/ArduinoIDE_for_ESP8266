# Tutorial para tu primer encedido/apagado de LED en el micro-controlador ESP8266

## Que es un ESP8266?
El microcontrolador ESP8266 (*Micro Control Unit MCU*) es una especie de mini computador, que contiene una unidad de Wifi, capacidades de microcontrolador, un LED y otras cosas.


![ESP8266](/images/ESP8266.jpg)
***

## ESP86 y placas que lo contienen como NodeMCU y Wemos D1 mini
El ESP8266 se puede encontrar en el mercado acoplado a diferentes placas (boards) como por ejemplo: NodeMCU, wemos d1 mini y una infinidad de otros.

por ejemplo en NodeMCU se puede observar que el microcontrolador ESP8266 viene incluido.

![NODEMCU](/images/NodeMCU.png)



Este tutorial esta basado en el Uso de Wemos D1 mini, que al igual que NodeMCU, trae incluido el ESP8266.

![wemos](/images/wemos_d1_mini.png)

Wemos D1 mini se puede conectar por medio de un adaptador directamente a un puerto USB en el computador.

**Atencion**: ESP8266 trabaja en base a 3,3 Volts. Normalmente una coneccion USB libera alrededor de 5v. Para solucionar esto Wemos D1 mini contiene un adaptador de voltaje, de modo que al conectar Wemos por cable USB todo funciona sin problemas.
***
## Installing the drive CH340 for recognition of the Wemos

After conecting Wemos to your computer you will need to download a driver. Which will allow your computer to recognize WEMOS as a device. For that purpose go to the [documentation of WEmos](https://docs.wemos.cc/en/latest/d1/d1_mini.html) and scroll down and in the section **Documentation** click on the link CH340 Driver like in the image 

![](/images/Wemos_Driver_CH340.png)

after downloading install it.

***
## Selecting an Environment to code , compile and load to the ESP8266

For running your fisrt led blinking on the WEMOS, it is recommended to work with an **Arduino Integrated DEvelopment Environment (Arduino IDE)**. Which is used to write an upload programs to *Arduino*. Although with some changes it allows us to write code, compile and charge on ESP8266 (contained in WEMOS).


First of all you need to download Arduino IDE from [Download here](https://www.arduino.cc/en/main/software).

![](/Images/Download_Arduino.png)

after the download, install the file **.exe** and follow instructions.

**OPTIONAL** you can try another IDE environment like *PlatformIO*

***
## Runing your first LED blinking 

Once you downloaded the environment Arduino IDE you can follow the next short [youtube tutorial](https://www.youtube.com/watch?v=2DL8FlrBTDs).

**NOTE:** Until now you have been able to run a led blinking on your device. Notwithstanding the code was loaded via USB-cable. In the next tutorial you will be able to load your code from the computer to your Wemos without any USB-cable. This is called **Over The Air (OTA)** and will be enorm usefull when your Wemos is for example into a case and you cannot access to it very easily.
***

## Cargando tu codigo a ESP8266 via OTA

para cargar el codigo sigue el siguiente [tutorial](http://www.sinaptec.alomar.com.ar/2017/10/tutorial-21-esp8266-ota-carga-tu-sketch.html?fbclid=IwAR0veX9cDm_ICz-lFepof7djdhEdTSH_44nynMQP-5e70gGXCdlnqqYAB-4)

puedes descargar el codigo de la misma pagina.