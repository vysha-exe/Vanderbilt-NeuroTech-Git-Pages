---
layout: project
title: "Brain Runner"
short_description: "Endless runner controlled with your brain—stay focused to sprint, stay calm to jump, spike for a dash."
status: Recruiting
order: 1
github: ""
# Set signup_url to your Google Form share link to show "Sign up to collaborate" (name + email fields in the form).
signup_url: ""
---

Build a simple **endless runner** (think Subway Surfers or the Chrome dino game)—but **no keyboard**. You steer with **EEG**: maintain the right mental state to survive longer.

**Example mapping (tunable):**

- **Focused** → character stays at full speed  
- **Losing focus** → speed drops  
- **Calm / controlled** → jump over obstacles  
- **Sudden spike** (blink, tension, artifact-like event) → dash or special move  

## How we’ll build it

### 1. Build the game first

Keep scope small:

- Character **runs forward** automatically  
- **Obstacles** on a timer  
- Core actions: **jump**, **speed up / slow down**  

**Stack options:** JavaScript (**Canvas**) or **Unity**—pick one and ship a playable loop before wiring EEG.

### 2. Define brain controls

Agree on a first-pass map, e.g.:

- Higher **beta / focus** → hold top speed  
- Higher **alpha / relaxed** → jump  
- Noise / **artifacts** or spikes → special action  

You can refine labels once data exists.

### 3. Collect training data

Record EEG while you **intentionally**:

- Focus  
- Relax  
- Blink / tense  

**Label** short segments by hand so the model has clear classes.

### 4. Train a classifier

**Input:** EEG features (band powers, simple stats)  
**Output:** discrete **action / state** (focus / relax / trigger)

Start with something lightweight: **logistic regression** or **SVM**, then iterate.

### 5. Real-time integration

- Stream EEG (e.g. Muse → Python)  
- Predict state every fraction of a second  
- Send commands to the game (**WebSockets** are a natural bridge from a Python inference process to JS Canvas or a Unity plugin)  

**Example loop:** model says “focus” → keep speed high; “relaxed” → queue a jump.

## Tech stack (starting point)

- **Python** — ML + signal processing  
- **Muse SDK** (or LSL path used elsewhere in the club)  
- **WebSockets** — connect the inference service to the game client  
- **JavaScript (Canvas)** or **Unity** — the runner itself  

## Extra ideas

- Short **calibration** phase before each run  
- On-screen **focus score** while playing  
- **Levels** that require different mental states to pass  

---

No public repo yet. Use **Join project** at the top of this page, or [Contact us]({{ site.baseurl }}/contact/) and mention **Brain Runner**.
