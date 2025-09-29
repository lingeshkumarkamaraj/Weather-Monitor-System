# Weather Monitor System using Wokwi

###### Designed and simulated a Weather Monitoring System in Wokwi using Arduino, integrating a DHT22 sensor to measure temperature and humidity. A 16x2 LCD display is used to show real-time weather data clearly. A push button is employed as a manual trigger in place of a rain sensor to simulate rainfall detection. This project demonstrates the use of embedded systems for environmental monitoring and user-interactive weather simulation.
---
## Here is the references...

Circuit Connections in TINKERCAD :-

<img src=https://github.com/lingeshkumarkamaraj/Weather-Monitor-System/blob/main/1.png> 
<img src=https://github.com/lingeshkumarkamaraj/Weather-Monitor-System/blob/main/2.png> 
<img src=https://github.com/lingeshkumarkamaraj/Weather-Monitor-System/blob/main/3.png> 
<img src=https://github.com/lingeshkumarkamaraj/Weather-Monitor-System/blob/main/4.png> 
<img src=https://github.com/lingeshkumarkamaraj/Weather-Monitor-System/blob/main/5.png> 

Working :- 

[<img width="300" height="300" src="https://img.icons8.com/color/96/start.png" alt="video"/>](https://youtu.be/WDVr2asdYXU)


---
Code :-
```

#include<LiquidCrystal.h>
#include "DHT.h"
LiquidCrystal lcd(13, 12, 7, 6, 5, 4);
DHT dht(2, DHT22);

void setup() {
  pinMode(3 ,INPUT);
  lcd.begin(16,2);
  dht.begin();
}

void loop() {
  int r;
  float t, h;
  r = digitalRead(3);
  t = dht.readTemperature();
  h = dht.readHumidity();
  if(t >= 35 && h < 40 && r == 0)
  {
    lcd.clear();
    lcd.setCursor(0,0);
    lcd.print("SUMMER");
    lcd.setCursor(0,1);
    lcd.print("T = ");
    lcd.print(t);
    lcd.print(" ");
    lcd.print("H = ");
    lcd.print(h);
    lcd.print(" ");
    delay(2000);
  }
  else if(t > 25 && t < 35 && h > 70 && r == 1)
  {
    lcd.clear();
    lcd.setCursor(0,0);
    lcd.print("RAINY");
    lcd.setCursor(0,1);
    lcd.print("T = ");
    lcd.print(t);
    lcd.print(" ");
    lcd.print("H = ");
    lcd.print(h);
    lcd.print(" ");
    delay(2000);
  }

  else if(t > 25 && t < 30 && h > 40 && h < 50 && r == 0)
  {
    lcd.clear();
    lcd.setCursor(0,0);
    lcd.print("SPRING");
    lcd.setCursor(0,1);
    lcd.print("T = ");
    lcd.print(t);
    lcd.print(" ");
    lcd.print("H = ");
    lcd.print(h);
    lcd.print(" ");
    delay(2000);
  }

  else if(t <= 25 && h > 40 && h < 60 && r == 0)
  {
    lcd.clear();
    lcd.setCursor(0,0);
    lcd.print("WINTER");
    lcd.setCursor(0,1);
    lcd.print("T = ");
    lcd.print(t);
    lcd.print(" ");
    lcd.print("H = ");
    lcd.print(h);
    lcd.print(" ");
    delay(2000);
  }
}


```
---
[WOKWI LINK](https://wokwi.com/projects/443354741038958593)
---
