
---

## 📄 File 3: `docs/06-DATA-MAPPING.md`

```markdown
# Data Mapping — NOAA to Music

How NOAA/SWPC space-weather parameters are normalized, derived, and
transduced into musical behaviour. Formulas are taken from `NOAAState`,
`EmotionState`, and `AlertSystem`.

---

## Primary data sources (60 s intervals)

| Parameter | Range | Musical mapping |
|-----------|-------|-----------------|
| **Bz (IMF)** | −20 to +20 nT | Register, tension, scale |
| **Solar wind speed** | 200–1000 km/s | Tempo (BPM), rhythm density |
| **Proton flux** | 0–500 pfu | Glitch intensity, chaos |
| **Electron flux** | 0–5000 pfu | Texture, ambient density |
| **Kp index** | 0–9 | Chaos level, state transition |
| **Alerts (R/S/G)** | 0–5 scales | Emergency states, glitch burst |

---

## Normalization

Each raw parameter is mapped to `[0, 1]` with a sensitivity curve.

| Parameter | Formula |
|-----------|---------|
| Bz | `(bz + 15) / 30` |
| Speed | `(speed − 300) / 500` |
| Protons | `protons / 100` |
| Electrons | `electrons / 1000` |
| Density | `density / 30` |
| Kp | `kp / 9` |

---

## Derived parameters

| Derived | Description |
|---------|-------------|
| **Gradients** | Δ/Δt with clamping (bz, speed, protons, electrons, density, kp) |
| **Spikes** | proton, electron, speed spike detection |
| **Moving averages** | MA5 for all parameters |
| **Cross-correlation** | 11×10 matrix across 3 time scales |

---

## Storm intensity

```text
bz_factor      = clamp( (−min(0, bz)) / 12, 0, 1 )
speed_factor   = clamp( (speed − 350) / 400, 0, 1 )
gradient_boost = clamp( |bz_gradient| / 5, 0, 0.3 )

storm = clamp( bz_factor·0.4 + speed_factor·0.4 + gradient_boost·0.2, 0, 1 )

```

Emotion mapping
EmotionState derives an affective state from NOAA data.

tension = (−min(0, bz)/15)·0.7 + (kp/9)·0.3
chaos   = (protons/80)·0.5 + (electrons/500)·0.3 + (|bz_gradient|/5)·0.2
valence = 0.5 + (bz/30)·0.3 − tension·0.3

### Musical Parameters

Direct musical parameters derived from NOAA state.

| Parameter       | Formula                                      |
|-----------------|----------------------------------------------|
| Tension         | clamp( (−min(0, bz)) / 12, 0, 1 )            |
| Chaos           | min(1, storm·0.7 + protons/100)              |
| Energy          | min(1, speed/800)                            |
| Density boost   | min(0.5, density/20)                         |
| Glitch boost    | min(0.8, protons/50)                         |
| Register        | 45 + 40 · bz_normalized                      |


### The 1:N Transduction Paradigm

A single data-event does not map to a single sonic parameter.  
It radiates across multiple layers, each with its own temporal dynamics:

| Layer             | Expressive Range                         |
|-------------------|-------------------------------------------|
| Harmonic tension  | CALM → TENSE → STORM → CHAOS              |
| Rhythmic density  | sparse → dense → glitchy                  |
| Granular texture  | smooth → shattered → drifting             |
| Spatial diffusion | narrow → wide → immersive                 |
| Affective state   | longing → ecstasy → fear                  |

The system does not ask **“what sound corresponds to this data point?”** —  
it asks **“how does this data pattern reorganize the internal state of the computational organism?”**


### Alert Scales (R / S / G)

| Scale | Meaning                 | Levels |
|-------|--------------------------|--------|
| R     | Radio blackout          | 0–5    |
| S     | Solar radiation storm   | 0–5    |
| G     | Geomagnetic storm       | 0–5    |

Combined alert level drives emergency states and glitch bursts.  
See **03-AI-SYSTEMS.md** for how alerts influence the state machine.
