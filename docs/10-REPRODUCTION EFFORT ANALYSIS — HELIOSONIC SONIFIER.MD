# Reproducibility Estimation — Time & Cost of Building a System Like the Heliosonic Sonifier

> **Version 1.0 · August 2026 · Reference system: Heliosonic Sonifier V18.5**
> (18,450 LOC · 25 modules · 20 autonomous agents · 81 presets · 2 hardware prototypes)

> [!NOTE]
> This is an **estimation for reproducibility planning**, not a quotation.
> All figures are indicative (EUR, 2026) with an uncertainty of **±30%**.
> Personnel effort dominates total cost (~99%); the science itself is free
> (open-source stack + public-domain NOAA data).

---

## 1. Methodology & Assumptions

- **Profile:** one skilled solo developer-researcher (Python + Qt/OpenGL +
  computer music + sonification design).
- **Stack:** 100% open-source (Python 3.9+, PySide6, PyOpenGL, mido/rtmidi,
  SQLite, pygame). **Software cost = €0.**
- **Data:** NOAA/SWPC public domain. **Data cost = €0.**
- **Hardware:** off-the-shelf components only (no custom PCB).
- **AI-assisted scenario** reflects the original project's methodology
  ("Hugo Paquete & DeepSeek AI"): LLM pair-programming across the whole build.
- **Excluded:** institutional overheads, grant administration, commercial
  licensing, custom PCB fabrication.

---

## 2. Time Estimation by Phase

| # | Phase | Scope | Solo expert (h) | AI-assisted (h) |
|:-:|-------|-------|:---------------:|:---------------:|
| 1 | Research & conceptual design | 1:N transduction paradigm, AI-Chimera framework, scientific-transparency framework | 250–400 | 150–250 |
| 2 | Core software | 7-layer pipeline, 25 modules, 18.5 k LOC, Qt6 UI, OpenGL visualisation, 16-ch MIDI | 800–1,100 | 400–600 |
| 3 | AI systems | RL memory, 3rd-order Markov + genetic/Perlin/CA, quantum glitch engine, adaptive FSM | 250–350 | 120–200 |
| 4 | Hardware prototyping | 16-key + 12-key controllers, joystick mapping, firmware | 100–160 | 80–120 |
| 5 | Testing & validation | Benchmarks (8.34 ms frame), mapping accuracy (97%), diversity metrics | 120–200 | 80–140 |
| 6 | Artistic content | 81 presets, 20+ scales, performance practice, rehearsal | 150–250 | 100–180 |
| 7 | Documentation | README + 10 docs, citation, transparency statements | 100–160 | 60–100 |
| | **TOTAL** | | **1,770–2,620** | **990–1,590** |

**Mid-points:** ~2,200 h (solo) · ~1,300 h (AI-assisted)
≈ **1.25 person-years** vs **0.75 person-years** (at 1,760 h/year).

pie title Effort distribution — AI-assisted mid estimate (~1,290 h)
"Core software" : 500
"Research & design" : 200
"AI systems" : 160
"Artistic content" : 140
"Testing & validation" : 110
"Hardware" : 100
"Documentation" : 80


### Calendar time

| Mode | Duration |
|------|----------|
| Solo, full-time (AI-assisted) | ~7–9 months |
| Solo, part-time 10 h/week | ~2.5 years |
| Small team (dev + composer + researcher) | ~6–9 months |
| Original project (reference) | ~8 months iterative (2026), alongside research duties |

### Productivity cross-check

18,450 LOC ÷ 1,300 h ≈ **14 LOC/h** — consistent with industry benchmarks
(10–50 LOC/h) for complex real-time audio/MIDI systems, confirming the
estimate's plausibility.

---

## 3. Cost Estimation

### 3.1 Personnel (dominant cost)

| Scenario | Rate | Hours | Cost |
|----------|:----:|:-----:|-----:|
| Academic (FCT postdoc-equivalent, loaded) | ~€30/h | 1,300 (AI-assisted) | **€39,000–45,000** |
| Academic, no AI assistance | ~€30/h | 2,200 | **€60,000–70,000** |
| Industry creative technologist | €50–70/h | 1,300 | **€65,000–95,000** |

### 3.2 Hardware Bill of Materials (full instrument)

| Component | Qty | Cost |
|-----------|:---:|-----:|
| Microcontroller (RP2040 / ATmega32U4 class) | 2 | €18–24 |
| Mechanical switches (linear) | 28 | €10–15 |
| Keycaps (orange + smoke translucent) | 28 | €15–20 |
| Rotary encoders + aluminium knobs | 5 | €20–30 |
| Laser-cut acrylic case + screws | 2 | €15–25 |
| Wiring, USB cables, misc | — | €10–15 |
| Joystick Thrustmaster T.Flight Stick X | 1 | €45–60 |
| **Total** | | **€140–200** |

*Optional:* physical MIDI interface €40–80 (virtual LoopMIDI = €0);
mid-range PC €900–1,600 (existing computer = €0).

### 3.3 Software, data & running costs

| Item | Cost |
|------|:----:|
| Full software stack (open-source) | €0 |
| NOAA/SWPC data (public domain) | €0 |
| Running: electricity + internet (existing) | ≈ €10/year |

### 3.4 Dissemination (annual)

| Item | Cost |
|------|:----:|
| Conference registrations (×2) | €300–800 |
| Travel & accommodation | €400–1,500 |
| **Annual total** | **€700–2,300** |

### 3.5 Total reproduction cost (summary)

| Configuration | Mid estimate |
|---------------|:------------:|
| Full rebuild, AI-assisted, academic rate, no PC | **≈ €40,000–46,000** |
| Full rebuild, no AI, academic rate | **≈ €61,000–71,000** |
| Hardware-only (software given) | **≈ €140–200** |

---

## 4. Reproduction Tiers

| Tier | What is reproduced | Time | Non-personnel cost |
|:----:|--------------------|:----:|:------------------:|
| T0 | Study docs, listen to excerpts | 0 | €0 |
| T1 | Run a published build (if released) | 1–2 h setup | €0 |
| T2 | Simplified functional equivalent (NOAA → MIDI, basic mapping) | 300–500 h | ~€0–60 |
| T3 | **Full system from scratch (AI-assisted)** | 990–1,590 h | €140–200 |
| T4 | Full system (no AI assistance) | 1,770–2,620 h | €140–200 |

---

## 5. Sensitivity & Risks

| Factor | Impact on time |
|--------|:--------------:|
| No Qt/OpenGL experience | +25–35% |
| No computer-music/sonification background | +20–30% |
| Custom PCB instead of acrylic prototype | +80–150 h |
| Without AI assistance | +70–80% |
| Regulatory/safety review of hardware | +40–80 h |

---

## 6. What This Estimation Deliberately Excludes

- Institutional overheads and FCT grant management (handled by INET-md / UA)
- Exact grant allocations (confidential to the funding agreement)
- Commercial productisation, certification, support
- Long-term maintenance beyond the first year

---

## 7. Conclusion

A system of this class is reproducible by a single skilled developer-researcher
in **~0.75–1.25 person-years**, at a total cost of **~€40–70k** (personnel-dominated),
while its **hardware is reproducible for ~€150–200** and its **software and data
for €0**. The AI-assisted methodology halves the effort — itself a finding of
the *AI as Catalyst* research programme.

*Heliosonic Sonifier documentation repository (FCT 2024.09158.CEECIND).*
