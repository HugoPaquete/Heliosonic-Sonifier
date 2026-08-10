# Hardware Integration

> Physical controllers, prototype specifications, and performance mappings
> for the Heliosonic Sonifier.

> [!NOTE]
> **Prototype status.** The controllers described here are **hand-built
> research prototypes (Revision A)**, used for live performance and system
> validation. They are **not commercial products** and are not sold or
> distributed. Schematics and firmware remain proprietary; this page
> documents the interface for performers and researchers.

---

## 🎛️ Physical Prototypes (Revision A)

<p align="center">
  <img src="../assets/hardware/proto-controllers.jpg" width="95%"
       alt="HS-16 and HS-12 prototype controllers">
  <br>
  <em>HS-16 PROTO A (left) · HS-12 PROTO A (right)</em>
</p>

### Prototype units

| Unit | Keys | Matrix | Rotary encoders | Keycaps | Case | Status |
|------|:----:|--------|:---------------:|---------|------|:------:|
| **HS-16 PROTO A** | 16 | 4 × 4 | 3 | Orange ABS | Black acrylic sandwich | ✅ Active |
| **HS-12 PROTO A** | 12 | 3 × 4 | 2 | Orange + smoke translucent | Black acrylic sandwich | ✅ Active |

### Design language

| Element | Meaning |
|---------|---------|
| 🟠 **Orange keycaps** | Primary performance controls (states, effects, presets) |
| ⬛ **Smoke translucent keycaps** | Secondary / system controls (toggles, shifts) |
| ⚙️ **Rotary knobs** | Continuous modulation (CC automation) |
| 🔩 **Acrylic sandwich case** | Laser-cut top/bottom plates, corner screws |

### Build specification (prototype)

| Component | HS-16 | HS-12 |
|-----------|-------|-------|
| Key switches | Mechanical, linear (red) | Mechanical, linear (red) |
| Keycaps | ABS orange | ABS orange + smoke translucent |
| Encoders | 3 × rotary, aluminium knob | 2 × rotary, aluminium knob |
| MCU | USB-MIDI class-compliant (Pro Micro / RP2040 class) | same |
| Connection | USB-C | USB-C |
| Case | 3 mm black acrylic, 4-screw sandwich | same |

### Rotary encoder mapping (firmware v0.1)

| Unit | Knob | Parameter | MIDI CC |
|------|:----:|-----------|:-------:|
| HS-16 | K1 | WARP | 28 |
| HS-16 | K2 | CHAOS | 20 |
| HS-16 | K3 | RESONANCE | 30 |
| HS-12 | K1 | REGISTER | 22 |
| HS-12 | K2 | TEMPO | 31 |

---

## 16-Key Controller (HS-16) — Logical Mapping

| Key | Function | Type | Description |
|:---:|----------|:----:|-------------|
| 1 | RHYTHMIC | Toggle | Percussive, fast tempo |
| 2 | MELODIC | Toggle | Expressive melody |
| 3 | SUSTAINED | Toggle | Long drones, atmospheric |
| 4 | GLITCH | Toggle | Chaos, glitches |
| 5 | SILENCE | Toggle | Musical silence |
| 6 | Solar Flare | Momentary | Explosive energy burst |
| 7 | Glitch Burst | Momentary | Quantum glitch cascade |
| 8 | Build-up | Momentary | Gradual tension increase |
| 9 | Drop | Momentary | Abrupt intensity drop |
| 10 | Time Warp | Momentary | Temporal modulation |
| 11 | Pitch Rise | Momentary | Register ascend |
| 12 | Resonance Sweep | Momentary | Frequency sweep |
| 13 | Freeze | Toggle | Hold all notes |
| 14 | Random Preset | Momentary | Apply random preset |
| 15 | Reset | Momentary | Reset to default values |
| 16 | Panic | Momentary | Kill all active notes |

## 12-Key Controller (HS-12) — Logical Mapping

| Key | Function | Type | Description |
|:---:|----------|:----:|-------------|
| 1 | Preset A | Momentary | Calm, melodic — Solar minimum |
| 2 | Preset B | Momentary | Moderate, rhythmic — Solar wind |
| 3 | Preset C | Momentary | Intense, glitch — Solar storm |
| 4 | Preset D | Momentary | Total chaos — CME |
| 5 | Gravity Invert | Toggle | Invert gravity effect |
| 6 | Mute Melody | Toggle | Mute melody layer |
| 7 | Mute Drone | Toggle | Mute drone layer |
| 8 | Mute Glitch | Toggle | Mute glitch layer |
| 9 | Scale Shift (−) | Momentary | Decrease scale shift |
| 10 | Scale Shift (+) | Momentary | Increase scale shift |
| 11 | Register Shift (−) | Momentary | Decrease register |
| 12 | Register Shift (+) | Momentary | Increase register |

---

## 🕹️ Joystick (T.Flight Stick X)

| Control | Type | Musical Effect | Range |
|---------|:----:|----------------|-------|
| Stick X | Analog | WARP + PHASE | −1.0 … +1.0 |
| Stick Y | Analog | CHAOS + REGISTER | −1.0 … +1.0 |
| Throttle | Analog | DENSITY + RESONANCE | 0.0 … 1.0 |
| Rudder (twist) | Analog | GLITCH | −1.0 … +1.0 |
| Trigger (Btn 0) | Digital | SOLAR FLARE | Momentary |
| Btn 1–4 | Digital | Performance effects | Momentary |
| Btn 5–8 | Digital | Modulation effects | Momentary |
| Btn 9–10 | Digital | System controls | Momentary |
| Btn 11 | Digital | PANIC | Momentary |
| Hat (D-pad) | Digital | Register / scale shifts | Momentary |

---

## 🗺️ Prototype roadmap

| Revision | Status | Notes |
|----------|:------:|-------|
| **PROTO A** (HS-16 / HS-12) | ✅ Current | Acrylic case, mechanical switches, USB-MIDI |
| **PROTO B** | 📋 Planned | Per-key RGB feedback, OLED state display |
| **PROTO C** | 💭 Concept | Integrated single-unit console |

---

*Documentation only. Hardware units are research prototypes and are not
available for purchase.*
