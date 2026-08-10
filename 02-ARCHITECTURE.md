# System Architecture

> **Heliosonic Sonifier V18.5** — Real-time NOAA solar wind sonification engine.
> 25 modules · ~18,450 LOC · 7-layer pipeline · 20 Hz operation.

---

## 7-Layer Pipeline

The system processes space weather data through seven sequential layers,
operating at **20 Hz** (50 ms frame budget).

```mermaid
flowchart TB
    subgraph L1["Layer 1 · Acquisition"]
        A["NoaaClient (thread, 60s)<br/>+ NoaaCache (SQLite, 7d)"]
    end
    subgraph L2["Layer 2 · Transformation"]
        B["DataMutator<br/>warp / phase / gravity"]
    end
    subgraph L3["Layer 3 · Inertia"]
        C["SonicInertia<br/>echo buffer · 50 samples"]
    end
    subgraph L4["Layer 4 · Emotion"]
        D["EmotionState · InternalState · AlertSystem<br/>tension / chaos / valence"]
    end
    subgraph L5["Layer 5 · State Machine"]
        E["AdaptiveStateManager<br/>8 states + 4 micro-states"]
    end
    subgraph L6["Layer 6 · Generation"]
        F["MotorC + Markov + Rhythm<br/>+ Glitch + Ghost + Scales"]
    end
    subgraph L7["Layer 7 · Output"]
        G["MIDIController + MidiProxy<br/>16 channels · 128 polyphony"]
    end
    A --> B --> C --> D --> E --> F --> G
