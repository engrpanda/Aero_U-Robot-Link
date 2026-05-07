<div align="center">

<img src="https://github.com/engrpanda/Aero_U-Robot-Link/blob/main/APP%20SC/icon.png?raw=true" width="120" alt="Aero Logo"/>

# Aero — U-Robot Link

### Universal Robot Controller for Android

**Control Arduino, ESP8266, ESP32, OrionStar, and LEGO MINDSTORMS robots — all from one app**

[![Android](https://img.shields.io/badge/Platform-Android%207.0%2B-3DDC84?style=flat-square&logo=android)]()
[![Min SDK](https://img.shields.io/badge/Min%20SDK-API%2024-blue?style=flat-square)](https://developer.android.com/about/versions/nougat)
[![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)](LICENSE)
[![Made in PH](https://img.shields.io/badge/Made%20in-Philippines%20🇵🇭-0038A8?style=flat-square)]()

[**GitHub Repository**](https://github.com/engrpanda/Aero_U-Robot-Link) • [Report a Bug](https://github.com/engrpanda/Aero_U-Robot-Link/issues) • [Request a Feature](https://github.com/engrpanda/Aero_U-Robot-Link/issues) • [Privacy Policy](https://raw.githubusercontent.com/engrpanda/Aero_U-Robot-Link/refs/heads/main/PRIVACY_POLICY.md)

---

<!-- Replace with actual screenshot collage -->
<img src="https://github.com/engrpanda/Aero_U-Robot-Link/blob/main/APP%20SC/0.png?raw=true" width="800" alt="App Screenshots"/>

</div>

---

## Table of Contents

1. [What Is Aero?](#1-what-is-aero)
2. [Supported Hardware](#2-supported-hardware)
3. [Quick Start — Choose Your Hardware](#3-quick-start--choose-your-hardware)
   - [A. Arduino + HC-05 Bluetooth Classic](#option-a-arduino--hc-05-bluetooth-classic)
   - [B. Arduino + HM-10 BLE](#option-b-arduino--hm-10-ble)
   - [C. ESP8266 via WiFi](#option-c-esp8266-via-wifi)
   - [D. ESP32 via WiFi or BLE](#option-d-esp32-via-wifi-or-ble)
   - [E. ESP32-CAM with Live Video](#option-e-esp32-cam-with-live-video)
   - [F. LEGO MINDSTORMS NXT or EV3 — beginner-friendly walkthrough](#option-f-lego-mindstorms-nxt-or-ev3)
4. [Control Modes — Complete Guide](#4-control-modes--complete-guide)
   - [Custom Controls](#-custom-controls)
   - [Joystick](#-joystick)
   - [Tilt Control](#-tilt-control)
   - [Gamepad](#-gamepad)
   - [RGB LED](#-rgb-led)
   - [Terminal](#-terminal)
   - [Timer](#-timer)
   - [IoT Dashboard](#-iot-dashboard)
   - [Voice Control](#-voice-control)
   - [IP Camera](#-ip-camera)
5. [IoT Sensor Dashboard — Deep Dive](#5-iot-sensor-dashboard--deep-dive)
   - [Widget Types](#widget-types)
   - [Web Dashboard](#web-dashboard)
   - [Sensor Protocol](#sensor-protocol)
   - [Wiring Popular Sensors](#wiring-popular-sensors)
6. [Complete Command Reference](#6-complete-command-reference)
7. [RGB LED Wiring & Code](#7-rgb-led-wiring--code)
8. [App Settings & Customization](#8-app-settings--customization)
9. [Tips & Tricks](#9-tips--tricks)
10. [Troubleshooting](#10-troubleshooting)
11. [FAQ](#11-faq)
12. [🤖 AI Code Generation](#13--ai-code-generation--let-ai-write-your-device-code)

---

## 1. What Is Aero?

Aero (U-Robot Link) is a professional Android controller app for makers, students, and engineers. It replaces the need to build a custom remote control app every time you start a new robotics project.

**One app. Every project.**

Whether you're building a toy car, a home automation system, a plant monitor, a LEGO MINDSTORMS robot, or a professional service robot — Aero speaks the same simple serial protocol over Bluetooth, BLE, or WiFi, and translates it into the LEGO Direct Commands protocol when you connect to an NXT or EV3 brick.

### What you get out of the box

| Feature | Description |
|---|---|
| **Custom Button Grid** | 8-column, unlimited rows. Drag, swap, resize. |
| **Dual Joystick** | Differential drive with two speed sliders |
| **Tilt Control** | Use your phone as a steering wheel |
| **Gamepad** | Full PS4/PS5/Xbox controller support |
| **RGB LED** | Color picker with real-time auto-send |
| **Terminal** | Full TX/RX serial monitor with timestamps |
| **Countdown Timer** | Auto-send any command when it hits zero |
| **IoT Dashboard** | 10 live widget types, drag-and-position, web dashboard |
| **Voice Control** | Google Speech Recognition → custom commands |
| **IP Camera** | Live video from ESP32-CAM or any MJPEG stream |
| **Named Profiles** | Save multiple control layouts per device |
| **Light / Dark Mode** | Easy on the eyes in any environment |

---

## 2. Supported Hardware

### Connection Types

| Protocol | Module | Speed | Range | Best For |
|---|---|---|---|---|
| **Bluetooth Classic** | HC-05, HC-06 | ~9600 baud | ~10m | Arduino robots, beginner projects |
| **BLE** | HM-10, ESP32 BLE | ~9600 baud | ~30m | Low power, wearables, indoor |
| **WiFi (TCP)** | ESP8266, ESP32 | ~115200+ | Same network | Fast control, IoT projects, long range |
| **WiFi + Camera** | ESP32-CAM | ~115200 | Same network | Video robots, surveillance |
| **LEGO Direct Commands** | LEGO NXT, LEGO EV3 brick | binary protocol | ~10m | LEGO MINDSTORMS robots — no custom firmware needed |

### Tested Microcontrollers & Robots

- Arduino Uno, Nano, Mega, Pro Mini
- ESP8266 (NodeMCU, Wemos D1 Mini, Generic)
- ESP32 (any variant)
- ESP32-CAM (AI-Thinker)
- OrionStar AI Robot (via dedicated Robot mode)
- **LEGO MINDSTORMS NXT** (motor ports A, B, C — original LEGO firmware)
- **LEGO MINDSTORMS EV3** (motor ports A, B, C, D — official LEGO firmware)

> 💡 **Important note for LEGO bricks:** Aero does NOT require you to install ev3dev, leJOS, or any custom firmware. The app talks to the brick's stock LEGO firmware over Bluetooth using the published Direct Commands protocol — same one the official LEGO software uses.

---

## 3. Quick Start — Choose Your Hardware

> **Before you start:** Install Aero on your Android phone (Android 7.0+, API 24+). For Bluetooth connections, go to Android Settings → Bluetooth and **pair your module first** before trying to connect inside the app.

---

### Option A: Arduino + HC-05 Bluetooth Classic

This is the most beginner-friendly setup. An HC-05 or HC-06 module connects to Arduino over UART and pairs with your phone like any Bluetooth device.

#### What You Need

| Component | Notes |
|---|---|
| Arduino Uno / Nano / Mega | Any variant works |
| HC-05 or HC-06 module | HC-05 can be master/slave; HC-06 is slave-only. Both work. |
| L298N motor driver | Or any H-bridge (L293D, TB6612, etc.) |
| DC motors × 2 | Or any actuators |
| 1kΩ and 2kΩ resistors | For voltage divider on RX line |
| Jumper wires | |
| 9V–12V battery | For motor driver |

#### Wiring Diagram

```
╔══════════════════════════════════════════════════════════╗
║  ARDUINO UNO                    HC-05 / HC-06            ║
║  ─────────                      ──────────               ║
║  5V  ──────────────────────────  VCC                     ║
║  GND ──────────────────────────  GND                     ║
║                                                          ║
║  Pin 11 (TX) ──┬── 1kΩ ──────── RXD  ←  3.3V ONLY!      ║
║                └── 2kΩ ──────── GND                     ║
║                   (voltage divider protects HC-05 RX)    ║
║                                                          ║
║  Pin 10 (RX) ──────────────────  TXD  (no resistor)      ║
╚══════════════════════════════════════════════════════════╝

╔══════════════════════════════════════════════════════════╗
║  ARDUINO UNO                    L298N MOTOR DRIVER       ║
║  ─────────                      ──────────               ║
║  Pin 5 (PWM) ───────────────── ENA  (left motor speed)   ║
║  Pin 6 (PWM) ───────────────── ENB  (right motor speed)  ║
║  Pin 2       ───────────────── IN1                       ║
║  Pin 3       ───────────────── IN2                       ║
║  Pin 4       ───────────────── IN3                       ║
║  Pin 7       ───────────────── IN4                       ║
║  GND         ───────────────── GND                       ║
║                                                          ║
║                    L298N ─── 9V–12V Battery (motor VCC)  ║
║                    L298N ─── Left Motor terminals        ║
║                    L298N ─── Right Motor terminals       ║
╚══════════════════════════════════════════════════════════╝
```

> ⚠️ **CRITICAL:** The HC-05 RX pin is 3.3V logic. Connecting it directly to Arduino's 5V TX **will damage the module** over time. Always use the voltage divider shown above (1kΩ series + 2kΩ to GND). HC-06 has the same issue.

> ✅ The HC-05 TX → Arduino RX direction is safe with no resistor. HC-05 TX outputs 3.3V which Arduino reads as HIGH just fine.

#### Arduino Code — Full Featured

```cpp
#include <SoftwareSerial.h>

// RX=10 (from HC-05 TX), TX=11 (to HC-05 RX via voltage divider)
SoftwareSerial BTSerial(10, 11);

// ── Motor Driver (L298N) ──
#define ENA 5    // Left motor speed (PWM pin)
#define ENB 6    // Right motor speed (PWM pin)
#define IN1 2    // Left motor direction
#define IN2 3
#define IN3 4    // Right motor direction
#define IN4 7

// ── Accessories ──
#define LED_PIN     13
#define BUZZER_PIN   8
#define SERVO_PIN    9   // Attach servo signal here

int speedValue = 150;    // Default speed 0–255

void setup() {
  Serial.begin(9600);
  BTSerial.begin(9600);  // HC-05 default baud rate

  // Motor pins
  pinMode(ENA, OUTPUT); pinMode(ENB, OUTPUT);
  pinMode(IN1, OUTPUT); pinMode(IN2, OUTPUT);
  pinMode(IN3, OUTPUT); pinMode(IN4, OUTPUT);

  // Accessories
  pinMode(LED_PIN,    OUTPUT);
  pinMode(BUZZER_PIN, OUTPUT);

  stopMotors();
  Serial.println("Aero ready!");
  BTSerial.println("READY");
}

void loop() {
  if (BTSerial.available()) {
    String cmd = BTSerial.readStringUntil('\n');
    cmd.trim();
    if (cmd.length() > 0) processCommand(cmd);
  }
}

void processCommand(String cmd) {
  Serial.println("RX: " + cmd);

  // ── Basic movement ──
  if      (cmd == "FWD") { forward();   BTSerial.println("OK:FWD"); }
  else if (cmd == "BWD") { backward();  BTSerial.println("OK:BWD"); }
  else if (cmd == "LFT") { turnLeft();  BTSerial.println("OK:LFT"); }
  else if (cmd == "RGT") { turnRight(); BTSerial.println("OK:RGT"); }
  else if (cmd == "STP") { stopMotors();BTSerial.println("OK:STP"); }

  // ── Speed: SPD:0–255 ──
  else if (cmd.startsWith("SPD:")) {
    speedValue = constrain(cmd.substring(4).toInt(), 0, 255);
    BTSerial.println("OK:SPD:" + String(speedValue));
  }

  // ── Joystick: JOY:linear,angular  (values -255 to 255) ──
  else if (cmd.startsWith("JOY:")) {
    int comma   = cmd.indexOf(',');
    int linear  = cmd.substring(4, comma).toInt();
    int angular = cmd.substring(comma + 1).toInt();
    driveMotor(ENA, IN1, IN2, constrain(linear + angular, -255, 255));
    driveMotor(ENB, IN3, IN4, constrain(linear - angular, -255, 255));
    BTSerial.println("OK:JOY");
  }

  // ── RGB: RGB:r,g,b  (0–255 each) ──
  else if (cmd.startsWith("RGB:")) {
    int i1 = cmd.indexOf(',');
    int i2 = cmd.indexOf(',', i1 + 1);
    int r  = cmd.substring(4, i1).toInt();
    int g  = cmd.substring(i1 + 1, i2).toInt();
    int b  = cmd.substring(i2 + 1).toInt();
    analogWrite(9,  r);   // Red pin
    analogWrite(10, g);   // Green pin (note: conflicts with BTSerial if using pin 10)
    analogWrite(11, b);   // Blue pin  (use different pins if needed)
    BTSerial.println("OK:RGB");
  }

  // ── Servo: SRV:0–180 ──
  else if (cmd.startsWith("SRV:")) {
    int angle = constrain(cmd.substring(4).toInt(), 0, 180);
    // myServo.write(angle);  // Uncomment after adding #include <Servo.h>
    BTSerial.println("OK:SRV:" + String(angle));
  }

  // ── LED: LED:1 or LED:0 ──
  else if (cmd.startsWith("LED:")) {
    digitalWrite(LED_PIN, cmd.substring(4).toInt() ? HIGH : LOW);
    BTSerial.println("OK:LED");
  }

  // ── Buzzer/Horn: BZR:1, HRN:1 ──
  else if (cmd.startsWith("BZR:") || cmd.startsWith("HRN:")) {
    digitalWrite(BUZZER_PIN, cmd.substring(4).toInt() ? HIGH : LOW);
    BTSerial.println("OK:" + cmd.substring(0, 3));
  }

  // ── Timer: TIMER:DONE ──
  else if (cmd.startsWith("TIMER:")) {
    stopMotors();   // Example: stop when timer expires
    BTSerial.println("OK:TIMER");
  }

  // ── Sensor request (optional — app can also poll) ──
  else if (cmd == "GET_SENSORS") {
    float temp = 25.3; // Replace with real sensor read
    BTSerial.println("SENSOR:temp:" + String(temp, 1));
  }

  // ── Echo unknown commands ──
  else { BTSerial.println("OK:" + cmd); }
}

// ── Motor helpers ──────────────────────────────────────────

void driveMotor(int en, int in1, int in2, int spd) {
  if (spd > 0)      { digitalWrite(in1, HIGH); digitalWrite(in2, LOW);  analogWrite(en, spd);  }
  else if (spd < 0) { digitalWrite(in1, LOW);  digitalWrite(in2, HIGH); analogWrite(en, -spd); }
  else              { digitalWrite(in1, LOW);  digitalWrite(in2, LOW);  analogWrite(en, 0);    }
}

void forward()    { driveMotor(ENA, IN1, IN2,  speedValue); driveMotor(ENB, IN3, IN4,  speedValue); }
void backward()   { driveMotor(ENA, IN1, IN2, -speedValue); driveMotor(ENB, IN3, IN4, -speedValue); }
void turnLeft()   { driveMotor(ENA, IN1, IN2, -speedValue); driveMotor(ENB, IN3, IN4,  speedValue); }
void turnRight()  { driveMotor(ENA, IN1, IN2,  speedValue); driveMotor(ENB, IN3, IN4, -speedValue); }
void stopMotors() { driveMotor(ENA, IN1, IN2,  0);          driveMotor(ENB, IN3, IN4,  0);          }
```

#### How to Connect (Step by Step)

1. Upload the code to your Arduino
2. Open **Android Settings → Bluetooth → Pair New Device**
3. Find **HC-05** (or HC-06) in the list. Default PIN: `1234` or `0000`
4. Open **Aero** → tap the device card → select **Bluetooth Classic**
5. Tap **SCAN** → select your HC-05 from the list
6. Tap **CONNECT** — the status bar turns green: "✓ Connected"
7. Press the **Forward** button — check Serial Monitor for `RX: FWD`

> 💡 **Pro Tip:** HC-05 has two modes — AT command mode (red LED blinks slow) and normal mode (fast blink). You don't need AT mode for basic use. Default baud is 9600. If you changed it, match it in the `BTSerial.begin()` call.

---

### Option B: Arduino + HM-10 BLE

HM-10 is a Bluetooth Low Energy module. Use this when you need lower power consumption or are connecting to devices that don't support Bluetooth Classic.

#### What You Need

- Arduino Uno / Nano / Mega
- HM-10 BLE module (CC2541 chip)
- Same motor driver setup as Option A

#### Wiring Diagram

```
╔══════════════════════════════════════════════════════════╗
║  ARDUINO UNO                    HM-10 BLE                ║
║  ─────────                      ──────                   ║
║  3.3V ─────────────────────────  VCC  ←  3.3V ONLY!      ║
║  GND  ─────────────────────────  GND                     ║
║                                                          ║
║  Pin 11 (TX) ── 1kΩ ─┬───────── RXD                     ║
║                       └── 2kΩ── GND  (voltage divider)  ║
║                                                          ║
║  Pin 10 (RX) ──────────────────  TXD                     ║
╚══════════════════════════════════════════════════════════╝
```

> ⚠️ HM-10 runs on **3.3V** — not 5V. Power it from the Arduino's 3.3V pin, not 5V. The same voltage divider on the RX line applies.

#### Arduino Code

The code is **identical** to Option A — just change the baud rate:

```cpp
#include <SoftwareSerial.h>
SoftwareSerial BTSerial(10, 11); // RX, TX

void setup() {
  Serial.begin(9600);
  BTSerial.begin(9600);  // HM-10 default is 9600
  // ... rest is same as Option A
}
```

#### How to Connect

1. Unlike HC-05, **no pairing needed** in Android Settings — BLE is automatic
2. Open Aero → device card → select **BLE**
3. Tap **SCAN** → the HM-10 appears as **"HMSoft"** or similar
4. Tap it → tap **CONNECT**

> 💡 If HM-10 doesn't appear in scan, make sure it's powered and the LED is blinking. First-time connection can take 5–10 seconds.

---

### Option C: ESP8266 via WiFi

WiFi gives you significantly faster data rates and works over your entire home network. No Bluetooth pairing needed.

#### What You Need

- ESP8266 NodeMCU or Wemos D1 Mini
- L298N motor driver
- Same motors as Option A
- A 2.4 GHz WiFi network (ESP8266 does not support 5 GHz)

#### Wiring Diagram (NodeMCU)

```
╔══════════════════════════════════════════════════════════╗
║  NodeMCU (ESP8266)              L298N Motor Driver       ║
║  ─────────────────              ──────────────────       ║
║  D1 (GPIO5)  ─────────────────  IN1  (Left  motor A)     ║
║  D2 (GPIO4)  ─────────────────  IN2  (Left  motor B)     ║
║  D7 (GPIO13) ─────────────────  IN3  (Right motor A)     ║
║  D4 (GPIO2)  ─────────────────  IN4  (Right motor B)     ║
║  D5 (GPIO14) ─────────────────  ENA  (PWM left  speed)   ║
║  D6 (GPIO12) ─────────────────  ENB  (PWM right speed)   ║
║  GND         ─────────────────  GND                      ║
║                                                          ║
║             IMPORTANT: Power L298N from separate         ║
║             7–12V battery. Do NOT power motors           ║
║             from NodeMCU's 3.3V or VIN pin.              ║
╚══════════════════════════════════════════════════════════╝
```

> ⚠️ **Never power motors from the ESP's 3.3V pin.** Motors draw too much current and will crash/damage the ESP. Always use a separate motor power supply.

> ✅ This wiring uses **D7 (GPIO13) for IN3** — avoids GPIO0 (D3) which must be HIGH at boot. Safe for motor control from the moment power is applied.

#### ESP8266 WiFi Code

> ✅ **This code is verified working.** Uses raw GPIO numbers (not D-pin aliases) for maximum compatibility across all ESP8266 boards.

```cpp
#include <ESP8266WiFi.h>

// ── Config ────────────────────────────────────────────────
const char* SSID     = "YOUR_WIFI_SSID";      // ← change this
const char* PASSWORD = "YOUR_WIFI_PASSWORD";   // ← change this
const int   PORT     = 8080;
const int   SPEED    = 150;                    // Default speed 0–255

// ── Pin Map (raw GPIO numbers — works on all ESP8266 boards)
#define ENA 14  // D5 — Left  motor PWM speed
#define ENB 12  // D6 — Right motor PWM speed
#define IN1  5  // D1 — Left  motor dir A
#define IN2  4  // D2 — Left  motor dir B
#define IN3 13  // D7 — Right motor dir A  ← safe, not GPIO0
#define IN4  2  // D4 — Right motor dir B

WiFiServer server(PORT);
WiFiClient client;
int speedValue = SPEED;

// ── Motor helper ──────────────────────────────────────────
void setMotor(int in1, int in2, int enPin, int spd) {
  if      (spd > 0) { digitalWrite(in1, HIGH); digitalWrite(in2, LOW);  }
  else if (spd < 0) { digitalWrite(in1, LOW);  digitalWrite(in2, HIGH); spd = -spd; }
  else              { digitalWrite(in1, LOW);   digitalWrite(in2, LOW);  }
  analogWrite(enPin, constrain(spd, 0, 255));
}

void forward()   { setMotor(IN1, IN2, ENA,  speedValue); setMotor(IN3, IN4, ENB,  speedValue); }
void backward()  { setMotor(IN1, IN2, ENA, -speedValue); setMotor(IN3, IN4, ENB, -speedValue); }
void turnLeft()  { setMotor(IN1, IN2, ENA, -speedValue); setMotor(IN3, IN4, ENB,  speedValue); }
void turnRight() { setMotor(IN1, IN2, ENA,  speedValue); setMotor(IN3, IN4, ENB, -speedValue); }
void stopAll()   { setMotor(IN1, IN2, ENA,  0);          setMotor(IN3, IN4, ENB,  0);          }

// ── Command processor ─────────────────────────────────────
void processCommand(const String& cmd) {
  Serial.println("CMD: " + cmd);

  // Basic movement
  if      (cmd == "FWD") { forward();   client.println("OK: FORWARD");  }
  else if (cmd == "BWD") { backward();  client.println("OK: BACKWARD"); }
  else if (cmd == "LFT") { turnLeft();  client.println("OK: LEFT");     }
  else if (cmd == "RGT") { turnRight(); client.println("OK: RIGHT");    }
  else if (cmd == "STP") { stopAll();   client.println("OK: STOP");     }

  // Speed control — SPD:0–255
  else if (cmd.startsWith("SPD:")) {
    speedValue = constrain(cmd.substring(4).toInt(), 0, 255);
    client.println("OK:SPD:" + String(speedValue));
  }

  // Joystick — JOY:linear,angular (-255 to 255)
  else if (cmd.startsWith("JOY:")) {
    int c = cmd.indexOf(',');
    setMotor(IN1, IN2, ENA, constrain(cmd.substring(4, c).toInt() + cmd.substring(c + 1).toInt(), -255, 255));
    setMotor(IN3, IN4, ENB, constrain(cmd.substring(4, c).toInt() - cmd.substring(c + 1).toInt(), -255, 255));
    client.println("OK:JOY");
  }

  // RGB LED — RGB:r,g,b (0–255 each)
  else if (cmd.startsWith("RGB:")) {
    int i1 = cmd.indexOf(','), i2 = cmd.indexOf(',', i1 + 1);
    // analogWrite(RGB_R_PIN, cmd.substring(4, i1).toInt());   // uncomment when wired
    // analogWrite(RGB_G_PIN, cmd.substring(i1 + 1, i2).toInt());
    // analogWrite(RGB_B_PIN, cmd.substring(i2 + 1).toInt());
    client.println("OK:RGB");
  }

  // Single LED — LED:1 or LED:0
  else if (cmd.startsWith("LED:")) {
    // digitalWrite(LED_PIN, cmd.substring(4).toInt() ? HIGH : LOW);  // uncomment when wired
    client.println("OK:LED");
  }

  // Buzzer / Horn — BZR:1 or HRN:1
  else if (cmd.startsWith("BZR:") || cmd.startsWith("HRN:")) {
    // digitalWrite(BUZZER_PIN, cmd.substring(4).toInt() ? HIGH : LOW);  // uncomment
    client.println("OK:" + cmd.substring(0, 3));
  }

  // Servo — SRV:0–180
  else if (cmd.startsWith("SRV:")) {
    int angle = constrain(cmd.substring(4).toInt(), 0, 180);
    // myServo.write(angle);  // uncomment after adding #include <Servo.h>
    client.println("OK:SRV:" + String(angle));
  }

  // IP query
  else if (cmd == "IP") {
    client.println("IP: " + WiFi.localIP().toString());
  }

  else { client.println("ERR: UNKNOWN CMD"); }
}

void setup() {
  Serial.begin(115200);
  delay(500);

  for (int pin : {ENA, ENB, IN1, IN2, IN3, IN4}) pinMode(pin, OUTPUT);
  stopAll();

  WiFi.mode(WIFI_STA);
  WiFi.begin(SSID, PASSWORD);
  Serial.print("Connecting to WiFi");

  unsigned long start = millis();
  while (WiFi.status() != WL_CONNECTED && millis() - start < 20000) {
    delay(500); Serial.print(".");
  }

  if (WiFi.status() == WL_CONNECTED) {
    Serial.println("\n✓ Connected!  IP: " + WiFi.localIP().toString());
    Serial.println("► In Aero: WiFi → " + WiFi.localIP().toString() + ":8080");
  } else {
    Serial.println("\n✗ WiFi failed — check SSID/password");
  }

  server.begin();
  Serial.printf("TCP server on port %d\n", PORT);
}

void loop() {
  if (!client || !client.connected()) client = server.available();
  if (client && client.available()) {
    String cmd = client.readStringUntil('\n');
    cmd.trim();
    if (cmd.length()) processCommand(cmd);
  }

  // Serial monitor IP query for debugging
  if (Serial.available()) {
    String cmd = Serial.readStringUntil('\n');
    cmd.trim(); cmd.toUpperCase();
    if (cmd == "IP") Serial.println(WiFi.status() == WL_CONNECTED
      ? "IP: " + WiFi.localIP().toString() : "Not connected");
  }
}
```

> 💡 **Full version with all controls:** Download `Aero_ESP8266.ino` from the repository root — it includes every command (joystick, tilt, gamepad buttons, servo, buzzer, RGB, sensors, timers) with `// uncomment` instructions for each one.

#### How to Connect

1. Upload the code. Open Serial Monitor (115200 baud)
2. Wait for `IP Address: 192.168.x.x` — **note this IP**
3. Open Aero → device card → select **WiFi**
4. Type: `192.168.x.x:8080` (replace with your actual IP)
5. Tap **CONNECT**

> 💡 **Static IP tip:** Add `WiFi.config(IPAddress(192,168,1,100), gateway, subnet)` before `WiFi.begin()` to fix the ESP at a stable IP so you never have to look it up again.

---

### Option D: ESP32 via WiFi or BLE

ESP32 is more powerful than ESP8266. It can run WiFi and BLE **simultaneously** and has hardware PWM on almost every pin.

#### WiFi Setup

The WiFi code is nearly identical to ESP8266. Just replace:
```cpp
#include <ESP8266WiFi.h>   // ← remove this
#include <WiFi.h>          // ← add this instead
```

Everything else (logic, motor functions, command parsing) is identical.

#### BLE Setup

```cpp
#include <BLEDevice.h>
#include <BLEServer.h>
#include <BLEUtils.h>
#include <BLE2902.h>

#define SERVICE_UUID        "6E400001-B5A3-F393-E0A9-E50E24DCCA9E"
#define CHARACTERISTIC_UUID_RX "6E400002-B5A3-F393-E0A9-E50E24DCCA9E"
#define CHARACTERISTIC_UUID_TX "6E400003-B5A3-F393-E0A9-E50E24DCCA9E"

// Motor pins (ESP32 — any GPIO works for PWM)
#define ENA 32  #define ENB 33
#define IN1 25  #define IN2 26  #define IN3 27  #define IN4 14

BLECharacteristic* pTxCharacteristic;
bool deviceConnected = false;
int speedValue = 150;

class ServerCallbacks : public BLEServerCallbacks {
  void onConnect(BLEServer* s)    { deviceConnected = true;  Serial.println("BLE Connected"); }
  void onDisconnect(BLEServer* s) { deviceConnected = false; s->startAdvertising(); }
};

class RxCallbacks : public BLECharacteristicCallbacks {
  void onWrite(BLECharacteristic* c) {
    String cmd = c->getValue().c_str();
    cmd.trim();
    processCommand(cmd);
  }
};

void setup() {
  Serial.begin(115200);
  // Motor pins
  pinMode(ENA,OUTPUT); pinMode(ENB,OUTPUT);
  pinMode(IN1,OUTPUT); pinMode(IN2,OUTPUT);
  pinMode(IN3,OUTPUT); pinMode(IN4,OUTPUT);
  stopMotors();

  BLEDevice::init("Aero_ESP32");
  BLEServer* pServer = BLEDevice::createServer();
  pServer->setCallbacks(new ServerCallbacks());
  BLEService* pService = pServer->createService(SERVICE_UUID);

  pTxCharacteristic = pService->createCharacteristic(
    CHARACTERISTIC_UUID_TX, BLECharacteristic::PROPERTY_NOTIFY);
  pTxCharacteristic->addDescriptor(new BLE2902());

  BLECharacteristic* pRx = pService->createCharacteristic(
    CHARACTERISTIC_UUID_RX, BLECharacteristic::PROPERTY_WRITE);
  pRx->setCallbacks(new RxCallbacks());

  pService->start();
  pServer->getAdvertising()->start();
  Serial.println("BLE advertising as 'Aero_ESP32'");
}

void loop() { delay(10); }

void processCommand(String cmd) {
  Serial.println("BLE CMD: " + cmd);
  // Same command parsing as Option A
  // Replace BTSerial.println() with: pTxCharacteristic->setValue(response); pTxCharacteristic->notify();
  if (cmd == "FWD") {
    forward();
    if (deviceConnected) { pTxCharacteristic->setValue("OK:FWD"); pTxCharacteristic->notify(); }
  }
  // ... add all other commands same as Option A
}

// Motor functions — identical to Option A
void driveMotor(int en, int in1, int in2, int spd) {
  if (spd > 0)      { digitalWrite(in1, HIGH); digitalWrite(in2, LOW);  analogWrite(en, spd);  }
  else if (spd < 0) { digitalWrite(in1, LOW);  digitalWrite(in2, HIGH); analogWrite(en, -spd); }
  else              { digitalWrite(in1, LOW);  digitalWrite(in2, LOW);  analogWrite(en, 0);    }
}
void forward()    { driveMotor(ENA, IN1, IN2,  speedValue); driveMotor(ENB, IN3, IN4,  speedValue); }
void backward()   { driveMotor(ENA, IN1, IN2, -speedValue); driveMotor(ENB, IN3, IN4, -speedValue); }
void turnLeft()   { driveMotor(ENA, IN1, IN2, -speedValue); driveMotor(ENB, IN3, IN4,  speedValue); }
void turnRight()  { driveMotor(ENA, IN1, IN2,  speedValue); driveMotor(ENB, IN3, IN4, -speedValue); }
void stopMotors() { driveMotor(ENA, IN1, IN2, 0); driveMotor(ENB, IN3, IN4, 0); }
```

#### How to Connect (ESP32 BLE)

1. Upload code. Open Serial Monitor — you should see `BLE advertising as 'Aero_ESP32'`
2. Open Aero → device card → select **BLE**
3. Tap **SCAN** → find **Aero_ESP32**
4. Tap it → **CONNECT**

---

### Option E: ESP32-CAM with Live Video

ESP32-CAM gives you a live video stream while controlling the robot at the same time.

#### Hardware

```
╔══════════════════════════════════════════════════════════╗
║  ESP32-CAM (AI-Thinker)         Notes                   ║
║  ──────────────────                                      ║
║  IO0  ──── GND                  (during upload only!)   ║
║  5V   ──── 5V power supply      (min 500mA — critical!) ║
║  GND  ──── GND                                          ║
║  U0TXD ─── FTDI RX              (for programming)       ║
║  U0RXD ─── FTDI TX              (for programming)       ║
║                                                          ║
║  Motor driver connects to available GPIO pins:           ║
║  IO12, IO13, IO15, IO2, IO14, IO4                       ║
╚══════════════════════════════════════════════════════════╝
```

> ⚠️ **Power is critical for ESP32-CAM.** It needs at least 500mA at 5V, especially when WiFi + camera are both running. A weak USB port or thin power wire causes random resets. Use a dedicated 5V/1A supply.

> ⚠️ IO0 must be tied to GND only during **upload**. Remove the jumper wire when running normally.

#### ESP32-CAM Code (Control + Video Stream)

```cpp
#include <WiFi.h>
#include "esp_camera.h"

const char* WIFI_SSID = "YOUR_WIFI";
const char* WIFI_PASS = "YOUR_PASS";

// Camera model (AI-Thinker)
#define PWDN_GPIO_NUM  32
#define RESET_GPIO_NUM -1
#define XCLK_GPIO_NUM   0
#define SIOD_GPIO_NUM  26
#define SIOC_GPIO_NUM  27
#define Y9_GPIO_NUM    35
#define Y8_GPIO_NUM    34
#define Y7_GPIO_NUM    39
#define Y6_GPIO_NUM    36
#define Y5_GPIO_NUM    21
#define Y4_GPIO_NUM    19
#define Y3_GPIO_NUM    18
#define Y2_GPIO_NUM     5
#define VSYNC_GPIO_NUM 25
#define HREF_GPIO_NUM  23
#define PCLK_GPIO_NUM  22

// Motors — use pins not occupied by camera
#define IN1 13  #define IN2 15  #define IN3 2  #define IN4 14

WiFiServer cmdServer(8080);   // Control port
WiFiClient client;
int speedValue = 150;

void setup() {
  Serial.begin(115200);

  // Init camera
  camera_config_t config;
  config.ledc_channel = LEDC_CHANNEL_0;
  config.ledc_timer   = LEDC_TIMER_0;
  config.pin_d0 = Y2_GPIO_NUM; config.pin_d1 = Y3_GPIO_NUM;
  config.pin_d2 = Y4_GPIO_NUM; config.pin_d3 = Y5_GPIO_NUM;
  config.pin_d4 = Y6_GPIO_NUM; config.pin_d5 = Y7_GPIO_NUM;
  config.pin_d6 = Y8_GPIO_NUM; config.pin_d7 = Y9_GPIO_NUM;
  config.pin_xclk  = XCLK_GPIO_NUM; config.pin_pclk = PCLK_GPIO_NUM;
  config.pin_vsync = VSYNC_GPIO_NUM; config.pin_href  = HREF_GPIO_NUM;
  config.pin_sscb_sda = SIOD_GPIO_NUM; config.pin_sscb_scl = SIOC_GPIO_NUM;
  config.pin_pwdn  = PWDN_GPIO_NUM;  config.pin_reset = RESET_GPIO_NUM;
  config.xclk_freq_hz = 20000000;
  config.pixel_format = PIXFORMAT_JPEG;
  config.frame_size   = FRAMESIZE_VGA;   // 640×480
  config.jpeg_quality = 12;              // Lower = better quality
  config.fb_count     = 1;
  esp_camera_init(&config);

  // WiFi
  WiFi.begin(WIFI_SSID, WIFI_PASS);
  while (WiFi.status() != WL_CONNECTED) { delay(500); Serial.print("."); }
  Serial.println("\nIP: " + WiFi.localIP().toString());

  // Start camera stream server on port 81
  startCameraServer();   // Uses ESP32-CAM example's camera_httpd.cpp

  cmdServer.begin();
  Serial.println("Control: port 8080 | Camera: port 81/stream");
}

void loop() {
  if (!client || !client.connected()) client = cmdServer.available();
  if (client && client.available()) {
    String cmd = client.readStringUntil('\n');
    cmd.trim();
    processCommand(cmd);
  }
}

// processCommand() — same as ESP8266 version above
// Motor functions — same as ESP8266 version above
// (No ENA/ENB PWM with ESP32-CAM — most GPIO used by camera)
// Use simple HIGH/LOW direction control without speed control
```

#### How to Connect with Video

1. Upload code, open Serial Monitor (115200 baud)
2. Note the IP: e.g. `192.168.1.77`
3. Open Aero → Camera section → enter: `http://192.168.1.77:81/stream`
4. For control: enter `192.168.1.77:8080`
5. Tap **CONNECT** — live video should appear at the top

---

### Option F: LEGO MINDSTORMS NXT or EV3

> 🎓 **This is the easiest option in the entire app.** You don't need to write code, you don't need a soldering iron, you don't need to install special firmware on the brick. Aero talks directly to the LEGO brick's built-in software over Bluetooth.

#### What You Need

| Component | Notes |
|---|---|
| LEGO MINDSTORMS NXT *or* EV3 brick | The orange (NXT) or stone-grey (EV3) brick that came in the kit |
| At least 2 LEGO motors | Plus their cables, plugged into the brick |
| 6 fresh AA batteries (NXT) or charged battery pack (EV3) | The brick must be powered on |
| Android phone with Bluetooth | Same phone you'll run Aero on |

You do **NOT** need: ev3dev, leJOS, RobotC, MicroPython, or any modified firmware. Aero works with the stock LEGO firmware that came with your brick.

#### Step 1 — Power on the brick and turn Bluetooth on

**On NXT:**
1. Press the orange button to turn on the brick.
2. Use the grey arrow buttons to navigate to **Bluetooth → On / Off → On**.
3. Then go to **Bluetooth → Visibility → Visible**.
4. The Bluetooth icon `<>` appears in the top-left of the brick screen — that means it's discoverable.

**On EV3:**
1. Press the dark grey button below the screen to power on.
2. Use the arrow buttons to go to the **Settings tab** (the wrench icon, far right).
3. Open **Bluetooth**, then tick both **Bluetooth** and **Visibility**.
4. A small Bluetooth icon `<` appears in the top-left of the screen.

#### Step 2 — Pair the brick with your Android phone

This is done in **Android system settings, not inside Aero**. Aero will use the pairing your phone already has on file.

1. On your phone, open **Settings → Connected devices → Pair new device** (the wording varies by phone).
2. The phone scans for nearby Bluetooth devices. After 5–10 seconds you should see something called **NXT** or **EV3** in the list. (You can rename your brick on the brick itself if you have several.)
3. Tap that entry. Android will prompt for a PIN.
4. **Enter `1234`** — this is the default LEGO Bluetooth passkey for both NXT and EV3.
5. The brick will beep / show a pairing prompt — confirm it on the brick by pressing the orange button (NXT) or the centre tick mark (EV3).
6. The phone now lists the brick as a **Paired device**. Done with Android settings.

> 💡 **Did pairing fail?** Make sure the brick's Bluetooth Visibility is on, the brick is within ~3 metres of the phone, and that no other phone or PC is currently connected to the brick (only one device at a time can connect).

#### Step 3 — Open Aero and pick the brick

1. Launch **Aero** on your phone.
2. On the home screen, tap the **Controller** card to expand it.
3. Scroll the list and tap **LEGO MINDSTORMS NXT** *or* **LEGO MINDSTORMS EV3** depending on which brick you have. **Picking the wrong one will fail to control the motors** — the protocols are different.
4. The Device Control screen opens. The address field shows "Select NXT brick…" or "Select EV3 brick…".
5. Tap the address field (or the **Scan** button). A list of paired Bluetooth devices appears.
6. Pick your brick. The address fills in automatically.
7. Tap **CONNECT**. Within 1–2 seconds the status pill turns green: **✓ Connected**.

> ✅ **Auto-connect:** Once you've connected once, the next time you open Aero with a LEGO type selected, it tries to reconnect automatically. The status pill briefly says "⟳ Auto-connecting…" then turns green. You don't have to tap Scan or Connect again until you change bricks.

#### Step 4 — Plug the motors into the right ports

By default Aero drives **port B (left)** and **port C (right)**. If your build wires the motors to different ports, that's fine — you can change the assignment in the LEGO settings (see Step 5).

```
NXT brick (3 motor ports)        EV3 brick (4 motor ports)
   A    B    C                      A    B    C    D
   │    │    │                      │    │    │    │
   │    └─ Left drive (default)     │    └─ Left drive (default)
   │         └─ Right drive         │         └─ Right drive (default)
   │              (default)         │              └─ free for arm/gripper
   └─ free for grippers/arms        └─ free for grippers/arms
```

Plug the motors using the standard LEGO black cables. The connector only fits one way, so you can't get it wrong physically.

#### Step 5 — Tune the brick (optional but recommended)

Tap the gear icon ⚙ at the top right of the Device Control screen. The settings panel slides out. Scroll to the **🟧 LEGO BRICK** section.

Everything in this section is optional — if you don't touch it, Aero uses sensible defaults. But these are the knobs you have:

| Setting | What it does | When you'd change it |
|---|---|---|
| **Left** | Which motor port is the left drive wheel | When you wired left to a port other than B |
| **Right** | Which motor port is the right drive wheel | When you wired right to a port other than C |
| **Inv** (next to Left or Right) | Flips that motor's direction | When the robot turns when you push forward — the easiest fix without rewiring |
| **Aux port** | Maps the right joystick to a single motor (e.g. a gripper) | When your build has an arm or gripper |
| **Aux axis** | Whether the right stick's X or Y axis drives the aux motor | Personal preference |
| **Brake on stop** | Whether motors brake actively when you release the joystick | Turn OFF for a smoother coast on a heavy chassis |
| **Swap stick X/Y** | Rotates the joystick 90° | If your phone is mounted sideways on a controller |
| **Max power** (20–100) | Hard cap on motor power | Lower this for kid-safe builds, or to protect a fragile attachment |
| **Deadband** (0–30) | Anything below this magnitude is treated as zero | Raise it if motors stutter when the joystick is barely off centre |
| **D-pad fwd / D-pad turn** | Powers used by the gamepad D-pad and direction buttons | Personal preference |
| **🔊 Beep** | Plays a quick test tone on the brick | Confirms the connection is alive |
| **↺ Reset** | Restores all the above to factory defaults | When you want a clean slate |

#### Step 6 — Drive!

Switch to any of the supported control modes (described below) and drive your robot.

**Which control modes work with LEGO?**

| Mode | Works on LEGO? | Notes |
|---|---|---|
| Custom Controls | ✅ Yes | See the LEGO command list in Section 6 |
| Joystick | ✅ Yes | Drives configured L/R motors |
| Tilt Control | ✅ Yes | Drives configured L/R motors |
| Gamepad (left stick + D-pad) | ✅ Yes | Same as Joystick / D-pad |
| RGB LED | ❌ Hidden | Bricks have no addressable RGB |
| Terminal | ✅ Yes | Send raw commands manually for testing |
| Timer / Countdown | ✅ Yes | Auto-fires LEGO commands at zero |
| IoT Dashboard | ❌ Hidden | LEGO sensor replies are binary; not yet parsed |
| Voice | ❌ Hidden | Voice presets target Arduino, not LEGO |
| IP Camera | ❌ Hidden | Bricks have no camera |

When LEGO is the active device, Aero **automatically hides** the modes that don't apply, so you won't see empty panels.

#### Step 7 — Custom buttons for grippers, arms, beeps, etc.

Switch to **Custom Controls** mode (the grid icon) and tap **✏️** to enter edit mode, then **＋ Add** to add a button. Use any of these as the button's command:

```
JOY:80,0           — full forward (instead of joystick)
STP                — stop drive motors
STOPALL            — stop ALL motors (A, B, C, D)
MOTOR:A:80         — run motor A at 80% forward
MOTOR:A:-80        — run motor A at 80% reverse
MOTOR:A:STOP       — stop motor A with brake
MOTOR:A:COAST      — stop motor A by coasting
TONE:880,250       — beep at 880 Hz for 250 ms
DPAD_LEFT          — quick left-spin using configured power
```

For a "hold to grip / release to stop" button, set **Command** to `MOTOR:A:80` and **Release / Off** to `MOTOR:A:STOP`. Holding the button runs the gripper motor; letting go stops it cleanly.

> 💡 **All of the above commands also work in the Terminal panel.** Type a command in the input box, hit send, and you'll see the brick respond. Useful for debugging your wiring before you build a fancy button layout.

#### Troubleshooting LEGO

| Symptom | Most likely fix |
|---|---|
| "No paired BT devices" toast when picking the brick | Pair the brick in Android Settings first (Step 2) |
| Phone scans but brick doesn't show up | Make sure brick's Bluetooth Visibility is ON (not just Bluetooth) |
| Connect succeeds but motors don't move | Check you picked NXT vs EV3 correctly; check motor cables; tap **🔊 Beep** to confirm the link works |
| Robot turns when you push forward | Tick the **Inv** switch on either Left or Right — easier than swapping cables |
| Motors stutter at small joystick angles | Raise the **Deadband** slider in LEGO settings |
| Brick disconnects randomly | Check battery level on the brick — low batteries cause Bluetooth to drop |
| EV3: brick beeps every few seconds after connect | That's normal — EV3 plays a short "I am connected" sound on each reconnect |
| Aero is frozen on "Connecting…" | Wait 15 seconds — first BT connection after a brick reboot can take that long. Then try Disconnect → Connect again |

---

## 4. Control Modes — Complete Guide

### 🎮 Custom Controls

The most flexible mode. Build any button layout you need.

<!-- Screenshot: custom_controls.png -->

**Entering Edit Mode**
1. Tap the **✏️ pencil icon** in the top bar
2. The grid turns into edit mode — buttons get an edit indicator

**Adding a Button**
1. Tap **＋ Add** at the bottom
2. Choose type: **Button**, **Hold Button**, **Toggle**, or **Slider**
3. Fill in the dialog:

| Field | Description | Example |
|---|---|---|
| **Label** | Text shown on button | `Arm Up` |
| **Command** | Sent when pressed | `ARM:UP\n` |
| **Release / Off** | Sent when released (Hold/Toggle) | `ARM:STOP\n` |
| **Col** | Column position (0–7) | `0` |
| **Row** | Row position (0 = top) | `2` |
| **Width** | How many columns wide (1 or 2) | `2` |
| **Color** | Hex color code | `#FF4444` |

**Button Types:**

| Type | Behavior | Use Case |
|---|---|---|
| **Button** | Sends command on tap | Simple actions (FWD, stop) |
| **Hold Button** | Sends on press, different cmd on release | Horn: `HRN:1` / `HRN:0` |
| **Toggle** | Alternates between on/off commands | LED on/off, relay |
| **Slider** | Sends command + value as you drag | Speed: `SPD:` + 0–255 |

**Moving a Button (Swap)**
Long-press a button → green highlight appears → tap another button to swap their positions.

**Profiles**

- **Switch**: tap the profile dropdown at the top
- **Save**: tap 💾 (saves current layout to active profile name)
- **New / Rename / Duplicate / Delete**: tap **⋮** next to the dropdown

> 💡 Each profile is stored independently. Great for having "Car Mode", "Arm Mode", "IoT Mode" etc. all saved and ready to switch.

---

### 🕹️ Joystick

Two virtual joysticks — left for linear/angular drive, right for camera pan/tilt.

**How it works:**
- Left joystick moves → sends `JOY:linear,angular` continuously while held
- Values range -255 to 255
- Release → sends `STP`

**Speed sliders** below the joysticks scale the maximum output (0–255).

**Right joystick** sends `RS:rx,ry` — wire this to a pan/tilt servo bracket.

**In your Arduino code:**
```cpp
// JOY:100,50 means: linear=100, angular=50
// Left motor  = linear + angular = 150
// Right motor = linear - angular = 50
// Result: curves right (differential drive)
```

---

### 📱 Tilt Control

Uses the phone's accelerometer/gyroscope. Tilt the phone to drive.

- **Forward / Backward:** Tilt phone toward/away from you
- **Left / Right:** Tilt phone sideways
- Sends `TILT:pitch,roll` in real time
- Or maps to `FWD/BWD/LFT/RGT` depending on threshold

> 💡 Hold the phone in landscape mode. Calibrate by keeping the phone level when you connect — that becomes "zero."

---

### 🎮 Gamepad

Connect a PS4, PS5, or Xbox controller to your Android phone via Bluetooth. Aero reads it through Android's InputEvent system.

**How to pair a PS4/PS5 controller:**
1. Hold PlayStation button + Share button until light flashes
2. Go to Android Bluetooth Settings → pair "Wireless Controller"
3. Open Aero → Gamepad mode is auto-detected

**Button mapping:**

| Controller | Command | Effect |
|---|---|---|
| Left stick | `JOY:linear,angular` | Drive |
| Right stick | `RS:rx,ry` | Camera / head |
| D-pad Up | `FWD` | Forward |
| D-pad Down | `BWD` | Backward |
| D-pad Left | `LFT` | Turn left |
| D-pad Right | `RGT` | Turn right |
| X / A button | Custom | Configurable |
| L2 / R2 triggers | Speed analog | 0–255 |

---

### 🌈 RGB LED

Pick any color → sends `RGB:r,g,b` to your device.

**Auto Mode:** Enable the **Auto** switch — the sliders send data live as you drag, no need to tap Send.

**Arduino wiring and code:** See [Section 7](#7-rgb-led-wiring--code).

---

### 💻 Terminal

Full serial monitor — shows every message received from your device and every command the app sends.

- **TX** (outgoing) shown in blue
- **RX** (incoming) shown in green
- Each line has a timestamp
- **Clear** button wipes the log
- **Send** field: type any raw command and send manually

Use this for **debugging**. If your robot isn't responding to a button, check the Terminal to confirm the command is actually being sent.

---

### ⏳ Timer

A countdown timer with auto-send capability.

1. Enter time in minutes and seconds
2. Press **Start**
3. When it reaches zero, if **Auto-send** is ON, the command in the field is sent

**Use cases:**
- Auto-stop a motor after 30 seconds
- Turn off a heater after 5 minutes
- Trigger an alarm relay

**Commands sent:**

| Event | Command |
|---|---|
| Start | `CD:START:totalMs` |
| Pause | `CD:PAUSE:remainingMs` |
| Reset | `CD:RESET` |
| Expires | Whatever you type in the command field (e.g. `STP\n`) |

---

### 📊 IoT Dashboard

The most powerful mode in the app. See [Section 5](#5-iot-sensor-dashboard--deep-dive) for the full deep-dive.

**Quick summary:** Send `SENSOR:name:value` from your Arduino/ESP and the IoT tab automatically creates a live widget for it. 10 widget types. Color-coded. Profiles. Live web dashboard.

---

### 🎤 Voice Control

Uses Google Speech Recognition. Speak a phrase → app matches it → sends the mapped command.

**Setup:**
1. Go to Voice tab
2. Add a voice trigger: e.g. phrase `"go forward"` → command `FWD\n`
3. Tap the microphone to start listening
4. Say your phrase — it appears in the text field
5. If it matches a trigger, the command is sent automatically

> 💡 Phrase matching is case-insensitive and partial (saying "forward" also matches "go forward").

---

### 📷 IP Camera

Displays a live MJPEG video stream from ESP32-CAM or any IP camera that serves MJPEG.

**Setup:**
1. Make sure your ESP32-CAM is on the same WiFi
2. Find its IP from Serial Monitor
3. Enter stream URL: `http://192.168.x.x:81/stream`
4. Tap the camera icon — video appears at the top of the screen

**Compatible streams:**
- ESP32-CAM (built-in example)
- Any IP camera with MJPEG stream URL

> 💡 The camera stream and the robot control connection are **independent**. You can stream from ESP32-CAM at port 81 while controlling motors via port 8080 simultaneously.

---

## 5. IoT Sensor Dashboard — Deep Dive

The IoT Dashboard is a full Blynk-style live monitoring system built directly into Aero. No cloud. No subscription. All local.

<!-- Screenshot: iot_dashboard.png -->

### How It Works

1. Your Arduino/ESP sends `SENSOR:name:value` over BT/BLE/WiFi
2. The IoT tab receives it → stores history (up to 500 readings per sensor in memory)
3. A widget auto-creates if it's a new sensor key
4. All widgets update live in real time

### Widget Types

| Widget | Best For | Auto-Created For |
|---|---|---|
| **Value** | Simple number display + sparkline | Any generic sensor |
| **Gauge** | Ranges (temp, pressure, battery) | `temp`, `humidity`, `pressure`, `light` |
| **Chart** | Trend over time | Any continuous sensor |
| **Bar** | Percentage or fill level | `battery`, `fuel`, `soil` |
| **LED** | On/Off state (PIR, relay, flame) | `pir`, `motion`, `status`, `relay` |
| **Compass** | Direction / heading | `compass`, `heading`, `dir` |
| **Terminal** | Raw log of all incoming data | `log`, `serial` |
| **Button** | Send a command to device | Manual add only |
| **Toggle** | On/off switch that sends commands | Manual add only |
| **Slider** | Send variable value to device | Manual add only |

### Managing Widgets

**Long-press** any widget to open the action menu:

| Action | Effect |
|---|---|
| ✏️ Edit | Change label, sensor key, command, unit, min/max, note, alert |
| 🎨 Color | Pick from 12 accent colors |
| ⤡ Resize | 5 preset sizes: 1×1, 2×1, 2×2, 4×1, 4×2 |
| 🧭 Move | Type Col (0–3) and Row (0+) to reposition |
| 📋 Duplicate | Copy the widget to a new position |
| 👁 Hide/Show | Hide a widget without deleting it |
| 🗑 Delete | Remove the widget permanently |

**Profiles:** tap the dropdown at the top → save different dashboard layouts per device. Tap 💾 to save, ⋮ for manage options.

**Lock mode:** tap the 🔓 icon to lock the layout — prevents accidental long-press edits.

### Alerts

Each widget supports high/low threshold alerts:

1. Edit the widget → enable **Alert**
2. Set **High** and **Low** values
3. When a reading goes outside the range → the widget border flashes red + phone vibrates

### Web Dashboard

The IoT tab also runs a mini web server on port **8080**. Open it from **any browser on the same WiFi** — laptop, tablet, second phone.

```
http://YOUR_PHONE_IP:8080
```

Find your phone's IP in Settings → WiFi → tap your network → IP address.

**What the web dashboard shows:**
- Live sensor cards with sparkline charts for every sensor
- Stats bar (top 4 sensors at a glance)
- LIVE / STALE badges (green = fresh data < 5s, yellow = stale)
- Sort cards by name or value
- Expand any card to see full history table with timestamps
- Export full history as CSV with one click
- Dark/light theme toggle

The web dashboard uses **WebSocket** for live push — data appears instantly without page refresh. If connection drops (e.g. your phone screen turns off), it auto-reconnects.

> 💡 The web dashboard is **read-only** — perfect for monitoring on a laptop while you use the phone app for control.

---

### Sensor Protocol

Every message from your Arduino/ESP to Aero that starts with `SENSOR:` is automatically routed to the IoT dashboard.

**Format:**
```
SENSOR:key:value\n
```

**Rules:**
- `key` = lowercase letters, no spaces (e.g. `temp`, `humidity`, `soil_moisture`)
- `value` = any number (integer or float)
- Must end with `\n` (newline) — `println()` adds this automatically
- Send from any connection type: BT, BLE, or WiFi

**Example (Arduino):**
```cpp
void sendSensorData() {
  // Temperature from LM35
  float tempC = analogRead(A0) * (5.0 / 1023.0) * 100.0;
  BTSerial.println("SENSOR:temp:" + String(tempC, 1));

  // Humidity from DHT11
  float hum = dht.readHumidity();
  if (!isnan(hum)) BTSerial.println("SENSOR:humidity:" + String(hum, 1));

  // Distance from HC-SR04
  long duration = pulseIn(ECHO_PIN, HIGH);
  float cm = duration * 0.034 / 2;
  BTSerial.println("SENSOR:distance:" + String(cm, 1));

  // PIR motion
  BTSerial.println("SENSOR:pir:" + String(digitalRead(PIR_PIN)));

  // Gas level (0–1023)
  BTSerial.println("SENSOR:gas:" + String(analogRead(MQ2_PIN)));

  delay(1000);  // Send every second
}
```

### Auto-Detected Sensor Names

Send these key names and the app automatically picks the right widget type and color:

| Key contains | Widget Type | Color | Icon |
|---|---|---|---|
| `temp`, `temperature` | Gauge | 🔴 Red | 🌡️ |
| `humidity`, `hum` | Gauge | 🔵 Blue | 💧 |
| `pressure` | Gauge | 🟣 Purple | 🔵 |
| `distance`, `ultrasonic` | Chart | 🟠 Orange | 📏 |
| `light`, `lux` | Gauge | 🟡 Yellow | 💡 |
| `gas`, `mq`, `co2` | Chart | 🩵 Teal | 💨 |
| `soil`, `moisture` | Bar | 🟢 Green | 🌱 |
| `voltage`, `current` | Value | 🟩 Lime | ⚡ |
| `pir`, `motion`, `status` | LED | default | 🚶 |
| `compass`, `heading`, `dir` | Compass | default | 🧭 |
| `log`, `serial` | Terminal | default | 💻 |
| anything else | Chart | 🟢 Green | 📊 |

---

### Wiring Popular Sensors

#### DHT11 / DHT22 — Temperature & Humidity

```
╔═══════════════════════════════════════════╗
║  Arduino          DHT11/DHT22             ║
║  ─────────        ──────────              ║
║  5V    ─────────  Pin 1 (VCC)             ║
║  Pin 2 ─────────  Pin 2 (DATA)            ║
║  GND   ─────────  Pin 4 (GND)             ║
║                                           ║
║  Also: 10kΩ pull-up resistor              ║
║  between DATA and VCC                     ║
╚═══════════════════════════════════════════╝
```

```cpp
#include <DHT.h>
DHT dht(2, DHT11);

void setup() { dht.begin(); }

void readDHT() {
  float t = dht.readTemperature();
  float h = dht.readHumidity();
  if (!isnan(t)) BTSerial.println("SENSOR:temp:" + String(t, 1));
  if (!isnan(h)) BTSerial.println("SENSOR:humidity:" + String(h, 1));
}
```

#### HC-SR04 — Ultrasonic Distance

```
╔═══════════════════════════════════════════╗
║  Arduino          HC-SR04                 ║
║  ─────────        ──────────              ║
║  5V    ─────────  VCC                     ║
║  Pin 9 ─────────  TRIG                    ║
║  Pin 8 ─────────  ECHO                    ║
║  GND   ─────────  GND                     ║
╚═══════════════════════════════════════════╝
```

```cpp
#define TRIG 9
#define ECHO 8

float readDistance() {
  digitalWrite(TRIG, LOW);  delayMicroseconds(2);
  digitalWrite(TRIG, HIGH); delayMicroseconds(10);
  digitalWrite(TRIG, LOW);
  return pulseIn(ECHO, HIGH) * 0.034 / 2;  // cm
}

// In loop: BTSerial.println("SENSOR:distance:" + String(readDistance(), 1));
```

#### MQ-2 — Gas Sensor

```
╔═══════════════════════════════════════════╗
║  Arduino          MQ-2                    ║
║  ─────────        ──────────              ║
║  5V    ─────────  VCC                     ║
║  GND   ─────────  GND                     ║
║  A0    ─────────  AOUT (analog)           ║
║  Pin 7 ─────────  DOUT (digital, optional)║
╚═══════════════════════════════════════════╝
```

```cpp
// In loop:
int gasLevel = analogRead(A0);  // 0–1023
BTSerial.println("SENSOR:gas:" + String(gasLevel));
```

#### BMP280 — Pressure & Temperature

```cpp
#include <Wire.h>
#include <Adafruit_BMP280.h>
Adafruit_BMP280 bmp;

void setup() {
  Wire.begin();
  bmp.begin(0x76);  // I2C address — use 0x77 if 0x76 fails
}

void readBMP() {
  BTSerial.println("SENSOR:temp:"     + String(bmp.readTemperature(), 1));
  BTSerial.println("SENSOR:pressure:" + String(bmp.readPressure() / 100.0F, 1));
  BTSerial.println("SENSOR:altitude:" + String(bmp.readAltitude(1013.25), 1));
}
```

---

## 6. Complete Command Reference

Every command the app sends ends with `\n` (newline). Your device reads until `\n` and processes. Use `readStringUntil('\n')` in your Arduino/ESP code.

> 💡 **Quick rule:** If it arrives at your device, it's in the tables below. If your device sends it back, it's in the "Device → App" table at the end.

---

### 🕹️ Custom Controls Mode

| Command | Example | When Sent | Description |
|---|---|---|---|
| *(anything you define)* | `FWD` | Button tap | Verbatim text from the "Command" field |
| *(anything you define)* | `ARM:STOP` | Hold button release | Text from the "Release / Off" field |
| `SPD:value` | `SPD:180` | Slider drag | Speed 0–255 from a speed slider |
| `RLY:1` / `RLY:0` | `RLY:1` | Toggle button | Relay / digital output on or off |

**Common patterns you can create:**
```
ARM:UP       — lift robotic arm
LIGHTS:ON    — turn on a lighting relay
PUMP:30      — trigger a pump for 30 seconds
MODE:AUTO    — switch device to autonomous mode
VALVE:OPEN   — open a water valve
FAN:1        — turn on a fan
```

---

### 🎮 Joystick Mode

| Command | Example | Range | Description |
|---|---|---|---|
| `JOY:linear,angular` | `JOY:150,50` | -255 to 255 each | Left stick — differential drive. Release sends `STP`. |
| `RS:rx,ry` | `RS:100,-50` | -255 to 255 each | Right stick — pan/tilt camera bracket |
| `SPD:value` | `SPD:200` | 0–255 | Speed slider 1 (scales left stick output) |
| `SPD2:value` | `SPD2:200` | 0–255 | Speed slider 2 (scales right stick output) |
| `STP` | `STP` | — | Sent automatically when stick returns to center |

**Differential drive math:**
```cpp
// JOY:150,50 → Left motor = linear + angular = 200, Right = 100 → curves right
Left  motor speed = constrain(linear + angular, -255, 255)
Right motor speed = constrain(linear - angular, -255, 255)
```

---

### 📱 Tilt Control Mode

| Command | Example | Range | Description |
|---|---|---|---|
| `TILT:pitch,roll` | `TILT:0.75,-0.30` | -1.0 to 1.0 | Continuous — phone pitch (fwd/bwd) and roll (left/right) |
| `FWD` | `FWD` | — | Discrete — sent when pitch exceeds forward threshold |
| `BWD` | `BWD` | — | Discrete — sent when pitch exceeds backward threshold |
| `LFT` | `LFT` | — | Discrete — sent when roll exceeds left threshold |
| `RGT` | `RGT` | — | Discrete — sent when roll exceeds right threshold |
| `STP` | `STP` | — | Sent when phone returns to neutral position |

**Tilt math in your code:**
```cpp
// TILT:pitch,roll — multiply by 255 to get motor speed
// positive pitch = phone tilted forward = go forward
else if (cmd.startsWith("TILT:")) {
  int c       = cmd.indexOf(',');
  float pitch = cmd.substring(5, c).toFloat();
  float roll  = cmd.substring(c + 1).toFloat();
  int linear  = (int)(pitch * 255.0);
  int angular = (int)(roll  * 255.0);
  setMotor(IN1, IN2, ENA, constrain(linear + angular, -255, 255));
  setMotor(IN3, IN4, ENB, constrain(linear - angular, -255, 255));
}
```

---

### 🎮 Gamepad Mode (PS4 / PS5 / Xbox)

**Analog inputs:**

| Command | Example | Range | Description |
|---|---|---|---|
| `JOY:linear,angular` | `JOY:200,-100` | -255 to 255 | Left analog stick — differential drive |
| `RS:rx,ry` | `RS:0,128` | -255 to 255 | Right analog stick — camera pan/tilt |
| `SPD:value` | `SPD:255` | 0–255 | L2 trigger — analog speed |
| `SPD2:value` | `SPD2:200` | 0–255 | R2 trigger — analog speed 2 |

**D-Pad (digital):**

| Command | PS4/PS5 | Xbox | Description |
|---|---|---|---|
| `DPAD_UP` | D-Pad ↑ | D-Pad ↑ | Drive forward |
| `DPAD_DOWN` | D-Pad ↓ | D-Pad ↓ | Drive backward |
| `DPAD_LEFT` | D-Pad ← | D-Pad ← | Turn left |
| `DPAD_RIGHT` | D-Pad → | D-Pad → | Turn right |

**Face buttons:**

| Command | PS4/PS5 Button | Xbox Button | Suggested Use |
|---|---|---|---|
| `BTN_A` | ✕ Cross | A | Primary action / confirm |
| `BTN_B` | ○ Circle | B | Secondary action / cancel |
| `BTN_X` | □ Square | X | Accessory toggle (LED/relay) |
| `BTN_Y` | △ Triangle | Y | Mode switch |

**Shoulder & trigger buttons:**

| Command | PS4/PS5 | Xbox | Suggested Use |
|---|---|---|---|
| `L1` | L1 | LB | Arm up / gripper open |
| `R1` | R1 | RB | Arm down / gripper close |
| `L2` | L2 (digital) | LT (digital) | Speed boost / secondary motor |
| `R2` | R2 (digital) | RT (digital) | Speed boost / secondary motor |
| `L3` | L3 (stick click) | LS | Extra function |
| `R3` | R3 (stick click) | RS | Extra function |

**System buttons:**

| Command | PS4/PS5 | Xbox | Description |
|---|---|---|---|
| `START` | Options | Menu | Start / pause sequence |
| `SELECT` | Create | View | Select / switch mode |
| `HOME` | PS button | Xbox button | Emergency stop / home |
| `TOUCHPAD` | Touchpad click | — | Extra function |
| `MUTE` | Mute | — | Toggle audio/buzzer |

---

### 🌈 RGB LED Mode

| Command | Example | Description |
|---|---|---|
| `RGB:r,g,b` | `RGB:255,128,0` | Set color — values 0–255 for each channel |

Sent continuously as you drag the color picker. Enable **Auto** switch for real-time updates without tapping Send.

---

### ⏳ Timer Mode

| Command | Example | When Sent | Description |
|---|---|---|---|
| `CD:START:ms` | `CD:START:30000` | Tap Start | Timer started — value is total milliseconds |
| `CD:PAUSE:ms` | `CD:PAUSE:18500` | Tap Pause | Timer paused — value is remaining milliseconds |
| `CD:RESUME:ms` | `CD:RESUME:18500` | Tap Resume | Timer resumed — value is remaining milliseconds |
| `CD:RESET` | `CD:RESET` | Tap Reset | Timer reset to zero |
| *(your command)* | `STP` | Timer hits zero | Whatever you typed in the Timer's send field |

---

### 🎤 Voice Control Mode

Voice commands work differently — you define them in the app. The phrase you speak is matched, and the **command you mapped to it** is sent. Those commands arrive at your device as normal commands listed in any section above.

| In-App Setup | What Gets Sent |
|---|---|
| Phrase: `"go forward"` → Command: `FWD` | `FWD` |
| Phrase: `"stop"` → Command: `STP` | `STP` |
| Phrase: `"turn on light"` → Command: `LED:1` | `LED:1` |
| Phrase: `"set speed"` → Command: `SPD:200` | `SPD:200` |

> 💡 Phrase matching is **case-insensitive** and **partial** — saying "forward" also triggers "go forward".

---

### 📊 IoT Dashboard Mode

The IoT dashboard receives data **from your device** (not the other way around). See the table below.

---

### Accessory Commands (any mode)

These can be triggered from Custom Buttons in any mode:

| Command | Example | Range | Description |
|---|---|---|---|
| `LED:1` / `LED:0` | `LED:1` | 0 or 1 | Single LED on/off |
| `BZR:1` / `BZR:0` | `BZR:1` | 0 or 1 | Buzzer on/off |
| `HRN:1` / `HRN:0` | `HRN:1` | 0 or 1 | Horn (hold = 1, release = 0) |
| `MOT:1` / `MOT:0` | `MOT:0` | 0 or 1 | Motor enable toggle |
| `RLY:1` / `RLY:0` | `RLY:1` | 0 or 1 | Relay on/off |
| `SRV:angle` | `SRV:90` | 0–180 | Servo angle in degrees |
| `SPD:value` | `SPD:180` | 0–255 | Speed (also from joystick slider) |

---

### Device → App (Incoming Data)

Your device sends these back to Aero over the same connection:

| Format | Example | Effect in App |
|---|---|---|
| `SENSOR:key:value` | `SENSOR:temp:25.3` | Creates / updates an IoT dashboard widget |
| `OK:CMD` | `OK:FWD` | Acknowledged — appears green in Terminal |
| `ERR:reason` | `ERR:UNKNOWN CMD` | Error — appears red in Terminal |
| *(anything else)* | `Hello!` | Appears as-is in Terminal log |

**Sensor key auto-detection:**

| Key contains | Widget Auto-Created | Color |
|---|---|---|
| `temp`, `temperature` | Gauge | 🔴 Red |
| `humidity`, `hum` | Gauge | 🔵 Blue |
| `pressure` | Gauge | 🟣 Purple |
| `distance`, `ultrasonic` | Chart | 🟠 Orange |
| `light`, `lux` | Gauge | 🟡 Yellow |
| `battery`, `fuel` | Bar | 🟢 Green |
| `pir`, `motion`, `status` | LED indicator | default |
| `compass`, `heading`, `dir` | Compass | default |
| `log`, `serial` | Terminal | default |
| anything else | Chart | 🟢 Green |

---

### 🟧 LEGO MINDSTORMS Mode (NXT and EV3)

LEGO commands are an extra vocabulary on top of the standard set above. They only do anything when the active device is a LEGO brick — Aero translates them into the LEGO Direct Commands binary protocol on the wire.

**Drive commands**

| Command | Example | Description |
|---|---|---|
| `JOY:lin,ang` | `JOY:80,0` | Differential drive on the configured Left + Right ports. Inputs >100 are normalised down to ±100 to match LEGO's power range. |
| `STP` | `STP` | Stop drive motors (brake or coast — see settings) |
| `STOPALL` | `STOPALL` | Stop *all* motors (A, B, C — and D on EV3) |
| `RS:rx,ry` | `RS:0,80` | Drive the configured aux motor. The axis (X or Y) and inversion are set in the LEGO panel. Ignored if Aux Port is "None". |
| `DPAD_UP` / `DPAD_DOWN` / `DPAD_LEFT` / `DPAD_RIGHT` | `DPAD_LEFT` | Fixed-power moves using the D-pad fwd / D-pad turn powers from the LEGO panel |

**Direct motor control (great for custom buttons)**

| Command | Example | Description |
|---|---|---|
| `MOTOR:port:power` | `MOTOR:A:80` | Run a single motor at the given power. Port is `A`, `B`, `C` (or `D` on EV3). Power is -100 to 100. |
| `MOTOR:port:STOP` | `MOTOR:A:STOP` | Brake-stop a single motor |
| `MOTOR:port:BRAKE` | `MOTOR:A:BRAKE` | Same as STOP — brake-stop |
| `MOTOR:port:COAST` | `MOTOR:A:COAST` | Coast-stop (motor freewheels to a halt) |

The separator can be `:` or `,` — `MOTOR:A:80`, `MOTOR,A,80`, and `MOTOR:A,80` all parse the same way.

**Sound**

| Command | Example | Description |
|---|---|---|
| `TONE:freq,dur` | `TONE:880,250` | Play a tone on the brick speaker. Frequency in Hz, duration in milliseconds. |

**What gets ignored on LEGO**

These commands are silently dropped when the device is a LEGO brick because no equivalent action exists on the brick:

```
LED:1 / LED:0      BZR:1 / BZR:0     RGB:r,g,b      SRV:angle
RLY:1 / RLY:0      MOT:1 / MOT:0     HRN:1 / HRN:0  TRG:l,r
SPD:value          SPD2:value        BTN_A          (any gamepad face button name)
START / SELECT / HOME / TOUCHPAD / MUTE / L1 / R1 / L2 / R2 / L3 / R3
```

The speed sliders (`SPD:` and `SPD2:`) still affect the joystick output **before** it's sent (they scale the values inside `JOY:`), so the slider you see in the app does work — it just doesn't fire a separate command on the LEGO side.

---

## 7. RGB LED Wiring & Code

### Common-Cathode RGB LED (most common)

```
╔═══════════════════════════════════════════╗
║  Arduino       RGB LED (Common Cathode)   ║
║  ─────────     ────────────────────────   ║
║  Pin 9  ──220Ω── Red pin                  ║
║  Pin 10 ──220Ω── Green pin                ║
║  Pin 11 ──220Ω── Blue pin                 ║
║  GND    ──────── Common Cathode (–)       ║
╚═══════════════════════════════════════════╝
```

### Common-Anode RGB LED

```
╔═══════════════════════════════════════════╗
║  Arduino       RGB LED (Common Anode)     ║
║  ─────────     ───────────────────────    ║
║  5V     ──────── Common Anode (+)         ║
║  Pin 9  ──220Ω── Red pin    (inverted!)   ║
║  Pin 10 ──220Ω── Green pin  (inverted!)   ║
║  Pin 11 ──220Ω── Blue pin   (inverted!)   ║
╚═══════════════════════════════════════════╝
```

> For common-anode, invert the values: `analogWrite(RED_PIN, 255 - r)`

### Arduino RGB Code

```cpp
#define RED_PIN   9
#define GREEN_PIN 10
#define BLUE_PIN  11

void setup() {
  pinMode(RED_PIN,   OUTPUT);
  pinMode(GREEN_PIN, OUTPUT);
  pinMode(BLUE_PIN,  OUTPUT);
}

// In processCommand():
if (cmd.startsWith("RGB:")) {
  int i1 = cmd.indexOf(',');
  int i2 = cmd.indexOf(',', i1 + 1);
  int r  = cmd.substring(4, i1).toInt();
  int g  = cmd.substring(i1 + 1, i2).toInt();
  int b  = cmd.substring(i2 + 1).toInt();

  // Common cathode — direct values
  analogWrite(RED_PIN,   r);
  analogWrite(GREEN_PIN, g);
  analogWrite(BLUE_PIN,  b);

  // Common anode — uncomment instead:
  // analogWrite(RED_PIN,   255 - r);
  // analogWrite(GREEN_PIN, 255 - g);
  // analogWrite(BLUE_PIN,  255 - b);

  BTSerial.println("OK:RGB");
}
```

### NeoPixel / WS2812B Strip

```cpp
#include <Adafruit_NeoPixel.h>

#define LED_PIN    6
#define LED_COUNT  8

Adafruit_NeoPixel strip(LED_COUNT, LED_PIN, NEO_GRB + NEO_KHZ800);

void setup() { strip.begin(); strip.show(); }

// In processCommand():
if (cmd.startsWith("RGB:")) {
  int i1 = cmd.indexOf(',');
  int i2 = cmd.indexOf(',', i1 + 1);
  int r  = cmd.substring(4, i1).toInt();
  int g  = cmd.substring(i1 + 1, i2).toInt();
  int b  = cmd.substring(i2 + 1).toInt();
  strip.fill(strip.Color(r, g, b));
  strip.show();
  BTSerial.println("OK:RGB");
}
```

---

## 8. App Settings & Customization

### Showing / Hiding Tabs

Tap the **⚙ gear icon** in the top bar to toggle visibility of each section:

| Toggle | Shows/Hides |
|---|---|
| Profile Bar | The profile switcher dropdown |
| Serial Monitor | The TX/RX log under the buttons |
| Mode Selector | The tab bar (Custom, Joystick, Tilt, etc.) |
| ESP Camera | The camera stream panel |
| RGB Tab | RGB LED color picker tab |
| Terminal Tab | Serial terminal tab |
| Timer Tab | Countdown timer tab |
| IoT Tab | IoT sensor dashboard tab |

All toggle states are saved and persist across app restarts.

### Light / Dark Mode

- Tap the **☰ hamburger menu** on the home screen
- Toggle between Light and Dark mode
- Changes apply app-wide instantly

### Custom Button Colors

Use hex codes in the button edit dialog:
```
#FF4444  — Red
#44CC66  — Green
#4488FF  — Blue
#FF9800  — Orange
#9C27B0  — Purple
#00BCD4  — Cyan
#FFAA00  — Amber
#FF6688  — Pink
```

---

## 9. Tips & Tricks

### Connection

- **HC-05 won't appear?** You must pair it in Android Bluetooth Settings first — the app can't pair unpaired devices.
- **BLE disconnects randomly?** Keep the phone closer to the module. BLE has good range but walls reduce it significantly.
- **WiFi ESP8266 connects but lags?** Reduce the sensor send interval — sending every 100ms over WiFi can cause TCP buffer buildup. Every 200–500ms is ideal.
- **Static IP for ESP:** Add before `WiFi.begin()`:
  ```cpp
  IPAddress ip(192,168,1,100), gateway(192,168,1,1), subnet(255,255,255,0);
  WiFi.config(ip, gateway, subnet);
  ```

### Custom Controls

- **Instant swap:** Long-press button A → button A glows → tap button B → they swap positions instantly. No dialog needed.
- **Make a wide stop button:** Set Width=2 on your STOP button and use color red `#FF2222` — hard to miss in a fast robot.
- **Profile per robot:** Create one profile per device (e.g. "Car", "Arm", "IoT Board"). Switching takes one tap.

### IoT Dashboard

- **Send sensors at different rates:** Not all sensors need to update at the same frequency. Send temperature every 5 seconds, distance every 100ms.
  ```cpp
  unsigned long lastTempSend = 0;
  unsigned long lastDistSend = 0;

  void loop() {
    if (millis() - lastTempSend > 5000) {
      BTSerial.println("SENSOR:temp:" + String(readTemp(), 1));
      lastTempSend = millis();
    }
    if (millis() - lastDistSend > 200) {
      BTSerial.println("SENSOR:distance:" + String(readDist(), 1));
      lastDistSend = millis();
    }
  }
  ```

- **Web dashboard for monitoring:** Leave the web dashboard open on a laptop at `http://phone-ip:8080` while using the phone for control. You get both simultaneously.
- **Export CSV:** Tap the ↓ CSV button on the web dashboard to export all sensor history with timestamps — useful for data logging experiments.
- **STALE badge:** If a sensor stops sending for more than 5 seconds, its badge turns yellow "STALE" and the widget dims. Great for spotting sensor dropouts.
- **Long key names:** Use underscores instead of spaces: `soil_moisture`, `left_motor_temp`. Works fine.

### Joystick Mode

- **Deadzone:** The joystick has a built-in dead zone — small finger jitter near center doesn't send commands. Good for phones with slightly off-center touch.
- **Speed slider:** Start with speed at 50% when testing a new robot. Full speed immediately can be dangerous with high-torque motors.

### Terminal

- **Always open Terminal first** when wiring a new project. Press any button — if you see `TX> FWD` but nothing happens on the robot, the problem is in your wiring or code, not the app.
- **Echo your commands:** Add `BTSerial.println("OK:" + cmd)` in your Arduino code. The terminal shows what the device received, confirming the message got through.

### Performance

- **Long delay() calls block everything.** Use `millis()` for timing in your loop so the serial buffer doesn't fill up while delay is running.
- **Don't use Serial.print() inside a fast loop** — it slows down command processing. Only print what you need.

---

## 10. Troubleshooting

| Problem | Likely Cause | Fix |
|---|---|---|
| HC-05 not in scan list | Not paired in Android settings | Go to Android Settings → Bluetooth → pair HC-05 first (PIN: 1234 or 0000) |
| HC-05 paired but won't connect | Wrong baud rate in code | Make sure `BTSerial.begin(9600)` — HC-05 default is 9600 |
| WiFi won't connect | Phone and ESP on different networks | Both must be on the same 2.4 GHz WiFi. 5 GHz won't work with ESP8266. |
| WiFi connects but commands fail | Wrong IP or port | Open Serial Monitor on ESP — it prints the IP. Double-check port `8080`. |
| Commands received but motors don't move | Wiring issue | Check motor driver wiring. Test LED first — if LED works, issue is motor driver. |
| Motors spin wrong direction | IN1/IN2 reversed | Swap IN1 and IN2 (or IN3 and IN4) wires on motor driver |
| IoT cards don't appear | Wrong format | Format must be exactly `SENSOR:name:value\n` — no spaces, lowercase name |
| IoT widgets show stale immediately | No data arriving | Check Terminal tab — can you see the SENSOR lines? If not, check code/wiring. |
| Web dashboard can't connect | Phone not on WiFi | The web server needs phone WiFi to be reachable. BT/BLE connection to device is separate. |
| Joystick sends nothing | Connection not active | Check connection status bar at top — must show green "Connected" |
| RGB colors look wrong | Common anode LED | Try inverted values: use `255 - r`, `255 - g`, `255 - b` in your code |
| App freezes on connect | Multiple connect attempts | Force-close the app, reopen, reconnect once |
| Terminal shows garbage characters | Baud mismatch | Match baud rate in your Arduino code exactly to what the module uses |
| Voice control not working | Microphone permission denied | Settings → Apps → Aero → Permissions → Microphone → Allow |
| Camera stream not showing | Wrong URL or port | Try accessing `http://esp-ip:81/stream` in phone browser first |
| HC-05 voltage divider gets hot | Resistor values wrong | Use exactly 1kΩ series and 2kΩ to GND. Total resistance to GND must be ≥ 2kΩ. |

---

## 11. FAQ

**Q: Can I use Aero with an ESP32 and HC-05 at the same time?**
A: No — choose one connection method. The app connects to one device at a time.

**Q: How many custom buttons can I have?**
A: Unlimited rows. The grid scrolls vertically. Practically tested up to 50+ buttons without performance issues.

**Q: Can I use Aero without a WiFi network (direct ESP Access Point)?**
A: Yes! Configure the ESP as a WiFi Access Point:
```cpp
WiFi.softAP("Aero-Robot", "12345678");
Serial.println(WiFi.softAPIP());  // Usually 192.168.4.1
```
Then connect your phone to the "Aero-Robot" WiFi network and use IP `192.168.4.1:8080`.

**Q: Does Aero work with Raspberry Pi?**
A: Yes — if the Pi is running a TCP server on port 8080, Aero (WiFi mode) connects to it. You'd write a Python script that reads commands via socket.

**Q: Can two phones control the same robot?**
A: Not simultaneously. One phone connects at a time. For multi-user control, consider building a relay layer on the ESP that accepts multiple TCP clients.

**Q: Is my data sent to the cloud?**
A: No. Everything is strictly local — phone to device over your local network or Bluetooth. No data leaves your network.

**Q: The IoT web dashboard — who can access it?**
A: Anyone on the same WiFi network as your phone. It's a local-only server — not accessible from the internet. No authentication is implemented (it's designed for personal/lab use).

**Q: Can I rename sensor keys after creating them?**
A: Yes — tap the widget, tap Edit, change the Sensor Key field to the new key name, save. The widget will then update when that new key arrives.

**Q: My ESP keeps resetting randomly under load. Why?**
A: Usually a power issue. Motors draw heavy current spikes. Always power motors from a separate supply, and make sure the ESP has its own stable 3.3V/5V source. Add a 100µF capacitor on the ESP power pins.

**Q: How do I add a servo to my robot?**
A: Wire servo signal to a PWM pin (e.g. Pin 9 on Arduino), add `#include <Servo.h>`, and handle `SRV:angle` command. See the command reference and Arduino code samples above.

---

### Adding New Commands

Your Arduino handles any command string — just add an `else if` branch:
```cpp
else if (cmd.startsWith("MYCOMMAND:")) {
  int val = cmd.substring(10).toInt();
  // do something with val
  BTSerial.println("OK:MYCOMMAND:" + String(val));
}
```

Then in Aero, create a Custom Button with command `MYCOMMAND:42\n`.

To add a new command on the **LEGO side**, edit the `interpretCommand` function in `LegoNxtConnection.kt` and/or `LegoEv3Connection.kt`. Add a `when` branch for your command prefix and emit the appropriate LEGO bytecode using the existing `writeBytes()` helper.


### Protocol Notes

- Arduino / ESP commands are plain UTF-8 text terminated by `\n`
- LEGO commands are translated to a length-prefixed binary protocol — the user still types/configures plain text in Aero
- No handshake or authentication for Arduino / ESP — trust network/pairing for security
- LEGO bricks require Bluetooth pairing (PIN `1234`) which provides the same trust boundary
- Max practical command frequency: ~50 Hz over BT, ~200 Hz over WiFi, ~30 Hz over LEGO BT

---

## 12. 🤖 AI Code Generation — Let AI Write Your Device Code

Aero uses a plain-text protocol, which means any AI assistant (ChatGPT, Claude, Gemini, Copilot, etc.) can generate complete, working Arduino/ESP code for your specific project in seconds.

Just **copy the prompt below**, fill in your hardware details, and paste it into any AI chat.

> 💡 **Note for LEGO MINDSTORMS users:** You don't need to generate any code for LEGO bricks — the brick's stock firmware already speaks the LEGO Direct Commands protocol that Aero handles natively. Skip this section if you're only using LEGO.

---

### 📋 The Universal Aero AI Prompt

Copy this entire block and paste it into any AI assistant:

---

```
I am building a project controlled by the Aero (U-Robot Link) Android app.
Aero sends plain-text TCP commands over WiFi (port 8080) or over
Bluetooth/BLE serial. All commands are terminated with a newline (\n).
The device reads commands using readStringUntil('\n') and responds with
plain-text ACK messages like "OK:CMD\n".

Here is the complete Aero command protocol:

MOVEMENT:
  FWD              — go forward
  BWD              — go backward
  LFT              — turn left
  RGT              — turn right
  STP              — stop all motors
  JOY:linear,angular  — differential drive, values -255 to 255
  RS:rx,ry            — right stick / camera pan-tilt, values -255 to 255
  SPD:value           — set speed 0–255
  SPD2:value          — second speed 0–255
  TILT:pitch,roll     — tilt control, values -1.0 to 1.0

ACCESSORIES:
  LED:1 / LED:0       — LED on/off
  BZR:1 / BZR:0       — buzzer on/off
  HRN:1 / HRN:0       — horn press/release
  RLY:1 / RLY:0       — relay on/off
  MOT:1 / MOT:0       — motor enable
  RGB:r,g,b           — RGB LED color (0–255 each)
  SRV:angle           — servo position 0–180 degrees

GAMEPAD FACE BUTTONS:
  BTN_A / BTN_B / BTN_X / BTN_Y

GAMEPAD SHOULDER/TRIGGERS:
  L1 / R1 / L2 / R2 / L3 / R3

GAMEPAD D-PAD:
  DPAD_UP / DPAD_DOWN / DPAD_LEFT / DPAD_RIGHT

GAMEPAD SYSTEM:
  START / SELECT / HOME / TOUCHPAD / MUTE

TIMER:
  CD:START:ms     — timer started (total milliseconds)
  CD:PAUSE:ms     — timer paused (remaining milliseconds)
  CD:RESUME:ms    — timer resumed (remaining milliseconds)
  CD:RESET        — timer reset

IOT SENSOR OUTPUT (device sends TO app):
  SENSOR:key:value\n   — e.g. SENSOR:temp:25.3
  The app auto-creates dashboard widgets for each key.
  Known keys: temp, humidity, pressure, distance, light, gas,
              soil, battery, pir, motion, compass, heading, voltage

RESPONSE FORMAT (device → app):
  OK:CMD           — command acknowledged
  ERR:reason       — error message
  SENSOR:key:value — sensor data for IoT dashboard
  IP:x.x.x.x      — device IP (response to "IP" query)

My hardware: [DESCRIBE YOUR HARDWARE HERE — see examples below]

Please generate complete, ready-to-upload Arduino/ESP code that:
1. Connects to WiFi (for ESP) or SoftwareSerial (for Arduino + HC-05)
2. Handles ALL the Aero commands relevant to my hardware
3. Includes comments explaining each command handler
4. Sends ACK responses back to the app for every command
5. Optionally sends sensor data back using SENSOR:key:value format

[ADD ANY EXTRA REQUIREMENTS HERE]
```

---

### Hardware Description Examples

Replace the `[DESCRIBE YOUR HARDWARE HERE]` section with your specific hardware:

#### Example A — Basic RC Car (ESP8266 + L298N)
```
My hardware:
- ESP8266 NodeMCU
- L298N motor driver: ENA=14(D5), ENB=12(D6), IN1=5(D1),
  IN2=4(D2), IN3=13(D7), IN4=2(D4)
- WiFi SSID: MyNetwork, Password: mypassword123
- I want joystick, tilt, and gamepad D-pad to all drive the motors
- Speed should be adjustable via SPD: command
```

#### Example B — Robot Arm (Arduino + HC-05 Bluetooth)
```
My hardware:
- Arduino Mega
- HC-05 on pins 10 (RX) and 11 (TX), baud 9600
- 4 servo motors on pins 3, 5, 6, 9
- I want: joystick left stick → base rotation (servo on pin 3)
  BTN_A → gripper open (servo pin 9 to 0°)
  BTN_B → gripper close (servo pin 9 to 180°)
  L1/R1 → shoulder up/down (servo pin 5)
  L2/R2 → elbow up/down (servo pin 6)
```

#### Example C — IoT Sensor Dashboard (ESP32)
```
My hardware:
- ESP32
- DHT22 temperature + humidity sensor on pin 21
- HC-SR04 ultrasonic distance sensor: TRIG=18, ECHO=19
- MQ-2 gas sensor on analog pin 34
- LED on pin 2, relay on pin 4
- WiFi SSID: HomeNet, Password: home12345
- I want sensor data sent every 2 seconds
- LED:1/0 and RLY:1/0 commands to control outputs
```

#### Example D — FPV Camera Robot (ESP32-CAM)
```
My hardware:
- ESP32-CAM (AI-Thinker)
- Motor driver on pins 13, 15, 2, 14 (no ENA/ENB PWM - camera uses those pins)
- Camera stream on port 81
- Control on port 8080
- WiFi SSID: RobotNet, Password: robot123
- I want FWD/BWD/LFT/RGT movement and gamepad D-pad
- No speed control needed (just full speed on/off)
```

#### Example E — Home Automation (Raspberry Pi / Python)
```
My device:
- Raspberry Pi running Python
- I need a Python TCP server script on port 8080
- GPIO 17 = LED, GPIO 27 = relay, GPIO 22 = buzzer
- Read DHT11 on GPIO 4 and send temp/humidity as SENSOR data
- Handle LED:, RLY:, BZR:, STP commands
- Send SENSOR:temp and SENSOR:humidity every 5 seconds
```

---

### What the AI Will Generate

After pasting the prompt with your hardware details, the AI will produce:

| Output | Description |
|---|---|
| Complete `.ino` or `.py` file | Ready to upload — no copy-pasting fragments |
| All command handlers | Every relevant Aero command with proper parsing |
| WiFi/BT setup | Complete connection code for your board |
| Sensor output loop | `SENSOR:key:value` lines with real sensor reads |
| Pin definitions | All `#define` constants at the top |
| Motor functions | `forward()`, `backward()`, `turnLeft()`, `turnRight()`, `stopAll()` |
| ACK responses | `OK:CMD` replies the Terminal tab can verify |

---

### Pro Tips for AI Prompting

- **Be specific about pins.** "L298N with ENA on pin 9" is better than "L298N connected."
- **List which control modes you'll use.** Joystick? Gamepad? Tilt? Voice? Only those commands need handlers.
- **Ask for sensor output.** "Send temp every 2 seconds" gets you a complete non-blocking sensor loop.
- **Mention your WiFi network name and password** (or ask the AI to use placeholder constants).
- **Ask for comments.** Add "add a comment above every command handler explaining what it does."
- **Iterate.** After the first generation, say "now add a servo on pin 9 controlled by SRV: command" — the AI knows the protocol from your first prompt.

---

<div align="center">

---

**Made with ♥ in the Philippines 🇵🇭**

Developed by **Engr. J R Cabataña, ECT**

[![GitHub](https://img.shields.io/badge/GitHub-engrpanda%2FAero__U--Robot--Link-181717?style=flat-square&logo=github)](https://github.com/engrpanda/Aero_U-Robot-Link)

*If Aero helped your project, consider leaving a ⭐ on GitHub or a review on the Play Store!*

</div>
