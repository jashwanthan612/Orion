                 ESP32 Dev Board
 -------------------------------------------------
 | 26 → IN1      27 → IN2                        |
 | 14 → IN3      12 → IN4                        |
 | 5  → TRIG     18 → ECHO                       |
 | 34 → Line L   35 → Line R                     |
 -------------------------------------------------

                 L298N
       IN1 IN2 IN3 IN4 → Motors
       12V ← Battery



🧠 ESP32 Dev Board – Pin Allocation
🔹 Motor Driver (L298N)
ESP32 Pin	Connects To	Function
GPIO26	IN1	Left motor direction 1
GPIO27	IN2	Left motor direction 2
GPIO14	IN3	Right motor direction 1
GPIO12	IN4	Right motor direction 2
GND	GND	Common ground
🔹 Ultrasonic Sensor (HC-SR04)
ESP32 Pin	Connects To
GPIO5	TRIG
GPIO18	ECHO
5V	VCC
GND	GND

⚠️ If unstable, use voltage divider on ECHO (ESP32 is 3.3V logic).

🔹 Line Sensors (2×)
Sensor	ESP32 Pin
Left OUT	GPIO34
Right OUT	GPIO35
VCC	3.3V
GND	GND

(GPIO34 & 35 are input-only → perfect choice.)

🔋 Power Diagram

Battery → L298N 12V
Battery → Buck Converter → 5V → ESP32 VIN

All grounds connected together.

📷 ESP32-CAM Wiring (Independent)

During normal operation:

ESP32-CAM	Connection
5V	5V stable supply
GND	GND

No connection to main ESP32 required.

Communication is via Wi-Fi router.

🚫 Pins We Avoided (Important)

Do NOT use:

GPIO0 (boot pin)

GPIO2 (boot sensitive)

GPIO15 (boot sensitive)

GPIO6–11 (flash memory pins)

This keeps ORION reliable.
