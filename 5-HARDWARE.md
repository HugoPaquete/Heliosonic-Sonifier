
---

## 📄 File 4: `docs/05-HARDWARE.md`

```markdown
# Hardware Integration

> Controller mappings for the Heliosonic Sonifier's
> custom hardware and joystick input.

---

## Controller Overview

| Controller | Type | Description |
|------------|------|-------------|
| **16-Key Controller** | Digital | Main musical state and effect triggers |
| **12-Key Controller** | Digital | Quick presets and parameter toggles |
| **Joystick (T.Flight Stick X)** | Analog + Digital | Continuous modulation + performance triggers |

---

## 16-Key Controller Mapping

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

---

## 12-Key Controller Mapping

| Key | Function | Type | Description |
|:---:|----------|:----:|-------------|
| 1 | Preset A | Momentary | Calm, melodic — Solar minimum |
| 2 | Preset B | Momentary | Moderate, rhythmic — Solar wind |
| 3 | Preset C | Momentary | Intense, glitch — Solar storm |
| 4 | Preset D | Momentary | Total chaos — Coronal mass ejection |
| 5 | Gravity Invert | Toggle | Invert gravity effect |
| 6 | Mute Melody | Toggle | Mute melody layer |
| 7 | Mute Drone | Toggle | Mute drone layer |
| 8 | Mute Glitch | Toggle | Mute glitch layer |
| 9 | Scale Shift (−) | Momentary | Decrease scale shift |
| 10 | Scale Shift (+) | Momentary | Increase scale shift |
| 11 | Register Shift (−) | Momentary | Decrease register |
| 12 | Register Shift (+) | Momentary | Increase register |

---

## Joystick — T.Flight Stick X

### Axis Mappings

| Control | Axis | Musical Effect | Range | Curve |
|---------|:----:|----------------|:-----:|:-----:|
| **Stick X** | 0 | WARP + PHASE | −1.0 to +1.0 | Exponential / Bipolar |
| **Stick Y** | 1 | CHAOS + REGISTER | −1.0 to +1.0 | Exponential / Linear |
| **Throttle** | 2 | DENSITY + RESONANCE | 0.0 to 1.0 | Logarithmic / Exponential |
| **Rudder (twist)** | 3 | GLITCH | −1.0 to +1.0 | Exponential |

### Axis Detail

| Axis | Parameter 1 | Range | Parameter 2 | Range |
|------|-------------|:-----:|-------------|:-----:|
| Stick X | WARP | 0.0 to 0.7 | PHASE | −0.3 to +0.3 |
| Stick Y | CHAOS | 0.0 to 0.5 | REGISTER SHIFT | −12 to +12 |
| Throttle | DENSITY | 0.0 to 0.6 | RESONANCE | 0.0 to 0.5 |
| Rudder | GLITCH | 0.0 to 0.6 | — | — |

### Button Mappings

| Button | Function | Type | Visual Color |
|:------:|----------|:----:|:------------:|
| **Trigger (0)** | Solar Flare | Momentary | 🟠 Orange |
| **1** | Glitch Burst | Momentary | 🟢 Green |
| **2** | Build-up | Momentary | 🟡 Yellow |
| **3** | Drop | Momentary | 🔴 Red |
| **4** | Time Warp | Momentary | 🔵 Blue |
| **5** | Freeze | Toggle | 🔷 Cyan |
| **6** | Resonance Sweep | Momentary | 🟣 Purple |
| **7** | Arpeggio Burst | Momentary | 🟨 Gold |
| **8** | Cosmic Ray | Momentary | 🟣 Violet |
| **9** | Helio Burst | Momentary | 🟠 Orange |
| **10** | Mute Moment | Momentary | ⚪ Grey |
| **11** | Panic | Momentary | 🔴 Red |

### Hat (D-pad) Mappings

| Direction | Function | Type |
|:---------:|----------|:----:|
| **UP** | Register +7 | Momentary |
| **DOWN** | Register −7 | Momentary |
| **LEFT** | Scale −1 | Momentary |
| **RIGHT** | Scale +1 | Momentary |

### Joystick Configuration

| Parameter | Value |
|-----------|-------|
| Deadzone | 0.15 |
| Poll rate | 60 Hz |
| Master intensity | 1.0 |
| Auto-start | Disabled |
| Calibration duration | 2.0 s |
| Reconnect interval | 5.0 s |
| Hysteresis threshold | 0.02 |

### Joystick Features

- **Auto-calibration** on startup (2 s, keep joystick centered)
- **Auto-reconnect** when joystick is disconnected/reconnected
- **Hysteresis filtering** to prevent jitter
- **Smoothing** per axis (0.80–0.90 factor)
- **Deadzone** per axis with extra deadzone for sensitive axes

---

## Keyboard Controls

### Global

| Key | Function |
|-----|----------|
| `H` | Toggle AI Monitor overlay |
| `V` | Video output (second screen) |
| `F11` | Toggle fullscreen |
| `Space` | **PANIC** — kill all notes |
| `I` | System info dialog |
| `K` | Controls help dialog |
| `?` | Quick help dialog |
| `D` | Debug info |
| `↑` / `↓` | Brightness adjust |
| `J` | Toggle joystick |
| `Shift+J` | Test joystick |

### Musical States

| Key | State |
|-----|-------|
| `1` | RHYTHMIC |
| `2` | MELODIC |
| `3` | SUSTAINED |
| `4` | GLITCH |
| `5` | SILENCE |

### Performance Effects

| Key | Effect |
|-----|--------|
| `B` | Build-up |
| `D` | Drop |
| `G` | Glitch Burst |
| `S` | Solar Flare |
| `T` | Time Warp |
| `P` | Pitch Rise |
| `R` | Resonance Sweep |
| `F` | Freeze |
| `L` | Rhythm Reset |
| `C` | Cosmic Ray |
| `A` | Arpeggio Burst |
| `M` | Mute Moment |
| `Shift+W` | Scale Shift |
| `W` (hold) | Warp (hold) |

### Presets

| Key | Function |
|-----|----------|
| `A` / `B` / `C` / `D` | Quick presets |
| `R` | Random preset |
| `Shift+R` | Reset all |

---

## Performance Effect Details

| Effect | Duration | Visual |
|--------|:--------:|--------|
| **Solar Flare** | 1.5 s | Orange particle burst |
| **Glitch Burst** | 1.0 s | Green visual glitch |
| **Build-up** | 2.0 s | Yellow crescendo |
| **Drop** | 1.5 s | Red collapse |
| **Time Warp** | 2.0 s | Blue waves |
| **Freeze** | 0.5 s | Cyan freeze |
| **Resonance Sweep** | 2.5 s | Purple resonance waves |
| **Arpeggio Burst** | 1.0 s | Gold sparks |
| **Cosmic Ray** | 2.0 s | Violet cosmic rays |
| **Helio Burst** | 2.0 s | Orange solar explosion |
| **Mute Moment** | 1.0 s | Grey fade |
| **Panic** | 0.5 s | Red intense flash |

---

*Documentation only. Source code is proprietary and not distributed.*
*See [02-ARCHITECTURE.md](02-ARCHITECTURE.md) for system overview.*

