## Blinking led por transmisión inalámbrica u Over The Air (OTA).

Ahora que tu ESP8266 contiene el programa transferido puedes desconectar el cable USB. Conéctalo a una fuente de poder con salida USB (Por ejemplo una PowerBank)

1. Ve a tu Arduino IDE > Tools > Port y selecciona la opcion esp8266-d77c at 192.168.1.105. Considera que la denominacion puede variar un poco debido a tu numero IP. Pero Sólo se trata de desmarcar el COM8 y establecer la ruta IP como medio deseado de transferencia.

![](/images/Tut3_Paso2.PNG)

2. Copia el siguiente codigo en tu Arduino IDE, ingresa tu SSID y tu Password.


```
/*********
  Franco Perez
  trabajo en base a codigo de Rui Santos. 
  Description on https://randomnerdtutorials.com/esp8266-ota-updates-with-arduino-ide-over-the-air/
  
*********/

#include <ESP8266WiFi.h>
#include <ESP8266mDNS.h>
#include <WiFiUdp.h>
#include <ArduinoOTA.h>

// Replace with your network credentials
const char* ssid = "SSID";
const char* password = "Contraseña";

const int ESP_BUILTIN_LED = 2;

void setup() {
  Serial.begin(115200);
  Serial.println("Booting");
  WiFi.mode(WIFI_STA);
  WiFi.begin(ssid, password);
  while (WiFi.waitForConnectResult() != WL_CONNECTED) {
    Serial.println("Connection Failed! Rebooting...");
    delay(5000);
    ESP.restart();
  }

  // Port defaults to 8266
  // ArduinoOTA.setPort(8266);

  // Hostname defaults to esp8266-[ChipID]
  // ArduinoOTA.setHostname("myesp8266");

  // No authentication by default
  // ArduinoOTA.setPassword((const char *)"123");

  ArduinoOTA.onStart([]() {
    Serial.println("Start");
  });
  ArduinoOTA.onEnd([]() {
    Serial.println("\nEnd");
  });
  ArduinoOTA.onProgress([](unsigned int progress, unsigned int total) {
    Serial.printf("Progress: %u%%\r", (progress / (total / 100)));
  });
  ArduinoOTA.onError([](ota_error_t error) {
    Serial.printf("Error[%u]: ", error);
    if (error == OTA_AUTH_ERROR) Serial.println("Auth Failed");
    else if (error == OTA_BEGIN_ERROR) Serial.println("Begin Failed");
    else if (error == OTA_CONNECT_ERROR) Serial.println("Connect Failed");
    else if (error == OTA_RECEIVE_ERROR) Serial.println("Receive Failed");
    else if (error == OTA_END_ERROR) Serial.println("End Failed");
  });
  ArduinoOTA.begin();
  Serial.println("Ready");
  Serial.print("IP address: ");
  Serial.println(WiFi.localIP());
  pinMode(ESP_BUILTIN_LED, OUTPUT);
}

void loop() {
  ArduinoOTA.handle();
  digitalWrite(ESP_BUILTIN_LED, LOW);
  delay(3000);
  digitalWrite(ESP_BUILTIN_LED, HIGH);
  delay(3000);
}

```

3. Hay click en "Upload" y espera el mensaje de "Done Uploading" en la ventana negra.

4. Ahora tu LED debería prender durante 3 segundos y apagarse durante 3 segundos.