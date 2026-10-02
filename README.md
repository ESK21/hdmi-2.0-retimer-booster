# High-Performance HDMI 2.0 Signal Booster & Retimer (4K60 UHD)

An open-source, hardware-level inline HDMI 2.0 retimer and signal equalizer engineered around the Texas Instruments **TMDS181RGZR** IC. Designed for reliable, jitter-free 4K60 HDR video transmission over long passive cable runs and lossy interconnects.

---

## 📌 Project Overview

Long HDMI cables and passive patch lines experience signal attenuation, high-frequency dispersion, and inter-symbol interference (ISI). At HDMI 2.0 data rates (up to 6.0 Gbps per channel), this degradation collapses the differential eye diagram, resulting in sparkling, image freezing, or total handshake failure.

This board provides active equalization, clock/data recovery (CDR), and output de-emphasis to clean and regenerate the high-speed TMDS lines before passing them to the sink display.

---

## ⚡ Key Specifications

| Parameter | Specification |
| :--- | :--- |
| **Primary Controller** | TI TMDS181RGZR (48-Pin VQFN) |
| **Standards Supported** | HDMI 1.4b & HDMI 2.0b |
| **Max Bandwidth** | 18 Gbps (6.0 Gbps per TMDS channel) |
| **Max Resolution** | 4K @ 60Hz (RGB / YCbCr 4:4:4), 1080p @ 240Hz |
| **Target Impedance** | 100Ω Differential ($\pm 10\%$) on all TMDS lanes |
| **PCB Stackup** | 4-Layer controlled-impedance (`JLC04161H-3313A`) |
| **Input Power** | 5V DC via HDMI In |
| **Onboard Voltage Rails** | 3.3V (`VCC` I/O) & 1.2V (`VDD` Core) via AMS1117 LDOs |
| **ESD Protection** | Ultra-low capacitance USON diode arrays (`D1`–`D4`) |

---

## 🛠️ Hardware & Layout Architecture

* **High-Speed Routing:** All TMDS differential channels are length-matched with smooth corner transitions to minimize reflections. Top escapes reference a solid Layer 2 Ground plane; bottom routes reference a dedicated Layer 3 Ground reference shield, preventing return-path discontinuities across the board.
* **Autonomous Hardware Pin-Strapping:** Operates plug-and-play without requiring an external microcontroller. Configuration pins (rate select, equalization level, and de-emphasis) are hard-tied via onboard precision resistor straps.
* **Thermal Dissipation:** A through-hole thermal via array stitches the central QFN-48 exposed pad directly into the internal ground planes. SOT-223 regulator tabs feature thermal via stitching into their respective Layer 3 power copper pours.
* **Auxiliary Signal Handling:** Transparent inline pass-through with dedicated pull-ups and ESD suppression for Display Data Channel (DDC/EDID), Hot Plug Detect (HPD), and CEC lines.

---

## 📂 Repository Contents

* `/Gerber/`: Production-ready Gerber and drill files (ZIP).
* `/Schematics/`: Schematic in PDF format.
* `/EasyEDA/`: Native project source archive (`.epro2`).
* `/Assembly/`: Pick & place file, Excel BOM, and interactive HTML BOM.
* `/3D_Renders/`: 3D renders of the assembled PCB.

---

## 🏭 Fabrication Guidelines

* **Layers:** 4 Layers
* **PCB Thickness:** 1.6 mm
* **Stackup:** `JLC04161H-3313A`
* **Impedance Control:** Yes (±10%)
* **Copper Weight:** Outer 1 oz / Inner 0.5 oz
* **Minimum Via Drill:** 0.3 mm (thermal pad vias 0.3mm to prevent solder wicking)

---

## 📄 License

This hardware project is open-source and licensed under the **CERN-OHL-P-2.0** (Permissive) license. See the [LICENSE](LICENSE) file for complete terms.
