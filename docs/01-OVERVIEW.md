# Heliosonic Sonifier — Overview

> *"How does solar wind become music? Not through representation, but through
> resonance. Not through translation, but through transduction."*

**Real-time NOAA solar wind sonification with AI, reinforcement learning,
and a quantum-inspired glitch engine.**

*Hugo Paquete & DeepSeek AI · INET-md, University of Aveiro · 2026*

---

## What it is

The **Heliosonic Sonifier** is a real-time artistic sonification instrument
that transforms **NOAA/SWPC space-weather data** into adaptive MIDI music.
It is not a data-to-sound mapper. It is a multi-agent computational organism
in which solar data *reorganizes internal states*, and sound *emerges* from
those states.

The system bridges scientific data representation with musical expression
through generative AI and computational creativity, providing a platform for
live performance and data exploration.

| Attribute | Value |
|-----------|-------|
| **Version** | 18.5 |
| **Scale** | ~18,450 LOC · 25 modules · 20 autonomous agents |
| **Operation** | 20 Hz real-time (50 ms frame budget) |
| **Output** | MIDI + CC · 16 channels · 128-note polyphony |
| **Platform** | Windows 10/11 |
| **Funding** | CEEC-FCT grant No. 2026-HELIOSONIC |

---

## Mission

Bridge scientific data with artistic musical expression through generative AI
and computational creativity.

---

## Core innovations

- **State-Aware Markov Chains** — 3rd-order, 8 musical states, ~80,000 transitions
- **Reinforcement Learning** — autonomous adaptation with 1,000-entry episodic memory
- **Quantum-inspired glitch engine** — tunneling, entanglement, superposition
- **Black-hole physics** — artistic metaphor for data mutation
- **Helioseismic modulation** — p-modes (3 mHz) and theoretical g-modes

---

## The 7-layer pipeline

```mermaid
flowchart TB
    subgraph L1["Layer 1 · Acquisition"]
        A["NoaaClient (thread)<br/>+ SQLite Cache (7d)"]
    end
    subgraph L2["Layer 2 · Transformation"]
        B["DataMutator<br/>warp / phase / gravity"]
    end
    subgraph L3["Layer 3 · Inertia"]
        C["SonicInertia<br/>echo buffer · 50 samples"]
    end
    subgraph L4["Layer 4 · Emotion"]
        D["EmotionState<br/>tension / chaos / valence"]
    end
    subgraph L5["Layer 5 · State Machine"]
        E["AdaptiveStateManager<br/>8 states + 4 micro"]
    end
    subgraph L6["Layer 6 · Generation"]
        F["MotorC + Markov + Rhythm<br/>+ Glitch + Ghost"]
    end
    subgraph L7["Layer 7 · Output"]

```
Full detail in 02-ARCHITECTURE.md.
        G["MIDIController<br/>16 channels · 128 polyphony"]
    end
    A --> B --> C --> D --> E --> F --> G

### Research Positioning

The **Heliosonic Sonifier** is part of the **AI as Catalyst** research programme  
(FCT 2024.09158.CEECIND · 2026–2029).  
It extends the **AEROSONIC** framework into the heliospheric domain and belongs to a family of interconnected sonifiers:

| Project                | Domain                          |
|------------------------|----------------------------------|
| AEROSONIC SONIFIER     | Atmospheric data sonification    |
| HELIOSONIC SONIFIER    | Solar / heliospheric sonification |
| CYBER ATTACK SONIFIER  | Cybersecurity threat sonification |
| GLITCH ECOLOGY         | Ecological data sonification     |

Developed with **INET-md / University of Aveiro**, in collaboration with:  
**Absonus Lab**, **Planetário do Porto – CCV**, and **OTTOsonics**.

### Documentation Map

| Document                     | Contents                               |
|------------------------------|-----------------------------------------|
| 02-ARCHITECTURE.md           | 7-layer pipeline, 25-module inventory   |
| 03-AI-SYSTEMS.md             | Markov, RL, quantum glitch deep-dive    |
| 04-MIDI-OUTPUT.md            | 16 channels, CCs, polyphony             |
| 05-HARDWARE.md               | 16/12-key controllers + joystick        |
| 06-DATA-MAPPING.md           | NOAA → music mapping                    |
| 07-PERFORMANCE.md            | Benchmarks & validation                 |
| 08-SCIENTIFIC-TRANSPARENCY.md| Verified / theoretical / artistic       |

> **NOTE**  
> This repository is documentation-only.  
> The source code and executables are proprietary and are not distributed here.
