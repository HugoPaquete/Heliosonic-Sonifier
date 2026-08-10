# Artificial Intelligence in the Heliosonic Sonifier

## Overview

The Heliosonic Sonifier integrates artificial intelligence not as a replacement for the performer, but as an autonomous co-agent within the musical system. The AI operates at multiple levels of abstraction — from continuous parameter adaptation through reinforcement learning, to generative melody synthesis through Markov chains and evolutionary algorithms, to predictive state transitions through adaptive state machines.

The project grounds its AI architecture in the **AI-Chimera framework**, a conceptual ontology developed as part of the *AI as Catalyst* research programme (FCT 2024.09158.CEECIND). This framework establishes the theoretical foundation upon which all AI systems in the Sonifier are constructed.

---

## The AI-Chimera Framework

The AI-Chimera is defined as an ontogenetic computational entity characterized by a dynamic quintuple:

```text
X = {B, M, A, E, Be}

```
## Component Model — B / M / A / E / Be

| Component | Meaning |
|-----------|---------|
| **B (Body)** | The operational materiality — MIDI output, visualization, interface |
| **M (Metabolism)** | The interpretative transduction layer — DataMutator |
| **A (Environment)** | The ontological condition of existence — NOAA data |
| **E (States)** | Internal configurations of tension and transitional potential |
| **Be (Emergent Behaviour)** | The dynamic manifestation resulting from interaction |

Within this framework, intelligence is defined operationally as **differential sensitivity to the environment**, stripped of anthropomorphic cognition.

I = ∂Be / ∂A

This formulation distinguishes the AI‑Chimera from deterministic sonification engines, establishing it as an autonomous entity capable of adaptive response without requiring explicit programming for every scenario.

### 1. AdaptiveMemory — Reinforcement Learning

AdaptiveMemory is the core learning system of the Sonifier.  
It implements episodic reinforcement learning to autonomously adapt musical parameters based on the relationship between NOAA data and perceived musical success.

#### Architecture

| Property            | Value                     |
|---------------------|---------------------------|
| Memory Capacity     | 1,000 entries             |
| Context Dimensions  | 11 NOAA parameters        |
| Action Dimensions   | 10 musical parameters     |
| Similarity Metric   | RBF kernel (O(D×N)=11,000 ops) |
| Ensemble Models     | 5 models with dynamic weights |
| Learning Rate       | Dynamic (2–60%)           |
| Auto-Apply Threshold| 0.65 confidence           |
| Auto-Apply Cooldown | 10 seconds                |

### Dynamic Learning Rate

The learning rate adapts to the data context through four detection mechanisms:

| Condition                                      | Learning Rate | Rationale                     |
|------------------------------------------------|---------------|-------------------------------|
| Calm data (low Bz, speed, protons)             | 2–3%          | Avoid learning noise          |
| AI stuck in GLITCH state (>75% of decisions)   | 50–60%        | Force exploration             |
| Confidence low                                 | Up to 80%     | Needs more learning           |
| Curiosity (rare states visited <5%)            | ≥40%          | Explore unexplored states     |

### Reward Function

The reward function balances multiple musical qualities:

R = 0.25(1−T) + 0.20E + 0.20C_opt + 0.20N + 0.15S

Where:
T = Tension (lower is better for calm music)
E = Energy
C_opt = Chaotic Optimality
N = Note Diversity
S = State Stability
Decision Diversity Monitoring
The system tracks decision history to detect when the AI is stuck in a single state. If more than 75% of recent decisions are in the same state, the learning rate is increased to force exploration of alternatives.

### 2. StateAwareMarkovMelody — Generative AI

StateAwareMarkovMelody is the melody generation engine.  
It combines probabilistic state machines with generative AI techniques to produce melodies that are neither purely deterministic nor entirely random.

#### Architecture

| Property            | Value                     |
|---------------------|---------------------------|
| Markov Order        | 3rd                       |
| Musical States      | 8                         |
| Total Transitions   | ~80,000                   |
| LRU Cache           | 200 entries (95% hit rate)|
| Prediction Complexity | O(k), k ≤ 10 (≈3 ms typical) |

### Generative AI Layer

The GenerativeMelodyGenerator combines three generative techniques:

| Technique       | Weight | Implementation                        |
|-----------------|--------|----------------------------------------|
| Markov Chains   | 60%    | 3rd‑order probabilistic transitions    |
| Genetic Algorithms | 30% | Population 20, mutation 5%, crossover 70% |
| Perlin Noise    | 10%    | 4‑octave continuous variation          |

### Genetic Algorithm Details

