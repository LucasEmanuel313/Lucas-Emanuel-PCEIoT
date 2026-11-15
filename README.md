# PCEIoT: Sensor Platform PCB for IoT

PCEIoT is a battery-powered IoT sensor board designed in Altium Designer. It combines environmental, motion, light and sound sensing with a Raspberry Pi Pico W, a 0.96" OLED display, user inputs and a mikroBUS socket for expansion boards.

This project produced a physical board. After design, layout and assembly, the assembled PCEIoT boards were used by the students of the embedded systems training program (capacitação em sistemas embarcados) at EMBRAPII-VIRTUS CC, who worked with the real sensors, power management and expansion hardware on the hardware they received.

This repository holds the complete Altium project: hierarchical schematics, PCB layout, libraries, rules and stackup, bill of materials, output jobs, and the datasheets for every key component.

<img width="4000" height="3000" alt="IMG_20250617_110508" src="https://github.com/user-attachments/assets/e9bc73d9-afeb-4c97-9626-aa27282ded22" />
## Purpose

- **From design to hardware:** the schematic, layout and BOM in this repository produced a physical board that was assembled and then used in practice.
- **Used for training:** the assembled boards were used by the students of the EMBRAPII-VIRTUS embedded systems training program.
- **Reference material:** the schematics, BOM, datasheets and layout files document the full design flow, from component choice to manufacturing outputs.

## Highlights

- **Environmental sensing:** temperature and humidity (Sensirion SHT4x) and barometric pressure (TE MS5637).
- **Motion and light:** 6-axis IMU (TDK ICM-42670-P) and ambient light sensor (TI OPT4001).
- **Sound:** microphone amplifier stage (Maxim MAX4466).
- **Wireless MCU:** Raspberry Pi Pico W (RP2040 with Wi-Fi/Bluetooth).
- **Battery power:** Li-ion charge management (Microchip MCP73831) and cell protection (TI BQ29700).
- **Stable reference:** 2.5 V shunt reference (TI LM4040) for analog measurements.
- **User interface:** 0.96" OLED, RGB status LED (Broadcom ASMT-YTB7), and push buttons.
- **Expansion:** mikroBUS socket following the MikroE mikroBUS v2.0 standard, plus I/O expansion via an SX1509B GPIO expander.
- **Debug access:** test points for bring-up and measurement.

## Block diagram

The top-level schematic is organized as numbered sheets:

| Sheet | Contents |
|---|---|
| `[1] TableOfContents` | Index of the design |
| `[2] BlockDiagram` | System overview |
| `[3] TopLevel` | Top-level connections between blocks |
| `[4] Sensors` | Temperature/humidity, pressure, light, IMU, microphone |
| `[5] ButtonsAndLeds` | Push buttons and status indicators |
| `[6] RgbLed` | RGB LED driver |
| `[7] PowerManagement` | Charging, battery protection, regulation and reference |
| `[8] Conectors` | Headers, OLED and mikroBUS connections |
| `[9] Mechanical` | Mounting holes and mechanical features |

Harness files (`.Harness`) group related sheets into reusable interfaces.

## Repository structure

```
Altium Project/
└── Lucas Emanuel - PCEIoT/
    ├── Sources/              Schematic sheets and harnesses
    ├── Libraries/            Custom schematic (SCHLIB) and PCB (PcbLib) libraries
    ├── Rules and Stackups/   PCB design rules (RUL) and layer stackup
    ├── Datasheets/           Component datasheets
    ├── Graphics/             Logos and artwork for the schematic and board
    ├── Templates/            A3 schematic template
    ├── PCB1.PcbDoc           Board layout
    ├── PCEIoT BOM.BomDoc     Bill of materials
    └── Lucas Emanuel - PCEIoT.OutJob   Output job for manufacturing files
Altium Project/Entregaveis 1/   Project deliverables (PDF and XLSX)
```

## Key components

| Function | Part | Datasheet |
|---|---|---|
| Wireless MCU | Raspberry Pi Pico W | `SC0918-RPI pico W.pdf` |
| Temperature and humidity | Sensirion SHT4xI | `SHT4xI.pdf` |
| Pressure | MS5637-02BA03 | `MS563702BA03.pdf` |
| Ambient light | TI OPT4001 | `OPT4001.pdf` |
| IMU | TDK ICM-42670-P | `ICM-42670-P.pdf` |
| Microphone amplifier | Maxim MAX4466 | `MAX4466.pdf` |
| GPIO expander | SX1509B | `SX1509B.pdf` |
| Li-ion charger | Microchip MCP73831T | `MCP73831T.pdf` |
| Battery protection | TI BQ29700 | `BQ29700DSER.pdf` |
| Voltage reference | TI LM4040 (2.5 V) | `LM4040DYM3-2.5-TR.pdf` |
| RGB LED | Broadcom ASMT-YTB7 | `ASMT-YTB7-0AA02.pdf` |
| Display | 0.96" OLED module | `OLED Module 0.96.pdf` |
| Expansion | mikroBUS standard v2.0 | `mikrobus-standard-specification-v200.pdf` |

## Opening the project

1. Install Altium Designer.
2. Open `Altium Project/Lucas Emanuel - PCEIoT/Lucas Emanuel - PCEIoT.PrjPcb`.
3. Start from `[1] TableOfContents.SchDoc` to navigate the schematic.

## Manufacturing outputs

The `.OutJob` file defines the outputs for fabrication and assembly. The BOM is in `PCEIoT BOM.BomDoc`. Finished reference documents are in `Altium Project/Entregaveis 1/`.

## Skills demonstrated

- Schematic capture with hierarchical sheets and harnesses
- PCB layout and routing in Altium Designer, including custom rules and stackup
- Component selection from datasheets for sensing, power and interfacing
- Battery charging and protection design for single-cell Li-ion
- Design documentation: BOM, output jobs and deliverables

## Author

**Lucas Emanuel Barbosa Vasconcelos**, electrical engineering student (UFCG) and double-degree student at ENSTA Paris, formerly embedded and hardware developer at EMBRAPII VIRTUS (VIRTUS CC).

