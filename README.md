# 💡 LDR 5-LED Light Meter — Arduino R4 Minima

> "Can a ₹50 sensor save lives?" — A project from our father-son maker channel.

This project uses a Light Dependent Resistor (LDR) to control 5 LEDs based on ambient light — like a signal bar for brightness. Dark room? All 5 LEDs on. Bright light? All LEDs off.

---

## 🎬 As Seen On

**Aryan Builds** — English-language Arduino & IoT for kids.

---

## ⚙️ How It Works

| Light Condition | LDR Value (approx) | LEDs ON |
|---|---|---|
| Dark | < 300 | 5 (all on) |
| Medium | 300 – 700 | 3 |
| Bright | > 700 | 0 (all off) |

The LDR is wired as a **voltage divider** with a 10kΩ resistor. As light increases, resistance drops and the analog voltage at A0 rises. The Arduino reads this and turns LEDs on/off accordingly.

---

## 🛒 Components Needed

| Component | Quantity | Approx Cost |
|---|---|---|
| Arduino UNO R4 Minima | 1 | ₹2,000 |
| LDR (Light Dependent Resistor) | 1 | ₹10 |
| 10kΩ resistor | 1 | ₹1 |
| 220Ω resistor | 5 | ₹5 |
| LED (any colour) | 5 | ₹25 |
| Breadboard | 1 | ₹80 |
| Jumper wires | several | ₹30 |

**Total: Under ₹200 for the full circuit**

---

## 🔌 Circuit Wiring

**LDR (voltage divider):**
```
5V ──── LDR ──── A0 ──── 10kΩ ──── GND
                  |
             (reads here)
```

**5 LEDs:**

| LED | Arduino Pin | Wiring |
|---|---|---|
| LED 1 | Pin 2 | Pin 2 → 220Ω → LED(+) → LED(-) → GND |
| LED 2 | Pin 3 | Pin 3 → 220Ω → LED(+) → LED(-) → GND |
| LED 3 | Pin 4 | Pin 4 → 220Ω → LED(+) → LED(-) → GND |
| LED 4 | Pin 5 | Pin 5 → 220Ω → LED(+) → LED(-) → GND |
| LED 5 | Pin 6 | Pin 6 → 220Ω → LED(+) → LED(-) → GND |

---

## 🚀 Getting Started

1. Clone this repo or download the `.ino` file
2. Open `ldr_5led_meter.ino` in **Arduino IDE 2.x**
3. Select board: **Arduino UNO R4 Minima**
4. Upload to your board
5. Open **Serial Monitor** at `9600 baud`
6. Cover/uncover the LDR and watch LEDs respond live

---

## 🔧 Tuning the Thresholds

Every LDR behaves slightly differently. Open Serial Monitor and note:
- Value in a **dark room** → set `LOW_LIGHT_THRESHOLD` just above it
- Value under a **torch or bright light** → set `HIGH_LIGHT_THRESHOLD` just below it

```cpp
const int LOW_LIGHT_THRESHOLD  = 300;  // ← tune this
const int HIGH_LIGHT_THRESHOLD = 700;  // ← tune this
```

---

## 📁 Repo Structure

```
ldr-5led-meter/
├── ldr_5led_meter.ino   # Main Arduino sketch
└── README.md            # This file
```

---

## 👦 About This Project

Built by **Aryan** (Creator) with his **Dad** (Creative Director) as part of a summer maker series.
We're exploring sensors, IoT, and AI — one circuit at a time.

*Part of Month 1: Sensor Exploration — Week 2 (LDR)*
