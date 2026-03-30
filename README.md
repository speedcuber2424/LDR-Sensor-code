# LDR Light Sensor Project 💡
**Arduino UNO R4 Minima | Aryan's YouTube Channel**

## What This Does
Reads an LDR (Light Dependent Resistor) and:
- Prints live light level to Serial Monitor
- Turns the built-in LED ON when it gets dark

## Circuit
| Component | Arduino Pin |
|-----------|------------|
| LDR (one leg) | A0 |
| LDR (other leg) | 5V |
| 10kΩ resistor | A0 → GND |
| Built-in LED | Pin 13 (built-in) |

## Serial Monitor Output
```
=== LDR Sensor Ready ===
Value | Light Level
-------------------
823   |  DARK
401   |  MEDIUM
187   |  VERY BRIGHT
```

## Files
- `arduino/ldr_sensor.ino` — Main Arduino sketch
- `simulation/ldr_simulation.html` — p5.js interactive demo (open in Chrome)

## How to Upload
1. Open Arduino IDE
2. Open `ldr_sensor.ino`
3. Select **Board:** Arduino UNO R4 Minima
4. Select correct **Port**
5. Click Upload ⬆️
