# Related Work & Comparative Positioning

> How the Heliosonic Sonifier relates to — and differs from — existing
> sonification, auditory-display, and AI music systems.
> This comparison is schematic; references are indicative and should be
> verified before formal citation.

---

## 1. The Landscape

Existing work around data sonification falls into four families:

| Family | Representative work | Typical stance |
|--------|--------------------|----------------|
| **Analytic / scientific sonification** | Parameter-Mapping Sonification (PMSon) as systematized in the *Sonification Handbook* (Hermann, Hunt & Neuhoff, 2011); solar-wind sonifications by R. Alexander (doctoral research, Univ. of Michigan); NASA/CXC data sonifications (2020–) | Data as *signal* to be analysed or communicated |
| **Auditory display / visualization tools** | TwoTone, Sonification Sandbox, Highcharts Sonification | Data as *display*; offline rendering |
| **Generative / AI music systems** | Magenta-style generative models; co-creative systems (e.g. Dubnov; Karchkhadze & Dubnov, 2026) | Music generation from learned priors or performer interaction |
| **Artistic research-creation** | Xenakis (stochastic/GENDY), Roads (microsound), the author's AEROSONIC family | Scientific concepts as *compositional material* |

---

## 2. Comparative Table

| Dimension | Scientific PMSon / audification | Offline AI generative music | AEROSONIC (Paquete) | **HELIOSONIC (this work)** |
|-----------|-------------------------------|------------------------------|---------------------|----------------------------|
| **Data source** | Archived datasets | None (learned priors) | Live atmospheric | **Live NOAA/SWPC (60 s refresh)** |
| **Temporal mode** | Offline / interactive | Offline | Real-time | **Real-time, 20 Hz engine** |
| **Mapping paradigm** | 1:1 parameter mapping | Latent model | 1:N | **1:N transduction (resonance)** |
| **Agency** | Deterministic | Stochastic AI | Adaptive | **Multi-agent AI (RL + Markov + generative)** |
| **Output** | Fixed audio render | Audio / MIDI | MIDI | **MIDI + CC — open instrumentation** |
| **Performance mode** | Listening / installation | Offline | Live | **Live instrument (hardware controllers)** |
| **Scientific claim** | Analytic | None | Artistic | **Artistic, with explicit transparency taxonomy** |

---

## 3. What Differentiates Heliosonic

1. **Live data loop.** Most sonification is offline; Heliosonic closes the loop
   with real-time space weather (60 s API refresh, 20 Hz internal engine).
2. **1:N transduction.** A single data-event radiates across harmonic, rhythmic,
   textural, spatial and affective layers, instead of a 1:1 parameter mapping.
3. **AI as co-agent, not tool.** Reinforcement learning with auto-apply,
   state prediction and transition learning operate autonomously; the performer
   *curates* emergence rather than controlling mappings.
4. **MIDI as open score.** The system fixes no timbre: any DAW/synth completes
   the work, making each performance a distinct instantiation.
5. **Hardware performativity.** Custom 16/12-key controllers and a flight stick
   make solar data *playable*, aligning it with instrumental practice.
6. **Transparency by design.** Physical models are explicitly labelled
   VERIFIED / THEORETICAL / ARTISTIC (see
   [08-SCIENTIFIC-TRANSPARENCY.md](08-SCIENTIFIC-TRANSPARENCY.md)).
7. **Post-techno aesthetics.** Glitch, noise and collapse are embraced as
   material (Paquete, EIMAD 2026), against the "clean" sound of auditory displays.

---

## 4. Complementary, Not Competitive

Heliosonic does **not** replace scientific sonification:

- It is **not** an analysis or prediction tool.
- It does **not** claim physical fidelity for its quantum/black-hole metaphors.
- It **extends** space-weather data into the artistic domain, offering a
  *performative* and *affective* reading where scientific sonification offers an
  *analytic* one.

The two practices are complementary readings of the same phenomena.

---

## 5. Lineage Within the Author's Ecosystem

| Project | Domain | Status |
|---------|--------|--------|
| AEROSONIC SONIFIER | Atmospheric data | Prior framework |
| **HELIOSONIC SONIFIER** | Solar / heliospheric | **This work** |
| CYBER ATTACK SONIFIER | Cybersecurity threats | In development |
| GLITCH ECOLOGY | Ecological data | In development |

---

## 6. Selected References (indicative)

- Hermann, T., Hunt, A., Neuhoff, J. (eds.) (2011). *The Sonification Handbook*. Logos.
- Alexander, R. (2013). Sonification of solar wind and space weather data. Doctoral research, University of Michigan.
- NASA / Chandra X-ray Center (2020–). Data sonification releases.
- Xenakis, I. (1992). *Formalized Music*. Pendragon.
- Roads, C. (2001). *Microsound*. MIT Press.
- Goodman, S. (2010). *Sonic Warfare*. MIT Press.
- Dubnov, S. (2026); Karchkhadze, A. & Dubnov, S. (2026). Real-time human–AI musical co-performance.
- Paquete, H. (2026a). SRT7 Framework. AVANCA 2026.
- Paquete, H. (2026b). Post-Techno Aesthetics. EIMAD 2026.
