# ESP32-C3 Star Matrix Hardware System

A custom geometric hardware system designed in Altium Designer featuring a star-shaped PCB that drives 35 surface-mount LEDs. The system utilizes an ESP32-C3 microcontroller and discrete low-side N-channel MOSFET switching arrays to achieve independent multiplexed branch control.

## 3D Design Preview
<p align="center">
  <img src="./design/front_render.png" width="45%" alt="PCB Front View" />
  <img src="./design/back_render.png" width="45%" alt="PCB Back View" />
</p>
<p align="center"><em>Figure 1: Complete 3D CAD models generated via Altium Designer.</em></p>

---

## Technical Specifications & Circuit Architecture

*   **Core Microcontroller:** ESP32-C3-WROOM-02-N4 (RISC-V single-core architecture with integrated Wi-Fi/BLE).
*   **LED Array & Driver Matrix:** 35 SMT LEDs arranged into 5 independent branches (7 parallel LEDs per branch) corresponding to the star's geometry. 
*   **Low-Side Switching Control:** Driven by 5 discrete AO3400A N-channel MOSFETs acting as low-side switches connected directly to ESP32-C3 GPIOs (`IO0` - `IO4`) for efficient power multiplexing.
*   **Power Management:** Dual-source power architecture (USB Type-C or external battery connector input) protected via SS24T3G Schottky diodes.
*   **Voltage Regulation:** Integrated AP2112K-3.3V low-dropout (LDO) linear regulator supplying stable `3V3` to the MCU, optimized with standard input/output decoupling capacitor networks.
*   **System Peripherals:** Built-in hardware RC reset circuit, hardware boot-option selector switch (`IO9`), and compliant $5.1\text{k}\Omega$ configuration channel (CC) pull-down resistors for USB-C power delivery negotiation.

---

## Engineering Project Milestones
- [x] **Schematic Capture:** Completed circuit architecture, discrete multiplexing control logic, and Electrical Rule Checks (ERC).
- [x] **PCB Layout & Routing:** Defined custom star geometry boundary rules, aligned SMT components, and completed 100% trace routing optimization.
- [x] **Manufacturing Preparation:** Production-ready Gerber data packages and NC Drill files fully generated.
- [ ] **Hardware Population:** Surface-mount technology component population and reflow soldering pending.
- [ ] **Firmware Architecture:** Bare-metal C branch-multiplexing and dynamic LED animation algorithms to be implemented.

---

## 📂 Repository Layout
* `/design`: Source design files, including Altium schematic (`.SchDoc`) and layout (`.PcbDoc`).
* `/manufacturing`: Complete production-ready manufacturing packages.
