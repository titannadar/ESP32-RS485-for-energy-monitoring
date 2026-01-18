# ESP32 RS485 Isolated Interface for Energy Monitoring

A complete 2-layer PCB design featuring ESP32 with fully integrated galvanically isolated RS485 interface. All isolation, protection, and transceiver components are on a single PCB - no external modules required.

![Project Status](https://img.shields.io/badge/status-active-success)
![License](https://img.shields.io/badge/license-MIT-blue)
![Hardware Version](https://img.shields.io/badge/hardware-v1.0-green)

---

## 🎯 Key Features

- **ESP32-WROOM-32U** with external WiFi antenna
- **2500V Galvanic Isolation** (ADUM1201 digital isolator)
- **600W Lightning/Surge Protection** (GDT + TVS multi-stage)
- **±15kV ESD Protection** 
- **Isolated DC-DC Power** (B0505S-1WR2)
- **RS485 Transceiver** (MAX485/SP485EE)
- **Auto Direction Control** (no manual DE/RE needed)
- **Single PCB Design** - No external modules

---

## 📋 Specifications

| Parameter | Value |
|-----------|-------|
| Input Voltage | 5V DC |
| ESP32 Supply | 3.3V (via AMS1117 LDO) |
| RS485 Supply | 5V Isolated (via B0505S) |
| Isolation Voltage | 2500V RMS |
| Surge Protection | 600W (8/20µs) |
| ESD Protection | ±15kV HBM |
| Baud Rate | Up to 115200 bps |
| Bus Length | Up to 1200m |
| PCB Size | 80mm × 50mm |
| Layers | 2-layer FR-4 |

---

## 🔧 Applications

- Energy Monitoring Systems
- Modbus RTU Communication
- Industrial Automation
- Smart Metering
- Building Management Systems
- SCADA Integration

---

## 📁 Repository Structure

```
├── Hardware/
│   ├── Schematics/           # Complete schematic files
│   ├── PCB/                  # PCB layout guidelines
│   └── BOM/                  # Bill of Materials
├── Firmware/
│   └── Arduino/              # Test firmware
├── Documentation/            # Design guides
└── README.md
```

---

## 🔌 Key Components

| Component | Part Number | Function |
|-----------|-------------|----------|
| U1 | AMS1117-3.3 | 3.3V LDO Regulator |
| U2 | ESP32-WROOM-32U | WiFi/BT MCU |
| U3 | ADUM1201ARZ | Digital Isolator (2500V) |
| U4 | MAX485ESA+ / SP485EEN | RS485 Transceiver |
| U5 | B0505S-1WR2 | Isolated DC-DC (5V→5V) |
| GDT1 | 2026-09-SM | Gas Discharge Tube (90V) |
| TVS1 | SMBJ12CA | TVS Diode (600W) |
| TVS2 | PESD5V0S2BT | ESD Protection Array |

---

## 📊 Block Diagram

```
┌─────────┐    ┌─────────┐    ┌──────────────┐
│  5V DC  │───▶│  3.3V   │───▶│    ESP32     │
│  Input  │    │   LDO   │    │  WROOM-32U   │
└─────────┘    └─────────┘    └──────┬───────┘
                                     │ UART2
     ════════════════════════════════╪════════════════
                ISOLATION BARRIER    │
     ════════════════════════════════╪════════════════
                                     │
┌─────────┐    ┌─────────┐    ┌──────┴───────┐    ┌──────────┐
│Isolated │───▶│ Digital │───▶│    RS485     │───▶│Protection│───▶ A/B/GND
│  DC-DC  │    │Isolator │    │ Transceiver  │    │ Circuit  │
└─────────┘    └─────────┘    └──────────────┘    └──────────┘
```

---

## 🛡️ Protection Features

### Multi-Stage Surge Protection
1. **Stage 1 - GDT**: Gas Discharge Tube (90V, 2.5kA)
2. **Stage 2 - TVS**: Transient Voltage Suppressor (600W)
3. **Stage 3 - ESD**: Low capacitance ESD array (±15kV)

### Isolation
- **Digital Isolation**: ADUM1201 (2500V RMS reinforced)
- **Power Isolation**: B0505S-1WR2 (1500V DC)
- **PCB Gap**: 4mm minimum between isolated zones

---

## 🚀 Getting Started

1. Clone this repository
2. Review schematics in `Hardware/Schematics/`
3. Check BOM in `Hardware/BOM/`
4. Fabricate PCB using provided guidelines
5. Flash test firmware from `Firmware/Arduino/`

---

## 📜 License

- **Hardware**: CERN-OHL-P v2
- **Software**: MIT License

---

## 🔗 Links

- [Repository](https://github.com/titannadar/ESP32-RS485-for-energy-monitoring)
- [Issues](https://github.com/titannadar/ESP32-RS485-for-energy-monitoring/issues)

---

**Made for Energy Monitoring Applications** ⚡