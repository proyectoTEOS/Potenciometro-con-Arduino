# Potenciometro con Arduino
Obtendremos los valores dados por un potenciómetro con Arduino.

### Requisitos
- Tener el IDE de [Arduino](https://www.arduino.cc/en/Main/Software) (o el de tu preferencia) con la versión más actual
- Tener el material para hacer el proyecto

### Código
**[Aqui](https://github.com/proyectoTEOS/Potenciometro-con-Arduino/blob/master/Potenciometro-con-Arduino.ino)** podrás obtener el link del código, también dejaremos
una vista previa aquí abajo.

```c++
/*
  Created by TEOS
  Domotic with Arduino https://goo.gl/btZpjs
  YouTube https://goo.gl/k7TUSZ
  Instagram https://goo.gl/zEIjia
  Facebook https://goo.gl/eivraR
  Twitter https://goo.gl/du5Wgn
  Github https://goo.gl/Xl5IiS
  Google Plus https://goo.gl/gBnUdh
  WEB https://www.proyecto-teos.com/
*/
const uint8_t potPinT = A0;
uint16_t valuepotT;

void setup() {
  Serial.begin(9600);
}

void loop() {
  char* toCharT = "", messageT = "%s";
  char resultSerialT[3] = "";

  valuepotT = analogRead(potPinT);
  valuepotT = map(valuepotT, 0, 1023, 0, 100);
  valuepotT = constrain(valuepotT, 0, 100);
  dtostrf(valuepotT, 3, 0, toCharT);
  sprintf(resultSerialT, messageT, toCharT);

  Serial.println(resultSerialT);
  delay(1000);
}

```

### Diagrama
El siguiente esquemático muestra como se debe conectar todos los componentes con la placa.
![](https://github.com/proyectoTEOS/Potenciometro-con-Arduino/blob/master/Potenciometro-con-Arduino.jpg)
