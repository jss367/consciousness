# Consciousness Experiments - Design Document

## Overview

Add 4 new interactive browser-based experiments to the consciousness exploration project. Each demonstrates a specific phenomenon from consciousness research, enabling personal exploration and illustrating philosophical arguments.

## Experiments

### 1. Motion-Induced Blindness

**Phenomenon:** Static objects vanish from awareness when surrounded by a moving pattern, despite remaining physically present.

**Implementation:**
- Central fixation cross on dark background
- 100-200 small blue dots in a grid, rotating around center (~0.5-1 rotation/sec)
- 3 bright yellow static target dots in a triangle formation around fixation
- User stares at fixation and notices targets vanishing

**Controls:**
- Rotation speed
- Background dot density
- Target dot brightness/size
- Pause/resume

**Philosophical point:** Consciousness actively suppresses unchanging peripheral information. Perception is editorial, not receptive.

---

### 2. Change Blindness

**Phenomenon:** Large changes to a scene go unnoticed when accompanied by a brief visual disruption.

**Implementation:**
- Geometric scenes built from colored shapes (self-contained, no external images)
- Continuous cycle: original → grey blank (80-100ms) → changed version → blank → original
- User searches for the changing element

**Controls:**
- Flicker duration
- Switch interval
- "Reveal" button
- Multiple scenes (5-6 puzzles)

**Philosophical point:** Our rich visual experience is a "grand illusion" - we sample sparsely but feel we see everything.

---

### 3. Intentional Binding

**Phenomenon:** Voluntary actions and their effects feel closer together in time than involuntary ones - agency compresses perceived time.

**Implementation:**
- Rotating clock hand (one rotation per ~2.5 seconds)
- Two conditions:
  - Voluntary: user presses button whenever they choose → tone after 250ms
  - Involuntary: visual cue triggers automatically → same tone, same delay
- User reports clock position at moment of action or tone
- Compare time estimates between conditions

**Flow:**
1. Practice trials
2. Voluntary block (report action time)
3. Voluntary block (report tone time)
4. Involuntary blocks (same judgments)
5. Results showing temporal compression

**Philosophical point:** Agency isn't just belief - it reshapes time perception, binding actions to effects.

---

### 4. Stopped Clock Illusion (Chronostasis)

**Phenomenon:** After shifting gaze to a clock, the first second feels abnormally long. The brain backdates visual input to cover the saccade.

**Implementation:**
- Analog clock with ticking second hand, positioned to one side
- Fixation cross on opposite side
- Trial: user fixates on cross, prompted to look at clock, first tick feels extended
- Measurement: slider estimates of first tick duration
- Control condition: already looking at clock when tick happens

**Controls:**
- Tick duration
- Distance between fixation and clock
- Comparison mode between saccade and non-saccade trials

**Philosophical point:** The "stream" of consciousness is edited retroactively - your present moment is partially confabulated.

---

## Project Structure

```
consciousness/
├── index.html                      # Update with all 6 experiments, grouped by category
├── color-phi-phenomenon.html       # existing
├── unconscious-response.html       # existing
├── motion-induced-blindness.html   # new
├── change-blindness.html           # new
├── intentional-binding.html        # new
├── stopped-clock.html              # new
└── docs/plans/
    └── 2026-02-01-consciousness-experiments-design.md
```

## Design Consistency

All experiments follow existing patterns:
- Dark theme (#1a1a2e background, #0d0d1a demo containers)
- System font stack
- #6366f1 accent color for controls
- Structure: title, philosophical subtitle, demo area, controls, explanation section

## Index Page Organization

Group experiments by category:
- **Perception & Construction:** Color Phi, Motion-Induced Blindness
- **Attention & Awareness:** Unconscious Response, Change Blindness
- **Agency & Will:** Intentional Binding
- **Self & Narrative:** Stopped Clock
