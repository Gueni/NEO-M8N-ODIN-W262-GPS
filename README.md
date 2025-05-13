# GPS Module with PS/2 Programming Trigger
This project features a dual GPS/Bluetooth PCB design using:

- **NEO-M8N** (Part: `672-NEO-M8N-0TR-ND`) for GNSS positioning  
- **ODIN-W262** (Part: `672-ODIN-W262-05BTR-ND`) for Bluetooth communication  
- A custom **PS/2-based connector** to enable programming mode automatically via pin shorting

The system is compact, enclosed, and fully programmable without disassembly — using a smart GND-detection feature via the PS/2 port.

---

## 💡 Features

- **GPS**: Multi-GNSS (GPS, GLONASS, Galileo, BeiDou) via NEO-M8N
- **Bluetooth**: Dual-mode BLE + classic via ODIN-W262
- **Enclosure**: Compact PCB with enclosure support
- **Programming Mode**: Automatically enabled when PS/2 connector is plugged in — GND pin shorts internal detection line
- **Power**: 3.3V operation with onboard LDO regulators
- **I/O**: Exposed UART for debug or data streaming
- **Connector**: 6-pin PS/2 Mini-DIN style programming interface

---

## 🔌 Pinout (PS/2 Connector)

| PS/2 Pin | Function         |
|----------|------------------|
| Pin 1    | VCC (3.3V)       |
| Pin 2    | TX (to programmer) |
| Pin 3    | RX (from programmer) |
| Pin 4    | GND              |
| Pin 5    | GND detect (shorted when inserted) |
| Pin 6    | NC / Reserved    |

*Ensure the PS/2 plug is inserted fully to engage GND detect pin.*

---

## 🛠 Programming Instructions

1. Plug in the PS/2 connector from the programming device.
2. This triggers programming mode automatically.
3. Use the provided UART interface at 3.3V levels.
4. Flash via standard tools (e.g., STM32CubeProgrammer, esptool.py, depending on MCU).

---

## 🧪 Testing & Debug

- LED indicators show GNSS fix and BT activity
- Test programming mode with multimeter: verify GND detect line goes LOW when PS/2 is inserted
- Firmware should check the GND detect pin at startup to enter bootloader

---




