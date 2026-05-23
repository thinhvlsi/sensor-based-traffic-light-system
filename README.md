# Traffic Light and Red-Light Violation Detection System Using Digital ICs

<br>
<div align="center">
  <img width="100%" alt="real-circuit" src="https://github.com/user-attachments/assets/34bc7113-d394-4c1c-a609-1f43ba9830c4" />
</div>
<br>

This is a digital hardware design project that involves simulating and fabricating a basic traffic light system integrated with a countdown timer and a violation warning mechanism. The highlight of this project is that the circuit is designed entirely using primitive digital ICs, **without the use of any microcontrollers or Arduino boards**.

## 🎯 Main Features
- **Automatic control** of the traffic light cycle (Green - Yellow - Red).
- **Countdown time display** for each phase using 7-segment LEDs.
- **Red-light violation warning:** Integrates an infrared (IR) sensor to detect motion. This sensor is logically designed to *only activate the warning system during the red light phase*.

## ⚙️ Operating Principle

<br>
<div align="center">
  <img width="853" height="653" alt="Block Diagram" src="https://github.com/user-attachments/assets/2dc94270-c066-41cf-9f5b-e3899bd4839e" />
</div>
<br>

- **Clock & Counting Block:** The square wave pulse from the NE555 timer is fed into the clock pin of the 74192 IC. The 74192 counts and outputs the BCD (Binary-Coded Decimal) code.
- **Display Block:** The BCD code is passed through the 74247 IC for decoding, pulling the corresponding pins LOW to drive the 7-segment LEDs, displaying the countdown value.
- **Violation Sensor Block:** To ensure the sensor only triggers an alarm when a vehicle runs a red light, the output of the IR sensor and the red light phase signal (from the Q0 pin of the 4017 IC) are passed through an AND logic gate (7408 IC). Therefore, the AND gate ensures the correct logic condition: only when the Red light is ON (Logic 1) AND the sensor detects motion (Logic 1) will the warning siren/light be activated.

## 🛠️ Hardware Components
The system utilizes basic 74LS/HC and CMOS series ICs:
- **NE555 Module:** Acts as the clock pulse generator for the system.
- **CD4017 IC:** 10-stage Johnson counter used to count and control the light phase transitions.
- **74147 IC:** 10-line to 4-line priority encoder.
- **74192 IC:** Up/Down BCD counter (used for the countdown timer).
- **74247 IC:** BCD to 7-segment decoder/driver (common anode).
- **7404 IC:** Hex inverter (NOT gates) to invert logic levels.
- **7408 IC:** Quad 2-input AND gates, used to lock/unlock the sensor activation condition.
- **Infrared (IR) Sensor:** Detects moving objects.
- **LEDs:** 7-segment displays and standard LEDs (Red, Yellow, Green).

## 💻 Tools & Practical Results

<br>
<div align="center">
  <img width="100%" alt="Proteus Simulation" src="https://github.com/user-attachments/assets/516f00b7-d4f4-4c95-aafa-cbeab9d27daf" />
</div>
<br>

- **Design & Simulation Software:** The system's schematic was successfully designed and simulated using **Proteus**.
- **Physical Hardware:** Successfully performed PCB layout design, board printing, component placement, and soldering.
- **Result:** The hardware circuit operates exactly according to the intended cycle, transitions phases correctly, the 7-segment LEDs display clearly, and the red-light violation detection sensor works flawlessly.

<br>
<div align="center">
  <img width="100%" alt="Final Hardware" src="https://github.com/user-attachments/assets/16da6a4c-0b7b-4b51-b2aa-f0a46b32004d" />
</div>
<br>

## 👥 Contributors
*This project was implemented by students from the University of Science, VNU-HCM (Group L):*
- Võ Thái Minh Triều (23130249)
- Nguyễn Thị Kiều Trang (23130248)
- Lê Quốc Thịnh (23130236)
- Đinh Việt Quang (23130212)
