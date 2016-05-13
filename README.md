# Pong
**Pong på en Arduino med et OLED display.**
### Forbindelser
Oled        | Arduino
------------|:--------:
DC (data)   | 11
CS (clock)  | 12
RESET       | 13

Knap op   | Arduino
------------|:--------:
OUT         | 2

Knap ned   | Arduino
-----------|:--------:
OUT        | 3

### Beskrivelse af koden
Først importeres de forskellige biblioteker, som er nødvendige for at kommunikere med skærmen:
```c++
    #include <SPI.h>
    #include <Wire.h>
    #include <Adafruit_SSD1306.h>
    #include <Adafruit_GFX.h>
```
    Derefter defineres de forskellige pin's til displayet:
```c++
    #define OLED_DC     11
    #define OLED_CS     12
    #define OLED_RESET  13
```
    Nu kan selve display'et konstrueres i koden:
```c++
    Adafruit_SSD1306 display(OLED_DC, OLED_RESET, OLED_CS);
```
    Som det sidste inden der kan tegnes på skærmen, startes skærmen inde i setup:
    
```c++
    display.begin(SSD1306_SWITCHCAPVCC);   
```

### Opgaver
    1. Lav en pong bane, med 2 firkanter (pads). En i hver side.
        1a. (Ekstra opgave) Lav en stiplet linje i midten af banen
    2. Lav en firkantet bold, der kan bevæge sig, som den skal i et Pong-spil
    3. Få bolden til at skifte retning hvis den rammer en af de tidligere lavede firkanter (ikke den stiplede linie).
    4. Få bolden til at starte midt på banen, hvis den ikke rammer en af disse firkanter.
    5. Lav et point-bræt, som holder styr på hvem der har fået point, og hvor mange.
    6. Lav nogle forskellige variabler som brugeren kan justere på, således spillets betingelser bliver sværere eller lettere.