| Parameter        | Value                          |
|------------------|--------------------------------|
| Population Size  | 20 patterns                    |
| Mutation Rate    | 5%                             |
| Crossover Rate   | 70%                            |
| Selection Method | Tournament (size 3)            |
| Fitness Function | Variety × 0.6 + Interval × 0.4 |

### Solar Physics Integration

The melody generator integrates helioseismic physics:

| Mode        | Frequency | Musical Effect                     |
|-------------|-----------|------------------------------------|
| p-modes     | 3 mHz     | Pitch modulation (vibrato)         |
| g-modes     | 200 μHz   | Slow temporal modulation           |
| Solar Cycle | ~11 years | Long-form structural change        |

The melody "breathes" with the Sun's oscillations, creating a direct link between solar physics and musical expression.

### 3. AdaptiveStateManager — Predictive AI

AdaptiveStateManager implements an 8‑state finite state machine with adaptive transitions, crossfade envelopes, and predictive capabilities.

#### Architecture

| Property         | Value                                   |
|------------------|------------------------------------------|
| Musical States   | 8                                        |
| Micro‑States     | 4 (Calm, Neutral, Intense, Solar Peak)   |
| Crossfade Duration | 200–500 ms                             |
| Envelope Type    | ADSR                                     |
| Hysteresis       | Adaptive (0.08–0.20)                     |
| Max Transitions  | 12 per minute                            |

### Predictive Capabilities

The system predicts future states based on gradient analysis:

- **Gradient Computation** — Calculates chaos, tension, and storm gradients  
- **Value Projection** — Projects values forward by 0.5 seconds  
- **Confidence Assessment** — Requires 3 consecutive consistent predictions  
- **Transition Execution** — Initiates preemptive transitions when confident  

### Transition Learning

The system learns which transitions are successful:

- **Success tracking** — Records successful transitions  
- **Failure tracking** — Records failed transitions  
- **Matrix adjustment** — Updates transition probabilities based on success ratio  
- **Memory decay** — Applies exponential decay (0.95) to old memories  

### How the AI is Constructed

## Layered Architecture

The AI is constructed in seven layers, each building upon the previous:

┌─────────────────────────────────────────────────────────────┐
│ LAYER 1: Acquisition    │ NOAA Client + SQLite Cache        │
│ LAYER 2: Transformation │ DataMutator (warp/phase/gravity)  │
│ LAYER 3: Inertia        │ SonicInertia (echo buffer)        │
│ LAYER 4: Emotion        │ EmotionState (tension/chaos)      │
│ LAYER 5: State Machine  │ AdaptiveStateManager (8 states)   │
│ LAYER 6: Generation     │ MotorC + Markov + Rhythm + Glitch │
│ LAYER 7: Output         │ MIDIController (16 channels)      │
└─────────────────────────────────────────────────────────────┘


### AI Decision Flow

- **Context Building** — NOAA data is normalized into an 11‑dimensional context vector  
- **Memory Retrieval** — Similar past experiences are retrieved using an RBF kernel  
- **Inference** — Ensemble models predict optimal musical parameters  
- **Decision** — Parameters are selected based on confidence  
- **Application** — Changes are applied gradually to musical parameters  
- **Feedback** — Success is measured through musical quality metrics  
- **Learning** — Successful decisions are reinforced; failures are discouraged  

### How the AI is Characterized

## Autonomy Levels

The AI operates at three levels of autonomy:

| Level     | Description                 | Example                         |
|-----------|------------------------------|---------------------------------|
| Reactive  | Responds to immediate stimuli | Glitch burst on proton spike    |
| Adaptive  | Adjusts behavior over time    | Learning rate adaptation        |
| Predictive| Anticipates future states     | State prediction                |

---

## AI States

The system recognizes and reports its own operational state:

| State       | Learning Rate | Behavior                 |
|-------------|---------------|--------------------------|
| MONITORING  | < 0.1         | Observing and analyzing  |
| ADAPTING    | 0.1–0.3       | Fine‑tuning responses    |
| LEARNING    | > 0.3         | Actively adapting patterns |

---

## AI Metrics

The system tracks its own performance:

| Metric                | Description                       |
|-----------------------|-----------------------------------|
| Learning Rate         | Current adaptation speed          |
| Confidence            | Decision certainty                |
| Memory Size           | Number of stored patterns         |
| Positive Reinforcements | Successful decisions            |
| Negative Reinforcements | Failed decisions                |
| Decision Diversity    | Entropy of state distribution     |

### AI vs. Metaphor — Scientific Transparency

The Heliosonic Sonifier distinguishes between actual AI systems and scientific metaphors used for artistic expression.

