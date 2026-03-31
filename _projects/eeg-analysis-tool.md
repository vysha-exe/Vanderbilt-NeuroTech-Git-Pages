---
layout: project
title: EEG Analysis Tool
short_description: Python tooling for OpenBCI Cyton + BrainFlow—stream, filter, visualize, and script analyses.
status: Active
order: 3
github: https://github.com/dnxjcui/neurotech-vandy
---

The **[neurotech-vandy](https://github.com/dnxjcui/neurotech-vandy)** repo is a **Python** toolkit used by Vanderbilt NeuroTech for working with **OpenBCI’s 8-channel Cyton** board through **BrainFlow**.

### Capabilities

- **Streaming:** real-time acquisition over USB serial or Bluetooth (with CLI helpers).  
- **Processing:** filtering, artifact handling hooks, and feature extraction workflows.  
- **Visualization:** time-series and plotting utilities (see `src/visualization/`).  
- **CLI:** `src/run.py` supports modes like receive-only runs with duration and connection flags.  

### Hardware expectations

- OpenBCI **Cyton**, typical defaults around **250 Hz**, 8 EEG channels, 24-bit resolution.  
- Requires a working BrainFlow install and correct port / MAC for your machine.  

Licensed under **Apache-2.0**; see the upstream README for setup, troubleshooting, and contribution notes.

**Repository:** [github.com/dnxjcui/neurotech-vandy](https://github.com/dnxjcui/neurotech-vandy)
