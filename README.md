# LDR + LED Dimmer — Arduino UNO R4 Minima

## What it does
Reads light level using an LDR (photoresistor) and automatically
adjusts LED brightness. Bright room → dim LED. Dark room → bright LED.
Classic night-light logic.

## Components
| Part | Value | Qty |
|------|-------|-----|
| Arduino UNO R4 Minima | — | 1 |
| LDR (photoresistor) | Any GL5516 type | 1 |
| Resistor | 10kΩ (voltage divider) | 1 |
| Resistor | 220Ω (LED current limit) | 1 |
| LED | Any colour | 1 |
| Breadboard + jumper wires | — | — |

## Wiring
| Component Pin | Arduino Pin |
|---|---|
| LDR leg 1 | 5V |
| LDR leg 2 | A0 |
| 10kΩ between LDR leg 2 | GND |
| LED anode (+) via 220Ω | D9 (PWM) |
| LED cathode (−) | GND |

## How the circuit works
The LDR and 10kΩ resistor form a **voltage divider**.
- Dark → LDR resistance goes up → voltage at A0 drops
- Bright → LDR resistance falls → voltage at A0 rises

`analogRead(A0)` gives 0–1023. `map()` inverts this to
0–255 for `analogWrite()` on the PWM pin D9.

## Pins used
- `A0` — LDR signal (analog in)
- `D9` — LED (PWM out, marked ~ on the board)

## Serial monitor
Open at **9600 baud** to watch live LDR and brightness values.
Great for testing with a phone torch or covering the LDR.

## Test ideas
- Flash phone torch → LED should dim instantly
- Try it during a power cut night vs daytime 🌓