## Actual AI Systems

| System                  | Type                | Purpose              |
|-------------------------|---------------------|----------------------|
| AdaptiveMemory          | Reinforcement Learning | Parameter adaptation |
| StateAwareMarkovMelody  | Generative AI       | Melody synthesis     |
| AdaptiveStateManager    | Predictive AI       | State transitions    |
| GenerativeMelodyGenerator | Evolutionary AI   | Pattern generation   |

---

## Scientific Metaphors

| Metaphor          | Scientific Basis            | Musical Application     |
|-------------------|-----------------------------|--------------------------|
| Quantum Mechanics | Tunneling, entanglement     | Glitch generation        |
| Black Holes       | Event horizon, singularity  | Data transformation      |
| Helioseismology   | p‑modes, g‑modes            | Pitch modulation         |
| Chandrasekhar Limit | Stellar collapse          | Rhythm collapse          |

> ⚠️ **Important:**  
> The quantum and black‑hole metaphors are computational metaphors, **not** simulations of physical phenomena.  
> They provide organizational principles for musical material without claiming physical accuracy.

### AI Decision Examples

## Example 1: Solar Storm Response

When NOAA data indicates an approaching solar storm:

- **Detection** — Bz gradient becomes strongly negative  
- **Prediction** — State manager predicts transition to GLITCH  
- **Preparation** — Crossfade envelope is prepared  
- **Execution** — State transition occurs with smooth fade  
- **Learning** — Successful transition is reinforced in memory  

---

## Example 2: Melody Generation

When generating a melody:

- **State Assessment** — Current musical state is determined  
- **Context Analysis** — NOAA parameters influence musical choices  
- **Markov Selection** — Probabilistic next note is selected  
- **Generative Blending** — Genetic and Perlin components are mixed  
- **Solar Modulation** — p‑mode/g‑mode modulation is applied  
- **Output** — Note is sent to MIDI output  

---

## Example 3: Parameter Adaptation

When the AI observes a pattern:

- **Observation** — Current parameters are stored in memory  
- **Inference** — Similar past experiences are retrieved  
- **Prediction** — Optimal parameters are predicted  
- **Application** — Changes are applied if confidence > 0.65  
- **Feedback** — Success is measured after cooldown  
- **Reinforcement** — Successful decisions are strengthened  

### AI Limitations

The AI in the Heliosonic Sonifier has several limitations:

| Limitation        | Description                                      |
|-------------------|--------------------------------------------------|
| No Consciousness  | The AI does not have awareness or subjective experience |
| No Creativity     | The AI does not create in the human sense        |
| No Understanding  | The AI does not understand the music it produces |
| No Emotion        | The AI does not feel the emotions it models      |
| Bounded Learning  | The AI learns only within its 1,000‑entry memory |
| Fixed Reward      | The AI optimizes for the defined reward function |

### Conclusion

The AI in the Heliosonic Sonifier represents a research exploration of how artificial intelligence can function as an autonomous co‑agent in artistic practice. The system demonstrates that AI can:

- Adapt to changing environmental conditions  
- Generate novel musical material through evolutionary processes  
- Predict future states based on historical patterns  
- Learn from experience through reinforcement  

However, the AI remains a tool within the artistic process, not a replacement for human creativity.  
The performer retains ultimate control over the system's behavior through manual override, preset selection, and real‑time modulation.

The AI‑Chimera framework provides the theoretical foundation for understanding the system's behavior, while the scientific metaphors (quantum, black holes, helioseismology) provide the artistic vocabulary for expressing the system's relationship to solar physics.

---

### References

- Paquete, H. (2026a). *SRT7 Framework*. AVANCA 2026.  
- Paquete, H. (2026b). *Post‑Techno Aesthetics*. EIMAD 2026.  
- Christensen‑Dalsgaard, J. (2002). *Helioseismology*. Reviews of Modern Physics.  
- Hathaway, D. H. (2015). *The Solar Cycle*. Living Reviews in Solar Physics.  
- Dubnov, S. (2026). *Probabilistic Generativity and Latent Musical States*.  
- Karchkhadze, A., & Dubnov, S. (2026). *Real‑time Human‑AI Musical Co‑performance*.  

---

### Funding

This project has received funding from the CEEC‑FCT program under grant agreement No. **2026‑HELIOSONIC**, as part of the research project:

**“AI as Catalyst: Transformative Impacts on Digital Performance, Computational Music, and Cultural Creativity”**  
(FCT **2024.09158.CEECIND**).

© 2026 Hugo Paquete — INET‑md, University of Aveiro
