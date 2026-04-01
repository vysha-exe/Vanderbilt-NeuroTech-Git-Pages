---
layout: project
title: "Gaze–EEG attention"
short_description: "Fuse webcam gaze/head pose with Muse EEG—detect when someone is both on-screen and mentally engaged."
status: Recruiting
order: 3
github: ""
# Set signup_url to your Google Form share link to show "Sign up to collaborate" (name + email fields in the form).
signup_url: ""
---

**Gaze–EEG attention** combines **where you’re looking** (vision) with **whether you’re paying attention** (EEG)—so the system can answer a richer question than either sensor alone.

**Example:** you’re watching a **lecture video**. A **camera** tracks gaze or face/head direction; a **Muse** tracks **focus-related** dynamics. Together:

- **Looking at the screen + mentally engaged** → high-confidence **attention**  
- **Looking but unfocused** → **passive watching**  
- **Not looking** → **distracted** / away from task  

That distinction matters for **education**, **accessibility**, and **productivity** tooling—real **multimodal** signal fusion, not just a buzzword.

## How it works

### Vision path

- **Face detection** and tracking  
- **Head pose** and/or **gaze** estimation (depending on hardware and tolerance for setup)  

### EEG path

- **Beta**-related features → **focus / engagement**  
- **Alpha** → **relaxed / possibly disengaged** (labels depend on calibration)  

### Fusion logic (first pass)

Combine streams with simple rules, then refine:

| Vision | EEG (simplified) | Interpretation |
|--------|------------------|----------------|
| On-screen | Focused | **True attention** |
| On-screen | Unfocused | **Passive watching** |
| Off-screen | (any) | **Distracted / away** |

You can later swap rule blocks for a small **learned** fusion model once you have labeled segments.

## Tech stack (starting point)

- **ESP32-CAM** or **laptop webcam** — start with whatever gets a stable face track fastest  
- **OpenCV** / **MediaPipe** — detection, landmarks, pose  
- **Python** — time-align streams, features, and any ML  
- **Muse SDK** — EEG (same ecosystem as other club Muse projects)  

## Why this project is strong

- **Practical:** study sessions, lecture capture, focus coaching  
- **Demonstrates multimodal ML** in a concrete, demo-friendly way  
- **Clear metrics:** on-screen rate, focus score, and a fused “attending” label you can show in a dashboard  

---

No public repo yet. Use **Join project** at the top of this page, or [Contact us]({{ site.baseurl }}/contact/) and mention **Gaze–EEG attention**.
