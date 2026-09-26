# Attentional Blink - Design Document

## Overview

Add an attentional blink experiment. The existing experiments show perception being edited (motion-induced blindness, blind spot, change blindness) and time being reshaped (intentional binding, stopped clock). None shows a stimulus that is fully processed yet never reaches awareness. The attentional blink does, and it lets each visitor measure it in their own data.

## Experiment

### Attentional Blink

**Phenomenon:** After you identify one target in a rapid stream, a second target arriving 200-500ms later often goes unseen. A second target immediately after the first (100ms) is often spared.

**Implementation:**
- Rapid serial visual presentation at the center of a canvas: one item every 100ms, each shown for the full 100ms
- Distractors are letters that can't be mistaken for digits (no B, G, I, O, Q, S, Z)
- Two target digits (2-9, never equal) hidden in the stream
- First digit at position 5-10; second digit 1, 2, 3, 4, 6, or 8 items later; 7 letters after the second digit mask it
- Timing driven by `requestAnimationFrame` timestamps; a trial is discarded and rerun (up to twice) if a frame gap exceeds 60ms, a target frame was skipped, or the tab was hidden

**Flow:**
1. Two practice trials at long gaps, with feedback
2. 24 trials: 4 per gap, shuffled
3. After each trial, pick up to two digits on a keypad (or type them), order-free. Feedback shows the actual digits.
4. Results

**Results:**
- Second-digit accuracy given the first was seen, at 200-400ms vs 600-800ms, plus first-digit accuracy
- Line chart of second-digit accuracy by gap, with the typical blink window shaded, per-point hover and focus tooltips, and a table view
- Interpretation text for a clear blink, a shallow or reversed pattern, and lag-1 sparing

**Philosophical point:** Processing and experience come apart. Missed digits still get identified (Luck, Vogel & Shapiro 1996 found an N400 to blinked words), but they never win Dennett's "fame in the brain" and never become available for report.

## Index Page

Add to **Attention & Awareness**, after Change Blindness.
