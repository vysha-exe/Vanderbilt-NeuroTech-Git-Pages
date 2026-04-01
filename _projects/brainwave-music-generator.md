---
layout: project
title: "Brainwave-based music generator"
short_description: "Muse 2 + ML: learn which music actually helps you focus or relax, then adapt playback from your brain signals—not a generic playlist."
status: Recruiting
order: 0
github: ""
# Set signup_url to your Google Form share link to show "Sign up to collaborate" (name + email fields in the form).
signup_url: ""
---

Wear a **Muse 2** headband while you listen to different kinds of music; the system tracks how your brain responds over time and learns **your** patterns—whether lo-fi really helps you focus, or ambient makes you *too* relaxed.

Eventually, the idea is to **generate or adjust music in real time** from your EEG so the app is building a personalized soundscape instead of you picking a static playlist.

## How we’ll build it

### 1. Collect data

Run a few sessions where you listen to different genres or tracks. Log:

- **EEG** from the Muse  
- **What you’re listening to** (track / genre tags)  
- A simple **label** each segment: focused, distracted, or relaxed  

### 2. Process the EEG

Start with straightforward features:

- **Alpha** → relaxation  
- **Beta** → focus / alertness  

Averages over short windows are enough to begin—no need for a research-grade pipeline on day one.

### 3. Train a model

**Inputs:** EEG features + music type (or embedding)  
**Output:** a predicted **focus / state score**

Begin with something interpretable: **linear regression** or a **Random Forest**, then iterate.

### 4. Generate or adjust music

**Early:** tweak **tempo**, **volume**, or **intensity** based on the model.  
**Later:** use something like **Tone.js** in the browser to synthesize or morph sound on the fly.

### 5. Close the loop

Continuously: **read EEG → update the music → log outcomes** so the system can learn what works *for you* over weeks, not one session.

## Tech stack (starting point)

- **Python** — datasets, features, and early ML models  
- **Muse SDK / LSL** — EEG streaming (aligned with other club Muse projects)  
- **Tone.js** — dynamic audio in the browser  
- **React** — optional UI; pairs well with Tone.js  

---

No public repo yet. Use the primary button at the top of this page to express interest, or reach out via [Contact us]({{ site.baseurl }}/contact/) and mention **Brainwave music**.
