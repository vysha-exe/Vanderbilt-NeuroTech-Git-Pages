---
layout: project
title: "Neurofeedback training system"
short_description: "Real-time EEG feedback with rewards when you hit focus or calm—personalized thresholds and progress over time."
status: Recruiting
order: 2
github: ""
# Set signup_url to your Google Form share link to show "Sign up to collaborate" (name + email fields in the form).
signup_url: ""
---

This project aims at a **serious training tool**: help someone **practice** shifting toward focus or calm—not just visualize raw EEG once, but **learn** through consistent feedback.

**Core loop:** show **live brain activity**, and when the user approaches a **target state**, **reward** them on screen (and optionally with sound). If they drift away, the feedback **softens** so the task stays meaningful.

**Examples:**

- Move toward **focus** → on-screen quality **improves** (clearer, brighter, faster progress)  
- **Distraction** or the wrong state → feedback **gets worse** (dimmer, slower, noisier)  

Over sessions, people can **feel** what works and generalize it outside the app.

## How we’ll build it

### 1. Pick a goal

Start with **one** primary objective:

- Improve **focus**  
- Increase **calmness**  
- Reduce **stress** (often overlaps with alpha / slow features)  

You can add more goals later; ship one loop first.

### 2. Process EEG in real time

Stream from **Muse** (or club-standard paths) and continuously estimate:

- **Alpha** → relaxation / calm  
- **Beta** → alertness / focus  

Thresholds can be **fixed** at first, then **personalized** (see below).

### 3. Design feedback

Keep the UI **obvious** in under a second:

- A **ball** that rises with focus  
- A **bar** that fills toward a target band  
- **Background audio** that gets calmer or richer with state  

Polish can come after the loop is stable.

### 4. Add ML personalization

- Collect **your own** (or pilot) session data  
- Train a lightweight model or **adapt thresholds** over time  
- Prefer **user-specific** rules over one global cutoff  

### 5. Track progress

Persist **session summaries** and show:

- Trend lines (**focus** or target metric **over weeks**)  
- **Average** target score per session  
- Optional: streaks or simple milestones  

## Tech stack (starting point)

- **Python** — streaming, features, early ML  
- **Muse SDK** (or LSL, consistent with other club tooling)  
- **React** — dashboard and live feedback UI  
- **Firebase** (or similar) — **auth-optional** session storage and progress charts  

## Advanced ideas

- **A/B** different interventions: **music vs silence**, **guided breathing** vs rest  
- Explore **reinforcement-style** tuning: which feedback patterns actually **improve** the signal fastest (careful scope—start with logging and offline analysis)  

---

No public repo yet. Use **Join project** at the top of this page, or [Contact us]({{ site.baseurl }}/contact/) and mention **Neurofeedback training**.
