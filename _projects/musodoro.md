---
layout: project
title: Musodoro
short_description: Muse2 EEG via LSL, Flask + Socket.IO backend, React UI—live band powers and adaptive beta alerts.
status: Active
order: 4
github: https://github.com/vysha-exe/Musodoro
---

**Musodoro** is a prototype stack that streams EEG from a **Muse2** (via **BlueMuse** and **Lab Streaming Layer**), computes spectral features on the backend, and pushes updates to a **React** frontend in real time.

### What the repo does

- Resolves an LSL stream with type **EEG** (Muse2 / BlueMuse, ~256 Hz).  
- **Backend (Flask + Socket.IO):** ingestion, filtering (e.g. 1–45 Hz), PSD (Welch), per-band power.  
- Emits band-power updates over the socket to the web app.  
- **Frontend:** shows band values and triggers an on-screen alert when **relative beta** crosses an **adaptive threshold** (calibration ~30 s: mean + 1.5× std).  

### Notes

This is intentionally a **prototype**: next steps could include artifact rejection, richer UI, persistent calibration, and safety disclaimers for any closed-loop use.

**Repository:** [github.com/vysha-exe/Musodoro](https://github.com/vysha-exe/Musodoro)
